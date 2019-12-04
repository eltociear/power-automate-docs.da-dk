---
title: Opret et påmindelsesflow for SharePoint-elementer | Microsoft Docs
description: Opret flow, der minder dig om forfaldsdatoer for SharePoint-elementer.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: 09ee39c918bb35721ee77a7cdcd432755ccfa8c4
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74361998"
---
# <a name="sharepoint-remind-me"></a>SharePoint-påmindelser
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Med SharePoint-lister og -biblioteker kan du definere brugerdefinerede metadatakolonner til at spore datoer. Med Power Automates integration med SharePoint kan du nemt oprette påmindelsesflow på basis af datetime-kolonner i SharePoint. Med påmindelsesflow modtager du en personlig underretning via mail med et forudbestemt antal dage forud for en dato i et dokument eller element i SharePoint.

## <a name="prerequisites"></a>Forudsætninger
- Adgang til Microsoft SharePoint Online.
- En SharePoint-liste eller et bibliotek med en datetime-kolonne.
- Adgang til Power Automate.

## <a name="create-a-reminder-flow"></a>Opret et påmindelsesflow

 1. Opret en [SharePoint-liste](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) med mindst én datetime-kolonne i den aktuelle visning. 
 1. Vælg **Flow** > **Angiv en påmindelse** > **Dato for deaktivering** (dette er kolonnen med datetime for påmindelsen).

     ![Vælg et påmindelsesflow](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Angiv et **flownavn** og antallet af dage før datetime-kolonneposten, hvor du vil modtage påmindelsen på kortet **Angiv en påmindelse**.

    ![Angiv oplysninger om påmindelsesflow](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Vælg **Opret** på kortet **Angiv en påmindelse**.

1. Du modtager følgende meddelelse, der angiver, at flowet blev oprettet:

    ![Påmindelsesflow blev oprettet](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Bekræft modtagne påmindelser

Du modtager en påmindelse via mail, der er baseret på posten **Mind mig om dette mange dage i forvejen**, som du oprettede i flowet **Angiv en påmindelse**, som du har oprettet tidligere. 

## <a name="edit-your-flow"></a>Rediger dit flow

Påmindelsesflowet er ligesom ethvert andet flow, så du kan få adgang til og redigere det via [Power Automate](https://flow.microsoft.com).

## <a name="learn-more"></a>Få mere at vide

- Kom i gang med [Power Automate](https://flow.microsoft.com).
- Angiv et [påmindelsesflow](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) i SharePoint.


