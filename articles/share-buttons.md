---
title: Del dine knapper med andre. | Microsoft Docs
description: Del dine knapper med andre, så de kan bruge dine knapper og spare tid.
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3209748b03823add7622472665ce70b4cd581b1f
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74372739"
---
# <a name="share-button-flows-in-power-automate"></a>Del knapflow i Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
I mobilappen Power Automate kan du dele [knapflow](introduction-to-button-flows.md) (knapper) med andre brugere eller grupper i din organisation. Når du deler en knap, kan personen eller gruppen, du deler med, bruge din knap på samme måde, som de bruger deres egne knapper. Du kan også [dele et link](share-buttons.md#re-share-a-button) til knapper, en anden person har delt med dig. Du kan til enhver tid [stoppe med at dele](share-buttons.md#stop-sharing-a-button) dine knapper.

> De skærmbilleder, der er brugt i dette dokument, er taget fra en Android-enhed. Hvis du bruger en iPhone, kan billederne se anderledes ud, men funktionaliteten er den samme.
> 
> 

Benyt [disse trin](share-buttons.md#use-shared-buttons) for at bruge en knap, som andre deler med dig.

## <a name="prerequisites"></a>Forudsætninger
Hvis du vil dele knapper, har du brug for følgende:

* En konto, der har adgang til [Power Automate](https://flow.microsoft.com).
* Et flow, du kan dele.
* En mobilenhed med mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).
* En gruppe eller en bruger i din organisation, som du vil dele din knap med.

## <a name="share-a-button"></a>Del en knap
Du kan dele en knap fra fanen **Knapper** i mobilappen Power Automate.

1. Tryk på det lille ikon ud for den knap, du vil dele.
   
    ![knappen del](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Tryk på **Inviter andre** på siden **Knapbrugere**.
   
    ![knappen del](./media/share-buttons/share-button-flows-button-users.png)
3. Søg efter, og vælg derefter den gruppe eller person, som du vil dele knappen med.
   
    ![knappen del](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Tryk på **SEND** på siden **Inviter andre**.
   
    ![knappen del](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Tryk på **UDFØRT** på den side, der angiver, at delingshandlingen for knappen blev fuldført.
   
    ![knappen del](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Kræver, at brugerne anvender deres egne forbindelser
> [!NOTE]
> Når du deler en knap, kan du tillade, at personer, du deler knappen med, bruger alle forbindelser, som knappen bruger. Du kan også kræve, at de bruger deres egne forbindelser. Hvis du tillader, at andre bruger dine forbindelser, kan de ikke få adgang til legitimationsoplysningerne i din forbindelse eller bruge dem i andre flow.
> 
> 

Følg disse trin for at kræve, at personer, du deler dine knapper med, bruger deres egne forbindelser.

1. Vælg **ADMINISTRER FORBINDELSER** på det skærmbillede, der vises, umiddelbart efter du har delt en knap.
2. Vælg **REDIGER** på den knap, du vil administrere.
3. Vælg **Opgivet af bruger** eller din mailadresse.
   
    Dit valg indikerer, hvis forbindelser, der skal bruges i den delte knap.
   
    ![knappen del](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Du kan til enhver tid se eller ændre dit valg. Hvis du vil gøre dette, skal du vælge fanen **Flow** > det flow, du delte > **Brugere og forbindelser** > fanen **FORBINDELSER** > **REDIGER** på den knap, du vil administrere.
   
    ![knappen del](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Få vist listen over knapbrugere
Du kan få vist alle grupper eller brugere, som en knap deles med, ved at følge disse trin under fanen **Knapper**:

1. Tryk på det lille ikon ud for den knap, du er interesseret i.
2. På siden **Knapbrugere** kan du se alle grupper eller brugere, knappen er delt med.
   
    ![få vist knapbrugere](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Stop med at dele en knap
Du kan stoppe delingen af en knap ved at følge disse trin under fanen **Knapper**:

1. Tryk på det lille ikon ud for den knap, du ikke længere vil dele.
2. På siden **Knapbrugere** skal du trykke på den bruger eller gruppe, du vil stoppe deling af knappen med.
   
    ![stop med at dele knap](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Tryk på **Fjern bruger**, når brugerens side vises.
   
    ![stop med at dele knap](./media/share-buttons/share-button-flows-remove-user.png)
4. Vent på, at fjernelsen fuldføres. Bemærk, at listen **Knapbrugere** opdateres, og at den bruger eller gruppe, du har fjernet, ikke længere vises.
   
    ![stop med at dele knap](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Overvåg kørselshistorikken
Hele kørselshistorikken, herunder de kørsler, der er initieret af en person, som en knap er delt med, vises kun under fanen **Aktivitet** i knapopretterens Power Automate-mobilapp.

## <a name="use-shared-buttons"></a>Brug delte knapper
Før du kan køre en knap, som en person har delt med dig, skal du føje den til din fane **Knapper** på siden **Tilføj knapper**.

1. Tryk på **HENT FLERE** (eller banneret **Nye knapper er tilgængelige**, hvis det vises) på fanen **Knapper**.
   
    ![Ny knap, der deles med mig](./media/share-buttons/share-button-flows-banner.png)
2. Tryk på den knap, du vil bruge.
   
    Den knap, du har trykket på, føjes med det samme til fanen **Knapper** i appen Power Automate. Derefter kan du bruge knappen fra fanen **Knapper**, ligesom du bruger andre knapper, der er angivet der.
   
    ![Ny knap, der deles med mig](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Del en knap igen
Du kan dele et link til en knap, der er blevet delt med dig.

1. Vælg **...** ud for den knap, du vil dele.
2. Vælg **Link til deling af knappen**.
   
    ![link til at dele en knap igen](./media/share-buttons/re-share-button.png)
3. Vælg den app, du vil bruge til at dele knappen, og følg derefter trinnene til at sende knappen til den person, du vil dele den med.

## <a name="stop-using-a-shared-button"></a>Stop med at bruge en delt knap
Hvis du ikke længere vil bruge en knap, der er delt med dig, kan du fjerne den fra fanen **Knapper** ved at benytte følgende trin:

1. På fanen **Knapper** skal du trykke på **...** ud for den knap, du ikke længere vil bruge.
   
    ![fjern knap](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Tryk på **Fjern** på den viste menu.

Det var det. Knappen vises ikke længere under fanen **Knapper** i appen Power Automate.

> [!NOTE]
> Når du har fjernet en delt knap, kan du tilføje den igen ved at vælge **HENT FLERE** under fanen **Knapper**.
> 
> 

