---
title: Opret et flow fra din telefon | Microsoft Docs
description: Opret et flow fra en skabelon, der f.eks. sender en pushmeddelelse, når du modtager en mail fra en angivet adresse
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 393ae5f6a86363610c26aea78a04748f34dc4f97
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193605"
---
# <a name="create-a-flow-from-your-phone-by-using-power-automate"></a>Opret et flow fra din telefon vha. Power Automate

Opret et flow fra din telefon ved hjælp af en skabelon, som du kan finde ved at søge på en liste over tjenester, gennemse kategorier eller angive nøgleord. Følg trinnene i dette emne for at oprette et flow, der sender en pushmeddelelse til din telefon, når du modtager en mail fra din chef.

Hvis du ikke er fortrolig med Power Automate, kan du [få vist en oversigt](getting-started.md).

## <a name="prerequisites"></a>Forudsætninger
* En [konto for Power Automate](sign-up-sign-in.md).
* Mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows) på en [understøttet enhed](getting-started.md#use-the-mobile-app). I grafikken til dette emne er iPhone-versionen af appen anvendt, men grænsefladen på en Android- eller Windows Phone-enhed ser ligesådan ud.
* Hvis du vil bruge den skabelon, der er demonstreret under dette emne, skal du også bruge:
  
  * Legitimationsoplysninger til Office 365.
  * Pushmeddelelser, der er aktiveret på telefonen.

## <a name="find-a-template"></a>Find en skabelon
1. Åbn mobilappen, og tryk derefter på **Gennemse** nederst i skærmbilledet.
   
    ![Ikonet for Gennemse](./media/mobile-create-flow/browse-icon.png)
   
    Du kan finde en skabelon på en af følgende måder:
   
   * Angiv et nøgleord i søgefeltet øverst i skærmbilledet.
   * Tryk på en indstilling på listen over tjenester.
   * Rul ned for at få vist en række kategorier, og tryk derefter på en skabelon i en vilkårlig kategori.
     
       ![Fanen Gennemse](./media/mobile-create-flow/browse-tab.png)
     
     I dette selvstudium skal du åbne den skabelon, der sender en pushmeddelelse, når du modtager en mail fra din chef.
2. Tryk på **Se alle** på listen over tjenester.
   
    ![Vis listen over tjenester](./media/mobile-create-flow/list-services.png)
3. Tryk på ikonet for **Pushmeddelelse**.
   
    ![Pushmeddelelser](./media/mobile-create-flow/push-notifications.png)
4. På søgelinjen skal du skrive **mail** og derefter trykke på skabelonen for at sende en pushmeddelelse, når du modtager en meddelelse fra din chef.
   
    ![Vælg skabelon](./media/mobile-create-flow/choose-template.png)
5. På skærmbilledet, der viser oplysninger om den valgte skabelon, skal du trykke på **Anvend denne skabelon**.
   
    ![Bekræft skabelon](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Afslut flowet
1. Hvis du bliver bedt om det, skal du trykke på **Log på** og angive dine legitimationsoplysninger til Office 365 Outlook, Office 365-brugere eller begge dele.
   
    ![Log på Office 365](./media/mobile-create-flow/office-signin.png)
   
    Du kan bruge de samme forbindelser, når du opretter andre flows.
2. Tryk på **Næste** i øverste højre hjørne.
   
    ![Tryk på Næste](./media/mobile-create-flow/next.png)
   
    På det næste skærmbillede vises den udløsende hændelse og alle de deraf følgende handlinger.
   
    ![Udløsende hændelse og handlinger](./media/mobile-create-flow/flow-structure.png)
   
    For denne skabelon udløser en ny mail flowet, der henter dine oplysninger (herunder din chefs adresse), og du får tilsendt en pushmeddelelse, når du modtager en mail fra den pågældende adresse. Nogle skabeloner kræver noget tilpasning, før de fungerer korrekt, men det er ikke tilfældet med denne skabelon.
3. (valgfrit) Næsten øverst i skærmbilledet skal du angive et andet navn for flowet.
   
    ![Omdøb flowet](./media/mobile-create-flow/rename-flow.png)
4. Tryk på **Opret** i øverste højre hjørne.
   
    ![Opret flow](./media/mobile-create-flow/create-flow.png)
   
    Dit flow er oprettet og søger efter mails fra din chef, indtil du stopper flowet midlertidigt eller sletter det.

## <a name="next-steps"></a>Næste trin
* [Overvåg din flowaktivitet](mobile-monitor-activity.md).
* [Administrer dine flows](mobile-manage-flows.md).

