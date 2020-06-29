---
title: Anmodninger i Power Automate om eksport af dataemner omfattet af GDPR | Microsoft Docs
description: Lær, hvordan du kan bruge Power Automate til at svare på anmodninger om eksport af dataemner omfattet af GPDR.
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
ms.openlocfilehash: f9fee8a217cdec28f6a3b49dee6335c4f13a3d45
ms.sourcegitcommit: 2284143cf147beb7d6071fd8005a41298e51e493
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/19/2020
ms.locfileid: "3384933"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Besvarelse af anmodninger i Power Automate om eksport af dataemner omfattet af GDPR


Som en del af vores forpligtelse i egenskab af din partner i forhold til generel forordning om databeskyttelse (GDPR) har vi udviklet dokumentation som hjælp til din forberedelse. Denne dokumentation beskriver ikke blot, hvad Microsoft gør for at forberede sig på GDPR, men kommer også med eksempler på, hvad du kan gøre i dag med Microsoft for at overholde GDPR, når du bruger Power Automate.

## <a name="manage-export-requests"></a>Administrer eksportanmodninger

*Retten til videregivelse af oplysninger* gør det muligt for en fysisk person at anmode om en kopi af hans eller hendes personlige data i et elektronisk format, dvs. i et format, der er "struktureret, almindeligt brugt, kan læses af en maskine, og som er kompatibelt", og som kan sendes til en anden datacontroller.

Power Automate tilbyder følgende funktioner til søgning efter eller eksport af personlige data for en bestemt bruger:

* **Websiteadgang:** Log på [Power Apps Administration](https://admin.powerapps.com/) eller [Power Automate Administration](https://admin.flow.microsoft.com/).

* **PowerShell-adgang:** [Power Apps Admin PowerShell-cdmlets](https://go.microsoft.com/fwlink/?linkid=871804).

|**Kundedata**|**Adgang til websted**|**PowerShell-adgang**|
|-----------------|------------------|-------------------|
|Systemgenererede logge|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|
|Kørselshistorik|Power Automate-udviklerportal||
|Flow|Power Automate-udviklerportal||
|Flowtilladelser| Power Automate-udviklerportal og Power Automate Administration||
|Brugerdetaljer||Power Apps-cmdlet'er|
|Forbindelser|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Forbindelsestilladelser|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Brugerdefinerede connectors|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Brugerdefinerede connectorer|Power Automate-udviklerportal|Power Apps-cmdlet'er |
|Gateway|Power Automate-udviklerportal|PowerShell-cmdlets til datagateway i det lokale miljø|
|Gatewaytilladelser|Power Automate-udviklerportal|PowerShell-cmdlets til datagateway i det lokale miljø|

## <a name="export-a-flow"></a>Eksporter et flow

En slutbruger eller en administrator, der har givet sig selv adgang til flowet, kan eksportere flowet ved at følge disse trin:

1. Log på [Power Automate](https://flow.microsoft.com/).

1. Vælg linket **Mine flows**, og vælg derefter det flow, der skal eksporteres.

1. Vælg **... Flere**, og vælg derefter **Eksporter**.

    ![Eksportér flow](./media/gdpr-dsr-export/export-flow.png)

1. Vælg **Pakke (.zip)**.

Dit flow er nu tilgængeligt som en zip-komprimeret pakke. Du kan finde flere oplysninger i blogindlægget om, [hvordan du eksporterer og importerer et flow](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Eksportér kørselsoversigt

Kørselsoversigten indeholder en liste over alle kørsler, der er sket for et flow. Disse data indeholder flowstatus, starttidspunkt, varighed og input/output-data for udløsere og handlinger.

Enten en slutbruger eller en administrator, som er tildelt adgang til flowet via Power Automate Administration, kan udføre disse trin for at eksportere disse data:

1. Log på [Power Automate](https://flow.microsoft.com/).
1. Vælg linket **Mine flows**, og vælg derefter det flow, som du vil eksportere kørselsoversigten for.
1. Vælg **Se alle** i ruden **KØRSELSOVERSIGT**.

    ![Kørselshistorik](./media/gdpr-dsr-export/run-history.png)

1. Vælg **Download CSV**.

    ![Hent CSV](./media/gdpr-dsr-export/download-csv.png)

Kørselsoversigten downloades som en .csv-fil, som kan åbnes i Microsoft Excel eller i et tekstredigeringsprogram, hvor du kan analysere resultaterne yderligere.

## <a name="export-a-users-activity-feed"></a>Eksportér en brugers aktivitetsopdatering

I [Power Automate](https://flow.microsoft.com/) viser aktivitetsopdateringen en brugers historik over aktiviteter, fejl og beskeder. Alle brugere kan få vist deres aktivitetsopdatering ved at følge disse trin:

1. Log på [Power Automate](https://flow.microsoft.com/), vælg klokkeikonet i nærheden af øverste højre hjørne, og vælg derefter **Vis alle aktiviteter**.

    ![Vis aktivitetsopdatering](./media/gdpr-dsr-export/show-activity-feed.png)

1. På skærmen **Aktivitet** kan du kopiere resultaterne og derefter indsætte dem i et dokumentredigeringsprogram, f.eks. Microsoft Word.

    ![Vis aktivitetsopdatering](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Eksportér en brugers forbindelser

Forbindelser gør det muligt for flow at oprette forbindelse til API'er, SaaS-programmer og andre tredjepartssystemer. Udfør disse trin for at få vist dine forbindelser:

1. Log på [Power Automate](https://flow.microsoft.com/), vælg tandhjulsikonet i nærheden af øverste højre hjørne, og vælg derefter **Forbindelser**.

    ![Vis forbindelser](./media/gdpr-dsr-export/show-connections.png)
1. Kopiér resultaterne, og indsæt dem derefter i et dokumentredigeringsprogram, f.eks. Microsoft Word.

Power Apps PowerShell-cmdlet'er til administratorer

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Eksporter en liste over en brugers forbindelsestilladelser

En bruger kan eksportere tildelingerne af forbindelsesroller for alle de forbindelser, de har adgang til, ved hjælp af funktionen Get-ConnectionRoleAssignment i [Power Apps PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Power Apps PowerShell-cmdlet'er til administratorer

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Eksporter en brugers brugerdefinerede connectorer

Brugerdefinerede connectorer supplerer standardconnectorer og tillader forbindelse til andre API'er, SaaS-systemer og specialudviklede systemer. Du kan overføre ejerskabet af en brugerdefineret connector eller slette den.

Udfør disse trin for at eksportere en liste over brugerdefinerede connectorer:

1. Naviger til [Power Automate](https://flow.microsoft.com).
1. Vælg **tandhjuls**ikonet for at få vist indstillinger.
1. Vælg **Brugerdefinerede connectorer**.
1. Kopiér og indsæt listen over brugerdefinerede connectors i et tekstredigeringsprogram, f.eks. Microsoft Word.

    ![Eksporter brugerdefinerede connectorer](./media/gdpr-dsr-export/export-custom-connectors.png)

Ud over de funktioner, der leveres i Power Automate, kan du bruge funktionen Get-Connector fra [Power Apps PowerShell-cmdlets](https://go.microsoft.com/fwlink/?linkid=871804) til at eksportere alle brugerdefinerede connectorer.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Power Apps PowerShell-cmdlet'er til administratorer

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Eksporter en brugers tilladelser til brugerdefinerede connectorer

En bruger kan eksportere alle tilladelser til brugerdefinerede connectoreer, de har oprettet via funktionen Get-ConnectorRoleAssignment i [Power Apps PowerShell-cdmlets](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Power Apps PowerShell-cmdlet'er til administratorer

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Eksporter oversigt over godkendelser

Oversigten over Power Automate-godkendelser viser en historisk registrering af godkendelser, der er modtaget af eller sendt til en bruger. Alle brugere kan få vist en oversigt over deres godkendelser ved at:

1. Log på [Power Automate](https://flow.microsoft.com/), vælg **Godkendelser**, og vælg derefter **Oversigt**.

    ![Få vist oversigt over godkendelser](./media/gdpr-dsr-export/view-approval-history.png)

1. En liste viser godkendelser, som brugeren har modtaget. Brugerne kan få vist godkendelser, som de har sendt, ved at vælge pil ned ud for **Modtaget** og derefter vælge **Sendt**.

    ![Få vist godkendelser, der er modtaget](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Eksporter brugeroplysninger
Brugeroplysningerne er en forbindelse mellem en bruger og en specifik lejer. En administrator kan eksportere disse oplysninger ved at foretage et kald til cmdlet'en **Get AdminFlowUserDetails** og overføre brugerens objekt-id.

Power Apps PowerShell-cmdlet'er til administratorer

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Eksporter gatewayindstillinger
Svar på eksportanmodninger fra fysiske personer for datagateways i det lokale miljø findes [her](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

