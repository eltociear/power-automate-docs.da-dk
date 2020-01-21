---
title: Få mere at vide om oprettelse af flow for brugergrænseflader| Microsoft Docs
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: afe9277ced28cdb964ed32550dd0402eaa0d1df4
ms.sourcegitcommit: 8c4231190023d17c3d620e1e58d1d3d6bcd289ab
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/14/2020
ms.locfileid: "75943490"
---
# <a name="create-and-test-desktop-ui-flows"></a>Opret og test desktopbrugergrænsefladeflow

[Dette emne er foreløbig dokumentation og kan ændres.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Se [Kendte problemer](create-desktop.md#known-issues-and-solutions) senere i dette emne for at få mere at vide om de problemer, der kan opstå, løsninger på disse problemer og scenarier, der ikke understøttes i denne prøveversion.


## <a name="create-a-desktop-ui-flow"></a>Opret et flow for brugergrænseflader

I følgende trin viser vi, hvordan du kan automatisere appen Lommeregner, så den lægger to tal sammen og derefter gemmer resultatet til senere brug.

> [!TIP]
> Du kan automatisere andre Windows Desktop-apps ved at følge et lignende mønster.

1. Sørg for, at din [enhed er klar](setup.md) til at oprette flow for brugergrænseflader. <!--Todo: link to the prereqs section-->

1. Brug [Chromium-versionen af Microsoft Edge](https://www.microsoftedgeinsider.com) eller Google Chrome til at åbne [Power Automate](https://flow.microsoft.com), og log derefter på den samme arbejds- eller skolekonto som på din enhed.

1. Vælg **Mine flow** > **Flow for brugergrænseflade (prøveversion)**  > **Ny**.

   ![Opret et nyt flow for brugergrænseflade](../media/create-windows-ui-flow/create-new.png "Opret et nyt flow for brugergrænseflade")

1. Vælg **Skrivebord-app** og vælg derefter **Næste**.

   ![Vælg skrivebord](../media/create-windows-ui-flow/select-desktop.png "Vælg skrivebord") 

1. Angiv et navn til dit brugergrænseflade-flow i feltet **Flownavn**, og vælg derefter **Næste**.

   ![Vælg skrivebord](../media/create-windows-ui-flow/give-a-name.png "Vælg skrivebord") 

1. Vælg **Næste** nederst for at springe over den valgfri skærm **Konfigurer input**, da vi ikke bruger input i denne gennemgang.

1. Vælg kortet **Optag app** for at udvide det.

   ![Vælg Optag app](../media/create-windows-ui-flow/select-record-app.png "Vælg Optag app")

1. Vælg **Start optager**.

   ![Vælg Start optager](../media/create-windows-ui-flow/select-launch-recorder.png "Vælg Start optager")

   Optagerkontrolelementet vises øverst på skærmen.

   ![Optagerkontrolelementet](../media/create-windows-ui-flow/recorder-control.png "Optagerkontrolelementet")

1. Start appen Lommeregner.

     >[!TIP]
     >Når du holder musemarkøren over kontrolelementer i appen, kan du se en blå kontur rundt om hvert enkelt kontrolelement. Vent altid på den blå markering, før du vælger et kontrolelement.
     >
     >Hvis elementet ikke er fremhævet med blåt, optages det muligvis ikke korrekt.

1. Vælg **Optag** fra optagerkontrolelementet.
1. Vælg det første tal, vælg **+** , vælg det andet tal, og vælg derefter **=** .

    ![Appen Lommeregner](../media/create-windows-ui-flow/app-to-record.png "Appen Lommeregner")
    
     > [!TIP] 
     > Du forbedre automatiseringens pålidelighed ved at:
     > - åbne og maksimere de apps, du vil optage, *før* du starter optagelsen
     > - starte din optagelse med et klik på titellinjen i appen for at flytte fokus til den.

1. Vælg **Færdig** i optagerkontrolelementet, når du har fuldført de handlinger, du vil optage.

1. Luk den app, du har optaget.

1. Vælg det kort, der starter med "Kør scriptet <app name>", for at få vist skærmbilleder af de trin, der er optaget.

     >[!TIP]
     >Vælg **...**  > **Slet** for at fjerne eventuelle identiske trin.

    ![Vis trin, der er optaget](../media/create-windows-ui-flow/show-recorded-steps.png "Vis trin, der er optaget")

1. Vælg **Næste**. 

1. Vælg **Næste** for at springe over det valgfri trin **Konfigurer input**, da vi ikke bruger output i denne gennemgang.

1. Test dit flow for brugergrænseflade ved at vælge knappen **Test nu**, og se derefter kørslen af dit flow for brugergrænseflade.
    
 >[!IMPORTANT]
 >Du opnår de bedste resultater ved ikke at interagere med din enhed under afspilningen.

1. Vælg **Gem og afslut** for at gemme dit flow for brugergrænseflade.

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [udløser dit flow for brugergrænseflade](run-ui-flow.md), du netop har oprettet.

- Hvis du vil foretage dig mere med flow for brugergrænseflader, kan du også afprøve flow for brugergrænseflader med [input- og output](inputs-outputs-web.md)parametre.

## <a name="known-issues-and-solutions"></a>Almindelige problemer og løsninger

- Skærmbilleder går i øjeblikket tabt efter lagring. Vi arbejder på at løse problemet.

- Det kan være en god idé at tilføje handlingen [**Luk**](edit-desktop.md#add-a-manual-action)i slutningen af dit flow for brugergrænseflade, fordi flow for brugergrænseflader starter en ny forekomst af programmerne med hver test eller kørsel.

- Vælg **...**  > **Slet** på kortet med handlinger, der er optaget, for at fjerne eventuelle unødvendige/identiske handlinger.

- Højreklik afspilles muligvis ikke korrekt. Hvis det er tilfældet, skal du klikke til venstre under optagelsen for at få flow for brugergrænseflade til at fokusere på destinationsbrugergrænsefladen og derefter højreklikke.

- Hvis brugergrænseflade-flow ikke længere optager eller afspiller Windows-programmer efter installation af en ny version, skal du fjerne den tidligere version og derefter installere en ny version.


### <a name="unsupported-application-types"></a>Ikke-understøttede programtyper

-   Interaktioner i Windows (Stifinder, menuen Start, proceslinje osv.).

-   Webbrowsere (Chrome, IE, Edge, Edge Chromium, Firefox, Mozilla osv.).
    Du skal se [Opret et flow for brugergrænseflade](edit-web.md) for at automatisere websteder.

-   Java-programmer.

-   ClickOnce-programmer.

-   Programmer med en webvisning, f. eks. Electron-programmer.

-   Microsoft Office 2016 og tidligere. 

-   Microsoft Office Online.

### <a name="unsupported-configurations"></a>Ikke-understøttede konfigurationer

-   Flere skærme.

-   Optagelse via en virtuel maskine-klient (Fjernskrivebord, Citrix osv.).

-   Flere forekomster af et program, hvor titlerne på hovedvinduet er identiske.

-   Programvinduer med identiske titler, f. eks. Microsoft Outlook med flere nye mailvinduer af typen **Ikke-navngivet – meddelelse (HTML)** samtidig.

-   Samtidige optagelsessessioner på en given enhed.

-   Samtidige afspilningssessioner på en given enhed. I tilfælde af samtidige kørsler af flow for brugergrænseflade har den første kørsel første prioritet, og de efterfølgende mislykkes, indtil den første er fuldført.

-   Afspilning på en enhed med et andet tastaturlayout end den enhed, hvor det blev optaget.

-   Optagelse på en enhed eller i en Windows-session, mens browseren med Microsoft Flow er på en anden enhed eller i en anden Windows-session.

### <a name="unsupported-action-types-and-behaviors"></a>Ikke-understøttede handlingstyper og funktionsmåder

Følgende handlinger optages ikke:

-   Dobbeltklik

-   Flytning af musen.

-   Peg med musen.

-   Klik og træk.

-   Touch- eller penneinput.

-   Åbning af app før optagelse.

<!-- -   Closed app before playback starts. -->

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Upålidelige funktionsmåder og løsninger til Microsoft Office (computer)
- Fastgør båndet, før du starter afspilning, for at undgå problemer, der kan opstå, hvis båndet er indstillet til at blive skjult automatisk under afspilning.
- Vælg ikke elementer ved at klikke og trække. Brug f. eks. ikke Skift-klik til at markere celler i Microsoft Excel, og vælg ikke tekst i Microsoft Word eller Microsoft PowerPoint ved at trække musen.
- Nogle elementer fungerer muligvis ikke korrekt i flow for brugergrænseflade (prøveversion) til Microsoft Word- og Microsoft PowerPoint-skrivebordsprogrammer. Punkter i menuen Filer, f. eks. start fra en tom side eller højreklik på kontrolelementer, for f.eks. at tilføje et afsnit i Microsoft Word eller ændre layoutet af dias i Microsoft PowerPoint, fungerer muligvis ikke.
