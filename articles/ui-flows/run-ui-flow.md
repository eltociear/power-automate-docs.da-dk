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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7d9142fa86b256ca816cf128f8b76bae7d1c5a90
ms.sourcegitcommit: 855ee8b55aebe7b8e202006c39debfff02df1d30
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/03/2020
ms.locfileid: "80627068"
---
# <a name="run-attended-and-unattended-ui-flows"></a>Kør ikke-automatiserede og automatiserede flow for brugergrænsefladen

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
    
   ![Vælg en udløser](../media/run-ui-flow/select-email-trigger.png "Vælg en udløser")

1. Vælg **Opret**, og vælg derefter **Nyt trin**.

1. Søg efter **Flow for brugergrænseflade**, og vælg derefter **Kør et flow for brugergrænsefladen på skrivebordet** på listen over **Handlinger**. 

   ![Søg efter handling](../media/run-ui-flow/search-action.png "Søg efter handling")

1. Angiv gatewayoplysninger og enhedsoplysninger. 

   Det skal du gøre én gang pr. enhed:

    - **Gateway**: Vælg den gateway, du oprettede tidligere, eller brug **Ny gateway** til at oprette en ny gateway.   
    - **Domæne og brugernavn**: Viser din arbejds- eller skolekonto fra enheden.
       >[!Important]
        >Sørg for, at du kan logge på enheden ved hjælp af disse legitimationsoplysninger.  
    - **Adgangskode**: Angiv adgangskoden til din arbejds- eller skolekonto.

      ![Indstillinger for forbindelse](../media/run-ui-flow/uiflow-connection-card.png "Indstillinger for forbindelse")

      >[!TIP]
      >Hvis du ikke kan se din gateway, er du muligvis i et miljø, hvis område er anderledes end gatewayområdet. Vælg **Foretag fejlfinding af en manglende gateway** på listen over gatewaynavne for at få mere at vide. Du kan også bekræfte, at dine gateway- og Power Automate-områder er [tilknyttet korrekt](../regions-overview.md#region-mappings-for-power-automate-and-gateways).

      >[!TIP]
      >Hvis du ikke kan se din gateway, skal du muligvis vælge en anden forbindelse. Det gør du ved at vælge **...** øverst til højre på kortet **Kør et flow for brugergrænsefladen på skrivebordet** eller **Kør et flow for brugergrænsefladen på internettet** og derefter vælge forbindelsen fra **Mine forbindelser**.


      ![Vælg en ny forbindelse](../media/run-ui-flow/select-new-connection.png "Vælg en ny forbindelse")

1. Vælg det flow for brugergrænsefladen, du oprettede tidligere.

   ![Vælg flow for brugergrænseflade](../media/run-ui-flow/select-ui-flow.png "Vælg flow for brugergrænseflade")

1. Vælg **Gem** for at gemme dit automatiserede flow.
 >[!TIP]
 >Bekræft, at din gateway er online, før du udfører testen. Gå til **Data** > **Gateways** i navigationsruden, vælg gatewaynavnet, og klik på **...** . Gå derefter til **Oplysninger**, og bekræft, at **gatewaystatussen** er **online**. Hvis **gatewaystatussen** er **offline**, skal du bekræfte, at enheden er slået til og har forbindelse til internettet. 

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

Når du føjer et flow for brugergrænsefladen til et flow, kan du vælge, om dit flow for brugergrænsefladen skal køre automatiseret eller ikke-automatiseret. Her er nogle vigtige forskelle mellem automatiserede og ikke-automatiserede kørsler:

### <a name="unattended-mode"></a>Automatiseret tilstand

Hvis du vil køre flow for brugergrænsefladen automatiseret, skal destinationsmaskinen være tilgængelig, og alle brugerne skal være logget af. 

>[!IMPORTANT]
>Låste Windows-brugersessioner forhindrer, at flow for brugergrænsefladen kører.

Der udføres følgende i flow for brugergrænsefladen:
1. Windows-brugersessionen oprettes, administreres og udgives derefter på destinationsenhederne ved hjælp af flow for brugergrænsefladen.

1. Automatiserede flow for brugergrænsefladen kører på enheder med skærmen låst, så ingen kan se flowet, mens det køres.

1. Windows 10-enheder kan ikke køre automatiseret, hvis der er aktive Windows-brugersessioner til stede (selv en låst). Du får vist følgende fejl: *Flow for brugergrænsefladen kan ikke udføres. Der er en låst eller inaktiv Windows-brugersession på destinationsenheden*.

1. Hvis du har en låst Windows-brugersession åben i Windows Server med den samme bruger, som flowet for brugergrænsefladen skal køre som, får du vist den samme fejl: *Flow for brugergrænsefladen kan ikke udføres. Der er en låst eller inaktiv Windows-brugersession på destinationsenheden*.

### <a name="attended-mode"></a>Ikke-automatiseret tilstand
Hvis du vil køre et ikke-automatiseret flow for brugergrænsefladen, skal du have en aktiv Windows-brugersession, der stemmer overens med navnet på den bruger, som er konfigureret for din forbindelse. Sessionen må ikke være låst.

Når et automatiseret flow for brugergrænsefladen starter på destinationsmaskinen, anbefaler vi, at du undgår at interagere med enheden, indtil kørslen er fuldført.


## <a name="schedule-multiple-ui-flows-on-the-same-device"></a>Planlæg flere flow for brugergrænsefladen på den samme enhed

Du kan planlægge at køre flere flow for brugergrænsefladen på en eller flere enheder. Hvis der udløses mere end ét flow for brugergrænsefladen, som skal køre på den samme enhed, følger Power Automate disse regler:

1.  Det første flow for brugergrænsefladen køres på destinationsenheden.

1.  Andre flow for brugergrænsefladen sættes i kø, og de vises som **Ventende** på siden med oplysninger om flow for brugergrænsefladen eller gatewayen.

1.  Det næste flow for brugergrænsefladen vælges, når hver kørsel er fuldført.

>[!NOTE]
>Disse orkestreringsregler gælder for kørsler af flow for brugergrænsefladen, der er planlagt af en hvilken som helst bruger eller af forskellige brugere på den samme enhed.

>[!IMPORTANT]
>Hvis der er for mange flow for brugergrænsefladen i udførelseskøen, kan der opstå timeout. Kørsler af flow for brugergrænsefladen mislykkes, hvis de ikke køres inden for 30 minutter, efter de blev udløst.

## <a name="load-balance-requests-across-gateways-in-a-cluster"></a>Anmodninger om justering af belastning på tværs af gateways i en klynge

Du kan vælge at distribuere kørsler af flow for brugergrænsefladen jævnt på tværs af gateways i en klynge. Valget af en gateway under justering af belastning er som standard vilkårlig.

Følg [disse trin for at tilføje en gateway og oprette en klynge](https://docs.microsoft.com/data-integration/gateway/service-gateway-install#add-another-gateway-to-create-a-cluster)

>[!NOTE]
>Medlemmer af offlinegatewayen i en klynge vil påvirke ydeevnen negativt. Deaktiver eller fjern disse medlemmer.

Hvis du vil angive justering af belastning på siden med oplysninger om Power Automate-gatewayen, skal du navigere til **Data** -> **Gateways** og derefter vælge din gatewayklynge. 

På siden med oplysninger om gatewayen skal du slå Kør på alle gateways i klyngen til. Dermed distribueres kørsler af flow for brugergrænsefladen til alle gateways i den pågældende klynge.

   ![Distribuer kørsel af flow for brugergrænsefladen på gatewayklynge](../media/run-ui-flow/gw_cluster.png "Distribuer kørsel af flow for brugergrænsefladen på gatewayklynge")
   
>[!IMPORTANT]
>Hvis du bruger lokale Windows-konti, skal alle maskiner i klyngen have den samme lokale konto med samme adgangskode. Brug disse legitimationsoplysninger, når du opretter forbindelse til flowet for brugergrænsefladen.
>Hvis du bruger maskiner, der er forbundet med Active Directory eller Azure AD, skal du bekræfte, at den brugerkonto, du bruger til at oprette forbindelse til flowet for brugergrænsefladen, kan få adgang til alle maskiner i klyngen.
   
## <a name="best-practices-to-avoid-timeouts-and-distribute-load-across-machines"></a>Bedste praksis for at undgå timeout og distribuere belastning på tværs af maskiner

Hvis du planlægger at køre flere flow for brugergrænsefladen, er der en række strategier, som du kan indføre for at distribuere belastningen og sikre, at alle dine flow for brugergrænsefladen kører uden at overbelaste destinationsmaskinerne, eller at der ikke opstår timeout, fordi der kører flere flow for brugergrænsefladen samtidigt. Du kan enten:

1. Planlægge, at dine flow for brugergrænsefladen kører på forskellige tidspunkter af dagen, så du dermed spreder belastningen over tid. Dette fungerer bedst, hvis du har en enkelt eller et begrænset antal maskiner, der kan køre arbejdsbelastninger, og du kan styre udløserne (f.eks. planlagte flow), der starter dit flow for brugergrænsefladen.
1. Oprette klynger af maskiner, der kan køre flow for brugergrænsefladen med identiske konfigurationer parallelt. 
1. Oprette flere flow, der hver især bruger en separat forbindelse til at henvende sig til forskellige maskiner. 

Når du følger disse strategier, kan du undgå, at forskellige flow for brugergrænsefladen konkurrerer med hinanden om at køre på den samme enhed, og at de i nogle tilfælde mislykkedes pga. timeout. 

>[!NOTE]
>Hvis du kører flow for brugergrænsefladen i automatiseret tilstand, skal du forudse, hvor mange flow for brugergrænsefladen organisationen planlægger at køre parallelt, og derefter købe et passende antal automatiserede tilføjelsesprogrammer. 


## <a name="rerun-failed-ui-flows"></a>Kør mislykkede flow for brugergrænsefladen igen

Hvis et flow for brugergrænsefladen mislykkes, skal du løse problemet og derefter forsøge følgende trin for at køre det igen: 

   1. Gå til siden med oplysninger, og identificer den mislykkede kørsel.

   1. Vælg knappen **Genindsend** i handlingsmenuen.

## <a name="troubleshoot-failures"></a>Foretag fejlfinding af fejl

1. Hvis dit automatiserede flow for brugergrænsefladen mislykkes med meddelelsen **En ny session kan ikke oprettes**, skal du følge disse trin for at løse problemet:

    - På Windows 10 skal du bekræfte, at du ikke har en aktiv brugersession låst eller oplåst på din destinationsenhed.
    - På Windows Server 2016 eller Windows Server 2019 skal du bekræfte, at du ikke har nået det maksimale antal aktive brugersessioner, der er konfigureret på din enhed. Flow for brugergrænsefladen kan ikke køres, hvis der ikke kan oprettes nye sessioner.

1. Hvis du kører flow for brugergrænsefladen på et operativsystem, der ikke er på engelsk, og du får vist meddelelsen *502 – Forkert anmodning*, skal du bekræfte, at du har fulgt [trinnene til at opgradere dine flow for brugergrænsefladen fra prøveversionen](upgrade.md).


1. Hvis **gatewaystatussen** er **offline**, skal du bekræfte, at enheden er slået til og har forbindelse til internettet. Du kan også foretage [fejlfinding af gatewayen](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot).

1. Hvis **gatewaystatussen** er **online**, kan du prøve følgende handlinger:

   - Bekræft, at programmet og tjenesterne til flow for brugergrænsefladen kører på din enhed.

   - Genstart tjenesten til flowet for brugergrænsefladen på enheden.

## <a name="learn-more"></a>Få mere at vide

 - Installér [datagatewayen i det lokale miljø](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - Dokumentation til [brug af datagatewayprogrammet i det lokale miljø](https://docs.microsoft.com/flow/gateway-manage).
 - [Foretag fejlfinding](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) af datagatewayen i det lokale miljø.



