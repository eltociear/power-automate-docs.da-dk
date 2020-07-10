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
ms.date: 06/30/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: dd3019c457316e58f86bda829bc2402b2be824a6
ms.sourcegitcommit: a51ebdce86c0c2399afa4ba36591fb3230eb82d9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527292"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>Bruge Softomotives WinAutomation sammen med flow for brugergrænseflade


Her er nogle tip, inden du går i gang med at bruge WinAutomation med flows for brugergrænseflade.

1.  Din Power Automate-overvågede RPA-licens (betalt eller gratis) giver dig fuld adgang til [WinAutomation](https://www.winautomation.com/). Dette dokument fører dig gennem hentning af WinAutomation-processer, der kører med Power Automate.

1.  Automatiseringsscripts i WinAutomation kaldes **processer**. I Power Automate kaldes automatiseringsscripts *flow* eller *Flows for brugergrænseflade*.

1.  Før du opretter en WinAutomation-proces, skal du kontrollere [listen over connectorer](https://flow.microsoft.com/connectors/) for at se, om der allerede er en connector for det program, du vil automatisere. Hvis det er tilfældet, kan du overveje at oprette et flow i stedet for et flow for brugergrænsefladen. Du kan også [oprette din egen connector](https://docs.microsoft.com/connectors/custom-connectors/). Generelt giver API-baserede connectorer en bedre overordnet oplevelse end automatisering af brugergrænsefladen med hensyn til skalerbarhed, pålidelighed og lavere omkostninger.

1.  Eksisterende WinAutomation-licenserede brugere kan få mere at vide på [Softomotives supportside](https://support.softomotive.com/support/home)

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil køre WinAutomation som en del af Power Automate, skal du gøre følgende:

1.  Kontrollér, at maskinen overholder [kravene til flows for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites).

2.  Installer appen til [flows for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/setup) , og installer og konfigurer derefter datagateway i det lokale miljø.

>[!IMPORTANT]
>Du skal have den nyeste version af WinAutomation og flows for brugergrænseflade for at kunne optage, teste eller køre UI-automatisering.

## <a name="licensing"></a>Licensering

Du skal have en Power Automate *Plan pr. bruger with overvåget RPA* for at kunne bruge flows for brugergrænseflade og WinAutomation. Hvis du ikke har en betalt plan, kan du starte en gratis prøveversion fra Power Automate.

 
## <a name="install-winautomation"></a>Installere WinAutomation

1.  Download [installationsprogrammet til WinAutomation](https://aka.ms/rpaDesktopAutomationInstallPage).

1.  Kør filen **WinAutomationSetup.exe** . Denne fil ligger sandsynligvis i mappen **Overførsler** .

1.  Følg vejledningen i installationsprogrammet til WinAutomation for at fuldføre installationen. Under installationen skal du kontrollere, at **Licenstype** er angivet til **Microsoft Power Automate**.

## <a name="sign-in-to-winautomation"></a>Logge på WinAutomation

1.  Når installationen er fuldført, skal du starte WinAutomation-konsollen fra menuen Start i Windows.

1.  Programmet startes, og du bliver bedt om at logge på. Angiv de brugerlegitimationsoplysninger, du bruger til [Power Automate](https://flow.microsoft.com/). Hvis du ikke har en gyldig licens, får du vist denne fejlmeddelelse. Du kan også gå til [prisfastsættelsessiden](https://flow.microsoft.com/pricing/) for at få mere at vide om denne licens eller for at få en prøvelicens.

      ![Licensfejl](../media/create-processes/license-error.png)

      >[!IMPORTANT]
      > Du skal bruge din lejeradministrator for at give samtykke til at bruge din Power Automate-arbejds- eller skolekonto sammen med WinAutomation. Hvis du vil gøre det, skal din administrator installere WinAutomation, logge på med deres lejeradministratorkonto og derefter tildele samtykke.

      ![Anmode om tilladelser](../media/create-processes/request-permissions.png)

1.  Når du bliver bedt om at oprette en Masternøgle under logon, skal du oprette en.

1.  Når du er logget på, kan du se WinAutomation-konsollen med et par eksempelprocesser. Du kan komme i gang ved at gå til **Indstillinger** \> **Hjælp** \> **Introduktion**, og derefter gennemgå nogle få eksempler på oprettelse af enkle processer eller oplysninger om, hvordan du kan se oplysninger [herfra](https://docs.winautomation.com/en/building-a-simple-process.html). Du kan få mere at vide på [WinAutomation, introduktionsvejledninger](https://www.winautomation.com/support/tutorials/).

Du kan nu oprette dine egne WinAutomation-processer og teste dem lokalt.

## <a name="run-winautomation-processes-from-power-automate"></a>Køre WinAutomation-processer fra Power Automate

1.  Når du har oprettet automatiseringsprocessen i WinAutomation, kan du køre den fra et flow i Power Automate via flows for brugergrænseflade(stationære computere) overvåget eller uovervåget. **Bemærk**! Du kan få mere at vide om, hvordan du opretter og kører flows for brugergrænseflade ved at gå videre [her](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

1.  Opret et nyt flos for brugergrænseflade på skrivebordet Slet det første standardtrin i "Post-app".

      ![Slet trin i post-app](../media/create-processes/delete-record-step.png)

1.  Vælg **Nyt trin**, **WinAutomation**, og vælg derefter **Kør WinAutomation (eksempel)**.

      ![Vælg Kør WinAutomation](../media/create-processes/select-run-winautomation.png)

1.  På kortet **Kør WinAutomation (eksempel)** skal du udfylde processtien og eventuelle valgfrie argumenter for kommandolinjen for den WinAutomation-proces, du vil køre.

      ![WinAutomation-kort](../media/create-processes/winautomation-card.png)

   >[!NOTE]
   >Du skal oprette og gemme WinAutomation-processer lokalt. *Processtien* skelner mellem store og små bogstaver i WinAutomation-konsollen til processen fra en basismappe med mine processer i ruden med mapper i venstre side. Hvis du har anbragt processen i en undermappe, skal du medtage de pågældende oplysninger i ProcessPath. Sæt ikke anførselstegn rundt om processtien.

   >[!TIP]
   >Du kan bruge flows for brugergrænseflade og dynamisk indhold i processtien og argumenterne for destinations-WinAutomation fra Power Automate-flowet.

1.  Du kan nu gemme og teste flows for brugergrænseflade for at se, hvordan den starter WinAutomation-processen.

1.  Tilføj derefter flow for brugergrænseflade til et flow. Du kan også oprette forbindelse til andre Power Automate-forbindelser og udløsere.

1.  Du kan derefter vælge *overvåget* eller *ikke-overvåget* som kørselstype.

    >[!TIP]
    >I WinAutomation-processen kan du bruge handlingen *Hent argumenter til kommandolinjen* til at hente argumenterne for kommandolinjen. Argumenterne er i en matrix. Brug deres indeks til at referere til de enkelte argumenter.

    >[!IMPORTANT]
    >Send ikke følsom tekst, f. eks. adgangskoder, via kommandolinjeargumenterne.

    >[!IMPORTANT]
    >Hvis du kører flows for brugergrænseflade i en ikke-overvåget klynge, skal du kontrollere, at WinAutomation er installeret på alle de computere, som destinationsprocessen kopieres til. Der er flere oplysninger om automatiserede og ikke-automatiserede flows for brugergrænseflader [her](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).

1.  Du kan gemme og derefter køre flowet og se programmet start WinAutomation-processen. Flowet for brugergrænseflade returneres, når WinAutomation-processen fuldføres. Du kan få vist kørselsresultaterne fra Power Automate. Hvis processen ikke gennemføres, kan du også se fejlmeddelelserne.

    >[!TIP]
    >Hvis du modtager undtagelser, har du muligvis ikke de nyeste flow for brugergrænseflade installeret. Installer de [nyeste flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/upgrade).

1.  Gør følgende, hvis WinAutomation skal tage et skærmbillede, når en proces ikke fungerer:

1.  Højreklik på en proces i WinAutomation-konsollen, og vælg "Rediger egenskaber for proces". Gå til fanen "Fejlhåndtering", og vælg "Tilsidesæt standardindstillinger". Klik på "Tilføj et skærmbillede til loggene", og gem. Hvis en proces ikke lykkes, kan du få vist det skærmbillede, der er hentet under kørslen, i Power Automate-flow for brugergrænsefladen.  

    ![Skærmbillede med procesegenskaber](../media/create-processes/process-properties.png)

I øjeblikket er du nødt til at bruge bestemte WinAutomation-trin for at skrive resultater og outputs fra processen i en fil i skydeling eller sende resultaterne via e-mail. Du kan derefter bruge forbindelser fra Power Automate for at få adgang til og bruge disse resultater.

## <a name="how-to-obtain-an-rpa-trial-license"></a>Sådan får du en RPA-prøvelicens

Log på [Power Automate](https://flow.microsoft.com/), og vælg fanen **Flow for brugergrænseflade** under  **Mine flows**. Du får vist prøvedialogboksen, hvor du kan starte prøveversionen.

![Starte en prøveversion eller købe en licens](../media/create-processes/trial-buy.png)

Hvis du allerede har en forudbetalt plan, eller du tidligere har brugt en prøveversion, kan du ikke starte en ny prøveversion. I dette tilfælde skal du bede din administrator om at købe eller starte en prøveversion af Power Automate *-plan pr. bruger med ikke-automatiseret RPA*. Den kan købes ved at gå til **Fakturering** \> **Køb tjenester**  i Microsoft 365 Administration og derefter søge efter den rette plan.

![Plan pr. bruger med ikke-automatiseret RPA](../media/create-processes/per-user-rpa.png)

Til sidst skal de, når de har købt en plan eller fået den gratis prøveversion, tildele en bruger denne plan.

>[!IMPORTANT]
>Når du tildeler en bruger en plan, kan der gå et par minutter, før tildelingen træder i kraft.

## <a name="troubleshooting-winautomation-licensing-issues"></a>Fejlfinding af WinAutomation-licensproblemer

Hvis du modtager licenseringsfejl under lanceringen af WinAutomation, skal du sikre dig, at den bruger, du logger på som, har en gyldig Power Automate RPA-licens. Gør følgende:

1.  Gå til [Power Automate](https://flow.microsoft.com/) og log på.

1.  Vælg Mine flows på navigationslinjen i venstre side.

1.  Vælg flow for brugergrænseflade på siden til højre. Du kan også se, hvordan du kan oprette nye flows for brugergrænseflade, hvis du har den rette licens.

1.  Du skal muligvis starte en prøveversion eller bede administrator om at gøre det.

    >[!NOTE]
    >Licensen er cachelagret, når brugerne starter WinAutomation, mens de har forbindelse til internettet.

Hvis du vil nulstille de licensoplysninger, der er gemt af WinAutomation, kan du slette følgende fil: %localappdata%\\Softomotive\\WinAutomation\\msalcache.bin3.

## <a name="learn-more"></a>Få mere at vide

-   Flere oplysninger om [WinAutomation-erhvervelsen](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/)
-   Få support til [WinAutomation](https://support.softomotive.com/support/home).
-   Kom godt i gang med [WinAutomation-selvstudier](https://www.winautomation.com/support/tutorials/).
-   Få mere at vide om [oprettelse af flow for brugergrænseflade på skrivebordet](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).
-   Få mere at vide om, hvordan du [kører flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).
-   Få mere at vide om, hvordan du [administrerer flow for brugergrænseflade.](https://docs.microsoft.com/power-automate/ui-flows/manage)
-   Få mere at vide om [gatewayen i det lokale miljø](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway).
