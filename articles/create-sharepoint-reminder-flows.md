---
title: Opret et påmindelsesflow for SharePoint-elementer | Microsoft Docs
description: Opret flows, der minder dig om forfaldsdatoer for SharePoint-elementer.
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
ms.date: 04/06/2020
ms.author: deonhe
ms.openlocfilehash: b5930ca6fa663d92497ec48b3cc6220d8c891d44
ms.sourcegitcommit: 71f9b72d551887324c92b122dadd1b4dd584bc4b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/23/2020
ms.locfileid: "3299271"
---
# <a name="sharepoint-remind-me"></a>Påmind mig i SharePoint


Med SharePoint-lister og -biblioteker kan du definere brugerdefinerede metadatakolonner til sporing af datoer. Med Power Automates integration med SharePoint kan du nemt oprette påmindelsesflows ud fra DateTime-kolonner i SharePoint. Med påmindelsesflows modtager du en personlig advarsel via mail et forudbestemt antal dage før en dato i et dokument eller element i SharePoint.

## <a name="prerequisites"></a>Forudsætninger
- Adgang til Microsoft SharePoint Online.
- En SharePoint-liste eller et bibliotek med en DateTime-kolonne.
- Adgang til Power Automate.

## <a name="create-a-reminder-flow"></a>Opret et påmindelsesflow

 1. Opret en [SharePoint-liste](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) med mindst én DateTime-kolonne i den aktuelle visning. 
 1. Vælg **Automate** > **Angiv en påmindelse** > **Dato for deaktivering** (dette er kolonnen med datetime for påmindelsen).

     ![Vælg et påmindelsesflow](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Du kan eventuelt få brug for at logge på de tjenester, som denne Power Automate-skabelon bruger.
     
1. Vælg **Fortsæt**.

1. Angiv et **flownavn** og antallet af dage før datetime-kolonneposten, hvor du vil modtage påmindelsen på kortet **Angiv en påmindelse**.

    ![Angiv oplysninger om påmindelsesflow](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Vælg **Opret** på kortet **Angiv en påmindelse**.

1. Du modtager følgende meddelelse, der angiver, at flowet blev oprettet:

    ![Påmindelsesflow blev oprettet](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Bekræft modtagne påmindelser

Du modtager en påmindelse via mail, der er baseret på posten **Mind mig om dette mange dage i forvejen**, som du oprettede i flowet **Angiv en påmindelse**, som du har oprettet tidligere. 

## <a name="edit-your-flow"></a>Rediger dit flow

Påmindelsesflowet er som ethvert andet flow, så du kan få adgang til og redigere det via [Power Automate](https://flow.microsoft.com).

## <a name="learn-more"></a>Få mere at vide

- Introduktion til [Power Automate](https://flow.microsoft.com).
- Angiv et [påmindelsesflow](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) i SharePoint.


