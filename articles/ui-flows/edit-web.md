---
title: Få mere at vide om, hvordan du redigerer webbrugergrænsefladeflow | Microsoft Docs
description: Få mere at vide om, hvordan du redigerer webbrugergrænsefladeflow.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f29873dff5ae842d2f7b86f4f6e3e5c31bf04712
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74371681"
---
# <a name="edit-web-ui-flows"></a>Rediger webbrugergrænsefladeflow

[Dette emne er foreløbig dokumentation og kan ændres].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Webbrugergrænsefladeflow automatiserer websteder, der kører i [den næste version af Microsoft Edge](https://www.microsoftedgeinsider.com/) eller Google Chrome. Når du har [oprettet et webbrugergrænsefladeflow](create-web.md), kan det være nødvendigt at redigere det. Følg trinnene i dette dokument for at få mere at vide om, hvordan du kan redigere webbrugergrænsefladeflow.

## <a name="edit-in-selenium-ide"></a>Rediger i Selenium IDE

Brug Selenium IDE til at redigere dine webbrugergrænsefladeflow.

>[!NOTE]
>Redigering i Selenium IDE er målrettet erfarne brugere og udviklere.

Du kan se [Selenium-kommandoer](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) for at få mere at vide om, hvordan du redigerer scriptet.

Selenium IDE foreslår forskellige vælgere og en standardvælger, når der fokuseres på et element på brugergrænsefladen. Du kan også definere en ny vælger, hvis ingen af de foreslåede vælgere er relevante. Dette sker typisk, når webstedets HTML-struktur er meget dynamisk.

Her er et eksempel på mulige vælgere, som Selenium IDE har identificeret:

![Mulige vælgere](../media/edit-web/possible-selectors.png "Mulige vælgere")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Adgang til en egenskab for en objektvariabel eller et element i en matrixvariabel**

Denne avancerede funktionalitet gør det muligt for dig at bruge syntaks som \${foo.bar} til at få adgang til egenskaben bar for objektets foo. Du kan også skrive til egenskaben bar for foo ved hjælp af foo.bar som værdiegenskaben i en lagringskommando. Du kan også bruge syntaks som f.eks. \${foo[0]} til at få adgang til elementet ved indeks 0 i foo-matrixen.

## <a name="next-steps"></a>Næste trin

- [Opret webbrugergrænsefladeflow](create-web.md)
- [Kør brugergrænsefladeflow](run-ui-flow.md)
