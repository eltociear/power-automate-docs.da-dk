---
title: Brug input og output i webbrugergrænsefladeflow | Microsoft Docs
description: Brug input og output i webbrugergrænsefladeflow
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
ms.openlocfilehash: 38b6ba7f8fe3ab7a386229b6c9c5ccc300a147de
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74371405"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Brug input og output i webbrugergrænsefladeflow

[Dette emne er foreløbig dokumentation og kan ændres].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Definer input til et webbrugergrænsefladeflow

Input til et brugergrænsefladeflow giver dig mulighed for at overføre oplysninger fra en ekstern kilde, f.eks. en database eller et andet brugergrænsefladeflow, til den ældre destinationssoftware, som du kan automatisere.

En hvilken som helst variabel, der bruges (læses) før initialisering (som regel udført via kommandoer til **lagring**), behandles automatisk som en inputvariabel, og den vises på handlingskortet **Kør et webbrugergrænsefladeflow**.

Du kan bruge variabler via strenginterpolering og f.eks. ændre destinationsfeltet for klik-kommandoen til "id =\${elementId}". Du kan også ændre kommandoens værdifelt til "\${inputText}".

Kommandoen **set window size** og kommandoen **type** på følgende skærmbilleder bruger ikke-initialiserede variabler \${Width}, \${Height} og \${Search}. Disse variabler bliver inputværdier.

![Set window size og type](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Set window size og type")

Du kan bruge variabler direkte i nogle kommandoer, forEach-kommandoens destinations-/værdifelter er begge variabler, og du behøver ikke at omslutte dem med "\${}".

Se [Selenium-kommandoer](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) for at finde ud af, hvilke kommandoer der tager imod et variabelnavn direkte.

## <a name="define-outputs-for-a-web-ui-flow"></a>Definer output til et webbrugergrænsefladeflow

Alle variabler, der er defineret i Selenium-scriptet, bliver automatisk en outputværdi. Brug følgende kommandoer til at angive variabler:

[Store](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Store attribute](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[Store json](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Store title](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[store value](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Store window handle](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Store xpath count](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Execute script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script)(tilføj syntaksen 'return' for at returnere det objekt, du vil lagre, i slutningen af scriptet)

## <a name="next-steps"></a>Næste trin

- Få mere at vide om [oprettelsen webbrugergrænsefladeflow](create-web.md).
- Få mere at vide om [udløsningen af brugergrænsefladeflow](run-ui-flow.md).

