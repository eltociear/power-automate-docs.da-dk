---
title: Konfigurer flow for brugergrænseflade og Power Automate Desktop (prøveversion) på enheden | Microsoft Docs
description: Konfigurer flow for brugergrænseflade og Power Automate Desktop (prøveversion) på enheden.
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
ms.date: 09/22/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ba01a6db7688180520962beafe7e41cd1065b672
ms.sourcegitcommit: 1ffc5ec190e8f0d6105bdf61508bd6121bc43959
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830851"
---
# <a name="set-up-ui-flows-and-power-automate-desktop-preview"></a>Konfigurer flow for brugergrænseflade og Power Automate Desktop (prøveversion)

Før du kan bruge din enhed til at oprette flow for brugergrænsefladen, skal du sikre dig, at den opfylder de krav, der er angivet her.

> [!TIP]
> Før du opretter et flow for brugergrænsefladen, skal du kontrollere [listen over connectorer](https://flow.microsoft.com/connectors/) for at se, om der allerede er en connector for det program, du vil automatisere. Hvis det er tilfældet, kan du overveje at oprette et flow i stedet for et flow for brugergrænsefladen. Du kan også oprette din [egen connector](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Forudsætninger

- Enten en [betalt](https://flow.microsoft.com/pricing/) eller en [prøve](https://flow.microsoft.com/manage/)-licens til Power Automate-overvåget RPA.

- En arbejds- eller skolekonto til at logge på din Windows-enhed med administratorrettigheder og Power Automate.

- En enhed, der kører Windows 10 Pro, Windows 10 Entreprise, Windows Server 2016 eller Windows Server 2019.

- [Microsoft Edge](https://www.microsoft.com/edge/) (version 80 eller nyere) eller en Google Chrome-browser.

- Et [miljø](https://docs.microsoft.com/power-platform/admin/environments-overview) med en [Common Data Service-database](https://docs.microsoft.com/power-platform/admin/create-database).

- Et tilsluttet understøttet tastatur.

>[!IMPORTANT]
>Du skal have de nyeste versioner af hver enkelt komponent for at optage, teste eller køre flow for brugergrænsefladen.

## <a name="install-ui-flows-and-power-automate-desktop-preview-on-your-device"></a>Installer flow for brugergrænseflade og Power Automate Desktop (prøveversion) på enheden

Installationsprogrammet indeholder alle de komponenter, du skal bruge for at kunne registrere, redigere og teste dine automatiseringer. 

Følg disse trin for at installere appen til flow for brugergrænsefladen:

1. [Download installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Åbn filen **Setup.Microsoft.PowerAutomate.UIflow.exe**. 

   Du finder sandsynligvis denne fil i mappen **Downloads**, efter du har downloadet den i forrige trin.

1. Følg vejledningen i installationsprogrammet til **Konfiguration af flow for brugergrænsefladen** for at fuldføre installationen.
1. Når installationsprogrammet starter, skal du vælge for at installere flow for brugergrænseflade, Power Automate Desktop (prøveversion) eller begge dele. 
1. Angiv de ønskede indstillinger for de enkelte funktioner i installationen. 

>[!IMPORTANT]
>Installationspakken til flow for brugergrænsefladen installerer Webdriver-komponenten og browserudvidelsen til flow for brugergrænsefladen. Begge er nødvendige for at registrere, teste og køre flow for brugergrænsefladen på skrivebordet.
>Pakken Power Automate Desktop (prøveversion) installerer Power Automate Desktop-appen, tredjepartskomponenterne og browserudvidelserne.

![Billede af installationsindstillinger](https://user-images.githubusercontent.com/48315710/92633908-c546e380-f2d3-11ea-8976-6a7609eb70f8.png)

### <a name="set-data-collection-options"></a>Angiv indstillinger for dataindsamling

Under installationen kan du ændre standardindstillingerne, hvis du ikke vil sende forbrugsdata til Microsoft. Det gør du ved at fjerne markeringen af **Tillad, at Microsoft indsamler forbrugsdata for at forbedre flow for brugergrænseflade**.

## <a name="activate-the-ui-flows-and-power-automate-desktop-preview-browser-extension"></a>Aktivér flow for brugergrænseflade og browserudvidelsen Power Automate Desktop (prøveversion) 

Når installationen er fuldført, skal du kontrollere, at udvidelserne til flow for brugergrænseflade og Power Automate Desktop (prøveversion) er aktive på de browsere, du bruger.

![Billede af Installationen lykkedes](https://user-images.githubusercontent.com/48315710/92635143-a5b0ba80-f2d5-11ea-96ec-4672d84d13b3.png)

1. Vælg et af de links, der vises i installationsprogrammet. Hvis du f.eks. vil bruge flow for brugergrænseflade på Microsoft Edge, skal du vælge linket **Microsoft Edge**.

   Lageret for din browser åbnes direkte på den offentlige side for udvidelsen.

1. Bekræft, at udvidelsen er installeret. Følg disse trin, hvis den ikke er installeret:

#### <a name="microsoft-edge"></a>Microsoft Edge: 
- Vælg **Hent**, og vælg derefter **Tilføj udvidelse**, når du bliver bedt om det. 
- Hvis du kan se meddelelsen: *Denne udvidelse er deaktiveret i Microsoft Edge*, skal du vælge **Slå udvidelse til** øverst på siden.

#### <a name="google-chrome"></a>Google Chrome: 
- Vælg **Føj til Chrome**, og vælg derefter **Aktivér udvidelse**, når du bliver bedt om det. 
- Hvis du kan se meddelelsen: *Dette element er deaktiveret i Chrome* øverst på siden, skal du vælge **Aktivér dette element**.

> [!TIP]
> Hvis du ikke kan aktivere udvidelserne i din browser, skal du kontrollere følgende:
> - Du skal bruge [Microsoft Edge](https://www.microsoft.com/edge/) (version 80 eller nyere) eller Google Chrome. Firefox understøttes kun med Power Automate Desktop-udvidelsen.
> - Hvis udvidelsen ikke vises, skal du geninstallere den ved hjælp af [installationsprogrammet til flow for brugergrænsefladen](https://go.microsoft.com/fwlink/?linkid=2102613).


## <a name="install-selenium-ide-to-automate-web-applications-with-ui-flows"></a>Installér Selenium IDE for at automatisere webprogrammer med flow for brugergrænseflade

Selenium IDE er et værktøj i åben kildekode, der giver dig mulighed for at optage og afspille personlige interaktioner på websteder.

Med flows for brugergrænsefladen kan du køre Selenium IDE-scripts fra Power Automate og gemme dem på en sikker måde (med passende it-styring) i Common Data Service.

Følg disse trin for at installere Selenium IDE:

1. [Download og installér](https://go.microsoft.com/fwlink/?linkid=2107665) Selenium IDE til [Microsoft Edge](https://www.microsoft.com/edge/) (version 80 eller nyere) eller Google Chrome.

1. I Microsoft Edge (version 80 eller nyere) skal du vælge **Tillad udvidelser fra andre lagre** og derefter vælge **Føj til Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Installere datagatewayen i det lokale miljø

Du skal bruge gatewayen til at udløse dit flow for brugergrænsefladen fra et [flow for en hændelse, en tidsplan eller en knap.](../getting-started.md#types-of-flows) på en fjernenhed.

>[!TIP]
>Gatewayen kræves ikke, hvis du kun vil oprette, redigere og teste dine flow på din enhed.

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
    - **Adgangskode**: Adgangskoden for din konto.
    - **Vælg en gateway**: Vælg den gateway, du vil bruge.

      ![Et skærmbillede, der viser, hvor du skal angive legitimationsoplysningerne for forbindelsen](../media/ui-flows-setup/credentials-screen.png)

1. Vælg **Opret**.

## <a name="troubleshoot-missing-gateway"></a>Foretag fejlfinding af manglende gateway

Du kan muligvis ikke finde gatewayen på listen under oprettelse af forbindelse af følgende årsager:

- Gatewayen kan være installeret i et andet område end dit Power Automate-område. Du kan løse dette problem ved at fjerne gatewayen fra enheden og derefter geninstallere den ved at vælge [det rette Power Automate-område](../regions-overview.md#region-mappings-for-power-automate-and-gateways).
- Gatewayen blev slettet af ejeren.

## <a name="supported-keyboard-layouts"></a>Understøttede tastaturlayout

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
Bulgarsk   |   Galicisk    |   Litauisk  |   Slovensk
Katalansk |   Tysk      |Malaysisk  |   Spansk
Kinesisk (forenklet)    |   Græsk   |   Norsk   |   Svensk
Kinesisk (traditionelt)   |   Hindi   |   Polsk  |   Thai
Kroatisk    |   Ungarsk   |   Portugisisk (Brasilien) |   Tyrkisk
Tjekkisk   |   Indonesisk  |   Portugisisk (Portugal)       |Ukrainsk
Dansk  |   Italiensk |   Rumænsk    |   Vietnamesisk
Nederlandsk       |Japansk   |   Russisk 
Estisk    |Kasakhisk |   Serbisk (kyrillisk, Serbien)  
Finsk     |Koreansk     |Serbisk (latinsk, Serbien)

>[!NOTE]
>Power Automate Desktop (prøveversion) er kun tilgængelig på engelsk, fransk, tysk, japansk, spansk. Eksempelvisningsfunktionerne er ikke beregnet til produktionsformål og kan have begrænset funktionalitet.


## <a name="uninstall-ui-flows"></a>Fjern Flow for brugergrænseflade

1. Åbn menuen **Start** > **Indstillinger** > **Apps**.
1. Søg efter **Flow for brugergrænseflade**, og vælg den derefter.
1. Vælg **Fjern**.

## <a name="limitations"></a>Begrænsninger

Følgende understøttes ikke:
- Installationer af Windows 10 Home understøttes ikke.

-   Flow for brugergrænseflade på skrivebordet

    -   Flere skærme.
    -   Dobbeltklik, peg med musen, input med touch/pen.
    -   Interaktioner i Windows (Stifinder, menuen Start, proceslinje osv.)

-   Flow for brugergrænseflade på internettet

    -   Højreklik.
    -   Oplysninger om brugersessionen (f.eks. cookies) genbruges ikke under afspilning. Du skal redigere scriptet for at integrere logonoplysninger, når det kræves af websteder.

- Power Automate Desktop (prøveversion)

   - touch-/penneinput

Du finder de funktionsspecifikke begrænsninger i dokumentationen for hver funktion.

## <a name="learn-more"></a>Flere oplysninger

- [Opgrader dine flow for brugergrænsefladen](upgrade.md) fra tidligere udgivelser
- Få mere at vide om [oprettelse af flow for brugergrænseflade på skrivebordet](create-desktop.md).
- Få mere at vide om, hvordan du [opretter flow for brugergrænsefladen på internettet](create-web.md).
- Få mere at vide om, hvordan du kører [flow for brugergrænseflade](run-ui-flow.md).
- Få mere at vide om, hvordan du [administrerer flow for brugergrænseflade.](manage.md).
- Få mere at vide om [gatewayen i det lokale miljø](../gateway-reference.md#use-a-gateway).
