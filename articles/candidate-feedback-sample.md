---
title: Eksempel på kandidatfeedback | Microsoft Docs
description: Brug dette eksempel til at oprette et adaptivt kort for at indsamle feedback om jobkandidater.
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
ms.openlocfilehash: 8d2cbaa54d4256484bf8d17693e30aec85f2a4df
ms.sourcegitcommit: 89fca599830de21709b47087302a030d91e5fe29
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/10/2020
ms.locfileid: "3549722"
---
# <a name="candidate-feedback-sample"></a>Eksempel på kandidatfeedback

Eksemplet med en **formular til kandidatfeedback** er en inputformular i et adaptivt kort, der er designet til at indsamle feedback under et samtaleloop. Vi anbefaler, at du bruger den sammen med en knap for et delt øjeblikkeligt flow for at gøre det muligt for alle i teamet at give feedback omteam kandidater i løbet af et samtaleloop. Du kan udvide funktionen ved at registrere svar i en database eller andre ønskede datakilder for at understøtte disse ekstra muligheder:

-   Gør det lettere at gennemgå forslag til opfølgning inden næste session med kandidaten.
-   Gør det lettere at gennemgå aggregerede data, når alle svar er registreret.
-   Underrette den personaleansvarlige om stemmer for/imod en ansættelse, når processen er afsluttet

     ![Formular til kandidatfeedback](media/adaptive-cards/candidate-form.png)

*Input/output og noter*

| Navn på dynamisk token | Pladsholdertekst | Noter:              |
|--------------------|------------------|---------------------|
| {acFullName}       | {acFullName}     | Vis tekst        |
| {acComments}       | {acComments}     | Vis tekst        |
| {acDecision}       |                  | **Output** for svar |
| {acFollowUp}       |                  | **Output** for svar |

``` json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "id": "Title",
      "text": "CANDIDATE FEEDBACK FORM",
      "horizontalAlignment": "Left"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acFullName}",
      "style": "text",
      "isMultiline": false,
      "maxLength": 75,
      "id": "acFullName"
    },
    {
      "type": "Input.Text",
      "placeholder": "{acComments}",
      "style": "text",
      "isMultiline": true,
      "maxLength": 200,
      "id": "acComments"
    },
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "Decision",
      "horizontalAlignment": "Left",
      "separator": true
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acDecision",
      "value": "1",
      "choices": [
        {
          "title": "Hire",
          "value": "Hire"
        },
        {
          "title": "No Hire",
          "value": "No Hire"
        }
      ],
      "style": "expanded"
    },
    {
      "type": "TextBlock",
      "text": "Suggest follow-up discussion regarding:",
      "weight": "Bolder"
    },
    {
      "type": "Input.ChoiceSet",
      "id": "acFollowUp",
      "isMultiSelect": true,
      "value": "",
      "choices": [
        {
          "title": "Past experience in the topic area",
          "value": "Experience"
        },
        {
          "title": "Inclusive behaviors and work ethics",
          "value": "Inclusivity"
        },
        {
          "title": "Ability to work without supervision",
          "value": "Independent"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.Submit",
      "title": "Submit"
    }
  ]
}
```


