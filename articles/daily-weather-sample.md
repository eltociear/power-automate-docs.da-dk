---
title: Eksempel med daglig vejrrapport i et adaptivt kort | Microsoft Docs
description: Et eksempel på oprettelse af et adaptivt kort til at sende en daglig vejropdatering til en Teams-kanal
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
ms.openlocfilehash: 8f7128104d3cb8aae361b6dd574822f503893e35
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868175"
---
# <a name="daily-weather-report-sample"></a>Eksempel på daglig vejrrapport

Eksemplet på den **daglige vejrrapport** er et adaptivt kort, der er designet til at blive brugt sammen med MSN Vejr for at poste en daglig vejropdatering på en Teams-kanal.

![](media/adaptive-cards/weather.png)

*Input/output og noter*

| Navn på dynamisk token     | Pladsholdertekst | Noter                                                                         |
|------------------------|------------------|--------------------------------------------------------------------------------|
| {acCityState}          | Se skabelon     | Vist tekst <br>  En variabel kan bruges til at indeholde værdierne by, stat eller postnummer                                                                   |
| {acDailySummary}       | Se skabelon     | Vist tekst                                                                   |
| {acCurrentDateTime}    | Se skabelon     | Vist tekst                                                                   |
| {acUrlConditionsImage} | Se skabelon     | Vist tekst  <br> Se kommentarer til skabelonen (skal erstattes med en gyldig URL-adresse)                                                                 |
| {acCurrentTemperature} | Se skabelon     | Vist tekst                                                                   |
| {actempHi}             | Se skabelon     | Vist tekst                                                                   |
| {actempHi}            | Se skabelon     | Vist tekst                                                                   |


``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "{acCity}, {acState}",
            "size": "Large",
            "isSubtle": true
        },
        {
            "type": "TextBlock",
            "text": "{acCurrentDateTime}",
            "spacing": "None"
        },
        {
            "type": "TextBlock",
            "text": "{acDailySummary}",
            "spacing": "None"
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "Image",
                            "url": "{acUrlConditionsImage}",
                            "size": "Large"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "{acCurrentTemperature}",
                            "size": "ExtraLarge",
                            "spacing": "None"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "°F",
                            "weight": "Bolder",
                            "spacing": "Small"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Hi {actempHi}",
                            "horizontalAlignment": "Left"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Lo {actempLow}",
                            "horizontalAlignment": "Left",
                            "spacing": "None"
                        }
                    ]
                }
            ]
        }
    ]
}
```
