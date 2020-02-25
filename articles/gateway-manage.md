---
title: Få mere at vide om administration af datagateways i det lokale miljø | Microsoft Docs
description: Få vist og installer en datagateway i det lokale miljø i Power Automate.
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
ms.date: 02/13/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f3600587897b9e64ecd76f85c8b9762e84bc7b94
ms.sourcegitcommit: dbba53a52e2c5b1c2965f6c608e586748d5baae0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/24/2020
ms.locfileid: "77567013"
---
# <a name="manage-an-on-premises-data-gateway-in-power-automate"></a>Administrer en datagateway i det lokale miljø i Power Automate.
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Installer og administrer en datagateway i det lokale miljø for at integrere en række cloudbaserede apps sikkert med dine data og apps i det lokale miljø med Power Automate.

Med en gateway kan du oprette forbindelse til data i det lokale miljø via disse forbindelser:

* Apache Impala
* Brugerdefinerede connectorer, som du opretter
* DB2
* Filsystem
* HTTP med Microsoft Azure Active Directory
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (prøveversion)

> [!IMPORTANT]
> Microsoft SharePoint-datagateways understøtter nu både HTTP- og HTTPS-trafik.

## <a name="prerequisites"></a>Forudsætninger

* Det brugernavn og den adgangskode, du brugte til at [tilmelde dig](sign-up-sign-in.md) til Power Automate.
* Administrative tilladelser til en gateway.

  Du har som standard disse tilladelser for hver gateway, du installerer. En administrator af en anden gateway kan også tildele dig disse tilladelser for den pågældende gateway.
* En licens, der understøtter gateways. Du kan finde flere oplysninger i afsnittet "Forbindelse" på [siden med priser](https://flow.microsoft.com/pricing/).

> [!TIP]
> Du kan oprette en gateway og en forbindelse i det lokale miljø for [et vilkårligt miljø](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Installér en gateway

Hvis du vil installere en gateway, skal du følge trinnene i [Installer en datagateway i det lokale miljø](/data-integration/gateway/service-gateway-install). Installer gatewayen i standardtilstand, eftersom _datagatewayen i det lokale miljø (personlig tilstand)_ kun er tilgængelig for Power BI.

## <a name="view-your-gateways"></a>Se dine gateways

I øverste højre hjørne af [Power Automate-webstedet](https://flow.microsoft.com) skal du vælge tandhjulsikonet og derefter vælge **Gateways**.

![Gateway under administration][1]

> [!NOTE]
> Hvis du har oprettet eller har fået adgang til en gateway i Power Apps, vises den pågældende gateway på listen **Mine gateways** i Power Automate.

## <a name="cluster-your-gateways"></a>Opret klynger til dine gateways

Du kan oprette [klynger med høj tilgængelighed for datagatewayinstallationer i det lokale miljø](/data-integration/gateway/service-gateway-high-availability-clusters) for at undgå enkelte fejlpunkter i forbindelse med adgang til dataressourcer i det lokale miljø.

Power Automate bruger som standard den primære gateway i klyngen. Hvis den primære gateway ikke er tilgængelig, skifter tjenesten til den næste gateway i klyngen osv.

Når du har konfigureret en gatewayklynge, kan du gøre det muligt at distribuere trafik på tværs af alle gateways i klyngen.

Følg disse trin for at fordele trafikken på tværs af dine gateways:

1. Vælg **Data** på navigationslinjen i venstre side.
1. Vælg **Gateways**.
1. Vælg en af dine gateways.
1. Vælg **Distribuer anmodninger på tværs af alle aktive gateways i klyngen**.
1. Vælg **Anvend** for at gemme dine ændringer.

Du kan finde flere oplysninger under [Forstå gateways](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
