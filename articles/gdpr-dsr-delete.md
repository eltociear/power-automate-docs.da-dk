---
title: Anmodninger i Power Automate om sletning af dataemner omfattet af GDPR | Microsoft Docs
description: Lær, hvordan du kan bruge Power Automate til at svare på anmodninger om sletning af dataemner omfattet af GPDR.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/14/2020
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 07c0f662eae3cebe49009de0730a65494fdbffa2
ms.sourcegitcommit: 39d7912519ff03dae924023c1a1c320a30efaa81
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2020
ms.locfileid: "3691146"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-power-automate"></a>Besvarelse af anmodninger i Power Automate om sletning af dataemner omfattet af GDPR


"Retten til at fjerne" ved fjernelse af personlige data fra en organisations kundedata er en vigtig beskyttelse i GDPR. Fjernelse af personlige data omfatter fjernelse af alle personlige data og systemgenererede logge, undtagen oplysninger om overvågningslog.

Power Automate gør det muligt for brugere at bygge automatiserede arbejdsprocesser, der er en vigtig del af den daglige drift i din organisation. Når en bruger forlader virksomheden, skal en administrator manuelt gennemse og afgøre, om nogle af de data og ressourcer, som brugeren har oprettet, skal slettes. Der er andre personlige data, som slettes automatisk, når brugerens konto slettes fra Azure Active Directory.

I følgende tabel vises, hvilke personlige data der slettes automatisk, og hvilke data der kræver, at administratoren manuelt gennemser og sletter dem:

|Kræver manuel gennemgang og sletning|Slettes automatisk, når brugeren slettes i Azure Active Directory|
|------|------|
|Miljø*|Systemgenererede logge|
|Miljøtilladelser**|Kørselshistorik|
|Flow|Aktivitetsopdatering|
|Flowtilladelser|Gateway |
|Brugerdetaljer|Gatewaytilladelser|
|Forbindelser*||
|Forbindelsestilladelser||
|Brugerdefineret forbindelse*||
|Brugerdefinerede connectorer||

* Hver af disse ressourcer indeholder posterne "Oprettet af" og "Ændret af", der indeholder personlige data. Af sikkerhedsmæssige årsager gemmes disse poster, indtil ressourcen slettes.

**For de miljøer, der indeholder en Common Data Service-database, gemmes miljøtilladelserne, dvs. hvilke brugere der har fået tildelt rollerne Miljøopretter og Miljøadministrator, som poster i Common Data Service. Se under [Udførelse af DSR'er i forhold til Common Data Service-kundedata](https://go.microsoft.com/fwlink/?linkid=872251), hvis du vil have vejledning i, hvordan du besvarer DSR'er for de brugere, der bruger Common Data Service.

For de data og ressourcer, der kræver manuel gennemgang, findes der følgende funktioner i Power Automate til søgning efter og ændring af personlige data for en bestemt bruger:

* **Websiteadgang:** Log på [Power Apps Administration](https://admin.powerapps.com/) eller [Power Platform Administration](https://admin.powerplatform.microsoft.com/)

* **PowerShell-adgang:** [Power Apps Admin PowerShell-cdmlets](https://go.microsoft.com/fwlink/?linkid=871804) 

Her er opdelingen af oplevelser, som en administrator kan slette, opdelt efter de enkelte typer personlige data inden for de enkelte typer ressourcer:

|Ressourcer, der indeholder personlige data|Adgang til websted|PowerShell-adgang|Automatisk sletning|
|-----|----|----|----|
|Systemgenererede logge|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|||
|Miljø|Power Automate Administration|Power Apps-cmdlet'er||
|Miljøtilladelser*|Power Automate Administration|Power Apps-cmdlet'er||
|Kørselshistorik||| Slettet i henhold til politikken for dataopbevaring i 28 dage|
|Aktivitetsopdatering |||Slettet i henhold til politikken for dataopbevaring i 28 dage|
|Brugerjob|| ||
|Flow|Power Automate-udviklerportal**|||
|Flowtilladelser|Power Automate-udviklerportal|||
|Brugerdetaljer||Power Apps-cmdlet'er||
|Forbindelser|Power Automate-udviklerportal| ||
|Forbindelsestilladelser|Power Automate-udviklerportal| ||
|Brugerdefineret connector|Power Automate-udviklerportal| ||
|Brugerdefinerede connectorer|Power Automate-udviklerportal| ||
|Oversigt over godkendelser|Microsoft Power Apps-udviklerportal*|||

*Med introduktionen af Common Data Service vil oprettelsen af en database i miljøet betyde, at miljøtilladelserne og modeldrevne apptilladelser gemmes som poster i forekomsten af Common Data Service. Se under [Udførelse af DSR'er i forhold til Common Data Service-kundedata](https://go.microsoft.com/fwlink/?linkid=872251), hvis du vil have vejledning i, hvordan du besvarer DSR'er for de brugere, der bruger Common Data Service.

\*\*En administrator kan kun få adgang til disse ressourcer fra Power Automate-udviklerportalen, hvis administratoren er tildelt adgang fra Power Automate Administration.

## <a name="manage-delete-requests"></a>Administrer sletteanmodninger

I fremgangsmåden nedenfor beskrives, hvordan du får adgang til administrative funktioner til behandling af sletteanmodninger for GDPR. Disse trin skal udføres i den rækkefølge, der er beskrevet nedenfor.

> [!IMPORTANT]
> Hvis du vil undgå at beskadige data, skal du følge disse trin i nævnte rækkefølge.
>
>

## <a name="list-and-re-assign-flows"></a>Vis og tildel flow igen

I disse trin kopieres eksisterende flow for en bruger, der er ved at forlade virksomheden. Hvis du tildeler nyt ejerskab til kopierne, kan disse flow fortsat understøtte eksisterende forretningsprocesser. Det er vigtigt at kopiere disse flows for at slette personlige id-forbindelsesled for den bruger, der forlader virksomheden, og der skal oprettes nye forbindelser, så flowet kan knyttes til andre API'er og SaaS-programmer.

1. Log på [Power Platform Administration](https://admin.powerplatform.microsoft.com/), og vælg derefter det miljø, der indeholder de flows, som den slettede bruger ejer.

    ![Vis miljøer](./media/gdpr-dsr-delete/view-environments.png)

1. Vælg **Ressourcer** > **Flows**, og vælg derefter titlen på det flow, du vil tildele igen.

    ![Vis flows](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Vælg **Administrer deling**.

    ![Administrer deling](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Tilføj dig selv som ejer i panelet **Del**, der vises i højre side, og vælg derefter **Gem**.

    ![Del flow](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Log på [Power Automate](https://flow.microsoft.com/), vælg **Mine flows**, og vælg derefter **Team-flows**.

1. Vælg ellipsen **(...)** for det flow, du vil kopiere, og vælg derefter **Gem som**.

    ![Gem flow som](./media/gdpr-dsr-delete/flow-save-as.png)

1. Konfigurer forbindelser efter behov, og vælg derefter **Fortsæt**.

1. Angiv et nyt navn, og vælg derefter **Gem**.

    ![Opret kopi af flow](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Denne nye version af flowet vises i **Mine flow**, hvor du kan dele det med flere brugere, hvis du ønsker det.

    ![Teamflows](./media/gdpr-dsr-delete/team-flows.png)

1. Slet det oprindelige flow ved at vælge ellipsen **(...)** for det, vælge **Slet** og derefter vælge **Slet** igen, når du bliver bedt om det. I dette trin fjernes også de underliggende personlige id'er, der er inkluderet i systemafhængigheder mellem brugeren og Power Automate.

    ![Bekræftelse af sletning af flow](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Aktivér kopien af flowet ved at åbne **Mine flow** og derefter slå til/fra-kontrolelementet **Til**.

    ![Aktivér proces](./media/gdpr-dsr-delete/toggle-on.png)

1. Kopien udfører nu samme arbejdsproceslogik som den oprindelige version.

## <a name="delete-approval-history-from-power-automate"></a>Slet godkendelseshistorik fra Power Automate

 Godkendelsesdata for Power Automate lagres i den aktuelle eller den tidligere version af Common Data Service. I en godkendelse findes der personlige oplysninger i form af godkendelsestildelinger og kommentarer, der er inkluderet i et godkendelsessvar. Administratorer kan få adgang til disse data ved at udføre disse trin:

1. Log på [PowerApps](https://make.powerapps.com/).

1. Vælg **Data**, og vælg derefter **Objekter**.

1. Vælg ellipsen **(...)** for objektet **Flowgodkendelse**, og åbn derefter dataene i Microsoft Excel.

1. I Microsoft Excel skal du søge efter, filtrere og derefter slette godkendelsesdata efter behov.

Se under [Udførelse af DSR'er i forhold til Common Data Service-kundedata](https://go.microsoft.com/fwlink/?linkid=872251), hvis du vil have yderligere vejledning i, hvordan du besvarer DSR'er for de brugere, der bruger Common Data Service.


## <a name="delete-connections-created-by-a-user"></a>Slet forbindelser, der er oprettet af en bruger

Forbindelser bruges sammen med connectorer til at oprette forbindelse til andre API'er og SaaS-systemer.  Forbindelser inkluderer referencer til den bruger, der har oprettet dem, og kan derfor slettes for at fjerne eventuelle referencer til brugeren.

PowerShell-cmdlets for Power Apps-udvikler

En bruger kan slette alle forbindelser ved hjælp af funktionen Remove-Connection i [Power Apps-udviklers PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Power Apps PowerShell-cmdlet'er til administratorer

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Slet brugerens tilladelser til delte forbindelser

PowerShell-cmdlets for Power Apps-udvikler

En bruger kan slette alle sine tildelinger af forbindelsesroller for delte forbindelser med funktionen Remove-ConnectionRoleAssignment i [Power Apps-udviklers PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Power Apps PowerShell-cmdlet'er til administratorer

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Rolletildelinger for ejer kan ikke slettes uden at slette forbindelsesressourcen.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Slet brugerdefinerede connectorer, der er oprettet af brugeren

Brugerdefinerede connectorer supplerer de eksisterende indbyggede connectorer og gør det muligt at oprette forbindelse til andre API'er, SaaS og brugerudviklede systemer. Brugerdefinerede connectorer indeholder dog referencer til den bruger, der har oprettet dem, og kan derfor slettes for at fjerne alle referencer til brugeren.

PowerShell-cmdlets for Power Apps-udvikler

En bruger kan slette alle sine brugerdefinerede connectors ved hjælp af funktionen Remove-Connector i [Power Apps-udviklers PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Power Apps PowerShell-cmdlet'er til administratorer
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Slet brugerens tilladelser til delte brugerdefinerede connectorer

PowerShell-cmdlets for Power Apps-udvikler

En bruger kan slette alle sine rolletildelinger for connectorer for delte brugerdefineret connectorer med funktionen Remove-ConnectionRoleAssignment i [Power Apps-udviklers PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Power Apps PowerShell-cmdlet'er til administratorer
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Rolletildelinger for ejer kan ikke slettes uden at slette forbindelsesressourcen.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Slet alle miljøer, der er oprettet af brugeren, eller tildel dem til andre

Som administrator skal du træffe to beslutninger, når du behandler en DSR-sletteanmodning for en bruger for hvert af de miljøer, der er oprettet af brugeren:

1. Hvis du kan konstatere, at miljøet ikke bruges af andre i din organisation, kan du slette miljøet
1. Hvis du kan konstatere, at miljøet stadig er påkrævet, kan du vælge ikke at slette miljøet og tilføje dig selv (eller en anden bruger i din organisation) som miljøadministrator.
> [!IMPORTANT]
> Hvis du sletter et miljø, slettes alle ressourcer i miljøet permanent, herunder alle apps, flows, forbindelser osv., så du skal gennemse indholdet af et miljø, før du sletter det.
>
>

## <a name="give-access-to-a-users-environments-from-the-power-automate-admin-center"></a>Giv adgang til en brugers miljøer fra Power Automate Administration

En administrator kan tildele administratoradgang til et miljø, der er oprettet af en bestemt bruger, fra [Power Platform Administration](https://admin.powerplatform.microsoft.com/). Du kan finde flere oplysninger om administration af miljøer ved at gå til [Brug af miljøer i Power Automate](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Slet brugerens tilladelser til alle andre miljøer

Brugere kan tildeles tilladelser (f.eks. miljøadministrator, miljøudvikler osv.) i et miljø, der er gemt i tjenesten Power Automate, som en "rolletildeling".

Med introduktionen af Common Data Service vil oprettelsen af en database i miljøet betyde, at disse "rolletildelinger gemmes som poster i forekomsten af Common Data Service.

Du kan finde flere oplysninger om, hvordan du fjerner en brugers tilladelse i et miljø, ved at gå til [Brug af miljøer i Power Automate](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Slet gatewayindstillinger

Svar på sletteanmodninger fra fysiske personer for datagateways i det lokale miljø findes [her](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Slet brugeroplysninger

Brugeroplysningerne er en forbindelse mellem en bruger og en specifik lejer. Inden du kører denne kommando, skal du sikre, at alle flows for denne bruger er blevet tildelt til en anden og/eller slettet. Når det er fuldført, kan en administrator slette brugeroplysninger med et kald til cmdlet'en **Remove-AdminFlowUserDetails** og overføre brugerens objekt-id.

Power Apps PowerShell-cmdlet'er til administratorer
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Hvis en bruger stadig ejer individuelle flows eller teamflows, vil kommandoen returnere en fejl. Du kan løse problemet ved at slette alle resterende flows eller teamflows for denne bruger og køre kommandoen igen.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Slet brugeren fra Azure Active Directory

Når du har udført trinnene ovenfor, er det sidste trin at slette brugerkontoen for Azure Active Directory ved at følge de trin, der er beskrevet i Azure-dokumentationen om anmodninger fra fysiske personer for GDPR, som du finder på [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>Slet brugeren fra en ikke-administreret lejer

Hvis du er medlem af en ikke-administreret lejer, skal du udføre handlingen **Kontolukning** fra [portalen til beskyttelse af personlige oplysninger for arbejde og skole](https://go.microsoft.com/fwlink/?linkid=873123).

Du kan finde ud af, om du er bruger af en administreret eller ikke-administreret lejer, ved at udføre følgende handlinger:

1. Åbn følgende URL-adresse i en browser, idet du erstatter din mailadresse i URL-adressen:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Hvis du er medlem af en **ikke-administreret lejer**, kan du se en `"IsViral": true` i svaret.

    {

     "Logon": "foobar@unmanagedcontoso.com",

    "Domænenavn": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. Ellers tilhører du en administreret lejer.
