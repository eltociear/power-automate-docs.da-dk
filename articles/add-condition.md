---
title: Føj en betingelse til et flow | Microsoft Docs
description: Angiv, at et flow kun skal udføre en eller flere opgaver, hvis en betingelse er sand.
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
ms.date: 06/08/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c717bfcb10fdae3da5d1a3642ece503ad3de4389
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/08/2020
ms.locfileid: "3434986"
---
# <a name="add-a-condition-to-a-flow"></a>Føj en betingelse til et flow


Angiv, at et flow kun skal udføre en eller flere opgaver, hvis en betingelse er sand. Angiv f.eks., at du kun skal have en mail, hvis et tweet, der indeholder et nøgleord, retweetes mindst ti gange.

## <a name="prerequisites"></a>Forudsætninger

* [Opret et flow](get-started-logic-template.md) fra en skabelon – dette selvstudium [bruger denne skabelon](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) som eksempel

## <a name="add-a-condition"></a>Tilføj en betingelse

1. Vælg **Mine flow** i [Power Automate](https://flow.microsoft.com).

    Du skal muligvis logge på, hvis du ikke allerede er logget på.

1. Vælg et flow i **Mine flow**, og vælg derefter **Flere kommandoer** (de tre punktummer).

   ![Vælg Rediger](./media/add-condition/select-edit.png)

    Dette selvstudium bruger et eksempel med en Twitter-udløser og en SharePoint-handling.

1. Vælg **Rediger**.

1. Vælg **Nyt trin** > **Betingelse** under den sidste handling.

1. Vælg et tomt område i feltet til venstre på kortet **Betingelse**.

    Listen **Dynamisk indhold** åbnes.

1. Markér parameteren **Antal retweet** for at føje den til feltet.

1. I feltet midt på kortet **Betingelse** skal du vælge **er større end eller lig med**.

1. Angiv **10** i feltet til højre.

    ![Feltet OBJEKTNAVN med en parameter i](./media/add-condition/specify-condition.png)

    Nu, hvor du har konfigureret betingelsen, skal du fortsætte med følgende trin for at sende en mail, hvis **Antal retweet** er større end 10.

1. Vælg **Tilføj en handling** for **Hvis ja** på sendebetingelsen. 
1. Angiv **Send en mail** i søgefeltet, og vælg derefter **Send en mail (V2)**.

   ![Søg for at sende en mail](./media/add-condition/if-yes-condition.png)

1. Konfigurer kortet **Send en mail (V2)** efter behov, og angiv indholdet af den mail, som flowet sender, hvis **Antal retweet** er større end 10.

   Du kan også konfigurere **Hvis nej** for betingelsen, hvis du vil udføre en handling, når **Antal retweet** er mindre end 10.

1. Gem processen.

>[!TIP]
>Du kan oprette komplekse betingelser ved hjælp af knappen **Tilføj** på betingelseskortet.

![Tilføje komplekse betingelser](./media/add-condition/add-complex-condition.png)

Du kan bruge et hvilket som helst udtryk fra *WDL (Workflow Definition Language)* i avanceret tilstand. Få mere at vide om alle de tilgængelige [udtryk](https://msdn.microsoft.com/library/azure/mt643789.aspx).

## <a name="next-steps"></a>Næste trin

Få mere at vide om, hvordan du [bruger udtryk](use-expressions-in-conditions.md) i betingelser i avanceret tilstand.
