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
ms.date: 08/14/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8b36b2cf5b4d400c1f2cb8a4094c984c57e5c76e
ms.sourcegitcommit: 39d7912519ff03dae924023c1a1c320a30efaa81
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2020
ms.locfileid: "3691050"
---
# <a name="faq-for-regions-in-power-automate"></a>Ofte stillede spørgsmål om områder i Power Automate

Dette dokument indeholder en liste over ofte stillede spørgsmål om Power Automate.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Hvordan finder jeg ud af, hvor mine flow er udrullet?
Dit flow er udrullet i det [område](https://azure.microsoft.com/regions/), der hoster [miljøet](environments-overview-admin.md). Hvis dit miljø f.eks. er oprettet i området Europa, er dit flow installeret i datacentre i Europa.

Administratorer kan identificere området, hvis de logger på Power Platform [Administration](https://admin.powerplatform.microsoft.com/). Under fanen **Miljøer** vises alle eksisterende miljøer og områder.

![vise miljøer](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Hvilke områder er tilgængelige?
* USA
* Europa
* Asien
* Australien
* Indien
* Japan
* Canada
* Sydamerika
* Storbritannien
* US Government (GCC)
* Frankrig

## <a name="what-features-are-specific-to-a-given-region"></a>Hvilke funktioner er specifikke for et bestemt område?

Miljøer kan oprettes i forskellige områder og er bundet til den pågældende geografiske placering. Når du opretter et flow i et miljø, installeres dette flow i datacentre på den pågældende geografiske placering. Dette gælder for alle elementer, du opretter i det pågældende miljø, herunder Common Data Model, flow, forbindelser, gateways, apps og brugerdefinerede connectors.

Opret dit miljø i det område, der er tættest på brugerne, for at få optimal ydeevne. Hvis dine brugere befinder sig i Europa, skal du f.eks. oprette miljøerne i området Europa. Hvis brugerne befinder sig i USA, skal du oprette miljøerne i området USA.

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
Sydamerika|Det sydlige Brasilien
Storbritannien|Det sydlige Storbritannien, Det vestlige Storbritannien

## <a name="is-power-automate-available-in-national-clouds"></a>Er Power Automate tilgængelig i nationale skyer?
Ja. [Få mere at vide](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Hvilke udgående IP-adresser bruges i hvert område?
Se [Grænser og konfiguration](limits-and-config.md).

