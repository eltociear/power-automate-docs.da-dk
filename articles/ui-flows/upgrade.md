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
ms.openlocfilehash: b73c550eb22948ea3c0e9ac14adf15674869da61
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/01/2020
ms.locfileid: "80525062"
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
    >Sørg for at bruge de rigtige legitimationsoplysninger som skitseret i [Konfigurer forbindelser og legitimationsoplysninger til maskinen for flow for brugergrænsefladen](setup.md#setup-ui-flows-connections-and-machine-credentials). Når du bruger de rigtige legitimationsoplysninger, sikrer du, at forbindelsen opdateres, og at kodestierne til de generelt tilgængelige flow for brugergrænsefladen bruges.

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [konfigurerer flow for brugergrænsefladen](setup.md). 
- Få mere at vide om de [forskellige flowtyper](..\getting-started.md#types-of-flows), som du kan bruge til at automatisere dine arbejdsprocesser.


