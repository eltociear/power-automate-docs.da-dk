---
title: Eksempel på indsamling af kundeemner | Microsoft Docs
description: Opret et adaptivt kort til indsamling af kundeemner fra de personer, der er interesserede i et sæt produkter.
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
ms.openlocfilehash: 6ec875a8a3bf682b7a3d9b44a0cc1d3624bf7a70
ms.sourcegitcommit: 0761c15339ba3de6036f7fe5251aa8ad9173ee8b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902211"
---
# <a name="lead-collection-sample"></a>Eksempel på indsamling af kundeemner

Eksemplet på **indsamling af kundeemner** er en inputformular i et adaptivt kort, der er designet til at indsamle kundeemner fra alle, der kommer i kontakt med personer, der er interesserede i et sæt produkter. Du er velkommen til at ændre valgene for produkterne, men husk, at hvert valg kan have vist tekst samt en intern værdi, der er outputtet, når nogen har indsendt kortet (de kan også være de samme som dem, der vises i afsnittet med eksempelkode).

![](media/adaptive-cards/lead-notification.png)

*Input/output og noter:*

| Navn på dynamisk token    | Pladsholdertekst       | Noter                                                                                       |
|-----------------------|------------------------|--------------------------------------|
| Titel                 |                        | Vist tekst                                                                                  |
| acInstructions        |                        | Vist tekst                                                                                  |
| acLeadFName           | {firstName}            | Svar**output**                                                                           |
| acLeadFName           | {lastName}             | Svar**output**                                                                           |
| acLeadEmail           | {emailAddress}         | Svar**output**                                                                           |
| acLeadPrimaryPhone    | {primaryPhone10digits} | Svar**output**                                                                           |
| acLeadProductInterest | {productInterests}     | Svar**output**  <br>Som værdier med flere markeringer, hvor hvert enkelt valg er adskilt med et komma.                                                                         |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": 2,
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Lead Notification",
                            "weight": "Bolder",
                            "id": "Title",
                            "size": "ExtraLarge"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Please fill out a single form for each individual expressing interest in our products. ",
                            "isSubtle": true,
                            "wrap": true,
                            "id": "acInstructions",
                            "size": "Large"
                        }
                    ]
                }
            ]
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Potential Customer FIRST NAME",
                    "wrap": true,
                    "size": "Medium"
                }
            ]
        },
        {
            "type": "Input.Text",
            "id": "acLeadFName",
            "placeholder": "{firstName}"
        },
        {
            "type": "TextBlock",
            "text": "Potential Customer LAST NAME",
            "wrap": true
        },
        {
            "type": "Input.Text",
            "id": "acLeadLName",
            "placeholder": "{lastName}"
        },
        {
            "type": "TextBlock",
            "text": "Corporate email",
            "wrap": true
        },
        {
            "type": "Input.Text",
            "id": "acLeadEmail",
            "placeholder": "{emailAddress}",
            "style": "Email"
        },
        {
            "type": "TextBlock",
            "text": "Business Phone Number"
        },
        {
            "type": "Input.Text",
            "id": "acLeadPrimaryPhone",
            "placeholder": "{primaryPhone10digits}",
            "style": "Tel"
        },
        {
            "type": "RichTextBlock",
            "inlines": [
                {
                    "type": "TextRun",
                    "text": "{productInterests}"
                }
            ]
        },
        {
            "type": "Input.ChoiceSet",
            "placeholder": "Placeholder text",
            "choices": [
                {
                    "title": "Office 365",
                    "value": "Office 365"
                },
                {
                    "title": "Dynamics 365",
                    "value": "Dynamics 365"
                },
                {
                    "title": "Azure Services",
                    "value": "Azure Services"
                },
                {
                    "title": "Power Platform",
                    "value": "Power Platform"
                }
            ],
            "style": "expanded",
            "id": "acLeadProductInterest",
            "isMultiSelect": true
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


