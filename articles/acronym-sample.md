---
title: Eksempel på akronymformular til Adaptive kort | Microsoft Docs
description: Opret et adaptivt kort, der indsamler akronymer og gemmer dem i Common Data Service.
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
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: b1ecc0240dba1866ea3468647d06637397d73170
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296499"
---
# <a name="acronyms-form-sample"></a>Eksempel på akronymformular

Eksemplet på **akronymformularen** er en inputformular til Adaptive kort, som er designet til at indsamle akronymer og gemme dem i Common Data Service. Der kan forespørges efter disse akronymer alle steder fra på grund af den løbende dataindsamling.

![Logføring af akronymer](media/adaptive-cards/acronym-logger.png)

*Input/output og noter*

| Navn på dynamisk token | Pladsholdertekst                        | Noter:              |
|--------------------|-----------------------------------------|---------------------|
| {acAcronym}        | Angiv forkortelsen for akronymet  | Svar**output** |
| {acDefinition}     | Angiv en definition af ovenstående akronym | Svar**output** |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Acronym Logger",
            "id": "Title",
            "spacing": "Medium",
            "horizontalAlignment": "Center",
            "size": "ExtraLarge",
            "weight": "Bolder",
            "color": "Accent"
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Acronym",
                    "wrap": true,
                    "spacing": "Medium"
                },
                {
                    "type": "Input.Text",
                    "id": "acAcronym",
                    "placeholder": "Enter the abbreviation for the acronym"
                },
                {
                    "type": "TextBlock",
                    "text": "Definition",
                    "wrap": true
                },
                {
                    "type": "Input.Text",
                    "placeholder": "Enter a definition of the acronym above",
                    "id": "acDefinition",
                    "isMultiline": true
                }
            ]
        }
    ],
    "actions": [
        {
            "type": "Action.Submit",
            "title": "Submit",            "id": "btnSubmit"
        }
    ]
}

```