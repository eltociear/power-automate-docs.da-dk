---
title: Godkend anmodninger på en mobilenhed | Microsoft Docs
description: Brug en mobilenhed til at godkende anmodninger, der er oprettet i Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 513200d18ac2a845cd63a6d269513f3bcb45118c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193973"
---
# <a name="approve-requests-on-your-mobile-device-by-using-power-automate"></a>Godkend anmodninger på en mobilenhed vha. Power Automate

Hvis et flow identificerer dig som godkender, og du har installeret mobilappen til Power Automate, modtager du en pushmeddelelse, når der anmodes om din godkendelse.

Denne artikel fører dig gennem nogle almindelige scenarier, som med stor sandsynlighed vil opstå, når du administrerer godkendelsesanmodninger i mobilappen til Power Automate.

> [!NOTE]
> Billederne i dette emne kommer fra en Android-enhed; slutbrugerens oplevelse i iOS ligner dog denne.
> 
> 

## <a name="prerequisites"></a>Forudsætninger
Hvis du vil fuldføre denne gennemgang, skal du:

* Bruge en [Android](https://aka.ms/flowmobiledocsandroid)- eller [iOS](https://aka.ms/flowmobiledocsios)-enhed, der kører mobilappen til Power Automate.
* Være udpeget som godkender i et godkendelsesflow.
* Have ventende godkendelsesanmodninger.

## <a name="view-pending-requests"></a>Få vist ventende anmodninger
1. Åbne mobilappen til Power Automate.
   
    ![åbn mobilappen](./media/mobile-approvals/open-app.png)
2. Vælg **GODKENDELSER** i øverste højre hjørne.
   
    ![vælg godkendelser](./media/mobile-approvals/select-approvals.png)
3. få vist alle ventende godkendelser:
   
    ![få vist ventende godkendelsesanmodninger](./media/mobile-approvals/show-pending-approval-requests.png)

Hvis du ikke har nogen ventende godkendelsesanmodninger, kan du oprette et [godkendelsesflow](modern-approvals.md), angive dig selv som godkender og derefter udløse flowet. Godkendelsesanmodninger vises i godkendelsescenteret et par sekunder efter, at flowet udløses og sender en godkendelsesanmodning.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Godkend anmodninger, og angiv evt. en kommentar
1. Hvis du ikke har gjort det, skal du benytte de foregående trin til at [få vist ventende anmodninger](mobile-approvals.md#view-pending-requests).
2. Vælg **GODKEND** på den anmodning, du vil godkende.
   
    ![vælg godkend](./media/mobile-approvals/select-approve.png)
3. (Valgfrit) vælg **Tilføj kommentar (valgfrit)** .
   
    ![vælg Tilføj en kommentar](./media/mobile-approvals/select-add-comment.png)
   
    Angiv en kommentar på skærmen **Tilføj kommentar**.
   
    ![angiv din kommentar](./media/mobile-approvals/enter-comment-for-approval.png)
4. Vælg **BEKRÆFT** i øverste højre hjørne.
   
    ![bekræft, at du er færdig](./media/mobile-approvals/tap-confirm-button.png)
   
    Skærmbilledet for vellykket godkendelse vises, når flowet registrerer beslutningen.
   
    ![Skærmbillede for vellykket godkendelse](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Afvis anmodninger, og angiv evt. en kommentar
Følg [trinnene for at godkende en anmodning](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), men vælg **AFVIS** i andet trin.

## <a name="learn-more"></a>Få mere at vide
[Opret moderne godkendelsesflows](modern-approvals.md).

