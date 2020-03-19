---
title: Kør flow for brugergrænsefladen fra andre flow | Microsoft Docs
description: Kør flow for brugergrænsefladen fra andre flow i ikke-automatiseret eller automatiseret tilstand.
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
ms.date: 03/03/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0852e8b52f7b158d8fc97316b0f719f8e557a15f
ms.sourcegitcommit: 14ea422c0b306f738757036cc0e240584dd810f5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79188134"
---
# <a name="run-attended-and-unattended-ui-flows"></a>Kør ikke-automatiserede og automatiserede flow for brugergrænsefladen

[Dette emne er foreløbig dokumentation og kan ændres].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Når du har oprettet og testet et flow for brugergrænsefladen, kan du køre det fra en hændelse, en tidsplan eller en knap. Hvis du vil gøre det muligt, skal du føje dit flow for brugergrænsefladen til et [automatiseret flow](../get-started-logic-flow.md), et [flow for en knap](../introduction-to-button-flows.md), et [planlagt flow](../run-scheduled-tasks.md) eller et [forretningsprocesflow](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Forudsætninger

- Du skal bruge [datagatewayen i det lokale miljø](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409), før flowet for brugergrænsefladen udløses af Power Automate på din enhed.
   
   Gatewayen er en sikker forbindelse i virksomhedsklassen mellem Power Automate og din enhed (hvor dit flow for brugergrænsefladen kører). Power Automate bruger gatewayen til at få adgang til din enhed i det lokale miljø, så den kan udløse dine flow for brugergrænsefladen fra en hændelse, en tidsplan eller en knap.
- En arbejds- eller skolekonto. 

   >[!IMPORTANT]
   >Du skal bruge samme arbejds- eller skolekonto til at konfigurere gatewayen, til at logge på Power Automate og til at logge på din Windows-enhed.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Kør dit flow for brugergrænsefladen fra en hændelse, en knap, et tidsplan eller et forretningsprocesflow

I dette eksempel bruger vi et automatiseret flow til at udløse et flow for brugergrænsefladen, når der modtages en ny mail.

1. Naviger til [Power Automate](https://flow.microsoft.com/).
1. Vælg **Mine flow** på navigationslinjen til venstre.
1. Vælg **Nyt**, og vælg derefter **Automatiseret – fra bunden**.

   >[!TIP]
   >Du kan vælge et hvilket som helst andet type flow, der passer til dine behov.

1. Giv dit flow et navn i feltet **Navn på flow**.
1. Søg efter "ny mail", og vælg derefter **Når en ny mail modtages (v3)** på listen over udløsere. 
    
   ![Vælg en udløser](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Vælg en udløser")

1. Vælg **Opret**, og vælg derefter **Nyt trin**.

1. Søg efter **Flow for brugergrænseflade**, og vælg derefter **Kør et flow for brugergrænsefladen på skrivebordet** på listen over **Handlinger**. 

   ![Søg efter handling](../media/run-ui-flow/search-action.png "Søg efter handling")

1. Angiv gatewayoplysninger og enhedsoplysninger. 

   Det skal du gøre én gang pr. enhed:

    - **Gateway**: Vælg den gateway, du oprettede tidligere, eller brug **Ny gateway** til at oprette en ny gateway.   
    - **Domæne og brugernavn**: Viser din arbejds- eller skolekonto fra enheden.
    - **Adgangskode**: Angiv adgangskoden til din arbejds- eller skolekonto.

      ![Indstillinger for forbindelse](../media/run-ui-flow/uiflow-connection-card.png "Indstillinger for forbindelse")

      >[!TIP]
      >Hvis du ikke kan se din gateway, skal du muligvis vælge en anden forbindelse. Det gør du ved at vælge **...** øverst til højre på kortet **Kør et flow for brugergrænsefladen på skrivebordet (prøveversion)** og derefter vælge den forbindelse, du vil bruge, fra **Mine forbindelser**.

      ![Vælg en ny forbindelse](../media/run-ui-flow/select-new-connection.png "Vælg en ny forbindelse")

1. Vælg det flow for brugergrænsefladen, du oprettede tidligere.

   ![Vælg flow for brugergrænseflade](../media/run-ui-flow/select-ui-flow.png "Vælg flow for brugergrænseflade")

1. Vælg **Gem** for at gemme dit automatiserede flow.

1. Test flowet ved at sende en mail for at udløse det. Du kan se, at de trin, du optog, bliver afspillet i dit flow for brugergrænsefladen. 

![Vellykket kørsel, der kalder et flow for brugergrænsefladen](../media/run-ui-flow/successful-run.png "Vellykket kørsel, der kalder et flow for brugergrænsefladen")

>[!TIP]
>Interager ikke med din enhed, mens flowet kører.

## <a name="use-inputs-and-outputs"></a>Brug input og output

Når du definerer input og output i et flow for brugergrænsefladen, kan du overføre oplysninger fra og til disse input.

1. Når du føjer et flow for brugergrænsefladen til et flow, kan du se en liste over input, der blev defineret i flowet for brugergrænsefladen.

   ![Input til flow for brugergrænsefladen](../media/run-ui-flow/inputs.png "Input til flow for brugergrænsefladen")

1. Du kan udfylde hvert inputfelt i flowet for brugergrænsefladen med værdier fra tidligere trin i flowet. Det gør du ved at vælge inputfeltet og derefter vælge et input fra tokenvælgeren.


1. Du kan også bruge output fra dit flow for brugergrænsefladen som input til handlinger, der vises senere i flowet. Det gør du ved at vælge inputfeltet og derefter vælge et input fra tokenvælgeren.

## <a name="run-ui-flows-unattended-or-attended"></a>Kør flow for brugergrænsefladen enten automatiseret eller ikke-automatiseret

Når du opretter flow for brugergrænsefladen, kører du dem enten i **ikke-automatiseret** eller i **automatiseret** tilstand. Automatiseret er bedst til programmer, der ikke har brug for menneskelig overvågning.

Når de køres automatiseret, logges flow for brugergrænsefladen automatisk på de enheder, der kører Windows 10, Windows Server 2016 eller Windows Server 2019. Når automatiseringen er fuldført, logges flow for brugergrænsefladen af enheden og rapporterer sin aktivitet i Power Automate.

Når de køres ikke-automatiseret, bruger flow for brugergrænsefladen en eksisterende Windows-brugersession.

Flow for brugergrænsefladen vælger mellem ikke-automatiseret og automatiseret tilstand afhængigt af tilstanden af maskinen, som beskrevet senere i denne artikel.

### <a name="unattended-mode"></a>Automatiseret tilstand

Hvis du vil køre flow for brugergrænsefladen automatiseret, skal destinationsmaskinen være tilgængelig, og alle brugerne skal være logget af. Låste Windows-brugersessioner forhindrer, at flow for brugergrænsefladen kører.

Flow for brugergrænsefladen udfører følgende:
1. Flow for brugergrænsefladen opretter, administrerer og udgiver derefter Windows-brugersessionen på destinationsenhederne.

1. Automatiserede kørsler af flow for brugergrænsefladen kører på enheder med skærmen låst.

1. Windows 10-enheder kan ikke køre automatiseret, hvis der er aktive Windows-brugersessioner på enheden (selv låste). Du får vist følgende fejl: *Flow for brugergrænsefladen kan ikke udføres. Der er en låst eller inaktiv Windows-brugersession på destinationsenheden*.

1. Hvis du har en låst Windows-brugersession åben i Windows Server med den samme bruger, som flowet for brugergrænsefladen skal køre som, får du vist den samme fejl: *Flow for brugergrænsefladen kan ikke udføres. Der er en låst eller inaktiv Windows-brugersession på destinationsenheden*.

### <a name="attended-mode"></a>Ikke-automatiseret tilstand
Hvis du vil køre et ikke-automatiseret flow for brugergrænsefladen, skal du have en aktiv Windows-brugersession, der stemmer overens med navnet på den bruger, som er konfigureret for din forbindelse. Sessionen må ikke være låst.

Når kørslen af et ikke-automatiseret flow for brugergrænsefladen startes på destinationsmaskinen, anbefales det, at du undgår interaktioner med din enhed (f.eks. at flytte musen), indtil udførelsen er fuldført.


## <a name="schedule-multiple-ui-flows-on-the-same-device"></a>Planlæg flere flow for brugergrænsefladen på den samme enhed

Du kan planlægge at køre flere flow for brugergrænsefladen på en eller flere enheder. Hvis mere end én kørsel af et flow for brugergrænsefladen udløses på den samme enhed, organiserer backend for flow for brugergrænsefladen kørslerne ved at følge disse regler:

1.  Det første flow for brugergrænsefladen sendes til destinationsenheden.

1.  Andre flow for brugergrænsefladen sættes i kø, og de vises som **ventende** på siden med oplysninger om flow for brugergrænsefladen eller gatewayen.

1.  Det næste flow for brugergrænsefladen sendes, når hver kørsel er fuldført.

>[!NOTE]
>Disse organiseringsregler gælder for begge flow for brugergrænsefladen, der er planlagt af den samme bruger eller af forskellige brugere på den samme enhed.

>[!IMPORTANT]
>Hvis der er for mange flow for brugergrænsefladen i udførelseskøen, kan der opstå timeout. Kørsler af flow for brugergrænsefladen mislykkes i øjeblikket, hvis de ikke køres inden for 30 minutter, efter de er blevet udløst.

## <a name="rerun-failed-ui-flows"></a>Kør mislykkede flow for brugergrænsefladen igen

Hvis kørslen af et flow for brugergrænsefladen mislykkes, kan du enten prøve at køre den, efter du har rettet årsagen til denne fejl, eller i visse tilfælde foretage fejlfinding af den mislykkede kørsel.

1. Gå til siden med oplysninger om flow for brugergrænsefladen, og identificer den kørsel, du vil køre igen.

1. Vælg det overordnede flow for den kørsel, du er interesseret i.

   Denne fører dig til den overordnede kørsel af flow, hvor flowet for brugergrænsefladen mislykkedes.

1. Vælg knappen for indsendelse igen i handlingsmenuen.

## <a name="troubleshoot-failures"></a>Foretag fejlfinding af fejl

### <a name="failed-ui-flows"></a>Mislykkede flow for brugergrænsefladen

1. Hvis dit automatiserede flow for brugergrænsefladen mislykkes med fejlmeddelelsen **En ny session kan ikke oprettes**, skal du følge disse trin for at løse problemet:

    1.  På Windows 10 skal du bekræfte, at du ikke har en aktiv brugersession låst eller oplåst på din destinationsenhed.
    1.  På Windows Server 2016 eller Windows Server 2019 skal du bekræfte, at du ikke har nået det maksimale antal aktive brugersessioner, der er konfigureret på din maskine, ellers kan flow for brugergrænsefladen ikke oprette nye sessioner til at køre nye flow for brugergrænsefladen.

### <a name="ui-flows-app-status"></a>Status af programmet til flow for brugergrænsefladen

Programmet til flow for brugergrænsefladen er den software, du installerer på din lokale maskine, som administrerer og udfører kørsler af flow for brugergrænsefladen. Det gør det muligt for vores cloudtjeneste til flow for brugergrænsefladen at kommunikere og organisere flow for brugergrænsefladen på din maskine.

På listen over gateways og siden med oplysninger om gatewayen kan du se den aktuelle status af programmet til flow for brugergrænsefladen for hver enhed.

![Et skærmbillede, der viser listen over gateways](../media/run-ui-flow/gateway-list.png)

Dit program til flow for brugergrænsefladen kan have en af følgende tilstande:

1. **Tilgængelig**: Programmet til flow for brugergrænsefladen er online og klar til at køre flow for brugergrænsefladen.

1. **Kører**: Et eller flere flow for brugergrænsefladen kører på maskinen. Alle andre flow for brugergrænsefladen, som backend sender til destinationsenheden, sættes i kø og venter på en plads til at blive kørt.

1. **Ret forbindelse til gateway**: Cloudtjenesten til flowet for brugergrænsefladen kan ikke nå destinationsenheden, sandsynligvis fordi der er et problem med gatewayforbindelsen. For at løse dette problem skal du gå til forbindelsen og bekræfte, at de legitimationsoplysninger, du bruger, er korrekte.

1. **Ukendt**: Denne status betyder, at backend ikke kan nå programmet til flow for brugergrænsefladen.

    1. Hvis **gatewaystatussen** er **offline**, skal du bekræfte, at enheden er slået til og har forbindelse til internettet. Du kan også foretage [fejlfinding af gatewayen](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot)

    1. Hvis **gatewaystatussen** er **online**, kan du prøve følgende handlinger:

        1. Bekræft, at programmet og tjenesterne til flow for brugergrænsefladen kører på din enhed.

        1. Genstart tjenesten til flowet for brugergrænsefladen på enheden.

## <a name="learn-more"></a>Få mere at vide

 - Installér [datagatewayen i det lokale miljø](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - Dokumentation til [brug af datagatewayprogrammet i det lokale miljø](https://docs.microsoft.com/flow/gateway-manage).
 - [Foretag fejlfinding](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) af datagatewayen i det lokale miljø.
