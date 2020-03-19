---
title: Konfigurer flow for brugergrænsefladen på din enhed | Microsoft Docs
description: Konfigurer flow for brugergrænsefladen på din enhed
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
ms.date: 03/04/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 825ebceb042215c379340f1e1b7e2dae6f921c2c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79196025"
---
# <a name="set-up-ui-flows"></a>Konfigurer brugergrænsefladeflow

[Dette emne er foreløbig dokumentation og kan ændres].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

> [!IMPORTANT]
> Funktionen Flow for brugergrænseflade udrulles i øjeblikket i flere områder. Hvis du ikke kan se funktionen i dit miljø, ikke kan oprette flow for brugergrænsefladen eller får vist en fejl, når du forsøger at køre funktionen i et flow, skal du prøve igen senere.

Før du kan bruge din enhed til at oprette flow for brugergrænsefladen, skal du sikre, at den opfylder de krav, der er angivet her.

> [!TIP]
> Før du opretter et flow for brugergrænsefladen, skal du kontrollere [listen over connectors](https://flow.microsoft.com/connectors/) for at se, om der allerede er en connector for det program, du vil automatisere. Hvis det er tilfældet, kan du overveje at oprette et flow i stedet for et flow for brugergrænsefladen. Du kan også skabe din [egen connector](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Forudsætninger

- Enten en [betalt](https://flow.microsoft.com/pricing/) Power Automate-plan eller en [prøveversion](https://flow.microsoft.com/manage/) af den.

- En arbejds- eller skolekonto til at logge på din Windows-enhed med administratorrettigheder og Power Automate.

- En enhed, der kører Windows 10 Pro, Windows Server 2016 eller Windows Server 2019.

- [Microsoft Edge](https://www.microsoftedgeinsider.com)- eller Google Chrom-browser.

- Et [miljø](https://docs.microsoft.com/power-platform/admin/environments-overview) med en [Common Data Service-database](https://docs.microsoft.com/power-platform/admin/create-database).

- Et tilsluttet understøttet tastatur.

## <a name="limitations"></a>Begrænsninger

Du skal have de nyeste versioner af hver enkelt komponent for at optage, teste eller køre flow for brugergrænsefladen.

Følgende understøttes ikke:
- Installationer af Windows 10 Home understøttes ikke.

-   Flow for brugergrænseflade på skrivebordet

    -   Flere skærme
    -   Dobbeltklik, hold over med mus, input med touch/pen
    -   Interaktioner i Windows (Stifinder, menuen Start, proceslinje osv.)

-   Flow for brugergrænseflade på internettet

    -   Højreklik
    -   Oplysninger om brugersessionen (f.eks.: cookies) genbruges ikke under afspilning. Du skal redigere scriptet for at integrere logonoplysninger, når det kræves af websteder.

Du finder de funktionsspecifikke begrænsninger, der er inkluderet i dokumentationen for hver funktion.

## <a name="install-ui-flows-on-your-device"></a>Installér Flow for brugergrænseflade på din enhed

Installationsprogrammet til flow for brugergrænsefladen indeholder alle de komponenter, der skal bruges til at optage, redigere og teste flow for brugergrænsefladen på skrivebordet. 

>[!IMPORTANT]
>Installationsprogrammet til flow for brugergrænsefladen installerer Webdriver-komponenten og browserudvidelsen til flow for brugergrænsefladen. Begge er nødvendige for at optage, teste og køre flow for brugergrænsefladen på skrivebordet.

Følg disse trin for at installere programmet til flow for brugergrænsefladen:

1. [Download installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Åbn filen **Setup.Microsoft.Flow.UIflow.exe**. Du finder sandsynligvis denne fil i mappen **Downloads**, efter du har downloadet den i forrige trin.
1. Følg vejledningen i installationsprogrammet til **Konfiguration af Flow for brugergrænseflade (prøveversion)** for at fuldføre installationen.

> [!WARNING]
> Du skal fjerne programmet til flow for brugergrænsefladen og derefter geninstallere det, hvis du har brug for at ændre indstillingerne for dataindsamling. Flow for brugergrænseflade fungerer ikke længere, hvis du ændrer indstillingerne for dataindsamling uden først at fjerne programmet til flow for brugergrænsefladen.

## <a name="activate-the-ui-flows-browser-extension"></a>Aktivér browserudvidelsen til flow for brugergrænsefladen 

Når installationsprogrammet til flow for brugergrænsefladen er fuldført, bliver du bedt om at aktivere udvidelsen i browseren.

- På Microsoft Edge skal du vælge hvert advarselsikon i øverste højre hjørne af browseren og derefter vælge **Aktivér udvidelse**.
-   På Google Chrome skal du vælge **Aktivér udvidelse**, når du bliver bedt om det.  

> [!TIP]
> Hvis du ikke fik vist prompten i din browser, skal du kontrollere følgende:
> - Du skal bruge Microsoft Edge eller Google Chrome
> - Du skal muligvis aktivere udvidelsen manuelt. Hvis du har Microsoft Edge, skal du gå til **edge://extensions**, og hvis du har Google Chrome, skal du gå til **chrome://extensions**.
> - Hvis udvidelsen til flow for brugergrænsefladen i Power Automate ikke vises, skal du geninstallere den ved hjælp af [installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).


## <a name="install-selenium-ide-to-automate-web-applications"></a>Installér Selenium IDE for at automatisere webprogrammer

Selenium IDE er et værktøj i åben kildekode, der giver dig mulighed for at optage og afspille personlige interaktioner på websteder.

Med flow for brugergrænsefladen kan du køre Selenium IDE-scripts fra Power Automate og gemme dem på en sikker måde (med passende it-styring) i Common Data Service.

Følg disse trin for at installere Selenium IDE:

1. [Download og installér](https://go.microsoft.com/fwlink/?linkid=2107665) Selenium IDE til den nyeste version af Microsoft Edge eller Google Chrome.

1. I forbindelse med Microsoft Edge skal du vælge **Tillad udvidelser fra andre butikker** og derefter vælge **Føj til Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Installér datagatewayen i det lokale miljø

Du skal bruge gatewayen til at udløse dit flow for brugergrænsefladen fra et [flow for en hændelse, en tidsplan eller en knap](../getting-started.md#types-of-flows) på en fjernenhed.

>[!TIP]
>Gatewayen kræves ikke, hvis du kun vil oprette, redigere og teste dine flow for brugergrænsefladen på din enhed.

[Installér datagatewayen i det lokale miljø](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), hvis du har brug for det.

## <a name="setup-ui-flows-connections-and-machine-credentials"></a>Konfigurer forbindelser og legitimationsoplysninger til maskinen for flow for brugergrænsefladen

1. Log på [Power Automate](https://powerautomate.microsoft.com).
1. Udvid **Data** i venstre side af skærmen.
1. Vælg **Forbindelser**.

   ![Et skærmbillede af fanen med forbindelser](../media/ui-flows-setup/connections-tab.png)

1. Vælg Ny forbindelse.

   ![Et skærmbillede af en forbindelse](../media/ui-flows-setup/new-connection.png)

1. Søg efter *Flow for brugergrænseflade*, og vælg derefter **Flow for brugergrænseflade (prøveversion).

   ![Et skærmbillede af søgefeltet](../media/ui-flows-setup/search-ui-flow.png)

1. Angiv gatewayoplysninger og enhedsoplysninger for *hver* gateway: 

    - **Domæne og brugernavn**: Angiv din enhedskonto. Du kan bruge en lokal konto ved hjælp af navnet på brugeren (f.eks. "NAVN PÅ MASKINE\\Bruger" eller "lokal\\Bruger") eller en Active Directory-konto såsom "DOMÆNE\\Bruger".
    - **Adgangskode**: Adgangskoden til din konto.
    - **Vælg en gateway**: Vælg en af de gateways, du vil konfigurere.

      ![Et skærmbillede, der viser, hvor du skal angive legitimationsoplysningerne for forbindelsen](../media/ui-flows-setup/credentials-screen.png)

1. Vælg **Opret**.

## <a name="supported-keyboard-layouts"></a>Layouts for tilsluttet tastatur

- Amerikansk tastatur – engelsk (USA)
- Amerikansk tastatur – engelsk (Australien)
- Amerikansk tastatur – engelsk (Canada)
- Microsoft Pinyin – kinesisk (forenklet Han, Kina)
- Tysk tastatur – tysk (Tyskland)
- Microsoft IME – japansk (Japan)
- Britisk tastatur – engelsk (Storbritannien)
- Fransk tastatur – fransk (Frankrig)
- Russisk tastatur – russisk (Rusland)
- Portugisisk tastatur (Brasiliansk ABNT) – portugisisk (Brasilien)
- Portugisisk tastatur (Brasiliansk ABNT2) – portugisisk (Brasilien)
- Microsoft IME – koreansk (Sydkorea)
- Spansk tastatur – spansk (Spanien)
- Italiensk tastatur – Italiensk (Italien)
- Latinamerikansk tastatur – spansk (Mexico)
- Polsk tastatur (programmører) – polsk (Polen)
- Amerikansk internationalt tastatur – hollandsk (Nederlandene)
- Tyrkisk Q-tastatur – tyrkisk (Tyrkiet)
- Indisk tastatur – engelsk (Indien)

## <a name="supported-languages"></a>Understøttede sprog

Her ses de sprog, som flow for brugergrænsefladen understøtter udover engelsk:

|||||
----|-----|-----|--------
Baskisk  | Fransk    | Lettisk   | Slovakisk
Bulgarsk   |   Galisisk    |   Litauisk  |   Slovensk
Catalansk |   Tysk      |Malaysisk  |   Spansk
Kinesisk (forenklet)    |   Græsk   |   Norsk   |   Svensk
Kinesisk (traditionelt)   |   Hindi   |   Polsk  |   Thai
Kroatisk    |   Ungarsk   |   Portugisisk (Brasilien) |   Tyrkisk
Tjekkisk   |   Indonesisk  |   Portugisisk (Portugal)       |Ukrainsk
Dansk  |   Italiensk |   Rumænsk    |   Vietnamesisk
Nederlandsk       |Japansk   |   Russisk 
Estisk    |Kasakhisk |   Serbisk (kyrillisk, Serbien)  
Finsk     |Koreansk     |Serbisk (latin, Serbien)

## <a name="uninstall-ui-flows"></a>Fjern Flow for brugergrænseflade

1. Åbn menuen **Start** > **Indstillinger** > **Programmer**.
1. Søg efter **Flow for brugergrænseflade (prøveversion)** , og vælg den derefter.
1. Vælg **Fjern**.

## <a name="learn-more"></a>Få mere at vide

- [Opgrader dine flow for brugergrænsefladen](upgrade.md) fra tidligere udgivelser
- Få mere at vide om, hvordan du [opretter flow for brugergrænsefladen på skrivebordet](create-desktop.md).
- Få mere at vide om, hvordan du [opretter flow for brugergrænsefladen på internettet](create-web.md).
- Få mere at vide om, hvordan du kører [flow for brugergrænsefladen](run-ui-flow.md).
- Få mere at vide om, hvordan du [administrerer flow for brugergrænsefladen](manage.md).
- Få mere at vide om [gatewayen i det lokale miljø](../gateway-reference.md#use-a-gateway)
