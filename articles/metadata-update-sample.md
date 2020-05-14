---
title: Eksempel på opdateringskort for metadata til Adaptive kort | Microsoft Docs
description: Giv teammedlemmer eller kanaler besked om eller opdater dem med metadata, der er relateret til en post, en fil eller et emne.
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
ms.openlocfilehash: 902510ac5c2dd61fbcaae7c1dad771588e431873
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297643"
---
# <a name="metadata-update-card-sample"></a>Eksempel på opdateringskort for metadata

Eksemplet **Metadataopdatering** er et adaptivt kort, der er designet til at gøre det muligt for flowoprettere at give teammedlemmer eller kanaler besked om eller opdatere dem med metadata, der er relateret til en post, en fil eller et emne. Dette kort er et adaptivt kort, der kun er beregnet til visning. Inputfelter kan dog tilføjes, hvis en af *vent på svar*-handlingerne bruges til at oprette dem.

Dette kort består af tre afsnit:

1. Headerområdet for emnet med overskrift, underoverskrift og beskrivelse.
1. Faktalisteområdet for relevante metadata for posten.
1.  Et kolonnesæt, der understøtter en tabelmatrix af data

![Eksempel på metadata](media/adaptive-cards/metadata-sample.png) 


*Input/output og noter*

| Navn på dynamisk token (input) | Pladsholdertekst    | Noter                                     |
|-----------------------------|---------------------|--------------------------------------------|
| acHeader                    | {Header}            | Vist tekst                               |
| acSubHeader                 | {SubHeader}         | Vist tekst                               |
| acDescription               | Latinsk tekst          | Vist tekst                               |
| acFact1                     | {acFact1}           | Vist tekst                               |
| acFact2                     | {acFact2}           | Vist tekst                               |
| acFact3                     | {acFact3}           | Vist tekst                               |
| acColumnSetHeader           | Headers 1 til 3 | Vist tekst <br>  Vist tekst for header for kolonnesæt                               |
| acColumnSet                 | Kolonne 1 til 3 | Erstat med matrix- eller kolonneværdier.       |


``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Metadata Update Card",
            "weight": "bolder",
            "size": "large",
            "id": "acTitle"
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Sub Header Tag Line",
                            "weight": "Bolder",
                            "wrap": true,
                            "id": "acSubHeader"
                        }
                    ]
                }
            ]
        },
        {
            "type": "TextBlock",
            "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In condimentum leo lorem, at facilisis augue hendrerit eget. Praesent ut malesuada ipsum. Vivamus semper faucibus felis quis sagittis. Nunc pellentesque metus at nunc gravida, vitae volutpat sapien vehicula. Nulla lorem nibh, porttitor vel semper ut, ornare nec erat.",
            "wrap": true,
            "id": "acDescriptionArea"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "title": "Fact 1:",
                    "value": "{acFact1}"
                },
                {
                    "title": "Fact 2:",
                    "value": "{acFact2}"
                },
                {
                    "title": "Fact 3:",
                    "value": "{acFact3}"
                }
            ],
            "id": "acFactSet"
        },
        {
            "type": "Container",
            "spacing": "Large",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 1"
                                }
                            ],
                            "width": "stretch"
                        },
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 2"
                                }
                            ],
                            "width": "stretch"
                        },
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "weight": "Bolder",
                                    "text": "HEADER 3"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 1",
                            "wrap": true,
                            "id": "acCol1"
                        }
                    ],
                    "width": "stretch"
                },
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 2",
                            "wrap": true,
                            "id": "acCol2"
                        }
                    ],
                    "width": "stretch"
                },
                {
                    "type": "Column",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Column 3",
                            "wrap": true,
                            "id": "acCol4"
                        }
                    ],
                    "width": "stretch"
                }
            ],
            "$data": "acDataContext"
        }
    ],
    "bleed": true

}
```
