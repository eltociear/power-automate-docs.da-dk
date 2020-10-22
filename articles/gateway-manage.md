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
ms.openlocfilehash: a1d01caa7ffa5f3611f7419fd4b3c384e1b89a52
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900234"
---
# <a name="manage-an-on-premises-data-gateway-in-power-automate"></a>Adminsitrer en datagateway i det lokale miljø i Power Automate


Installer og administrer en datagateway i det lokale miljø for at integrere en række cloudbaserede apps sikkert med dine data og apps i det lokale miljø gennem Power Automate.

Med en gateway kan du oprette forbindelse til data i det lokale miljø via disse forbindelser:

* Apache Impala
* Brugerdefinerede connectorer, som du opretter
* DB2
* Filsystem
* Http med Azure AD
* Informix
* MySQL
* Oracle-database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (prøveversion)

> [!IMPORTANT]
> Microsoft SharePoint-datagateways understøtter nu både HTTP- og HTTPS-trafik.

## <a name="prerequisites"></a>Forudsætninger

* Det brugernavn og den adgangskode, du brugte til at [tilmelde dig](sign-up-sign-in.md) til Power Automate.
* Administrative tilladelser på en gateway.

  Du har som standard disse tilladelser for hver gateway, du installerer. En administrator af en anden gateway kan også tildele dig disse tilladelser for den pågældende gateway.
* En licens, der understøtter gateways. Du kan finde flere oplysninger i afsnittet "Forbindelse" på [siden med priser](https://flow.microsoft.com/pricing/).

> [!TIP]
> Du kan oprette en gateway og en forbindelse i det lokale miljø for [et vilkårligt miljø](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Installér en gateway

Hvis du vil installere en gateway, skal du følge trinnene i [Installer en datagateway i det lokale miljø](/data-integration/gateway/service-gateway-install). Installer gatewayen i standardtilstand, eftersom _datagatewayen i det lokale miljø (personlig tilstand)_ kun er tilgængelig for Power BI.

## <a name="view-your-gateways"></a>Se dine gateways

Log på [Power Automate](https://flow.microsoft.com), og vælg derefter **Data** > **Gateways** i venstre navigationsrude.

> [!NOTE]
> Hvis du har oprettet eller har fået adgang til en gateway i Power Apps, vises denne gateway på listen **Mine gateways** i Power Automate.

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
