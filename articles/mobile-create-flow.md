---
title: Opret et flow fra din telefon | Microsoft Docs
description: Opret et flow fra en skabelon, der f.eks. sender en pushmeddelelse, når du modtager en mail fra en angivet adresse
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2020
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4b0dfb8efd5781e67f569bafddbf223ba2105f7e
ms.sourcegitcommit: 772a71443a19ce3da5e02470eda849762ad83671
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/18/2020
ms.locfileid: "3821001"
---
# <a name="create-a-flow-from-your-phone-by-using-power-automate"></a>Opret et flow fra din telefon ved hjælp af Power Automate

Opret et flow fra din telefon ved hjælp af en skabelon, som du kan finde ved at søge på en liste over tjenester, gennemse kategorier eller angive nøgleord.

Følg trinnene i dette emne for at oprette et flow, der sender en pushmeddelelse til din telefon, når du modtager en mail fra din chef.

Hvis du ikke kender Power Automate, kan du [få vist en oversigt](getting-started.md).

## <a name="prerequisites"></a>Forudsætninger
* En [konto til Power Automate](sign-up-sign-in.md).
* Mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows) på en [understøttet enhed](getting-started.md#use-the-mobile-app). I grafikken til dette emne er iPhone-versionen af appen anvendt, men grænsefladen på en Android- eller Windows Phone-enhed ser ligesådan ud.
* Hvis du vil bruge den skabelon, der er demonstreret under dette emne, skal du også bruge:
  
  * Legitimationsoplysninger for Office 365.
  * Pushmeddelelser, der er aktiveret på telefonen.

## <a name="find-a-template"></a>Find en skabelon
1. Åbn mobilappen, og tryk derefter på **Gennemse** nederst i skærmbilledet.
   
    ![Ikonet Søg](./media/mobile-create-flow/browse-icon.png)
   
    Du kan finde en skabelon på en af følgende måder:
   
   * Angiv et nøgleord i søgefeltet øverst i skærmbilledet.
   * Tryk på en indstilling på listen over tjenester.
   * Rul ned for at få vist en række kategorier, og tryk derefter på en skabelon i en vilkårlig kategori.
     
  
       ![Fanen Gennemse](./media/mobile-create-flow/browse-tab.png)
     
     I dette selvstudium skal du åbne den skabelon, der sender en pushmeddelelse, når du modtager en mail fra din chef.
1. Tryk på **Se alle** på listen over tjenester.
   

    ![Vis listen over tjenester](./media/mobile-create-flow/list-services.png)
1. Tryk på serviceikonet **Meddelelser**.
    
    ![Pushmeddelelser](./media/mobile-create-flow/push-notifications.png)
1. På søgelinjen skal du skrive **chef** og derefter trykke på skabelonen for at sende en pushmeddelelse, når du modtager en meddelelse fra din chef.
   
  
    ![Vælg en skabelon](./media/mobile-create-flow/choose-template.png)
1. På skærmbilledet, der viser oplysninger om den valgte skabelon, skal du trykke på **Anvend denne skabelon**.
   
    ![Bekræft skabelon](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Afslut flowet
1. Hvis du bliver bedt om det, skal du trykke på **Log på** og angive dine legitimationsoplysninger til Office 365 Outlook, Office 365-brugere eller begge dele.
   
    ![Log på Office 365](./media/mobile-create-flow/office-signin.png)
   
    >[!TIP]
    >Du kan bruge de samme forbindelser, når du opretter andre flows.

1. Tryk på **Opret** i øverste højre hjørne.
   
    ![Tryk på Opret](./media/mobile-create-flow/create.png)

      
    Dit flow oprettes og søger efter mail fra din chef, indtil du stopper flowet midlertidigt eller sletter det.

    ![Fuldført flow](./media/mobile-create-flow/success.png)

## <a name="next-steps"></a>Næste trin
* [Overvåg din flowaktivitet](mobile-monitor-activity.md).
* [Administrer dine flows](mobile-manage-flows.md).

