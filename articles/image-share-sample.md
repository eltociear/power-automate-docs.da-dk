---
title: Eksempel på billeddeling til deling af billeder | Microsoft Docs
description: Få mere at vide om, hvordan du opretter et adaptivt kort til deling af billeder.
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
ms.openlocfilehash: c804a65eee3b217dd2b6d66d54c7e39d87ef0eae
ms.sourcegitcommit: 3f582a1e462124d44f63cef7d450fc94be148f3b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2020
ms.locfileid: "3372778"
---
# <a name="image-share-sample"></a>Eksempel på billeddeling 

Eksemplet på **Billeddelingsformular** er et adaptivt kort, der er designet til deling af fotos, der er blevet sendt til SharePoint, og som kan være en afhængighed for en proces, der skal udføres (f.eks. processer, der er relateret til inspektion, overholdelse og overvågning). Dette kort er et adaptivt kort, der kun er beregnet til visning.

![Et adaptivt kort, der kun er beregnet til visning](media/adaptive-cards/image-share.png)

*Input/output og noter*

| Navn på dynamisk token (input) | Pladsholdertekst   | Noter                                              |
|-----------------------------|--------------------|-----------------------------------------------------|
| acphotoTitle                | {acphotoTitle}     | Vist tekst                                        |
| acTimestamp                 | {acTimestamp}      | Dato/klokkeslæt for visning                                   |
| acImageThumbnail            | {acImageThumbnail} | Vist billede <br>Skal erstattes med en gyldig URL-adresse|
| acAltText                   | {acAltText}        | Alternativ tekst til tilgængelighed                      |

``` json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "{acphotoTitle}",
            "id": "Title",
            "size": "Large"
        },
        {
            "type": "TextBlock",
            "text": "{acTimestamp}",
            "size": "Medium",
            "weight": "Lighter"
        },
        {
            "type": "Image",
            "altText": "{acAltText}",
            "url": "{acImageThumbnail}"
        }
    ],
    "spacing": "None"
}
```


