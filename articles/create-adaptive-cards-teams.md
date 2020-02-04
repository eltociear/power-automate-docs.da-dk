---
title: Lær, hvordan du opretter flows, der sender tilpassede kort til Microsoft Teams | Microsoft Docs
description: Lær, hvordan du opretter flows, der sender indhold med omfattende formatering sammen med tilpassede kort til Microsoft Teams.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 3813b32ea50c9f91ff3ac3b620796983926d365e
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74362941"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Brug tilpassede kort i Microsoft Teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Du kan oprette et flow, der sender [tilpassede kort](https://adaptivecards.io) til en Microsoft Teams-kanal. Med tilpassede kort kan du bruge omfattende formatering til at gøre dine opslag tydeligere, interaktive og inspirerende. Tilpassede kort kan indeholde komponenter, som billeder, grafer, tekst med omfattende formatering og meget mere.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Opret et flow, der sender tilpassede kort til et team

Følg disse trin for at oprette et flow, der sender et tilpasset kort til den generelle kanal i teamet Strategi og planlægning. Det flow, vi opretter, bruger handlingen **Send dine egne tilpassede kort som Flow bot til en kanal (prøveversion)** til at sende det tilpassede korts indhold til teamets kanal ugentligt.

1. Log på Microsoft Teams.
1. Vælg ikonet **Teams** i navigationspanelet til venstre, og vælg derefter teamet **Strategi og planlægning**.

    ![Vælg teams](media/create-adaptive-cards-teams/select-teams-team.png)

1. Vælg fanen **Flow** øverst på skærmen.
1. Vælg ikonet **+** (Opret fra bunden).
1. Søg efter **gentagelser**, og vælg derefter udløseren **Gentagelse**.

    ![Gentagelseskort](media/create-adaptive-cards-teams/select-recurrence.png)

1. Angiv tidsplanen, som følger for at gentage hver uge på et tidspunkt og i en tidszone efter eget valg:
    
    ![Gentagelseskort](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Vælg **næste trin**.
1. Søg efter **tilpasset**, vælg **Microsoft Teams**, og vælg derefter den **Send dine egne tilpassede kort som Flow bot til en kanal (prøveversion)** .

   ![Tilpasset kort](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Udfyld oplysningerne i **Team**, **Kanal** og **Meddelelse** på kortet **Send dine egne tilpassede kort som Flow bot til en kanal (prøveversion)** for at angive det team og den kanal, det tilpassede kort **Meddelelse** sendes til.

   ![Tilpasset kort](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Du kan bruge dette eksempel på JSON-indhold til **Meddelelse**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Navngiv dit flow, og gem det.


## <a name="run-the-flow"></a>Kør flowet

Bemærk, at når gentagelsestiden er forløbet, sender flowet det tilpassede korts indhold til den teamkanal, du har defineret.

![Kør flowet](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Få mere at vide

- Kom i gang med [eksempler på tilpassede kort](https://adaptivecards.io/samples/).
- Opret [indhold til tilpassede kort](https://adaptivecards.io) på den nemme måde.



