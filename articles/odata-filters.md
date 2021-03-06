---
title: Filtrere og kopiere data | Microsoft Docs
description: Lær, hvordan du filtrerer og kopierer data fra en kilde til en destination med Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 30b3488cf3918b5a9bd13c49d44fe49a1cc2120e
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/15/2020
ms.locfileid: "3697263"
---
# <a name="filter-and-copy-data-with-power-automate"></a>Filtrer og kopier data med Power Automate

Denne gennemgang viser, hvordan du opretter et flow, der overvåger en kilde til nye eller ændrede elementer og derefter kopierer disse ændringer til en destination. Du kan oprette et flow som dette, hvis dine brugere indtaster data på én placering, men dit team skal bruge dem på en anden placering eller i et andet format.

I denne gennemgang kopieres data fra en Microsoft SharePoint-[liste](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) (kilden) til en [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)-tabel (destinationen), men du kan kopiere data mellem alle de mere end 380 [connectorer](https://flow.microsoft.com/connectors/), som Power Automate understøtter.

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

> [!IMPORTANT]
> Ændringer, som du foretager i destinationen, kopieres ikke til kilden, fordi tovejssynkronisering ikke understøttes. Hvis du forsøger at konfigurere tovejssynkronisering, skal du oprette en uendelig løkke, hvor ændringer sendes uendeligt mellem kilde og destination.

## <a name="prerequisites"></a>Forudsætninger
* Adgang til en datakilde og en destination. Denne gennemgang omfatter ikke trin til oprettelse af kilden og destinationen.
* Adgang til [Power Automate](https://flow.microsoft.com).
* En grundlæggende forståelse af, hvordan dine data er gemt.
* Kendskab til de grundlæggende funktioner i oprettelse af flow. Du kan gennemse, hvordan du tilføjer [handlinger, udløsere](multi-step-logic-flow.md#add-another-action) og [betingelser](add-condition.md). I de følgende trin forudsættes det, at du ved, hvordan disse handlinger udføres.

> [!TIP]
> Hvert kolonnenavn i kilden og destinationen behøver ikke at stemme overens, men du skal angive data til alle *påkrævede* kolonner, når du indsætter eller opdaterer et element. Power Automate identificerer de påkrævede felter for dig.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Hurtig oversigt over trinnene
Hvis du kender Power Automate godt, kan du bruge disse hurtige trin til at kopiere data fra én datakilde til en anden:

1. Identificer den kilde, du vil overvåge, og den destination, som du vil kopiere ændrede data til. Bekræft, at du har adgang til begge.
2. Vælg mindst én kolonne, der entydigt identificerer elementer i kilden og destinationen. I eksemplet, der følger, bruger vi kolonnen **Titel**, men du kan bruge enhver kolonne.
3. Konfigurer en udløser, der overvåger kilden til ændringer.
4. Søg i destinationen for at se, om det ændrede element findes.
5. Brug en **Betingelse** som denne:
   * Hvis det nye eller ændrede element ikke findes i destinationen, kan du oprette det.
   * Hvis det nye eller ændrede element findes i destinationen, kan du opdatere det.
6. Udløs dit flow, og bekræft derefter, at nye eller ændrede elementer, kopieres fra kilden til destinationen.

> [!NOTE]
> Hvis du ikke tidligere har oprettet forbindelse til SharePoint eller Azure SQL Database, skal du følge vejledningen, når du bliver bedt om at logge på.
> 
> 

Her er de detaljerede trin til oprettelse af flowet.

## <a name="monitor-the-source-for-changes"></a>Overvåge kilden til ændringer
1. Log på [Power Automate](https://flow.microsoft.com), og vælg **Mine flows** > **Opret fra bunden**.
2. Søg efter **SharePoint** > vælg udløseren **SharePoint – Når et element oprettes eller ændres** på listen med udløsere.
3. Angiv **Webstedsadresse**, og vælg derefter **Listenavn** på kortet **Når et element oprettes eller ændres**.
   
    Angiv **Websiteadresse** og **Listenavn** for den SharePoint-listen, som dit flow overvåger for at finde eventuelle nye eller opdaterede elementer.
   
    ![konfigurere sharepoint-udløser](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Søg i destinationen efter det nye eller ændrede element
Vi bruger handlingen **SQL Server – Hent rækker** til at søge i destinationen efter det nye eller ændrede element.

1. Vælg **Nyt trin** > **Tilføj en handling**.
2. Søg efter **Hent rækker**, vælg **SQL Server – Hent rækker**, og vælg derefter den tabel, du vil overvåge, på listen **Tabelnavn**.
3. Vælg **Vis avancerede indstillinger**.
4. I feltet **Filterforespørgsel** skal du angive **Titel eq '**, vælge tokenet **Titel** på listen med dynamisk indhold og derefter angive **'**.
   
    I det forrige trin forudsættes det, at du matcher titlerne på rækkerne i kilden og destinationen.
   
    Kortet **Hent rækker** bør nu se ud som dette billede:
   
    ![prøve at hente elementet fra destinationsdatabasen](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Kontrollér, om det nye eller ændrede element blev fundet
Vælg **Nyt trin** > **Tilføj en betingelse** for at åbne kortet **Betingelse**.

På kortet Betingelse:

1. Markér afkrydsningsfeltet til venstre.
   
    Listen **Tilføj dynamisk indhold fra de apps og forbindelser, der anvendes i dette flow** åbnes.
2. Vælg **værdi** i kategorien **Hent rækker**.
   
   > [!TIP]
   > Bekræft, at du har valgt **værdi** i kategorien **Hent rækker**. Vælg ikke **værdi** i kategorien **Når et element oprettes eller ændres**.
   > 
   > 
3. Vælg **er lig med** på listen i det midterste felt.
4. Angiv **0** (nul) i feltet i højre side.
   
    Kortet **Betingelse** ligner nu dette billede:
   
    ![konfigurere en betingelse](media/odata-filters/configure-condition.png)
5. Vælg **Rediger i avanceret tilstand**.
   
    Når avanceret tilstand åbnes, kan du se udtrykket **\@lig med(brødtekst('Hent_rækker')?['værdi'], 0)** i feltet. Rediger udtrykket ved at tilføje **længde()** omkring funktionen **brødtekst('Hent_elementer')? ["værdi"]**. Hele udtrykket ser nu således ud: **@equals(length(body('Get_rows')?['value']), 0)**
   
    Kortet **Betingelse** ligner nu dette billede:
   
    ![konfigurere en betingelse](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > Tilføjelse af funktionen **length()** tillader, at flowet kontrollerer listen **value** og fastlægger, om den indeholder elementer.
   > 
   > 

Når dit flow "henter" elementer fra destinationen, er der to mulige resultater.

| Resultat | Næste trin |
| --- | --- |
| Elementet findes |[Opdatere elementet](odata-filters.md#update-the-item-in-the-destination) |
| Elementet findes ikke |[Oprette et nyt element](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> Billederne af kortene **Indsæt række** og **Opdater række**, der er vist derefter, kan være anderledes end dem, du får vist, fordi disse kort viser navnene på kolonnerne i den Azure SQL Database-tabel, der bruges i flowet.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Oprette elementet i destinationen
Hvis elementet ikke findes i destinationen, kan du oprette det ved hjælp af handlingen **SQL Server – Indsæt række**.

I forgreningen **Hvis ja** i **Betingelse**:

1. Vælg **Tilføj en handling**, søg efter **indsæt række**, og vælg derefter **SQL Server – Indsæt række**.
   
    Kortet **Indsæt række** åbnes:
2. På listen **Tabelnavn** skal du vælge den tabel, som det nye element, skal indsættes i.
   
    Kortet **Indsæt række** udvides og viser alle felter i den valgte tabel. Felter med en stjerne (*) er obligatoriske og skal udfyldes, hvis rækken skal være gyldig.
3. Vælg hvert felt, du vil udfylde, og indtast dataene.
   
    Du kan indtaste dataene manuelt, markere et eller flere tokens fra det **dynamiske indhold** eller angive en kombination af tekst og tokens i felterne.
   
    Kortet **Indsæt række** ligner nu denne afbildning:
   
    ![konfigurere en betingelse](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Opdater elementet i destinationen
Hvis elementet findes i destinationen, kan du opdatere det med ændringerne.

1. Føj handlingen **SQL Server – Opdater række** til forgreningen **Hvis nej** af den pågældende **Betingelse**.
2. Følg trinnene i afsnittet [oprette elementet](odata-filters.md#create-the-item-in-the-destination) i dette dokument for at udfylde felterne i tabellen.
   
    ![vise miljøer](media/odata-filters/update-row.png)
3. Angiv et navn til dit flow i øverst på siden i feltet **Flownavn**, og vælg derefter **Opret flow** for at gemme det.
   
    ![navngive dit flow](media/odata-filters/give-the-flow-a-name.png)

Når et element på din SharePoint-liste (kilde) nu ændres, udløses flowet og indsætter enten et nyt element eller opdaterer et eksisterende element i din Azure SQL Database (destination).

> [!NOTE]
> Dit flow udløses ikke, når et element slettes fra kilden. Hvis dette er et vigtigt scenarie, kan du overveje at tilføje en separat kolonne, der angiver, hvornår et element ikke længere er nødvendigt.
> 
> 

## <a name="learn-more"></a>Få mere at vide
Brug [datahandlinger](data-operations.md) i dine flows.

