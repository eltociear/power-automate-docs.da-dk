---
title: Få mere at vide om oprettelse af flow for brugergrænseflader | Microsoft Docs
description: Få mere at vide om oprettelse af flow for brugergrænseflader til skrivebordet til Windows-programmer.
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
ms.date: 03/28/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4c50db7a26c2657ec7152132ebdbbce9f17e31c7
ms.sourcegitcommit: 7b39517611bff350c760e76d0d6eed03739194a7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/20/2020
ms.locfileid: "3710532"
---
# <a name="create-and-test-desktop-ui-flows"></a>Opret og test flow for brugergrænsefladen på skrivebordet

I følgende trin viser vi, hvordan du kan automatisere appen Lommeregner, så den lægger to tal sammen og derefter gemmer resultatet til senere brug.

## <a name="create-a-desktop-ui-flow"></a>Oprette et flow for brugergrænseflader

> [!TIP]
> Du kan automatisere andre Windows Desktop-apps ved at følge et lignende mønster.

1. Sørg for, at din [enhed er klar](setup.md#prerequisites) til at oprette flow for brugergrænseflader.

1. Brug [Microsoft Edge (version 80 eller nyere)](https://www.microsoftedgeinsider.com) eller Google Chrome til at åbne [Power Automate](https://flow.microsoft.com), og log derefter på med den samme arbejds- eller skolekonto som på din enhed.

1. Vælg **Mine flow** > **Flow for brugergrænseflade** > **Nyt**.

   ![Oprette et nyt flow for brugergrænsefladen](../media/create-windows-ui-flow/create-new.png "Oprette et nyt flow for brugergrænsefladen")

1. Vælg **Skrivebordsapp**, og vælg derefter **Næste**.

   ![Vælge skrivebord](../media/create-windows-ui-flow/select-desktop.png "Vælge skrivebord") 

1. Angiv et navn til dit flow for brugergrænsefladen i feltet **Flownavn**, og vælg derefter **Næste**.

   ![Vælge skrivebord](../media/create-windows-ui-flow/give-a-name.png "Vælge skrivebord") 

1. Vælg **Næste** nederst for at springe over den valgfri skærm **Konfigurer input**, da vi ikke bruger input i denne gennemgang.

1.  Vælg **Download pakke**.
1.  Åbn filen **Setup.Microsoft.PowerAutomate.UIflow.exe**. Du finder sandsynligvis denne fil i mappen **Downloads**, efter du har downloadet den i forrige trin.
1.  Følg vejledningen i installationsprogrammet til Konfiguration af flow for brugergrænsefladen for at fuldføre installationen.

    Når installationsprogrammet til flow for brugergrænsefladen er fuldført, bliver du i browseren bedt om at aktivere udvidelsen.

1. I Microsoft Edge (version 80 eller nyere) skal du vælge hvert advarselsikon øverst til højre i browseren og derefter vælge **Aktivér udvidelse**.
1. På Google Chrome skal du vælge **Aktivér udvidelse**, når du bliver bedt om det.

   > [!TIP]
   > Hvis du ikke fik vist prompten i din browser, skal du kontrollere følgende:
   > - Du skal bruge browseren Microsoft Edge (version 80 eller nyere) eller Google Chrome.
   > - Du skal muligvis opdatere udvidelsen for [Microsoft Edge (version 80 eller nyere)](https://www.microsoft.com/store/collections/edgeextensions/pc) eller [Google Chrome](https://chrome.google.com/webstore/category/extensions).

   Fortsæt, når du har installeret udvidelsen.

1. Vælg kortet **Optag app** for at udvide det.

   ![Vælge Optag app](../media/create-windows-ui-flow/select-record-app.png "Vælge Optag app")

1. Vælg **Start optager**.

   ![Vælg Start optager](../media/create-windows-ui-flow/select-launch-recorder.png "Vælg Start optager")

   Optagerkontrolelementet vises øverst på skærmen.

   ![Optagerkontrolelementet](../media/create-windows-ui-flow/recorder-control.png "Optagerkontrolelementet")

1. Start appen Lommeregner.

     >[!TIP]
     >Når du holder musen over kontrolelementer i appen, kan du se en blå kontur rundt om hvert enkelt kontrolelement. Vent altid på den blå kontur, før du vælger et kontrolelement.
     >
     >Hvis elementet ikke er fremhævet med blåt, optages det muligvis ikke korrekt.

1. Vælg **Optag** i optagerkontrolelementet.
1. Vælg det første tal, vælg **+**, vælg det andet tal, og vælg derefter **=**.

    ![Appen Lommeregner](../media/create-windows-ui-flow/app-to-record.png "Appen Lommeregner")

     > [!TIP]
     > Du forbedrer automatiseringens pålidelighed ved at:
     > - åbne og maksimere de apps, du vil optage, *før* du starter optagelsen
     > - starte din optagelse med et klik på titellinjen i appen for at flytte fokus til den.

1. Vælg **Færdig** i optagerkontrolelementet, når du har fuldført de handlinger, du vil optage.

1. Luk den app, du har optaget.

1. Vælg det kort, der starter med "Kør scriptet <app name>", for at få vist skærmbilleder af de trin, der er optaget.

     >[!TIP]
     >Vælg **...** > **Slet** for at fjerne eventuelle identiske trin.

    ![Vise trin, der er optaget](../media/create-windows-ui-flow/show-recorded-steps.png "Vise trin, der er optaget")

1. Vælg **Næste**. 

1. Vælg **Næste** for at springe over det valgfri trin **Konfigurer input**, da vi ikke bruger output i denne gennemgang.

1. Test dit flow for brugergrænseflade ved at vælge knappen **Test nu**, og se derefter kørslen af dit flow for brugergrænseflade.
    
 >[!IMPORTANT]
 >Du opnår de bedste resultater ved ikke at interagere med din enhed under afspilningen.

1. Vælg **Gem og afslut** for at gemme dit flow for brugergrænseflade.

## <a name="known-issues-and-solutions"></a>Almindelige problemer og løsninger

- Skærmbilleder går i øjeblikket tabt efter lagring. Vi arbejder på at løse problemet.

- Det kan være en god idé at tilføje handlingen [**Luk**](edit-desktop.md#add-a-manual-action)i slutningen af dit flow for brugergrænseflade, fordi flow for brugergrænseflader starter en ny forekomst af programmerne med hver test eller kørsel.

- Vælg **...** > **Slet** på kortet med handlinger, der er optaget, for at fjerne eventuelle unødvendige/identiske handlinger.

- Højreklik afspilles muligvis ikke korrekt. Hvis det er tilfældet, skal du klikke til venstre under optagelsen for at få flow for brugergrænseflade til at fokusere på destinationsbrugergrænsefladen og derefter højreklikke.

- Hvis flow for brugergrænsefladen ikke længere optager eller afspiller Windows-programmer, når der er installeret en ny version, skal du kontrollere, at du har den [nyeste version](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409).


### <a name="unsupported-application-types"></a>Ikke-understøttede programtyper

- Interaktioner i Windows (Stifinder, menuen Start, proceslinje osv.).

- Webbrowsere (Chrome, IE Microsoft Edge, Firefox, Mozilla osv.).
    Du skal se [Oprette et flow for brugergrænseflade](create-web.md) for at automatisere websteder.

- Java-programmer.

- ClickOnce-programmer.

- Programmer med en webvisning, f. eks. Electron-programmer.

- Microsoft Office 2016 og tidligere. 

- Microsoft Office online.

### <a name="unsupported-configurations"></a>Ikke-understøttede konfigurationer

- Flere skærme.

- Optagelse via en virtuel maskine-klient (Fjernskrivebord, Citrix osv.).

- Flere forekomster af et program, hvor titlerne på hovedvinduet er identiske.

- Programvinduer med identiske titler, f.eks. Microsoft Outlook med flere nye mailvinduer af typen **Ikke-navngivet – meddelelse (HTML)** samtidig.

- Samtidige optagelsessessioner på en given enhed.

- Samtidige afspilningssessioner på en given enhed. I tilfælde af samtidige kørsler af flow for brugergrænseflade har den første kørsel første prioritet, og de efterfølgende mislykkes, indtil den første er fuldført.

- Afspilning på en enhed med et andet tastaturlayout end den enhed, hvor det blev optaget.

- Optagelse på en enhed eller i en Windows-session, mens browseren med Power Automate er på en anden enhed eller i en anden Windows-session.

### <a name="unsupported-action-types-and-behaviors"></a>Ikke-understøttede handlingstyper og funktionsmåder

Følgende handlinger optages ikke:

- Dobbeltklik.

- Flytning af musen.

- Peg med musen.

- Klik og træk.

- Touch- eller penneinput.

- Åbning af app før optagelse.


## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Upålidelige funktionsmåder og løsninger til Microsoft Office (computer)

- Fastgør båndet, før du starter afspilning, for at undgå problemer, der kan opstå, hvis båndet er indstillet til at blive skjult automatisk under afspilning.
- Vælg ikke elementer ved at klikke og trække. Brug f.eks. ikke Skift-klik til at markere celler i Microsoft Excel, og vælg ikke tekst i Microsoft Word eller Microsoft PowerPoint ved at trække musen.
- Nogle elementer fungerer muligvis ikke korrekt i flow for brugergrænsefladen til Microsoft Word- og Microsoft PowerPoint-skrivebordsprogrammer. Punkter i menuen **Filer**, f.eks. start fra en tom side eller højreklik på kontrolelementer, for f.eks. at tilføje et afsnit i Microsoft Word eller ændre layoutet af dias i Microsoft PowerPoint, fungerer muligvis ikke.

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [udløser det flow for brugergrænsefladen](run-ui-flow.md), du netop har oprettet.

- Hvis du vil udføre mere med flow for brugergrænsefladen, kan du også oprette flow for brugergrænsefladen med [input- og outputparametre](inputs-outputs-web.md).
