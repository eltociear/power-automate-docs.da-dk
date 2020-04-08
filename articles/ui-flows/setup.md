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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 97456d637dd272a465559d4cee8fb1d17fe3de8d
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524634"
---
# <a name="set-up-ui-flows"></a>Konfigurer flow for brugergrænsefladen

Før du kan bruge din enhed til at oprette flow for brugergrænsefladen, skal du sikre, at den opfylder de krav, der er angivet her.

> [!TIP]
> Før du opretter et flow for brugergrænsefladen, skal du kontrollere [listen over connectors](https://flow.microsoft.com/connectors/) for at se, om der allerede er en connector for det program, du vil automatisere. Hvis det er tilfældet, kan du overveje at oprette et flow i stedet for et flow for brugergrænsefladen. Du kan også skabe din [egen connector](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Forudsætninger

- Enten en [betalt](https://flow.microsoft.com/pricing/) Power Automate-plan eller en [prøveversion](https://flow.microsoft.com/manage/) af den.

- En arbejds- eller skolekonto til at logge på din Windows-enhed med administratorrettigheder og Power Automate.

- En enhed, der kører Windows 10 Pro, Windows Server 2016 eller Windows Server 2019.

- Browseren [Microsoft Edge](https://www.microsoft.com/edge/) (version 80 eller nyere) eller Google Chrome.

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

    -   Højreklik.
    -   Oplysninger om brugersessionen (f.eks. cookies) genbruges ikke under afspilning. Du skal redigere scriptet for at integrere logonoplysninger, når det kræves af websteder.

Du finder de funktionsspecifikke begrænsninger, der er inkluderet i dokumentationen for hver funktion.

## <a name="install-ui-flows-on-your-device"></a>Installér Flow for brugergrænseflade på din enhed

Installationsprogrammet til flow for brugergrænsefladen indeholder alle de komponenter, der skal bruges til at optage, redigere og teste flow for brugergrænsefladen på skrivebordet. 

>[!IMPORTANT]
>Installationsprogrammet til flow for brugergrænsefladen installerer Webdriver-komponenten og browserudvidelsen til flow for brugergrænsefladen. Begge er nødvendige for at optage, teste og køre flow for brugergrænsefladen på skrivebordet.

Følg disse trin for at installere programmet for flow for brugergrænsefladen:

1. [Download installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Åbn filen **Setup.Microsoft.PowerAutomate.UIflow.exe**. Du finder sandsynligvis denne fil i mappen **Downloads**, efter du har downloadet den i forrige trin.
1. Følg vejledningen i installationsprogrammet til **Konfiguration af flow for brugergrænsefladen** for at fuldføre installationen.

### <a name="set-data-collection-options"></a>Angiv indstillinger for dataindsamling

Under installationen kan du ændre standardindstillingerne, hvis du ikke vil sende forbrugsdata til Microsoft. Det gør du ved at fjerne markeringen af **Tillad, at Microsoft indsamler forbrugsdata for at forbedre flow for brugergrænseflade**.

![Billede, der viser indstillingerne for dataindsamling](../media/ui-flows-setup/data-collection-settings.png)

## <a name="activate-the-ui-flows-browser-extension"></a>Aktivér browserudvidelsen til flow for brugergrænsefladen 

Når installationsprogrammet til flow for brugergrænsefladen er fuldført, bliver du bedt om at aktivere udvidelsen i browseren.

- I [Microsoft Edge](https://www.microsoft.com/edge/) (version 80 eller nyere) skal du vælge hvert advarselsikon øverst til højre i browseren og derefter vælge **Aktivér udvidelse**.
-   På Google Chrome skal du vælge **Aktivér udvidelse**, når du bliver bedt om det.  

> [!TIP]
> Hvis du ikke fik vist prompten i din browser, skal du kontrollere følgende:
> - Du skal bruge [Microsoft Edge](https://www.microsoft.com/edge/) (version 80 eller nyere) eller Google Chrome.
> - Du skal muligvis aktivere udvidelsen manuelt. Hvis du har Microsoft Edge, skal du gå til **edge://extensions**, og hvis du har Google Chrome, skal du gå til **chrome://extensions**.
> - Hvis udvidelsen til flow for brugergrænsefladen i Power Automate ikke vises, skal du geninstallere den ved hjælp af [installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).


## <a name="install-selenium-ide-to-automate-web-applications"></a>Installér Selenium IDE for at automatisere webprogrammer

Selenium IDE er et værktøj i åben kildekode, der giver dig mulighed for at optage og afspille personlige interaktioner på websteder.

Med flow for brugergrænsefladen kan du køre Selenium IDE-scripts fra Power Automate og gemme dem på en sikker måde (med passende it-styring) i Common Data Service.

Følg disse trin for at installere Selenium IDE:

1. [Download og installér](https://go.microsoft.com/fwlink/?linkid=2107665) Selenium IDE til [Microsoft Edge](https://www.microsoft.com/edge/) (version 80 eller nyere) eller Google Chrome.

1. I Microsoft Edge (version 80 eller nyere) skal du vælge **Tillad udvidelser fra andre lagre** og derefter vælge **Føj til Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Installér datagatewayen i det lokale miljø

Du skal bruge gatewayen til at udløse dit flow for brugergrænsefladen fra et [flow for en hændelse, en tidsplan eller en knap](../getting-started.md#types-of-flows) på en fjernenhed.

>[!TIP]
>Gatewayen kræves ikke, hvis du kun vil oprette, redigere og teste dine flow for brugergrænsefladen på din enhed.

[Installér datagatewayen i det lokale miljø](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), hvis du har brug for det.


>[!IMPORTANT]
>Når du installerer gatewayen, bruger den som standard det område, der bruges til Power Automate.


## <a name="setup-ui-flows-connections-and-machine-credentials"></a>Konfigurer forbindelser og legitimationsoplysninger til maskinen for flow for brugergrænsefladen

1. Log på [Power Automate](https://powerautomate.microsoft.com).
1. Udvid **Data** i venstre side af skærmen.
1. Vælg **Forbindelser**.

   ![Et skærmbillede af fanen med forbindelser](../media/ui-flows-setup/connections-tab.png)

1. Vælg Ny forbindelse.

   ![Et skærmbillede af en forbindelse](../media/ui-flows-setup/new-connection.png)

1. Søg efter *Flow for brugergrænseflade*, og vælg derefter **Flow for brugergrænseflade**.

   ![Et skærmbillede af søgefeltet](../media/ui-flows-setup/search-ui-flow.png)

1. Angiv gatewayoplysninger og enhedsoplysninger: 

    - **Domæne og brugernavn**: Angiv din enhedskonto. Du kan bruge en lokal konto ved hjælp af navnet på brugeren (f.eks. "NAVN PÅ MASKINE\\Bruger" eller "lokal\\Bruger") eller en Active Directory-konto såsom "DOMÆNE\\Bruger".
    - **Adgangskode**: Adgangskoden til din konto.
    - **Vælg en gateway**: Vælg den gateway, du vil bruge.

      ![Et skærmbillede, der viser, hvor du skal angive legitimationsoplysningerne for forbindelsen](../media/ui-flows-setup/credentials-screen.png)

1. Vælg **Opret**.

## <a name="troubleshoot-missing-gateway"></a>Foretag fejlfinding af manglende gateway

Du kan muligvis ikke finde gatewayen på listen under oprettelse af forbindelse af følgende årsager:

- Gatewayen kan være installeret i et andet område end dit Power Automate-område. Du kan løse dette problem ved at fjerne gatewayen fra enheden og derefter geninstallere den ved at vælge [det rigtige Power Automate-område](../regions-overview.md#region-mappings-for-power-automate-and-gateways).
- Gatewayen blev slettet af ejeren.

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
1. Søg efter **Flow for brugergrænseflade**, og vælg den derefter.
1. Vælg **Fjern**.

## <a name="learn-more"></a>Få mere at vide

- [Opgrader dine flow for brugergrænsefladen](upgrade.md) fra tidligere udgivelser
- Få mere at vide om, hvordan du [opretter flow for brugergrænsefladen på skrivebordet](create-desktop.md).
- Få mere at vide om, hvordan du [opretter flow for brugergrænsefladen på internettet](create-web.md).
- Få mere at vide om, hvordan du kører [flow for brugergrænsefladen](run-ui-flow.md).
- Få mere at vide om, hvordan du [administrerer flow for brugergrænsefladen](manage.md).
- Få mere at vide om [gatewayen i det lokale miljø](../gateway-reference.md#use-a-gateway)
