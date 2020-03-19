---
title: Opdater programmet til flow for brugergrænsefladen og forbindelser fra tidligere udgivelser | Microsoft Docs
description: Opdater programmet til flow for brugergrænsefladen og forbindelser fra tidligere udgivelser.
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
ms.date: 03/03/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 617f61e1c08f7a4a51bb6916bcadf5e02691d46f
ms.sourcegitcommit: f7d040ae93eabbc60ce922f497ab47977130d877
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79132929"
---
# <a name="upgrade-ui-flows-app-and-connections-from-previous-releases"></a>Opgrader programmet til flow for brugergrænsefladen og forbindelser fra tidligere udgivelser

Vi har ændret flere underliggende komponenter og tilføjet flere funktioner i udgivelsen fra februar med automatiseret support. Du skal opdatere dit lokale program til flow for brugergrænsefladen og dine gatewayforbindelser for at bruge disse nye funktioner, herunder automatiserede funktioner.

### <a name="what-does-it-mean-for-my-existing-ui-flows"></a>Hvad betyder det for mine eksisterende flow for brugergrænsefladen?

Der kræves ingen handling, før du enten opdaterer programmet til flow for brugergrænsefladen eller forbindelsen til gatewayen. Du skal opdatere begge dele samtidigt.

### <a name="how-do-i-upgrade"></a>Hvordan opgraderer jeg?

1.  Download det [nyeste program til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409), og installér det på dine enheder.

1.  Gør følgende for hver enhed, du har installeret programmet til flow for brugergrænsefladen på:

    1. Log på [Power Automate](https://powerautomate.microsoft.com).
    1. Udvid **Data** i venstre side af skærmen.
    1. Vælg **Forbindelser**.
    1. Rediger de forbindelser for flow for brugergrænsefladen, der er målrettet din enhed.
    1. Angiv dine legitimationsoplysninger for forbindelsen, og gem den derefter.

    >[!IMPORTANT]
    >Sørg for at bruge de rigtige legitimationsoplysninger som skitseret i [Konfigurer forbindelser og legitimationsoplysninger til maskinen for flow for brugergrænsefladen](setup.md). Når du bruger de rigtige legitimationsoplysninger, sikrer du, at forbindelsen opdateres, og at kodestierne til de generelt tilgængelige flow for brugergrænsefladen bruges.

 <!-- todo      1. See (Managing UI flows app (Install, update, versions…)) for more
            details. -->

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [konfigurerer flow for brugergrænsefladen](setup.md). 
- Få mere at vide om de [forskellige flowtyper](..\getting-started.md#types-of-flows), som du kan bruge til at automatisere dine arbejdsprocesser.


