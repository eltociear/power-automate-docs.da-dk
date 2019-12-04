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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e364c4d9c07f3bac1f78fa6941d1823272ae2466
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74370899"
---
# <a name="set-up-ui-flows"></a>Konfigurer Flow for brugergrænseflade

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

- En enhed, der kører Windows 10, Windows Server 2016 eller Windows Server 2019.
- Et amerikansk tastatur (QWERTY) tilsluttet.

- Den [nyeste version af Microsoft Edge](https://www.microsoftedgeinsider.com) eller Google Chrome.

- Et [miljø](https://docs.microsoft.com/power-platform/admin/environments-overview) med en [Common Data Service-database](https://docs.microsoft.com/power-platform/admin/create-database).

## <a name="limitations"></a>Begrænsninger

Flow for brugergrænseflade (prøveversion) er tilgængelig på engelsk.

Følgende understøttes ikke:

-   Flow for brugergrænseflade på skrivebordet

    -   Flere skærme
    -   Virtuelle maskiner
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

Følg disse trin for at installere programmet for flow for brugergrænsefladen:

1. [Download installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Åbn filen **Setup.Microsoft.Flow.UIflow.exe**. Du finder sandsynligvis denne fil i mappen **Downloads**, efter du har downloadet den i forrige trin.
1. Følg vejledningen i installationsprogrammet til **Konfiguration af Flow for brugergrænseflade (prøveversion)** for at fuldføre installationen.

> [!TIP]
> Hvis du vil ændre indstillingen for dataindsamling, skal du geninstallere Flow for brugergrænseflade og ændre indstillingen.

## <a name="activate-the-ui-flows-browser-extension"></a>Aktivér browserudvidelsen til flow for brugergrænsefladen 

Når installationsprogrammet til flow for brugergrænsefladen er fuldført, bliver du bedt om at aktivere udvidelsen i browseren.

- På Microsoft Edge (Chromium) skal du vælge hvert advarselsikon i øverste højre hjørne af browseren og derefter vælge **Aktivér udvidelse**.
-   På Google Chrome skal du vælge **Aktivér udvidelse**, når du bliver bedt om det.  

> [!TIP]
> Hvis du ikke fik vist prompten i din browser, skal du kontrollere følgende:
> - Du skal bruge Microsoft Edge (Chromium) eller Google Chrome
> - Du skal muligvis aktivere udvidelsen manuelt. Hvis du har Microsoft Edge (Chromium), skal du navigere til **edge://extensions**, og hvis du har Google Chrome, skal du navigere til **chrome://extensions**.
> - Hvis udvidelsen til flow for brugergrænsefladen i Power Automate ikke vises, skal du geninstallere den ved hjælp af [installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).

<!-- To do for Gautier: check if the below is not bugged as there was one at some point.
> - Reinstall the extension from the Chrome store
Navigate to this link https://chrome.google.com/webstore/detail/microsoft-flow-preview/jcajipieipkmjpfakbdhmjidmhidogoo and install it manually, that will fix any issues. (For Edge Chromium, use the same link and accept when prompted to install from external stores.)
-->

## <a name="optional-install-selenium-ide-to-automate-web-applications"></a>(valgfrit) Installér Selenium IDE for at automatisere webprogrammer

Selenium IDE er et værktøj i åben kildekode, der giver dig mulighed for at optage og afspille personlige interaktioner på websteder.

Med flow for brugergrænsefladen kan du køre Selenium IDE-scripts fra Power Automate og gemme dem på en sikker måde (med passende it-styring) i Common Data Service.

Følg disse trin for at installere Selenium IDE:

1. [Download og installér](https://go.microsoft.com/fwlink/?linkid=2107665) Selenium IDE til den nyeste version af Microsoft Edge eller Google Chrome.

1. I forbindelse med Microsoft Edge (Chromium) skal du vælge **Tillad udvidelser fra andre butikker** og derefter vælge **Føj til Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Installér datagatewayen i det lokale miljø

Du skal bruge gatewayen til at udløse flow for brugergrænsefladen fra et [flow for en hændelse, en tidsplan eller en knap.](../getting-started.md#types-of-flows).

>[!TIP]
>Gatewayen kræves ikke, hvis du kun vil oprette, redigere og teste dine flow for brugergrænsefladen på din enhed.

[Installér datagatewayen i det lokale miljø](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), hvis du har brug for det.

## <a name="uninstall-ui-flows"></a>Fjern Flow for brugergrænseflade

1. Åbn menuen **Start** > **Indstillinger** > **Programmer**.
1. Søg efter **Flow for brugergrænseflade (prøveversion)**, og vælg den derefter.
1. Vælg **Fjern**.

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [opretter flow for brugergrænsefladen på skrivebordet](create-desktop.md).
- Få mere at vide om, hvordan du [opretter flow for brugergrænsefladen på internettet](create-web.md).
- Få mere at vide om, hvordan du kører [flow for brugergrænsefladen](run-ui-flow.md).
- Få mere at vide om, hvordan du [administrerer flow for brugergrænsefladen](manage.md).
- Få mere at vide om [gatewayen i det lokale miljø](../gateway-reference.md#use-a-gateway)

## <a name="limitations"></a>Begrænsninger
- De nyeste versioner af hver enkelt komponent kræves for at kunne optage, teste eller køre flow for brugergrænsefladen.
- Fjern tidligere versioner, før du installerer den nyeste.


