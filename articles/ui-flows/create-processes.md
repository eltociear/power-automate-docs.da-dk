---
title: Lær mere om, hvordan du opretter flows for brugergrænseflade med WinAutomation | Microsoft Docs
description: Lær mere om oprettelse af flows for brugergrænseflade med WinAutomation.
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
ms.date: 07/08/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d4df7419712b406004c029c3bea75295c0e2990e
ms.sourcegitcommit: c3eee935e8e8c64963817d2a692a38e8c90400b3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/22/2020
ms.locfileid: "3835133"
---
# <a name="use-softomotives-winautomation-with-ui-flows"></a>Brug Softomotives WinAutomation med flows for brugergrænseflade

>[!IMPORTANT]
>Se dokumentationen til [Power Automate Desktop (prøveversion)](./desktop/introduction.md) for at få mere at vide om udviklingen i WinAutomation.

Her er nogle tip, inden du går i gang med at bruge WinAutomation sammen med flows for brugergrænsefladen.

1.  Din Power Automate-licens til deltagelse i RPA (betalt eller prøveversion) giver dig fuld adgang til [WinAutomation](https://www.winautomation.com/). I dette dokument føres du gennem hentning af WinAutomation-processer, der kører med Power Automate.

1.  Automatiseringsscripts i WinAutomation kaldes **Processer**. I Power Automate kaldes automatiseringsscripts *flow* eller *Flows for brugergrænseflade*.

1.  Før du opretter en WinAutomation-proces, skal du kontrollere [listen over connectorer](https://flow.microsoft.com/connectors/) for at se, om den applikation, du vil automatisere, allerede har en connector. Hvis det er tilfældet, kan du overveje at oprette et flow i stedet for et flow for brugergrænsefladen. Du kan også [oprette din egen connector](https://docs.microsoft.com/connectors/custom-connectors/). API-baserede connectorer giver generelt en bedre oplevelse end automatisering af brugergrænsefladen med hensyn til skalerbarhed, pålidelighed og lavere omkostninger.

1.  Eksisterende WinAutomation-licenserede brugere kan lære mere på [supportsiden til Softomotive](https://support.softomotive.com/support/home)

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil køre WinAutomation som en del af Power Automate, skal du gøre følgende:

1.  Kontrollér, at maskinen overholder [kravene til flows for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/setup#prerequisites).

2.  Installer appen til [flows for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/setup) , og installer og konfigurer derefter datagateway i det lokale miljø.

>[!IMPORTANT]
>Du skal have den seneste version af WinAutomation og flows for brugergrænsefladen for at kunne optage, teste eller køre automatisering af brugergrænsefladen.

## <a name="licensing"></a>Licensering

Du skal have en Power Automate-plan af typen *Pr. bruger med overvåget RPA* for at bruge flows for brugergrænsefladen og WinAutomation. Hvis du ikke har en betalt plan, kan du starte en gratis prøveversion fra Power Automate.

 
## <a name="install-winautomation"></a>Installer WinAutomation

1.  Hent [WinAutomation-installationsprogrammet](https://aka.ms/rpaDesktopAutomationInstallPage).

1.  Kør filen **WinAutomationSetup.exe** . Denne fil ligger sandsynligvis i mappen **Overførsler** .

1.  Følg instruktionerne i WinAutomation-installationsprogrammet for at fuldføre installationen. Under installationen skal du kontrollere, at **Licenstype** er angivet til **Microsoft Power Automate**.

## <a name="sign-in-to-winautomation"></a>Log på WinAutomation

1.  Når installationen er fuldført, skal du starte WinAutomation-konsollen fra menuen Start i Windows.

1.  Programmet startes, og du bliver bedt om at logge på. Angiv de brugerlegitimationsoplysninger, du bruger til [Power Automate](https://flow.microsoft.com/). Hvis du ikke har en gyldig licens, får du vist denne fejlmeddelelse. Du kan også gå til [prisfastsættelsessiden](https://flow.microsoft.com/pricing/) for at få mere at vide om denne licens eller for at få en prøvelicens.

      ![Licensfejl](../media/create-processes/license-error.png)

      >[!IMPORTANT]
      > Du skal bruge din lejeradministrator for at give samtykke til at bruge din Power Automate-arbejds- eller skolekonto sammen med WinAutomation. Til dette formål skal din administrator installere WinAutomation, logge på med deres lejeradministratorkonto og derefter tildele samtykke.

      ![Anmode om tilladelser](../media/create-processes/request-permissions.png)

1.  Når du bliver bedt om at oprette en masternøgle, mens du logger på, skal du oprette den.

1.  Når du har logget på, kan du se WinAutomation-konsollen med nogle få eksempler på processer. Du kan komme i gang ved at gå til **Indstillinger** \> **HjælpK** \> **Kom i gang** og derefter gennemgå nogle få eksempler på oprettelse af enkle processer eller se oplysninger fra [WinAutomation-dokumenter: Oprettelse af en simpel proces](https://docs.winautomation.com/en/building-a-simple-process.html). Du kan lære mere med [selvstudier for introduktion til WinAutomation](https://www.winautomation.com/support/tutorials/).

Du kan nu oprette dine egne WinAutomation-processer og teste dem lokalt.

## <a name="run-winautomation-processes-from-power-automate"></a>Køre WinAutomation-processer fra Power Automate

1.  Når du har oprettet din automatiseringsproces i WinAutomation, kan du køre den fra et flow i Power Automate via flows for brugergrænseflade (stationære computere) eller automatiseret. 
    
    >[!TIP]
    >Få mere at vide om [oprettelse og kørsel af flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).

1.  Opret et nyt flos for brugergrænseflade på skrivebordet Slet det første standardtrin i "Post-app".

      ![Slet trin i post-app](../media/create-processes/delete-record-step.png)

1.  Vælg **Nyt trin**, vælg **WinAutomation**, og vælg derefter handlingen **Kør WinAutomation (prøveversion)**.

      ![Vælge Kør WinAutomation](../media/create-processes/select-run-winautomation.png)

1.  På kortet **Kør WinAutomation (prøveversion)** skal du udfylde processtien og eventuelle valgfrie argumenter for kommandolinjen for den WinAutomation-proces, du vil køre.

      ![WinAutomation-kort](../media/create-processes/winautomation-card.png)

   >[!NOTE]
   >Du skal oprette og gemme WinAutomation-processer lokalt. *Processti* er en sti, hvor der skelnes mellem store og små bogstaver, som du kan vælge på WinAutomation-konsollen for processen fra basismappen Mine processer i ruden Mapper til venstre. Hvis du har anbragt processen i en undermappe, skal du medtage de pågældende oplysninger i ProcessPath. Sæt ikke anførselstegn rundt om processtien.

   >[!TIP]
   >Du kan bruge input og og dynamisk indhold for brugergrænsefladens flows i WinAutomation-processens destinationssti og argumenterne fra Power Automate-flowet.

1.  Du kan nu gemme og teste dit flow for brugergrænsefladen, så du kan se, hvordan den starter WinAutomation-processen.

1.  Tilføj derefter flow for brugergrænseflade til et flow. Du kan også oprette forbindelse til andre Power Automate-forbindelser og udløsere.

1.  Du kan derefter vælge *overvåget* eller *ikke-overvåget* som kørselstype.

    >[!TIP]
    >I WinAutomation-processen kan du bruge handlingen *Hent argumenter for kommandolinje* til at hente argumenterne for kommandolinjen. Argumenterne er i en matrix. Brug deres indeks til at referere til de enkelte argumenter.

    >[!IMPORTANT]
    >Send ikke følsom tekst, f. eks. adgangskoder, via kommandolinjeargumenterne.

    >[!IMPORTANT]
    >Hvis du kører flows for brugergrænsefladen i en automatisk klynge, skal du sikre, at WinAutomation er installeret på alle de computere, som destinationsprocessen er kopieret til. Der er flere oplysninger om automatiserede og ikke-automatiserede flows for brugergrænseflader [her](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).

1.  Du kan gemme og derefter køre flowet og se, hvordan det starter WinAutomation-processen. Flowet for brugergrænsefladen returneres, når kørslen af WinAutomation-processen er fuldført. Du kan få vist kørselsresultaterne fra Power Automate. Hvis processen ikke gennemføres, kan du også se fejlmeddelelserne.

    >[!TIP]
    >Hvis du modtager undtagelser, har du muligvis ikke de nyeste flow for brugergrænseflade installeret. Installer de [nyeste flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/upgrade).

1.  Hvis WinAutomation skal tage et skærmbillede, når en proces mislykkes, skal du gøre følgende:

1.  Højreklik fra WinAutomation-konsollen på en proces, og vælg "Rediger egenskaber for proces". Gå til fanen "Fejlhåndtering", og vælg "Tilsidesæt standardindstillinger". Klik på "Tilføj et skærmbillede til loggene", og gem. Hvis en proces ikke lykkes, kan du få vist det skærmbillede, der er hentet under kørslen, i Power Automate-flow for brugergrænsefladen. Du kan finde flere oplysninger om procesegenskaber i [WinAutomation-dokumenter: Procesegenskaber](https://docs.winautomation.com/en/process-properties.html).  

    ![Skærmbillede med procesegenskaber](../media/create-processes/process-properties.png)

I øjeblikket skal du bruge bestemte WinAutomation-trin for at skrive resultater og output fra processen i en fil i skyen for at dele eller sende resultaterne via email. Du kan derefter bruge connectorer fra Power Automate for at få adgang til og bruge disse resultater.

## <a name="how-to-obtain-an-rpa-trial-license"></a>Sådan får du en RPA-prøvelicens

Log på [Power Automate](https://flow.microsoft.com/), og vælg fanen **Flow for brugergrænseflade** under **Mine flows**. Du får vist prøvedialogboksen, hvor du kan starte prøveversionen.

![Starte en prøveversion eller købe en licens](../media/create-processes/trial-buy.png)

Hvis du allerede har en forudbetalt plan, eller du tidligere har brugt en prøveversion, kan du ikke starte en ny prøveversion. I dette tilfælde skal du bede din administrator om at købe eller starte en prøveversion af Power Automate *-plan pr. bruger med ikke-automatiseret RPA*. Den kan købes ved at gå til **Fakturering** \> **Køb tjenester** i Microsoft 365 Administration og derefter søge efter den rette plan.

![Plan pr. bruger med ikke-automatiseret RPA](../media/create-processes/per-user-rpa.png)

Til sidst skal de, når de har købt en plan eller fået den gratis prøveversion, tildele en bruger denne plan.

>[!IMPORTANT]
>Når du tildeler en bruger en plan, kan der gå et par minutter, før tildelingen træder i kraft.

## <a name="troubleshooting"></a>Fejlfinding

### <a name="troubleshooting-winautomation-licensing-issues"></a>Fejlfinding af problemer med WinAutomation-licenser

Hvis du modtager licensfejl under starten af WinAutomation, skal du sikre dig, at den bruger, du logger på som, har en gyldig Power Automate RPA-licens. Gør følgende:

1.  Gå til [Power Automate](https://flow.microsoft.com/) og log på.

1.  Vælg Mine flows på navigationslinjen i venstre side.

1.  Vælg flow for brugergrænseflade på siden til højre. Du kan også se, hvordan du kan oprette nye flows for brugergrænseflade, hvis du har den rette licens.

1.  Du skal muligvis starte en prøveversion eller bede administrator om at gøre det.

    >[!NOTE]
    >Licensen cachelagres, når brugerne starter WinAutomation, mens de har forbindelse til internettet.

Hvis du vil nulstille de licensoplysninger, der er gemt i WinAutomation, kan du slette følgende fil: %localappdata%\\Softomotive\\WinAutomation\\msalcache.bin3.

### <a name="troubleshooting-other-issues"></a>Fejlfinding af andre problemer

Følg linkene i dette afsnit for at få hjælp til fejlfinding af de problemer, der kan opstå.

WinAutomation
- [Installationsfejl](https://support.softomotive.com/support/solutions/folders/35000220522)
- [Konsol](https://support.softomotive.com/support/solutions/folders/35000220523)
- [Procesfejl](https://support.softomotive.com/support/solutions/folders/35000220524)
- [Webautomatisering](https://support.softomotive.com/support/solutions/folders/35000220531)
- [Automatisering af brugergrænseflade](https://support.softomotive.com/support/solutions/folders/35000220532)
- [Excel-automatisering](https://support.softomotive.com/support/solutions/folders/35000220533)
- [Billedbehandling](https://support.softomotive.com/support/solutions/folders/35000220534)
- [Mailautomatisering](https://support.softomotive.com/support/solutions/folders/35000220535)
- [Databaser](https://support.softomotive.com/support/solutions/folders/35000220536)

ProcessRobot
- [Kontrolskrivebord](https://support.softomotive.com/support/solutions/folders/35000220525)
- [Process Studio](https://support.softomotive.com/support/solutions/folders/35000220526)
- [ProcessRobot-database](https://support.softomotive.com/support/solutions/folders/35000220528)
- [Robotfejl](https://support.softomotive.com/support/solutions/folders/35000220529)
- [Procesfejl](https://support.softomotive.com/support/solutions/folders/35000220530)
- [Webautomatisering](https://support.softomotive.com/support/solutions/folders/35000220531)
- [Automatisering af brugergrænseflade](https://support.softomotive.com/support/solutions/folders/35000220532)
- [Excel-automatisering](https://support.softomotive.com/support/solutions/folders/35000220533)
- [Billedbehandling](https://support.softomotive.com/support/solutions/folders/35000220534)
- [Mailautomatisering](https://support.softomotive.com/support/solutions/folders/35000220535)
- [Databaser](https://support.softomotive.com/support/solutions/folders/35000220536)


## <a name="best-practices-for-creating-processes"></a>Bedste praksis for oprettelse af processer

Her er nogle tip, du kan overveje, når du opretter processer.


WinAutomation

- [Udløsere](https://support.softomotive.com/support/solutions/folders/35000220511)
- [Webautomatisering](https://support.softomotive.com/support/solutions/folders/35000220512)
- [Automatisering af brugergrænseflade](https://support.softomotive.com/support/solutions/folders/35000220513)
- [Excel-automatisering](https://support.softomotive.com/support/solutions/folders/35000220514)
- [Tekstmanipulation](https://support.softomotive.com/support/solutions/folders/35000220515)
- [Billedbehandling](https://support.softomotive.com/support/solutions/folders/35000220516)
- [Mailautomatisering](https://support.softomotive.com/support/solutions/folders/35000220517)
- [Databaser](https://support.softomotive.com/support/solutions/folders/35000220518)
- [Matematiske funktioner](https://support.softomotive.com/support/solutions/folders/35000220519)
- [Variabler](https://support.softomotive.com/support/solutions/folders/35000220520)

ProcessRobot

- [Kontrolskrivebord](https://support.softomotive.com/support/solutions/folders/35000220537)
- [Dashboards](https://support.softomotive.com/support/solutions/folders/35000220538)
- [Udløsere](https://support.softomotive.com/support/solutions/folders/35000220521)
- [Webautomatisering](https://support.softomotive.com/support/solutions/folders/35000220512)
- [Automatisering af brugergrænseflade](https://support.softomotive.com/support/solutions/folders/35000220513)
- [Excel-automatisering](https://support.softomotive.com/support/solutions/folders/35000220514)
- [Tekstmanipulation](https://support.softomotive.com/support/solutions/folders/35000220515)
- [Billedbehandling](https://support.softomotive.com/support/solutions/folders/35000220516)
- [Mailautomatisering](https://support.softomotive.com/support/solutions/folders/35000220517)
- [Databaser](https://support.softomotive.com/support/solutions/folders/35000220518)
- [Matematiske funktioner](https://support.softomotive.com/support/solutions/folders/35000220519)
- [Variabler](https://support.softomotive.com/support/solutions/folders/35000220520)


## <a name="learn-more"></a>Flere oplysninger

-   Læs om [WinAutomation-anskaffelsen](https://flow.microsoft.com/blog/microsoft-acquires-softomotive-to-expand-low-code-robotic-process-automation-capabilities-in-microsoft-power-automate/).
-   Lær mere om [WinAutomation-dokumenter](https://docs.winautomation.com/index.html?lang=en).
-   Lær mere på [WinAutomation Academy](https://academy.softomotive.com/).
-   Få support til [WinAutomation](https://support.softomotive.com/support/home).
-   Kom hurtigt i gang med [WinAutomation-selvstudier](https://www.winautomation.com/support/tutorials/).
-   Få mere at vide om [oprettelse af flow for brugergrænseflade på skrivebordet](https://docs.microsoft.com/power-automate/ui-flows/create-desktop).
-   Få mere at vide om, hvordan du [kører flow for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/run-ui-flow).
-   Få mere at vide om, hvordan du [administrerer flow for brugergrænseflade.](https://docs.microsoft.com/power-automate/ui-flows/manage)
-   Få mere at vide om [gatewayen i det lokale miljø](https://docs.microsoft.com/power-automate/gateway-reference#use-a-gateway).
