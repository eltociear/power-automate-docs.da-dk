---
title: Se kørslen af et flow | Microsoft Docs
description: Få vist input og output for hvert hver trin i et flow for at bekræfte, at det fungerer som forventet.
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
ms.date: 02/05/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 97fa3091a75abcec80dac594e4146283ae6310f0
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296521"
---
# <a name="watch-your-flows-in-action"></a>Se dine flows i aktion


>[!VIDEO https://www.youtube.com/embed/3wPoUCGm7Yg]

Hvis du vil sikre dig, at dine flows fungerer som forventet, skal du aktivere udløseren og derefter gennemgå de input og output, der genereres for hvert trin i flowet.

1. Opret eller opdater et flow, og lad derefter designeren være åben, efter du har valgt **Opret flow** eller **Opdater flow**.

     Du kan f.eks. [oprette et flow](get-started-logic-flow.md), der sender mails, når nogen tweeter ved hjælp af hashtagget **#azure**.
1. Udfør starthandlingen for dit flow.

    Send f.eks. et tweet, der indeholder hashtagget **#azure**.

    Starthandlingen og hvert af de efterfølgende trin angiver, om handlingen lykkedes, og hvor lang tid den tog.

    ![Billede af en vellykket kørsel](./media/see-a-flow-run/successful-flow-run.png)
1. Vælg udløseren eller handlingen for at få vist de relaterede input og output.

    ![Billede af en vellykket kørsel med udvidede kort](./media/see-a-flow-run/successful-flow-expanded-cards.png)
1. Vælg **Rediger flow** for at foretage flere ændringer, eller vælg **Udført**, hvis flowet fungerer som forventet.
