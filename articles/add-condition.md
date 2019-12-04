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
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b842fa3cd4f7f8e3a1460f345a17ec805a7acb00
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74355282"
---
# <a name="add-a-condition-to-a-flow"></a>Føj en betingelse til et flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Angiv, at et flow kun skal udføre en eller flere opgaver, hvis en betingelse er sand. Angiv f.eks., at du kun skal have en mail, hvis en tweet, der indeholder et nøgleord, videresendes mindst ti gange.

## <a name="prerequisites"></a>Forudsætninger

* [Opret et flow](get-started-logic-template.md) fra en skabelon – dette selvstudium [bruger denne skabelon](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) som eksempel

## <a name="add-a-condition"></a>Tilføj en betingelse

1. I [Power Automate](https://flow.microsoft.com) skal du vælge **Mine flow** på den øverste navigationslinje.

    Du skal muligvis logge på, hvis du ikke allerede er logget på.

1. Vælg et af de flow, du har oprettet, på listen over flow.

    Dette selvstudium bruger et eksempel med en Twitter-udløser og en SharePoint-handling.

1. Vælg **Rediger flow**.

1. Vælg **Nyt trin** under den sidste handling.

1. Vælg **Tilføj en betingelse**.

    ![Betingelsesknap](./media/add-condition/add-condition.png)

1. Vælg et tomt område i feltet til venstre på kortet **Betingelse**.

    Listen **Dynamisk indhold** åbnes.

1. Markér parameteren **Antal retweet** for at føje den til feltet.

1. I feltet midt på kortet **Betingelse** skal du vælge **er større end eller lig med**.

1. Angiv **10** i feltet til højre.

    ![Felet OBJEKTNAVN med en parameter i](./media/add-condition/specify-condition.png)

1. Markér overskriften for den handling, du vil bruge inde i betingelsen (f.eks **Opret vare**), og træk den hen under teksten **Hvis ja**.

    Når du slipper markøren, flyttes handlingen ind i det pågældende felt.

    ![Træk handling](./media/add-condition/drag-action.png)

1. Konfigurer handlingen efter behov.

1. Gem flowet.

## <a name="edit-in-advanced-mode"></a>Rediger i avanceret tilstand

Du kan også markere **Rediger i avanceret tilstand** for at skrive mere avancerede betingelser. Du kan bruge et hvilket som helst udtryk fra *WDL (Workflow Definition Language)* i avanceret tilstand. Få mere at vide om alle tilgængelige [udtryk](https://msdn.microsoft.com/library/azure/mt643789.aspx).

## <a name="next-steps"></a>Næste trin

Få mere at vide om, hvordan du [bruger udtryk](use-expressions-in-conditions.md) i betingelser i avanceret tilstand.
