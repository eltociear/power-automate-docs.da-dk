---
title: Forstå datahandlinger | Microsoft Docs
description: Få mere at vide om at udføre handlinger, f.eks. oprette en HTML-tabel, oprette en CSV-tabel, skrive en meddelelse, joinforbinde, vælge og filtrere en matrix med Power Automate.
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
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0541a89ad0fe5f8d7dae0acfc6f257be7532ef15
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195064"
---
# <a name="use-data-operations-with-power-automate"></a>Brug datahandlinger med Power Automate

I denne gennemgang får du mere at vide om nogle af de populære datahandlinger i Power Automate, f.eks. at skrive en meddelelse, joinforbinde, vælge, filtrere en matrix, oprette en tabel og opdele JSON, som er tilgængelige til redigering af data, når du opretter flow.

## <a name="prerequisites"></a>Forudsætninger
* Adgang til Power Automate.
* Et værktøj som [PostMan](https://www.getpostman.com/postman) til at sende HTTP POST-anmodninger med en JSON-matrix til dit flow.

## <a name="use-the-compose-action"></a>Brug handlingen meddelelse
Brug handlingen **Datahandlinger – Meddelelse** (meddelelse), så du undgår at skulle angive identiske data flere gange, når du designer et flow. Hvis du f.eks. skal angive en matrix af cifre: ````[0,1,2,3,4,5,6,7,8,9]```` flere gange, mens du designer dit flow, kan du bruge handlingen meddelelse til at gemme matrixen, som følger:

1. Søg efter **Meddelelse**, og vælg derefter handlingen **Datahandlinger – Meddelelse** (meddelelse).
   
    ![søg efter og vælg handlingen meddelelse](./media/data-operations/search-select-compose.png)
2. Angiv matrixen i feltet **Input**, som du vil henvise til senere:
   
    ![konfigurer handlingen meddelelse](./media/data-operations/add-array-compose.png)

> [!TIP]
> Hvis du vil gøre efterfølgende henvisning nemmere, kan du omdøbe kortet **Meddelelse** ved at klikke på teksten "Meddelelse" på titellinjen i kortet **Meddelelse**.
> 
> 

Når du har brug for at få adgang til indholdet af handlingen meddelelse, kan du gøre det via tokenet **Output** på listen **Tilføj dynamisk indhold fra de apps og forbindelser, der anvendes i dette flow** ved at følge disse trin:

1. Tilføj en handling, f.eks. **Datahandlinger – Joinforbind**.
2. Vælg kontrolelementet, hvor du vil tilføje det indhold, du har gemt i handlingen meddelelse.
   
    **Tilføj dynamisk indhold fra de apps og forbindelser, der anvendes i dette flow** åbnes.
3. I **Tilføj dynamisk indhold fra de apps og forbindelser, der anvendes i dette flow** skal du vælge **Output**-tokenet, som findes under kategorien **Meddelelse** under fanen **Dynamisk indhold**.
   
    ![brug output fra handlingen meddelelse](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Brug joinhandlingen
Brug handlingen **Datahandlinger – Joinforbind** (Joinforbind) til at afgrænse en matrix med en separator efter eget valg. Antag f.eks., at dit flow modtager en webanmodning, der omfatter følgende matrix med mailadresser: ````["d@example.com", "k@example.com", "dal@example.com"]````. Dit mailprogram kræver imidlertid, at adresser skal være en enkelt streng adskilt med semikolon. Hvis du vil gøre dette, skal du bruge handlingen **Datahandlinger – Joinforbind** (joinforbind) til at ændre kommaafgrænseren til et semikolon ";" ved at følge disse trin:

1. Tilføj en ny handling, søg efter **Joinforbind**, og vælg derefter **Datahandlinger – Joinforbind** (joinforbind).
   
    ![søg efter og vælg joinhandlingen](./media/data-operations/search-select-join.png)
2. Angiv matrixen i feltet **Fra**, og angiv derefter den nye afgrænser, du vil bruge, i feltet **Joinforbind med**.
   
    Her har jeg brugt semikolon (;) som den nye afgrænser.
   
    ![konfigurer joinhandlingen](./media/data-operations/add-array-join.png)
3. Gem dit flow, og kør det derefter.
4. Når dit flow er kørt, vil outputtet af handlingen **Datahandlinger – Joinforbind** være:
   
    ![joinoutput](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Brug den valgte handling
Brug **Datahandlinger – Vælg** (vælg) til at transformere formen af objekter i en matrix. Du kan f.eks. tilføje, fjerne eller omdøbe elementer i hvert objekt i en matrix.

> [!NOTE]
> Mens du kan tilføje eller fjerne elementer med brug af den valgte handling, kan du ikke ændre antallet af objekter i matrixen.
> 
> 

Du kan f.eks. bruge den valgte handling, hvis data overføres til dit flow via en webanmodning i dette format:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

og du vil omforme de indgående data ved at omdøbe "first" til "FirstName", "last" til "LastName" og tilføje et nyt medlem med navnet og tilføje et nyt medlem kaldet "FamilyName", der kombinerer "first" og "last" (adskilt med et mellemrum):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Det gør du på følgende måde:

1. Føj handlingen **Anmodning/Svar – Svar** (anmodning) til dit flow.
2. Vælg **Anvend eksempel på nyttedata til at generere skema** fra kortet **Anmodning**.
3. I det felt, der vises, skal du indsætte et eksempel på matrixen med dine kildedata og derefter vælge knappen **Udført**.
4. Tilføj handlingen **Datahandlinger – Vælg** (vælg), og konfigurer det så som i følgende afbildning.
   
    ![konfigurer den valgte handling](./media/data-operations/select-card.png)
   
   > [!TIP]
   > Outputtet fra den valgte handling er en matrix, der indeholder de objekter, der netop er formet. Du kan derefter bruge denne matrix i en vilkårlig anden handling, f.eks. **Meddelelse**, som beskrevet tidligere.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Brug handlingen filtermatrix
Brug **Datahandlinger – Filtermatrix** (filtermatrix) til at reducere antallet af objekter i en matrix til en delmængde, der svarer til de kriterier, som du angiver.

> [!NOTE]
> Filtermatrix kan ikke bruges til at ændre formen på objekterne i en matrix. Desuden skelnes der også mellem store og små bogstaver i den tekst, du filtrerer efter.
> 
> 

Du kan f.eks. bruge filtermatrix til denne matrix:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

til at oprette en ny matrix, der udelukkende indeholder objekter, hvor *first* er angivet til "Deon".

Lad os gøre det.

1. Find handlingen **Datahandlinger –Filtermatrix** (filtermatrix), og føj den derefter til dit flow.
2. Konfigurer handlingen filtermatrix som i følgende afbildning.
   
    ![konfigurer handlingen filtermatrix](./media/data-operations/add-configure-filter-array.png)
3. Gem dit flow, og kør det derefter.
   
    Du kan bruge [PostMan](https://www.getpostman.com/postman) til at oprette en webanmodning, der sender en JSON-matrix til dit flow.
4. Når dit flow køres, og det antages, at JSON-inputtet ser ud som denne matrix:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    outputtet ser ud som denne matrix (bemærk, at kun objekter, hvor *first* er angivet til "Deon", er medtaget i outputtet fra denne handling):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Brug handlingen opret csv-tabel
Brug **Datahandlinger – Opret CSV-tabel** (opret csv-tabel) til at ændre et JSON-matrixinput til en kommasepareret værditabel (CSV). Du kan også vælge at bevare overskrifterne synlige i CSV-outputtet. Du kan f.eks. konvertere følgende matrix til en CSV-tabel ved hjælp af handlingen **Opret CSV-tabel**:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Find, tilføj og konfigurer derefter handlingen **Datahandlinger – Opret CSV-tabel**, så den ligner følgende afbildning.
   
    ![konfigurer handlingen opret csv-tabel](./media/data-operations/create-csv-table.png)
   
    Bemærk! Tokenet **Body (Brødtekst)** i denne afbildning stammer fra en handling af typen **Anmodning/Svar – Svar**, men du kan dog få input til handlingen **Opret CSV-tabel** fra outputtet fra en eventuel tidligere handling i dit flow, eller du kan angive det direkte i feltet **Fra**.
2. Gem dit flow, og kør det derefter.
   
    Når dit flow kører, ser output fra **Opret CSV-tabel** ud som denne afbildning:
   
    ![opret csv-tabeloutput](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Brug handlingen opret html-tabel
Brug **Datahandlinger – Opret HTML-tabel** til at ændre et JSON-matrixinput til en HTML-tabel. Du kan også vælge at bevare overskrifterne synlige i HTML-outputtet.

Det gør du ved at følge disse trin i [opret csv-tabel-afsnittet](#use-the-create-csv-table-action), som indeholder et detaljeret eksempel. Sørg for at bruge handlingen **Datahandlinger – Opret HTML-tabel** og ikke handlingen **Datahandlinger – Opret CSV-tabel**.

> [!TIP]
> Hvis du planlægger at sende HTML-tabellen via mail, skal du huske at vælge "IsHtml" i mailhandlingen.
> 
> 

