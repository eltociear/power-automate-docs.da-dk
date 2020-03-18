---
title: Datagateways i det lokale miljø | Microsoft Docs
description: Denne artikel er en oversigt over datagatewayen i det lokale miljø til Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2a0e2d3ff9fb39019ef4b8f37a7715229844c388
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/13/2020
ms.locfileid: "79224348"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Hvad er en datagateway i det lokale miljø?


Datagatewayen i det lokale miljø fungerer som en bro, der giver hurtig og sikker dataoverførsel mellem lokale data (data, der ikke er i cloudmiljøet) og adskillige Microsoft-cloudtjenester. Disse cloudtjenester omfatter Power BI, Power Apps, Power Automate, Azure Analysis Services og Azure Logic Apps. Ved hjælp af en gateway kan organisationer opbevare databaser og andre datakilder på deres netværk i det lokale miljø og samtidig sikkert bruge disse lokale data i cloudtjenester.

## <a name="how-the-gateway-works"></a>Sådan virker gatewayen

![Oversigt over gateways](media/gateway-reference/on-premises-data-gateway.png)

Du kan finde flere oplysninger om, hvordan gatewayen fungerer i [Arkitektur for datagateway i det lokale miljø](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Typer af gateways

Der er to forskellige typer gateways til hvert sit scenarie:

- **Datagateway i det lokale miljø** gør det muligt for flere brugere at oprette forbindelse til flere datakilder i det lokale miljø. Du kan bruge en datagateway i det lokale miljø til alle understøttede tjenester med en enkelt gatewayinstallation. Denne gateway er velegnet til komplekse scenarier, hvor flere personer tilgår flere datakilder.

- **Datagateway i det lokale miljø (personlig tilstand)** gør det muligt for én bruger at oprette forbindelse til datakilder og kan ikke deles med andre. En datagateway i det lokale miljø (personlig tilstand) kan kun bruges med Power BI. Denne gateway er velegnet til scenarier, hvor du er den eneste, der opretter rapporter, og du ikke behøver at dele datakilder med andre.

## <a name="use-a-gateway"></a>Brug en gateway

Du skal udføre fire primære trin, når du vil bruge en gateway.

1. [Download og installér gatewayen](/data-integration/gateway/service-gateway-install) på en lokal computer.
2. [Konfigurer](/data-integration/gateway/service-gateway-app) gatewayen på baggrund af din firewall og andre netværkskrav.
3. [Tilføj gatewayadministratorer](/data-integration/gateway/service-gateway-manage), der også kan administrere andre netværkskrav.
4. [Foretag fejlfinding](/data-integration/gateway/service-gateway-tshoot) af gatewayen i tilfælde af fejl.

## <a name="next-steps"></a>Næste trin

- [Installér datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-install)
