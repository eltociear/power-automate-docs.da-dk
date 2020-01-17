---
title: Eksempel på billeddeling til deling af fotos | Microsoft Docs
description: Få mere at vide om, hvordan du opretter et adaptivt kort til deling af fotos.
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
ms.openlocfilehash: 0d310eb96a69f66b8f45718554f36ba8b2a51989
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868727"
---
# <a name="image-share-sample"></a>Eksempel på billeddeling 

Eksemplet på **en formular til billeddeling** er et adaptivt kort, der er beregnet til deling af fotos, der er blevet sendt til SharePoint, og som kan være en afhængighed for en proces, der skal udføres (f.eks. processer, der er relateret til inspektion, overholdelse og overvågning). Dette kort er et adaptivt kort, der kun er beregnet til visning.

![Et adaptivt kort, der kun er beregnet til visning](media/adaptive-cards/image-share.png)

*Input/output og noter*

| Navn på dynamisk token (input) | Pladsholdertekst   | Noter                                              |
|-----------------------------|--------------------|-----------------------------------------------------|
| acphotoTitle                | {acphotoTitle}     | Vist tekst                                        |
| acTimestamp                 | {acTimestamp]      | Dato/klokkeslæt for visning                                   |
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


