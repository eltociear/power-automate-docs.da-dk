---
title: Få mere at vide om oprettelse af forbindelse til dine data ved hjælp af forbindelser og datagateways i det lokale miljø | Microsoft Docs
description: Tilføj eller administrer forbindelser til SharePoint, SQL Server, OneDrive for Business, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drev med mere
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/23/2020
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0edd05a5c08b71c534a6b6b4a58bf96dcb33a6cf
ms.sourcegitcommit: 3732af8b39dcbc028de934694b54afc919e7eeef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/26/2020
ms.locfileid: "3893750"
---
# <a name="manage-connections-in-power-automate"></a>Administrere forbindelser i Power Automate

Power Automate bruger *forbindelser* til at gøre det nemt for dig at få adgang til dine data under oprettelse af flow. Power Automate indeholder almindeligt anvendte forbindelser, herunder SharePoint, , SQL Server, Office 365, OneDrive for Business, Salesforce, Excel, Dropbox, Twitter og meget mere. Forbindelser deles med Power Apps, så når du opretter en forbindelse i én service, viser forbindelsen sig i den anden service.

Du kan bruge forbindelser til udføre disse opgaver:

- Opdatere en SharePoint-liste.
- Hente data fra en Microsoft Excel-fil i din OneDrive for Business- eller Dropbox-konto.
- Sende mail i Office 365.
- Sende et tweet.

Du kan oprette en forbindelse i flere scenarier som:

- Oprette et [flow ud fra en skabelon](./get-started-logic-template.md)

- Oprette et [flow fra bunden](./get-started-logic-flow.md) eller opdatere et eksisterende flow

- Oprette en forbindelse i [Power Automate](https://flow.microsoft.com/).

>[!TIP]
> Du kan finde detaljerede oplysninger om brugen af SharePoint sammen med Power Automate i  [SharePoint-dokumentationen](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers).

## <a name="add-a-connection"></a>Tilføj en forbindelse

1. Log i [Power Automate](https://flow.microsoft.com/) på med din arbejds- eller organisationskonto.

1. Vælg **Data** > **Forbindelser** på navigationslinjen til venstre.

   ![Billede, der viser forbindelsesindstillingen](media/add-manage-connections/data-connections-link.png)

1. Vælg **Ny forbindelse** øverst på siden.

1. På listen over tilgængelige forbindelser skal du vælge den forbindelse, du vil konfigurere, (f.eks. SharePoint) ved at vælge ikonet **+**.

   ![Liste over forbindelser, der kan konfigureres](media/add-manage-connections/new-connections-list.png)

1. Følg trinnene for at angive dine legitimationsoplysninger for at konfigurere forbindelsen.

   > [!TIP]
   > Du kan finde alle de forbindelser, du har oprettet, under **Data** > **Forbindelser**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Opret forbindelse til dine data via en datagateway i det lokale miljø

Nogle connectorer, f.eks. SharePoint-connectoren, understøtter datagateway i det lokale miljø. Sådan opretter du en forbindelse, der bruger en gateway:

1. Følg fremgangsmåden, der er angivet tidligere i dette emne, for at [tilføje en forbindelse](#add-a-connection).

1. På listen med tilgængelige forbindelser skal du vælge **SharePoint**.

1. Vælg indstillingen **Opret forbindelse via en datagateway i det lokale miljø**.

   ![Vælg indstillingen for det lokale miljø](media/add-manage-connections/select-on-prem-option.png)

1. Angiv forbindelsens legitimationsoplysninger, og vælg derefter den gateway, du vil bruge.

   >[!TIP]
   > Du kan få flere oplysninger under [Administrere gateways](./gateway-manage.md) og [Om gateways](./gateway-reference.md).

   > [!NOTE]
   > Når forbindelsen er konfigureret, står den **Forbindelser**.

**Sletning af en forbindelse**

1. Gå til siden **Data** > **Forbindelser** , og vælg den forbindelse, du vil slette.

1. Vælg **…** for at få vist flere kommandoer, og vælg derefter **Slet**.

   ![Vælg Slet for at slette forbindelsen](media/add-manage-connections/delete-connection.png)

1. Vælg **Slet** for at bekræfte, at du vil slette forbindelsen.

   ![Bekræftelse af sletning af forbindelse](media/add-manage-connections/delete-connection-confirmation.png)

Når du sletter en forbindelse, fjernes den fra både Power Apps og Power Automate.

## <a name="update-a-connection"></a>Opdatere en forbindelse

Du kan opdatere en forbindelse, der ikke virker, fordi dine kontooplysninger eller din adgangskode er blevet ændret.

1. Gå til **Data** > **Forbindelser**, og vælg derefter linket **Reparer forbindelsen** for den forbindelse, du vil opdatere.

   ![Vælg dette link for at rette forbindelsen](media/add-manage-connections/fix-connection-link.png)

1. Når du bliver bedt om det, skal du opdatere din forbindelse med nye legitimationsoplysninger.

Når du opdaterer en forbindelse, opdateres den både for Power Apps og Power Automate.

## <a name="troubleshoot-a-connection"></a>Fejlfinding af forbindelse

Afhængigt af organisationens politikker skal du muligvis bruge den samme konto for at logge på Power Automate og oprette en forbindelse til SharePoint, Office 365 eller OneDrive for Business.

Du kan f.eks. logge på Power Automate med *ditnavn@outlook.com*, men blive blokeret, når du forsøger at oprette forbindelse SharePoint med *ditnavn@contoso.com*. Du kan i stedet logge ind på Power Automate med *ditnavn@contoso.com*, og du kan oprette forbindelse til SharePoint.
