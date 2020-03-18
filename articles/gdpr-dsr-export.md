---
title: Eksportanmodninger fra registrerede omfattet af GDPR i Power Automate | Microsoft Docs
description: Få mere at vide om, hvordan du bruger Power Automate til at svare på eksportanmodninger fra registrerede omfattet af GPDR.
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: df82a2aa48a8e85c950757ef4f72a6f7ee88e071
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79192041"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Svar på eksportanmodninger fra registrerede omfattet af GDPR for Power Automate


Som led i vores bestræbelser på at være med dig gennem hele processen omkring den generelle forordning om databeskyttelse (GDPR) har vi udviklet denne dokumentation. Denne dokumentation beskriver ikke blot, hvad Microsoft gør for at forberede sig på GDPR, men kommer også med eksempler på, hvad du kan gøre i dag med Microsoft for at overholde GDPR, når du bruger Power Automate.

## <a name="manage-export-requests"></a>Administrer eksportanmodninger

*Retten til videregivelse af oplysninger* gør det muligt for en fysisk person at anmode om en kopi af hans eller hendes personlige data i elektronisk format, dvs. i et format, der er "struktureret, almindeligt brugt, kan læses af en maskine, og som er kompatibelt", og som kan sendes til en anden datacontroller.

Power Automate indeholder følgende funktioner, som du kan bruge til at finde eller eksportere de personlige data for en bestemt bruger:

* **Webstedsadgang:** Log på [Power Apps Administration](https://admin.powerapps.com/) eller [Power Automate Administration](https://admin.flow.microsoft.com/).

* **PowerShell-adgang:**  [PowerShell-cmdlet'er til Power Apps Administration](https://go.microsoft.com/fwlink/?linkid=871804).

|**Kundedata**|**Webstedsadgang**|**PowerShell-adgang**|
|-----------------|------------------|-------------------|
|Systemoprettede logge|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|
|Kørselsoversigt|Power Automate-udviklerportal||
|Flow|Power Automate-udviklerportal||
|Flowtilladelser| Power Automate-udviklerportal og Power Automate Administration||
|Brugeroplysninger||Power Apps-cmdlet'er|
|Forbindelser|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Forbindelsestilladelser|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Brugerdefinerede forbindelser|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Tilladelser til brugerdefineret connector|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Gateway|Power Automate-udviklerportal|PowerShell-cmdlet'er til datagateway i det lokale miljø|
|Gatewaytilladelser|Power Automate-udviklerportal|PowerShell-cmdlet'er til datagateway i det lokale miljø|

## <a name="export-a-flow"></a>Eksportér et flow

Enten en slutbruger eller en administrator, der har givet sig selv adgang til flowet, kan eksportere flowet ved at følge disse trin:

1. Log på [Power Automate](https://flow.microsoft.com/).

1. Vælg linket **Mine flow**, og vælg derefter det flow, der skal eksporteres.

1. Vælg **... Flere**, og vælg derefter **Eksportér**.

    ![Eksportér flow](./media/gdpr-dsr-export/export-flow.png)

1. Vælg **Pakke (.zip)** .

Dit flow er nu tilgængeligt som en zip-komprimeret pakke. Du kan finde flere oplysninger i blogindlægget om, [hvordan du eksporterer og importerer et flow](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Eksportér kørselsoversigt

Kørselsoversigten indeholder en liste over alle kørsler, der er indtruffet for et flow. Disse data indeholder flowstatus, starttidspunkt, varighed og input/output-data for udløsere og handlinger.

Enten en slutbruger eller en administrator, som er tildelt adgang til flowet via Power Automate Administration, kan udføre disse trin for at eksportere disse data:

1. Log på [Power Automate](https://flow.microsoft.com/).
1. Vælg linket **Mine flow**, og vælg derefter det flow, som du vil eksportere kørselsoversigten for.
1. I ruden **KØRSELSOVERSIGT** skal du vælge **Se alle**.

    ![Kørselsoversigt](./media/gdpr-dsr-export/run-history.png)

1. Vælg **Download CSV**.

    ![Download CSV](./media/gdpr-dsr-export/download-csv.png)

Kørselsoversigten hentes som en .csv-fil, som kan åbnes i Microsoft Excel eller i en teksteditor, hvor du kan analysere resultaterne yderligere.

## <a name="export-a-users-activity-feed"></a>Eksportér en brugers aktivitetsopdatering

I [Power Automate](https://flow.microsoft.com/) viser aktivitetsopdateringen en brugers oversigt over aktiviteter, fejl og beskeder. Alle brugere kan få vist deres aktivitetsopdatering ved at følge disse trin:

1. Log på [Power Automate](https://flow.microsoft.com/), vælg klokkeikonet i nærheden af øverste højre hjørne, og vælg derefter **Vis alle aktiviteter**.

    ![Vis aktivitetsopdatering](./media/gdpr-dsr-export/show-activity-feed.png)

1. På skærmen **Aktivitet** skal du kopiere resultaterne og derefter indsætte dem i en dokumenteditor, f.eks. Microsoft Word.

    ![Vis aktivitetsopdatering](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Eksportér en brugers forbindelser

Forbindelser gør det muligt for flow at oprette forbindelse til API'er, SaaS-programmer og andre tredjepartssystemer. Udfør disse trin for at få vist dine forbindelser:

1. Log på [Power Automate](https://flow.microsoft.com/), vælg tandhjulsikonet i nærheden af øverste højre hjørne, og vælg derefter **Forbindelser**.

    ![Vis forbindelser](./media/gdpr-dsr-export/show-connections.png)
1. Kopiér resultaterne, og indsæt dem derefter i en dokumenteditor, f.eks. Microsoft Word.

Power Apps Admin PowerShell-cmdlet'er

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Eksportér en liste over en brugers forbindelsestilladelser

En bruger kan eksportere tildelingerne af forbindelsesroller for alle de forbindelser, som brugeren har adgang til, ved hjælp af funktionen Get-ConnectionRoleAssignment i [PowerShell-cmdlet'erne til Power Apps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
PowerShell-cmdlet'er til Power Apps Administration

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Eksportér en brugers brugerdefinerede connectors

Brugerdefinerede connectors supplerer standardconnectors og tillader forbindelse til andre API'er, SaaS-systemer og specialudviklede systemer. Du kan overføre ejerskabet af en brugerdefineret connector eller slette den.

Udfør disse trin for at eksportere en liste over brugerdefinerede connectors:

1. Naviger til [Power Automate](https://flow.microsoft.com).
1. Vælg **tandhjuls**ikonet for at få vist indstillinger.
1. Vælg **Brugerdefinerede connectors**.
1. Kopiér og indsæt listen over brugerdefinerede connectors i en teksteditor, f.eks. Microsoft Word.

    ![Eksportér brugerdefinerede connectors](./media/gdpr-dsr-export/export-custom-connectors.png)

Ud over den oplevelse, der leveres i Power Automate, kan du bruge funktionen Get-Connector fra [Power Apps PowerShell-cmdlet'er](https://go.microsoft.com/fwlink/?linkid=871804) til at eksportere alle brugerdefinerede connectors.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

PowerShell-cmdlet'er til Power Apps Administration

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Eksportér en brugers tilladelser til brugerdefinerede connectors

En bruger kan eksportere alle tilladelser til brugerdefinerede connectors, som brugeren har oprettet via funktionen Get-ConnectorRoleAssignment i [Power Apps PowerShell-cdmlet'er](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

PowerShell-cmdlet'er til Power Apps Administration

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Eksportér oversigt over godkendelser

Oversigten over Power Automate-godkendelser henter en oversigtsliste over godkendelser, der er modtaget af eller sendt til en bruger. Alle brugere kan få vist en oversigt over deres godkendelser ved at:

1. Logge på [Power Automate](https://flow.microsoft.com/), vælge **Godkendelser** og derefter vælge **Oversigt**.

    ![Få vist oversigt over godkendelser](./media/gdpr-dsr-export/view-approval-history.png)

1. En liste viser godkendelser, som brugeren har modtaget. Brugerne kan få vist godkendelser, som de har sendt, ved at vælge pil ned ud for **Modtaget** og derefter vælge **Sendt**.

    ![Få vist godkendelser, der er modtaget](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Eksportér brugeroplysninger
Brugeroplysningerne er en forbindelse mellem en bruger og en specifik lejer. En administrator kan eksportere disse oplysninger ved at foretage et kald til cmdlet'en **Get AdminFlowUserDetails** og overføre brugerens objekt-id.

PowerShell-cmdlet'er til Power Apps Administration

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Eksportér gatewayindstillinger
Svar på eksportanmodninger fra fysiske personer for datagateways i det lokale miljø findes [her](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

