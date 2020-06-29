---
title: Få mere at vide om, hvordan du opretter flow for brugergrænseflade med WinAutomation | Microsoft Docs
description: Få mere at vide om, hvordan du opretter flow for brugergrænseflade med WinAutomation.
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
ms.date: 05/19/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1b9bd3a1f79885d17406e882b4432eff930d342c
ms.sourcegitcommit: 549224cf13fc761f473c880e8d0d8f2741cc7b0f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435034"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>Bruge Softomotives WinAutomation sammen med flow for brugergrænseflade

Din ikke-automatiserede Power Automate RPA-licens (betalt eller prøve) giver nu fuld adgang til Softomotives [WinAutomation](https://www.winautomation.com/). Dette dokument fører dig gennem hentning af WinAutomation-processer, der kører med Power Automate.

Eksisterende WinAutomation-brugere kan få mere at vide på [Softomotives supportside](https://support.softomotive.com/support/home)

## <a name="overview-for-existing-ui-flows-users"></a>Oversigt for eksisterende brugere af flow for brugergrænseflade

[Download](https://aka.ms/rpaDesktopAutomationInstallPage) for at installere og derefter logge på WinAutomation med den samme arbejds- eller skolekonto som i Power Automate. Når du har oprettet en proces i WinAutomation, kan du køre den ikke-automatiseret eller automatiseret med det samme fra Power Automate ved hjælp af et flow for brugergrænseflade. Det kan du gøre ved at benytte følgende fremgangsmåde:

1. Start en optagelse af flow for brugergrænseflade.
1. Åbn kommandoprompten.
1. Angiv kommandoen for at udløse processen.
   - I forbindelse med en proces, der ikke kræver inputvariabler, skal du angive *"%programfiles%\WinAutomation\WinAutomationController.exe" /start "/My robots/MyAutomationName"*.
   - Hvis det skal være en proces, der kræver inputvariabler, skal du angive dem efter procesnavnet. Hvis en proces f.eks. kaldes *MyAutomationName* og kræver *VariableA* og *VariableB*, skal du placere deres værdier som denne: *"%programfiles%\WinAutomation\WinAutomationController.exe" /start "/My Robots/MyAutomationName" ValueA ValueB.*

   >[!TIP] 
   >Du kan bruge input af flow for brugergrænseflade og dynamisk indhold til at ændre WinAutomation-målprocessen fra Power Automate.

1. Tryk på Enter ved kommandoprompten, og stop derefter optagelsen af flow for brugergrænseflade. 
   Flow for brugergrænseflade henter alle de nødvendige oplysninger på det tidspunkt, hvor WinAutomation-processen starter.
   
1. Føj flow for brugergrænseflade til et flow, og vælg derefter *automatisk* eller *ikke-automatisk* som kørselstype.

   >[!TIP] 
   >I WinAutomation-processen skal du bruge handlingen *Hent argumenter til kommandolinjen* til at hente argumenterne for kommandolinjen. Argumenterne er i en matrix. Brug deres indeks til at referere til de enkelte argumenter.
   
## <a name="set-up-winautomation"></a>Konfigurere WinAutomation

>[!TIP]
>Automatiseringsscripts i WinAutomation kaldes **processer**. I Power Automate kaldes automatiseringsscripts *flow* eller *flow for brugergrænseflade*.

Før du opretter en WinAutomation-proces, skal du kontrollere [listen over connectorer](https://flow.microsoft.com/connectors/) for at se, om der allerede er en connector for det program, du vil automatisere. Hvis det er tilfældet, kan du overveje at oprette et flow i stedet for et flow for brugergrænsefladen. Du kan også [oprette din egen connector](https://docs.microsoft.com/connectors/custom-connectors/). Generelt giver API-baserede connectorer en bedre overordnet oplevelse end automatisering af brugergrænsefladen med hensyn til skalerbarhed, pålidelighed og lavere omkostninger.

>[!TIP]
>Hvis du vil køre WinAutomation-scripts fra Power Automate, skal du først starte afspilningen af scripts fra flow for brugergrænseflade.

## <a name="prerequisites"></a>Forudsætninger 

Hvis du vil køre WinAutomation som en del af Power Automate, skal du gøre følgende:
1. Kontrollér, at maskinen overholder [kravene til flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites).
1. Installer appen til [flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/setup), og installer og konfigurer derefter datagateway i det lokale miljø.

## <a name="licensing"></a>Licensering

Du skal have en *Plan pr. bruger med ikke-automatiseret RPA* for at kunne bruge flow for brugergrænseflade og WinAutomation. Hvis du ikke har en forudbetalt plan, kan du starte en prøveversion af *Plan pr. bruger med ikke-automatiseret RPA* ved at gå til Power Automate og derefter vælge fanen **Flow for brugergrænseflade** under **Mine flow**. Du får vist prøvedialogboksen, hvor du kan starte prøveversionen.

![Starte en prøveversion eller købe en licens](../media/create-processes/trial.png)

Hvis du allerede har en forudbetalt plan, eller du tidligere har brugt en prøveversion, kan du ikke starte en ny prøveversion. I dette tilfælde skal du bede din administrator om at købe eller starte en prøveversion af Power Automate med *Plan pr. bruger med ikke-automatiseret RPA*. Den kan købes ved at gå til **Fakturering** > **Køb tjenester** i Microsoft 365 Administration og derefter søge efter den rette plan.

![Plan pr. bruger med ikke-automatiseret RPA](../media/create-processes/license-plan.png)

Til sidst skal de, når de har købt en plan eller fået den gratis prøveversion, tildele en bruger denne plan. 

>[!NOTE]
>Når du tildeler en bruger en plan, kan der gå et par minutter, før tildelingen træder i kraft.

>[!WARNING]
>Du skal have den nyeste version af hver enkelt komponent for at optage, teste eller køre UI Automation.

## <a name="install-winautomation"></a>Installere WinAutomation

Når flow for brugergrænseflade er installeret på computeren, kan du installere WinAutomation for at optage, redigere og teste automatiseringsscripts til skrivebordet ved at benytte følgende fremgangsmåde:

1.  Download [installationsprogrammet til WinAutomation](https://aka.ms/rpaDesktopAutomationInstallPage).

1.  Åbn filen **WinAutomationSetup.exe**. Denne fil ligger sandsynligvis i mappen **Overførsler**.

1.  Følg vejledningen i installationsprogrammet til WinAutomation for at fuldføre installationen. Under installationen skal du kontrollere, at **Licenstype** er angivet til **Microsoft Power Automate**.

## <a name="sign-in-to-winautomation"></a>Logge på WinAutomation 

Når installationen er fuldført, skal du starte WinAutomation-konsollen fra menuen Start i Windows. Programmet startes, og du bliver bedt om at logge på. Hvis du allerede har en *Plan pr. bruger med ikke-automatiseret RPA*-licens til Power Automate, eller hvis du har en Power Automate-prøvelicens, skal du angive de brugerlegitimationsoplysninger, du bruger til [Power Automate](https://flow.microsoft.com). Du kan også gå til [prisfastsættelsessiden](https://flow.microsoft.com/pricing/) for at få mere at vide om denne licens eller for at få en prøvelicens.

Hvis du ikke har en gyldig licens, får du vist denne fejlmeddelelse.

![Licensfejl](../media/create-processes/license-error.png)


>[!WARNING]
>Du skal bruge din lejeradministrator for at give samtykke til at bruge din Power Automate-arbejds- eller skolekonto sammen med WinAutomation. I forbindelse hermed kan de installere WinAutomation, logge på med deres lejeradministratorkonto og derefter tildele samtykke.

![Anmode om tilladelser](../media/create-processes/permissions-request.png)

Når du er logget på, kan du se WinAutomation-konsollen med et par eksempelprocesser. Du kan komme i gang ved at gå til **Indstillinger** > **Hjælp** > **Introduktion** og derefter gennemgå nogle få eksempler på oprettelse af enkle processer. Derudover er der flere [WinAutomation-introduktionsvejledninger](https://www.winautomation.com/support/tutorials/) tilgængelige.

## <a name="run-winautomation-processes-from-power-automate"></a>Køre WinAutomation-processer fra Power Automate

Når du har defineret dit automatiseringsscript i WinAutomation, kan du køre det fra et flow i Power Automate ved hjælp af flow for brugergrænsefladens understøttelse af programstart med kommandoprompten. Du kan få mere at vide om, hvordan du opretter og tester flow for brugergrænseflade, ved at gå [her](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

### <a name="running-winautomation-processes"></a>Kørsel af WinAutomation-processer 

Hvis du vil køre en WinAutomation-proces uden konsolmiljøet, kan du bruge kommandoen WinAutomationController.EXE. Denne proces ligger i installationsmappen til WinAutomation og kan startes fra **kommandoprompten** i Windows. Selvom der er mange nyttige parametre til at starte automatiseringen, skal du bruge flaget '/start', som vil starte den angivne proces. Her er et eksempel på kommandoen: **WinAutomationController /start processPath**

*processPath* er stien i WinAutomation-konsollen til processen fra en basismappe i Mine processer i ruden Mapper til venstre. Hvis du har anbragt processen i en undermappe, skal du medtage de pågældende oplysninger i processPath. Bemærk, at hvis processPath indeholder mellemrum, skal den omsluttes af dobbelte anførselstegn (f.eks. WinAutomationController /start "/My Processes/../../processName").

### <a name="launching-winautomation-processes-from-ui-flows"></a>Start af WinAutomation processer fra flow for brugergrænseflade

Når du har identificeret kommandoen til at køre WinAutomation-processer herover, kan du nu kalde denne kommando direkte fra flow for brugergrænseflade. Dette gør du på denne måde:

1.  Tilføj et nyt trin til optagelse i flow for brugergrænseflade ved at klikke på **Start optager**, hvis du har et flow for brugergrænseflade. Hvis du allerede har foruddefinerede trin i flow for brugergrænseflade, kan du klikke på **Nyt trin** og derefter **Optagerappen** for at starte optageren. Der er flere oplysninger om optagelsesoplevelsen [her](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

1.  Vælg **Optag** i den startede optager.

1.  Åbn **kommandoprompt**-appen i Windows.

1.  Skriv den WinAutomationController-kommando, du har oprettet tidligere (f.eks. WinAutomationController /start "/My Processes/../../process").

1.  Vælg **Udført** i optageren.

Du får en meddelelse om, at optageren tilføjer nye trin i dit flow for brugergrænseflade, der nu inkluderer start af WinAutomationController.


>[!TIP]
>Flow for brugergrænseflade kan køre i både automatiserede og ikke-automatiserede tilstande. Du kan også køre WinAutomationController i begge tilstande. Hvis du udfører flow for brugergrænseflade i en automatisk klynge, skal du kontrollere, at den WinAutomationController-kommando, der er angivet ovenfor, kan køre på alle computere i klyngen. Der er flere oplysninger om automatiserede og ikke-automatiserede flow for brugergrænseflade [her](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).

## <a name="waiting-for-a-winautomation-process-to-complete-in-ui-flows"></a>Venter på, at en WinAutomation-proces fuldføres i flow for brugergrænseflade

WinAutomationController.exe kører som standard processer i baggrunden. Hvis du vil have flow for brugergrænseflade til at vente på, at automatisering af WinAutomation-proces er fuldført, kan du oprette en meddelelsesboks med oplysninger i slutningen af WinAutomation-processen ved hjælp af kommandoen **Vis meddelelse** og derefter vente i flow for brugergrænseflade for at klikke på den pågældende knap i denne meddelelsesboks. Dette gør du på denne måde:

1.  Tilføj kommandoen "Vis meddelelse" som sidste trin i din WinAutomation-proces. Det kan du gøre ved at filtrere panelet Handlinger til venstre for at finde frem til Vis meddelelse og trække og slippe kommandoen til processcripteditoren. Du kan give den en sigende titel og beskrivelse og bevare standardknapvalget, der viser knappen OK.
1.  Kør WinAutomation-processen, indtil meddelelsesboksen vises. 
1.  Tilføj en ny optagelse i flow for brugergrænseflade, klik på titlen i feltet Vis meddelelse, og klik derefter på OK. 
1.  Stop optagelsen ved at klikke på Udført. Scriptet vises nu i flow for brugergrænseflade med et nyt sæt handlinger, der skal bruges til at klikke på i dialogboksen og kassere meddelelsesfeltet.
1.  Og endelig skal du få flow for brugergrænseflade til at give WinAutomation en vis tid til at blive fuldført. Det kan du gøre ved at udvide den tidligere kommando Send taster, som starter kommandoen WinAutomationController.exe, udvide for at få vist de avancerede indstillinger og angive egenskaben Vent efter til at vente på den maksimale tid, som det tager WinAutomation-processcriptet at blive udført.


## <a name="uninstall-winautomation"></a>Fjerne WinAutomation

1.  Åbn menuen **Start** \> **Indstillinger** \> **Apps**.

1.  Søg efter **WinAutomation**, og vælg den derefter.

1.  Vælg **Fjern**.

## <a name="troubleshooting-winautomation-licensing-issues"></a>Fejlfinding af WinAutomation-licensproblemer

Hvis du modtager licensfejl under starten af WinAutomation, skal du sikre dig, at den bruger, du logger på som, har en gyldig licens til flow for brugergrænseflade. Det kan du gøre sådan: 

1.  Gå til [Power Automate](https://flow.microsoft.com), og log på.
1.  Vælg Mine flows på navigationslinjen i venstre side.
1.  Vælg flow for brugergrænseflade på siden til højre. Du skal muligvis starte en prøveversion eller bede din administrator om at gøre det.

Hvis du vil nulstille de licensoplysninger, der er gemt af WinAutomation, kan du slette følgende fil: %localappdata%\Softomotive\WinAutomation\msalcache.bin3

>[!NOTE]
>Denne licens cachelagres, når brugerne starter WinAutomation, mens de har forbindelse til internettet. 


## <a name="learn-more"></a>Få mere at vide

- Læs om [WinAutomation-erhvervelsen](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)
- Få support til [WinAutomation](https://support.softomotive.com/support/home).
- Kom godt i gang med [WinAutomation-selvstudier](https://www.winautomation.com/support/tutorials/).
- Få mere at vide om [oprettelse af flow for brugergrænseflade på skrivebordet](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).
- Få mere at vide om, hvordan du [kører flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).
- Få mere at vide om, hvordan du [administrerer flow for brugergrænseflade.](https://docs.microsoft.com/power-automate/ui-flows/manage)
- Få mere at vide om [gatewayen i det lokale miljø](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway).
