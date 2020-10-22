---
title: Oversigt over områder i Power Automate | Microsoft Docs
description: Oversigt med spørgsmål og svar om områder i Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2020
ms.author: hamenon
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 81f9a3533d8180184b12b07ab6379e86ce20c198
ms.sourcegitcommit: dc401f03be124fffb1cb34e368784e8072a73ccb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/25/2020
ms.locfileid: "3892755"
---
# <a name="power-automate-regions-overview"></a>Oversigt over Power Automate-områder

I Power Automate oprettes flows i dit Power Platform-miljø. Disse miljøer er specifikke for et område, som svarer til placeringen af de datacentre, hvor Power Platform-miljøet er gemt.

Med andre ord installeres dine flows i det [datacenterområde](https://azure.microsoft.com/regions/), der er vært for dit [Power Platform-miljø](environments-overview-admin.md).

## <a name="more-information-about-power-platform-regions"></a>Flere oplysninger om Power Platform-områder

[Oversigt over Power Platform-områder](/power-platform/admin/regions-overview)

[Geografiske områder i Azure](https://azure.microsoft.com/global-infrastructure/geographies/)

## <a name="region-mappings-for-power-automate-and-gateways"></a>Områdetilknytninger for Power Automate og gateways

Det område, hvor gatewayen er installeret, skal være knyttet til dit Power Automate-område. Tværgående geografiske grænser understøttes ikke. 

Her er tilknytningsoplysningerne:

Power Platform-område|Gatewayområde
-----|-----
USA, inklusive prøveversion|Det centrale USA, Det østlige USA 2, Det østlige USA, Det nordcentrale USA, Det sydcentrale USA, Det vestlige USA 2, Det vestlige centrale USA, Det vestlige USA
Asien|Det østlige Asien, Det sydøstlige Asien
Australien|Det østlige Australien, Det sydøstlige Australien
Canada|Det centrale Canada, Det østlige Canada
Europa|Det nordlige Europa, Det vestlige Europa
Frankrig|Det centrale Frankrig, Det sydlige Frankrig
Indien|Det centrale Indien, Det sydlige Indien, Det vestlige Indien
Japan|Det østlige Japan, Det vestlige Japan
Sydamerika|Det Sydlige Brasilien
Storbritannien|Det sydlige Storbritannien, Det vestlige Storbritannien

## <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

### <a name="what-region-should-i-use"></a>Hvilket område skal jeg bruge?

Det er en god ide at oprette dit flow i et miljø, der er i det område, der er nærmest dine kunder. Når de datacentre, der er vært for miljøet, er tættere på de personer, der har adgang til oplysningerne, vil du sandsynligvis opleve bedre ydeevne.

### <a name="how-can-i-find-out-the-region-where-my-flow-is-deployed"></a>Hvordan finder jeg frem til det område, hvor mit flow er udrullet?

Administratorer kan identificere området ved at logge på Power Platform [Administration](https://admin.powerplatform.microsoft.com/). Under fanen **Miljøer** vises alle eksisterende miljøer og områder.

### <a name="is-power-automate-available-in-national-clouds"></a>Er Power Automate tilgængelig i nationale skyer?

Ja. [Få mere at vide](./us-govt.md).

### <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Hvilke udgående IP-adresser bruges i hvert område?

Se [Grænser og konfiguration](limits-and-config.md).
