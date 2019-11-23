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
ms.openlocfilehash: 5d38ee4df1e1edb16b86c402e77ce43ff659dc64
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74373567"
---
# <a name="watch-your-flows-in-action"></a>Se dine flows i aktion
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

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
