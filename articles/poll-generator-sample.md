---
title: Eksempel på afstemningsgenerator | Microsoft Docs
description: En inputformular i et adaptivt kort, der er designet til at sende afstemninger til Microsoft Teams.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b19a5b58db4680786ade089731846f0f8000d164
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297291"
---
# <a name="create-a-poll-sample"></a>Opret et eksempel på en afstemning

Eksemplet på **opret en afstemning** er en inputformular i et adaptivt kort, der er designet til at sende afstemninger til Microsoft Teams. Erstat den viste tekst på dette kort for at tilpasse den til afstemningen. Dette adaptive kort gør det muligt for dig at følge forskellige beslutningsstier, afhængigt af de svar, der angives i afstemningsværdierne, eller antallet af stemmer for kortforbrugerne.

![Eksempel på afstemning](media/adaptive-cards/poll.png)

*Input/output og noter*

| Navn på dynamisk token | Pladsholdertekst | Noter:                                            |
|--------------------|------------------|---------------------------------------------------|
| Titel              |                  | Vist tekst                                      |
| acHeaderTagLine    |                  | Vist tekst                                      |
| acHeader           |                  | Vist tekst                                      |
| acPollQuestion     |                  | Vist tekst                                      |
| acPollChoices      |                  | Svar**output**  <br> Enkelt valg som alternativknapper|

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Poll Request",
            "id": "Title",
            "spacing": "Medium",
            "horizontalAlignment": "Center",
            "size": "ExtraLarge",
            "weight": "Bolder",
            "color": "Accent"
        },
        {
            "type": "TextBlock",
            "text": "Header Tagline Text",
            "id": "acHeaderTagLine",
            "separator": true
        },
        {
            "type": "TextBlock",
            "text": "Poll Header",
            "weight": "Bolder",
            "size": "ExtraLarge",
            "spacing": "None",
            "id": "acHeader"
        },
        {
            "type": "TextBlock",
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vestibulum lorem eget neque sollicitudin, quis malesuada felis ultrices. ",
            "id": "acInstructions",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "Poll Question",
            "id": "acPollQuestion"
        },
        {
            "type": "Input.ChoiceSet",
            "placeholder": "Select from these choices",
            "choices": [
                {
                    "title": "Choice 1",
                    "value": "Choice 1"
                },
                {
                    "title": "Choice 2",
                    "value": "Choice 2"
                },
                {
                    "title": "Choice 3",
                    "value": "Choice 3"
                }
            ],
            "id": "acPollChoices",
            "style": "expanded"
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit",
            "id": "btnSubmit"
        }
    ]
}
```


