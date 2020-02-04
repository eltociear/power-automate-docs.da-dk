---
title: Få mere at vide om oprettelse af forbindelse til dine data ved hjælp af forbindelser og datagateways i det lokale miljø | Microsoft Docs
description: Tilføj eller administrer forbindelser til SharePoint, SQL Server, OneDrive for Business, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drev med mere
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2e46711637497120872848f239d59651ab875d5
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74358088"
---
# <a name="manage-connections-in-power-automate"></a>Administrer forbindelser i Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Hvis du opretter en forbindelse i Power Automate, kan du nemt få adgang til dine data, mens du bygger et flow. Power Automate indeholder almindeligt anvendte forbindelser, herunder SharePoint, SQL Server, Office 365, OneDrive for Business, Salesforce, Excel, Dropbox, Twitter m.m. Forbindelser deles med Power Apps, så når du opretter en forbindelse i ét produkt, viser forbindelsen sig i det andet.

Du kan f.eks. bruge en forbindelse til udføre disse opgaver:

* opdatere en SharePoint-liste.
* hente data fra en Excel-fil i din OneDrive for Business- eller Dropbox-konto.
* sende mail i Office 365.
* sende et tweet.

Du kan oprette en forbindelse i flere forskellige scenarier, såsom:

* oprette et [flow vha. en skabelon](get-started-logic-template.md)
* oprette et [flow fra bunden](get-started-logic-flow.md) eller opdatere et eksisterende flow
* oprette en forbindelse direkte på [Power Automate-webstedet][1]

I dette emne vises, hvordan du kan administrere forbindelser på [Power Automate-webstedet][1].

## <a name="add-a-connection"></a>Opret en forbindelse
1. På [Power Automate-webstedet][1] skal du logge på med din arbejds- eller organisationskonto.
2. Vælg gearikonet i det øverste højre hjørne, og vælg derefter **Forbindelser**.
   
    ![Vælg Forbindelser](./media/add-manage-connections/connections-menu.png)
3. Vælg **Opret forbindelse**.
4. På listen over **tilgængelige forbindelser** skal du vælge den forbindelse, du vil oprette, f.eks. SharePoint.
5. Vælg knappen **Opret forbindelse**, og indtast derefter dine legitimationsoplysninger for at oprette forbindelsen.

Når forbindelsen er oprettet, angives den under **Mine forbindelser**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Opret forbindelse til dine data via en datagateway i det lokale miljø
Fra og med denne skrivelse understøtter SQL Server og SharePoint Server datagateways i det lokale miljø. Sådan opretter du en forbindelse, der bruger en gateway:

1. Følg fremgangsmåden, der er angivet tidligere under dette emne, for at tilføje en forbindelse.
2. På listen over **tilgængelige forbindelser** skal du vælge **SQL Server** og derefter markere afkrydsningsfeltet **Opret forbindelse via datagateway i det lokale miljø**.
   
    ![Vælg gateway](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Microsoft SharePoint-datagateways understøtter HTTP-trafik, men ikke HTTPS-trafik.
   > 
   > 
3. Angiv forbindelsens legitimationsoplysninger, og vælg derefter den gateway, du vil bruge.
   
    Du kan få flere oplysninger under [Administrer gateways](gateway-manage.md) og [Om gateways](gateway-reference.md).
   
    Når forbindelsen er oprettet, angives den under **Mine forbindelser**.

## <a name="delete-a-connection"></a>Slet en forbindelse
1. Gå til siden **Mine forbindelser**, og vælg derefter skraldespandsikonet for den forbindelse, du vil slette.
   
    ![Slet forbindelse](./media/add-manage-connections/delete-connection.png)
2. Vælg **OK** for at bekræfte, at du vil slette forbindelsen.
   
    ![Bekræft sletning](./media/add-manage-connections/delete-confirmation.png)

Når du sletter en forbindelse, fjernes den fra både Power Apps og Power Automate.

## <a name="update-a-connection"></a>Opdater en forbindelse
Du kan opdatere en forbindelse, der ikke virker, fordi dine kontooplysninger eller din adgangskode er blevet ændret.

1. På siden **Forbindelser** skal du vælge linket **Bekræft adgangskode** for den forbindelse, du vil opdatere.
   
    ![Bekræft adgangskode](./media/add-manage-connections/verify-password.png)
2. Når du bliver bedt om det, skal du opdatere din forbindelse med nye legitimationsoplysninger.

Når du opdaterer en forbindelse, opdateres den for både Power Apps og Power Automate.

## <a name="troubleshoot-a-connection"></a>Fejlfinding af forbindelse
Afhængigt af organisationens politikker skal du muligvis bruge den samme konto for at logge på Power Automate og oprette en forbindelse til SharePoint, Office 365 eller OneDrive for Business.

Du får f.eks. tilladelse til at logge på Power Automate med *yourname@outlook.com* , men blokeres, når du forsøger at oprette forbindelse til SharePoint med *yourname@contoso.com* . Du kan i stedet logge på Power Automate med *yourname@contoso.com* , og så kan du oprette forbindelse til SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
