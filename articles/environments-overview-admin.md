---
title: Oversigt over miljøer for administratorer | Microsoft Docs
description: Brug, oprettelse og administration af miljøer i Power Automate
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/14/2020
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 1f0300f4d9381b669107680ff68e703bff74b00e
ms.sourcegitcommit: 39d7912519ff03dae924023c1a1c320a30efaa81
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2020
ms.locfileid: "3691170"
---
# <a name="using-environments-within-power-automate"></a>Brug af miljøer i Power Automate


## <a name="benefits"></a>Forsikringsydelser

Miljøer giver følgende fordele:

* **Datalokalitet**: Miljøer kan oprettes i forskellige områder, og de er bundet til den pågældende geografiske placering. Når du opretter et flow i et miljø, distribueres dette flow til alle datacentre på den pågældende geografiske placering. Det giver også en ydelsesmæssig fordel.

    Hvis dine brugere befinder sig i Europa, skal du oprette og bruge miljøet i området Europa. Hvis brugerne befinder sig i USA, kan du oprette og bruge miljøet i USA. 

    > [!IMPORTANT]
    > Hvis du sletter miljøet, slettes alle flow i dette miljø også. Dette gælder for alle elementer, du opretter i det pågældende miljø, herunder forbindelser, gateways, Power Apps og meget mere.
* **Forebyggelse af datatab:** Som administrator ønsker du ikke flows, der modtager data fra en intern placering (f.eks *OneDrive for Business* eller en SharePoint-liste, der indeholder lønoplysninger) og derefter slår dataene op offentligt (f.eks. på *Twitter*). Brug [forebyggelse af datatab](https://docs.microsoft.com/power-platform/admin/wp-data-loss-prevention) til at styre, hvilke tjenester der kan dele data i din Power Automate-udrulning.

    Du kan f.eks. føje tjenesterne *SharePoint* og *OneDrive for Business* til en politik, der kun tillader virksomhedsdata. Alle flows, der er oprettet i dette miljø, kan bruge tjenesterne *SharePoint* og *OneDrive for Business*. De kan dog ikke dele data med andre tjenester, som ikke er inkluderet i politikken, der kun tillader firmadata.

  > [!NOTE]
  > Forebyggelse af datatab fås med nogle licens-SKU'er, herunder P2-licensen.

* **Isoleringsgrænse for alle ressourcer**: Alle flow, gateways, forbindelser, brugerdefinerede connectorer osv., der er placeret i et specifikt miljø. De findes ikke i andre miljøer.
* **Common Data Service**: Her er dine muligheder, hvis du vil oprette et flow, der indsætter data i en tjeneste:

  * Indsæt data i en Excel-fil, og gem Excel-filen på en cloudstoragekonto, f.eks OneDrive.
  * Opret en SQL Database, og gem derefter dine data i den.
  * Brug Common Data Service til at gemme dine data.

    Der kan maksimalt være én database til dine flows i hvert miljø i Common Data Service. Adgang til Common Data Service afhænger af, hvilken licens du har købt. Common Data Service er ikke inkluderet i den gratis licens.

## <a name="limitations"></a>Begrænsninger

Selvom miljøer giver mange fordele, medfører de også nye begrænsninger. Den omstændighed, at miljøer er en isoleringsgrænse, betyder, at du aldrig kan have ressourcer, der refererer til ressourcer *på tværs af* miljøer. Du kan f.eks. ikke oprette en brugerdefineret connector i ét miljø og derefter oprette et flow, der bruger den pågældende brugerdefinerede connector i et andet miljø.

## <a name="use-the-default-environment"></a>Bruge standardmiljøet

**Standard**-miljøet deles af alle brugere, og alle brugere kan oprette flow i **Standard**-miljøet.

> [!TIP]
> Hvis du er bruger af prøveversionen, findes alle eksisterende flows i standardmiljøet. En *prøveversionsbruger* er en person, der har brugt Power Automate, inden den er generelt tilgængelig (GA).

## <a name="the-admin-center"></a>Administration

Administratorer kan bruge Administration til at oprette og administrere miljøer. Her er de to måder, du kan åbne Administration på:

### <a name="option-1-select-settings"></a>Mulighed 1: Vælg Indstillinger

1. Log på [flow.microsoft.com](https://flow.microsoft.com).
1. Vælg tandhjulet Indstillinger, og vælg **Administration** på listen:

   ![Indstillinger og Administratorportal](./media/environments-overview-admin/settings.png)
1. Administratorcenteret åbnes.

### <a name="option-2-open-power-platform-admin-center"></a>Mulighed 2: Åbn Power Platform Administration

Gå til [Power Platform Administration](https://admin.powerplatform.microsoft.com/), og log på med din arbejdskonto.

## <a name="create-an-environment"></a>Opret et miljø

1. I [Power Platform Administration](https://admin.powerplatform.microsoft.com/) skal du vælge **Miljøer**. Du kan se alle eksisterende miljøer: ![Miljøer](./media/environments-overview-admin/environments-list.png)
2. Vælg **Nyt miljø**, og angiv derefter de påkrævede oplysninger:


   |     Egenskab     |                                                 Beskrivelse                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Miljønavn |              Angiv navnet på dit miljø, f.eks. `Human Resources` eller `Europe flows`.              |
   |      Område      | Vælg den placering, som dit miljø skal bruge som vært. Du opnår den bedste ydeevne ved at bruge et område, der er tæt på dine brugere. |
   | Miljøtype |                  Vælg en miljøtype på baggrund af din licens: Produktion eller Prøve.                   |

     ![miljøindstillinger](./media/environments-overview-admin/new-environment-dialog.png)
3. Klik på **Opret miljø**.
4. Du kan nu enten vælge **Opret database** eller **Spring over**.
5. Hvis du vælger **Opret database**, bliver du bedt om at angive **Valuta** og **Sprog** for databasen. Du kan desuden vælge, om eksempelapps og -data også skal udrulles.

   ![konfigurationsindstillinger for database](./media/environments-overview-admin/create-database-dialog2.png)


Du kan nu føje brugere til miljøet.

## <a name="manage-your-existing-environments"></a>Administrere dine eksisterende miljøer

1. I [Power Automate Administration](https://admin.powerplatform.microsoft.com/) skal du vælge **Miljøer**:

   ![menuelementet miljøer](./media/environments-overview-admin/select-environments.png)
1. Vælg et miljø for at åbne dets egenskaber.
1. Brug fanen **Detaljer** til at få vist yderligere oplysninger om et miljø, herunder hvem der har oprettet miljøet, dets geografiske placering m.m.:

   ![fanen Detaljer](./media/environments-overview-admin/open-environment.png)
1. Vælg **Sikkerhed**.

    Hvis du ikke valgte **Opret database** i det forrige trin, har du to muligheder under**Miljøroller**: **Miljøadministrator** og **Miljøopretter**:

    ![administratorroller](./media/environments-overview-admin/environment-roles.png)

    En **Opretter** kan oprette nye ressourcer, f.eks. flow, dataforbindelser og gateways, i et miljø.

   > [!NOTE]
   > En bruger behøver ikke være **Opretter** for at kunne *redigere* ressourcer i et miljø. De enkelte oprettere bestemmer, hvem der kan redigere deres ressourcer, ved at tildele rettigheder til brugere, der ikke er miljøoprettere.
   > 
   > 

    En **Administrator** kan oprette politikker til forebyggelse af datatab og udføre andre administrative opgaver, f.eks. oprette miljøer, føje brugere til miljøer og tildele rettigheder som administrator/opretter.

   1. Vælg rollen **Miljøopretter**, og vælg derefter **Brugere**: ![opretterrolle](./media/environments-overview-admin/add-environment-maker.png)
   1. Angiv et navn, en mailadresse eller en brugergruppe, som du vil tildele rollen **Opretter**.
   1. Vælg **Gem**.

1. Vælg **Brugerroller** under **Sikkerhed**:

    ![brugerroller](./media/environments-overview-admin/security-user-roles.png)

    Alle eksisterende roller er angivet, herunder mulighederne for at redigere eller slette rollen.

    Vælg **Ny rolle** for at oprette en ny rolle.
1. Vælg **Rettighedssæt** under **Sikkerhed**:

    ![indstillinger for rettigheder](./media/environments-overview-admin/security-permission-set.png)

    Du kan se alle eksisterende rettighedssæt og muligheder for at redigere eller slette roller.

    Vælg **Nyt rettighedssæt** for at oprette et nyt rettighedssæt.
1. Hvis du valgte **Opret database** for at gemme dine data, indgår denne database i Common Data Service. Når du klikker på fanen **Sikkerhed**, bliver du bedt om at navigere til **Dynamics 365-instansadministration**, hvor der kan angives rollebaseret sikkerhed.
![sikkerhedsindstillinger for dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Vælg brugeren på listen over brugere i miljøet/forekomsten.
  ![sikkerhedsindstillinger for dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Tildel rollen til brugeren.

   ![tildele rolle for bruger](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> De brugere eller grupper, der er tildelt til disse miljøroller, får ikke automatisk adgang til miljøets database (hvis de findes), og de skal tildeles specifik adgang af en databaseejer. 
>
>

### <a name="database-security"></a>Databasesikkerhed
Muligheden for at oprette og ændre et databaseskema og for at oprette forbindelse til de data, der er gemt i en database, som er klargjort i dit miljø, styres af databasens brugerroller og tilladelsessæt. Du kan administrere brugerrollerne og rettighedssættene for dit miljøs database fra afsnittet **Brugerroller** og **Rettighedssæt** under fanen **Sikkerhed**. 

   ![tildele rolle for bruger](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

### <a name="can-i-move-a-flow-between-environments"></a>Kan jeg flytte et flow mellem miljøer?

Ja, flow kan eksporteres fra ét miljø og importeres til et andet miljø.

### <a name="which-license-includes-common-data-service"></a>Hvilken licens indeholder Common Data Service?

Du kan få adgang til Common Data Service med enhver Power Automate-[licens](https://flow.microsoft.com/pricing).

I dokumentet [Spørgsmål om fakturering](billing-questions.md) kan du finde svar på ofte stillede spørgsmål om fakturering.

### <a name="can-common-data-service-be-used-outside-of-an-environment"></a>Kan Common Data Service bruges uden for et miljø?

Nej. Common Data Service kræver et miljø. [Læs mere](common-data-model-intro.md) om det.

### <a name="what-regions-include-power-automate"></a>Hvilke områder indeholder Power Automate?

Power Automate understøtter de fleste af de områder, som Office 365 understøtter. Se [oversigten over områder](regions-overview.md) for at få flere oplysninger.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Hvad er påkrævet for at oprette mit eget brugerdefinerede miljø?

Alle brugere med licensen Power Automate Plan 2 kan oprette deres egne miljøer. Alle Power Automate-brugere kan bruge de miljøer, der er oprettet af Plan 2-administratorer, men de kan ikke oprette deres egne miljøer.
