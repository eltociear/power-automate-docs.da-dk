---
title: Kør flow for brugergrænsefladen fra andre flow | Microsoft Docs
description: Kør flow for brugergrænsefladen fra andre flows
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
ms.openlocfilehash: d0d5380e1ade6d1d11d557f38e7fc5db6616d1d9
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74370945"
---
# <a name="run-ui-flows"></a>Kør flow for brugergrænsefladen

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

    - **Navn på forbindelse**: Vælg et navn til enheden for flowforbindelsen. Det kan være forskelligt fra navnet på gatewayen.
    - **Brugernavn**: Angiv arbejds- eller skolekontoen for din enhed.
    - **Godkendelsestype**: Vælg Windows.
    - **Adgangskode**: Adgangskoden til din arbejds- eller skolekonto.
    - **Gateway**: Vælg den gateway, du oprettede under installationen.

      ![Indstillinger for forbindelse](../media/run-ui-flow/connection-settings.png "Indstillinger for forbindelse")

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

## <a name="limitations-and-known-issues"></a>Begrænsninger og kendte problemer

- Gatewayklynger understøttes ikke.
- Da tastaturer, der ikke er amerikanske (QWERTY), ikke understøttes i denne version, vil afspilning af inputtrin, hvor tastesekvensen blev optaget med et tastatur, der ikke er amerikansk (QWERTY), resultere i tastetryk på amerikansk (QWERTY).

## <a name="learn-more"></a>Få mere at vide

 - Installér [datagatewayen i det lokale miljø](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - Dokumentation til [brug af datagatewayprogrammet i det lokale miljø](https://docs.microsoft.com/flow/gateway-manage).
 - [Foretag fejlfinding](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) af datagatewayen i det lokale miljø.
