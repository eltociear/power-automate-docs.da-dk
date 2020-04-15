---
title: Sletteanmodninger fra den registrerede i forbindelse med GDPR i Power Automate | Microsoft Docs
description: Få mere at vide om, hvordan du bruger Power Automate til at reagere på sletteanmodninger fra den registrerede i forbindelse med GPDR.
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
ms.date: 4/07/2020
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 16d92a2d8aad6e39ff5e2eb446438dc769b1baf8
ms.sourcegitcommit: 27ee91452be26cf5c96397c39f9f5b8bede14cdb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/08/2020
ms.locfileid: "80862670"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-power-automate"></a>Reaktion på sletteanmodninger fra den registrerede i forbindelse med GDPR i Power Automate


"Retten til sletning" ved at fjerne personlige data fra en organisations kundedata er en central sikkerhedsdetalje i persondataforordningen. Fjernelse af personlige data inkluderer fjernelse af alle personlige data og systemoprettede logge, men ikke oplysninger fra overvågningslogge.

I Power Automate kan brugere skabe automatiserede arbejdsprocesser, der er en vigtig del af den daglige drift i organisationen. Når en bruger forlader virksomheden, skal en administrator manuelt gennemse og afgøre, om nogle af de data og ressourcer, som brugeren har oprettet, skal slettes. Der er andre personlige data, som slettes automatisk, når brugerens konto slettes fra Azure Active Directory.

I følgende tabel vises, hvilke personlige data der slettes automatisk, og hvilke data der kræver, at administratoren manuelt gennemser og sletter dem:

|Kræver manuel gennemgang og sletning|Slettes automatisk, når brugeren slettes fra Azure Active Directory|
|------|------|
|Miljø*|Systemoprettede logge|
|Miljøtilladelser**|Kørselsoversigt|
|Flow|Aktivitetsopdatering|
|Flowtilladelser|Gateway |
|Brugeroplysninger|Gatewaytilladelser|
|Forbindelser*||
|Forbindelsestilladelser||
|Brugerdefineret connector*||
|Tilladelser til brugerdefineret connector||

*Hver af disse ressourcer indeholder posterne "Oprettet af" og "Ændret af", som indeholder personlige data. Af sikkerhedsmæssige årsager gemmes disse poster, indtil ressourcen slettes.

**For de miljøer, der indeholder en Common Data Service-database, gemmes miljøtilladelserne, dvs. hvilke brugere der har fået tildelt rollerne Miljøopretter og Miljøadministrator, som poster i Common Data Service. Under [Udfør DSR-anmodninger imod Common Data Service-kundedata](https://go.microsoft.com/fwlink/?linkid=872251) kan du finde en vejledning i, hvordan du besvarer DSR-anmodninger for brugere, der anvender Common Data Service.

For de data og ressourcer, der kræver manuel gennemgang, findes følgende funktioner i Power Automate til søgning efter og ændring af private oplysninger for en bestemt bruger:

* **Webstedsadgang:** Log på [Power Apps Administration](https://admin.powerapps.com/) eller [Power Automate Administration](https://admin.flow.microsoft.com/)

* **PowerShell-adgang:**  [PowerShell-cmdlet'er til Power Apps Administration](https://go.microsoft.com/fwlink/?linkid=871804) 

Her er opdelingen af oplevelser, som en administrator kan slette opdelt efter de enkelte typer personlige data inden for de enkelte typer ressourcer:

|Ressourcer, der indeholder personlige data|Webstedsadgang|PowerShell-adgang|Automatisk sletning|
|-----|----|----|----|
|Systemoprettede logge|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|||
|Miljø|Power Automate Administration|Power Apps-cmdlet'er||
|Miljøtilladelser*|Power Automate Administration|Power Apps-cmdlet'er||
|Kørselsoversigt||| Slettet i henhold til politikken for dataopbevaring i 28 dage|
|Aktivitetsopdatering |||Slettet i henhold til politikken for dataopbevaring i 28 dage|
|Brugerjob|| ||
|Flow|Power Automate-udviklerportal**|||
|Flowtilladelser|Power Automate-udviklerportal|||
|Brugeroplysninger||Power Apps-cmdlet'er||
|Forbindelser|Power Automate-udviklerportal| ||
|Forbindelsestilladelser|Power Automate-udviklerportal| ||
|Brugerdefineret connector|Power Automate-udviklerportal| ||
|Tilladelser til brugerdefineret connector|Power Automate-udviklerportal| ||
|Oversigt over godkendelser|Microsoft Power Apps-udviklerportal*|||

*Med introduktionen af Common Data Service forholder det sig sådan, at hvis en database oprettes i miljøet, gemmes miljøtilladelserne og tilladelserne til modeldrevne apps som poster i forekomsten af Common Data Service. Under [Udfør DSR-anmodninger imod Common Data Service-kundedata](https://go.microsoft.com/fwlink/?linkid=872251) kan du finde en vejledning i, hvordan du besvarer DSR-anmodninger for brugere, der anvender Common Data Service.

\*\* En administrator kan kun få adgang til disse ressourcer fra Power Automate-udviklerportalen, hvis administratoren har fået tildelt adgang fra Power Automate Administration.

## <a name="manage-delete-requests"></a>Administrer sletteanmodninger

I fremgangsmåden nedenfor beskrives, hvordan du får adgang til administrative funktioner til behandling af sletteanmodninger for GDPR. Disse trin skal udføres i den rækkefølge, der er beskrevet nedenfor.

> [!IMPORTANT]
> Hvis du vil undgå at beskadige data, skal du følge disse trin i nævnte rækkefølge.
>
>

## <a name="list-and-re-assign-flows"></a>Vis og tildel flow igen

I disse trin kopieres eksisterende flow for en bruger, der er ved at forlade virksomheden. Hvis du tildeler nyt ejerskab til kopierne, kan disse flow fortsat understøtte eksisterende forretningsprocesser. Det er vigtigt at kopiere disse flow for at slette personlige id-forbindelsesled for den bruger, der forlader virksomheden, og der skal oprettes nye forbindelser, så flowet kan knyttes til andre API'er og SaaS-programmer.

1. Log på [Power Automate Administration](https://admin.flow.microsoft.com/), og vælg derefter det miljø, der indeholder flow, som den slettede bruger ejer.

    ![Vis miljøer](./media/gdpr-dsr-delete/view-environments.png)

1. Vælg **Ressourcer** > **Flow**, og vælg derefter titlen på det flow, du vil tildele igen.

    ![Vis flow](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Vælg **Administrer deling**.

    ![Administrer deling](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. I panelet **Del**, der vises i højre side, skal du tilføje dig selv som ejer og derefter vælge **Gem**.

    ![Del flow](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Log på [Power Automate](https://flow.microsoft.com/), vælg **Mine flow**, og vælg derefter **Teamflow**.

1. Vælg ellipsen **(...)**  for det flow, du vil kopiere, og vælg derefter **Gem som**.

    ![Gem flow som](./media/gdpr-dsr-delete/flow-save-as.png)

1. Konfigurer forbindelser efter behov, og vælg derefter **Fortsæt**.

1. Angiv et nyt navn, og vælg derefter **Gem**.

    ![Opret kopi af flow](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Denne nye version af flowet vises i **Mine flow**, hvor du kan dele den med flere brugere, hvis du ønsker det.

    ![Teamflow](./media/gdpr-dsr-delete/team-flows.png)

1. Slet det oprindelige flow ved at vælge ellipsen **(...)** for det, vælge **Slet** og derefter vælge **Slet** igen, når du bliver bedt om det. I dette trin fjernes også de underliggende personlige id'er, som er inkluderet i systemafhængigheder mellem brugeren og Power Automate.

    ![Bekræftelse af sletning af flow](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Aktivér kopien af flowet ved at åbne **Mine flow** og derefter slå til/fra-kontrolelementet **til**.

    ![Aktivér flow](./media/gdpr-dsr-delete/toggle-on.png)

1. Kopien udfører nu samme arbejdsproceslogik som den oprindelige version.

## <a name="delete-approval-history-from-power-automate"></a>Slet oversigten over godkendelse fra Power Automate

 Godkendelsesdata for Power Automate gemmes i den aktuelle eller tidligere version af Common Data Service. I en godkendelse findes der personlige oplysninger i form af godkendelsestildelinger og kommentarer, der er inkluderet i et godkendelsessvar. Administratorer kan få adgang til disse data ved at udføre disse trin:

1. Log på [PowerApps](https://make.powerapps.com/).

1. Vælg **Data**, og vælg derefter **Enheder**.

1. Vælg ellipsen **(...)** for enheden **Flowgodkendelse**, og åbn derefter dataene i Microsoft Excel.

1. I Microsoft Excel skal du søge efter, filtrere og derefter slette godkendelsesdata efter behov.

Hvis du vil have yderligere hjælp til, hvordan du besvarer DSR-anmodninger for brugere af Common Data Service, skal du se [Udfør DSR-anmodninger imod Common Data Service-kundedata](https://go.microsoft.com/fwlink/?linkid=872251).


## <a name="delete-connections-created-by-a-user"></a>Slet forbindelser, der er oprettet af en bruger

Forbindelser, der bruges sammen med connectors til at oprette forbindelse til andre API'er og SaaS-systemer.  Forbindelser indeholder referencer til den bruger, der har oprettet dem, og kan derfor slettes for at fjerne alle referencer til brugeren.

PowerShell-cmdlet'er til Power Apps-udvikler

En bruger kan slette alle sine forbindelser ved hjælp af funktionen Remove-Connection i [PowerShell-cmdlet'er til Power Apps-udvikler](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

PowerShell-cmdlet'er til Power Apps Administration

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Slet brugerens tilladelser til delte forbindelser

PowerShell-cmdlet'er til Power Apps-udvikler

En bruger kan slette alle forbindelsens rolletildelinger for delte forbindelser via funktionen Remove-ConnectionRoleAssignment i [PowerShell-cmdlet'er til Power Apps-udvikler](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

PowerShell-cmdlet'er til Power Apps Administration

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Du kan ikke slette tildeling af ejerroller uden at slette forbindelsesressourcen.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Slet brugerdefinerede connectors, der er oprettet af brugeren

Brugerdefinerede connectors supplerer de eksisterende standardconnectors og gør det muligt at oprette forbindelse til andre API'er, SaaS-systemer og specialudviklede systemer. Brugerdefinerede connectors indeholder dog referencer til den bruger, der har oprettet dem, og kan derfor slettes for at fjerne alle referencer til brugeren.

PowerShell-cmdlet'er til Power Apps-udvikler

En bruger kan slette alle sine brugerdefinerede connectors ved hjælp af funktionen Remove-Connector i [PowerShell-cmdlet'er til Power Apps-udvikler](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

PowerShell-cmdlet'er til Power Apps Administration
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Slet brugerens tilladelser til delte brugerdefinerede connectors

PowerShell-cmdlet'er til Power Apps-udvikler

En bruger kan slette alle connectorens rolletildelinger for delte brugerdefinerede connectors via funktionen Remove-ConnectorRoleAssignment i [PowerShell-cmdlet'er til Power Apps-udvikler](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

PowerShell-cmdlet'er til Power Apps Administration
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Du kan ikke slette tildeling af ejerroller uden at slette forbindelsesressourcen.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Slet alle miljøer, der er oprettet af brugeren, eller tildel dem til andre

Som administrator skal du træffe to beslutninger, når du behandler en DSR-sletteanmodning for en bruger for hvert af de miljøer, der er oprettet af brugeren:

1. Hvis du kan konstatere, at miljøet ikke bruges af andre i din organisation, kan du slette miljøet
1. Hvis du kan konstatere, at miljøet stadig er påkrævet, kan du vælge ikke at slette miljøet og tilføje dig selv (eller en anden bruger i din organisation) som miljøadministrator.
> [!IMPORTANT]
> Hvis du sletter et miljø, slettes alle ressourcer i miljøet permanent, herunder alle apps, flow, forbindelser osv., og derfor skal du gennemse indholdet af i et miljø, inden det slettes.
>
>

## <a name="give-access-to-a-users-environments-from-the-power-automate-admin-center"></a>Giv adgang til en brugers miljøer fra Power Automate Administration

En administrator kan tildele administratoradgang til et miljø, der er oprettet af en bestemt bruger, fra [Power Automate Administration](https://admin.flow.microsoft.com/). Du kan finde flere oplysninger om administration af miljøer ved at navigere til [Brug af miljøer i Power Automate](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Slet brugerens tilladelser til alle andre miljøer

Brugere kan få tildelt tilladelser (f.eks. miljøadministrator, miljøudvikler osv.) i et miljø, der er gemt i tjenesten Power Automate-tjenesten, som en "rolletildeling".

Med introduktionen af Common Data Service forholder det sig sådan, at hvis en database oprettes i miljøet, gemmes disse "rolletildelinger" som poster i Common Data Service.

Du kan finde flere oplysninger om, hvordan du fjerner en brugers tilladelse i et miljø, ved at navigere til [Brug af miljøer i Power Automate](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Slet gatewayindstillinger

Svar på sletteanmodninger fra fysiske personer for datagateways i det lokale miljø findes [her](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Slet brugeroplysninger

Brugeroplysningerne er en forbindelse mellem en bruger og en specifik lejer. Inden du kører denne kommando, skal du sikre, at alle flows for denne bruger er blevet tildelt til en anden og/eller slettet. Når det er fuldført, kan en administrator slette brugeroplysninger med et kald til cmdlet'en **Remove-AdminFlowUserDetails** og overføre brugerens objekt-id.

PowerShell-cmdlet'er til Power Apps Administration
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

Hvis du er medlem af en ikke-administreret lejer, skal du udføre **kontolukning** fra [portalen til beskyttelse af personlige oplysninger for arbejde og skole](https://go.microsoft.com/fwlink/?linkid=873123).

Hvis du vil finde ud af, om du bruger en administreret eller ikke-administreret lejer, skal du gøre følgende:

1. Åbn følgende URL-adresse i en browser, og sørg for at erstatte din mailadresse i URL-adressen:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Hvis du er medlem af en **ikke-administreret lejer**, vil du få vist `"IsViral": true` i svaret.

    {

     "Login": "foobar@unmanagedcontoso.com",

    "Domænenavn": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. Ellers tilhører du en ikke-administreret lejer.
