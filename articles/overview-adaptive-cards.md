---
title: Oversigt over adaptive kort til Teams | Microsoft Docs
description: Få mere at vide om brug af adaptive kort i Microsoft Teams.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/01/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7b39474bbc59ba059fd73f2edc7f9b5750edbec2
ms.sourcegitcommit: e3543e32e4e8e8163bef0565e27b657eabbdc741
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/10/2020
ms.locfileid: "75868750"
---
# <a name="overview-of-adaptive-cards-for-microsoft-teams"></a>Oversigt over adaptive kort til Microsoft Teams

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/FqQ3jM2qPRM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


Adaptive kort er en platformsagnostisk metode til deling og visning af blokke af oplysninger uden kompleksiteten ved at skulle tilpasse CSS eller HTML for at gengive kortene. Du opretter adaptive kort i JSON-format med integrationer, som cloudapps og -tjenester åbent kan udveksle. Når kortet leveres til en specifik vært, f.eks. Microsoft Teams, omdannes JSON til oprindelig brugergrænseflade, der automatisk tilpasses værten. Derfor kan procesdesignere nu tilbyde ensartede brugergrænseflademønstre, når de har brug for at vise oplysninger som en del af en virksomhedsproces/automatisering.
 
Da adaptive kort tilpasses deres vært, er de perfekte til deling af oplysninger mellem Microsoft Teams og andre tjenester.

  ![Et skærmbillede af adaptive kort](media/adaptive-cards/multi-adaptive-cards.png)
 
## <a name="currently-available-actions-for-flows"></a>Aktuelt tilgængelige handlinger til flows
 
Følgende handlinger gør det muligt at oprette adaptive kort til Microsoft Teams. I takt med at integrationsscenarierne udvikles, understøttes andre værter også via Power Automate, hvilket vil udvide dine muligheder for at benytte adaptive kort i Microsoft Cloud-abonnementer.
 
## <a name="directing-content-to-teams-members-or-aad-users"></a>Omdirigering af indhold til **teammedlemmer eller AAD-brugere**
 
- **Send dit eget adaptive kort som flowrobotten til en bruger**  
  Denne handling sender et adaptivt kort som en flowrobot til en bestemt bruger. I dette tilfælde skal du angive en modtagers mailadresse, hvorefter kortet vises i modtagerens chat-og/eller aktivitetsopdateringer under kørsel af flowet. Det er ikke nødvendigt for brugeren at være en del af en instans i Teams for at modtage disse typer adaptive kort. I dette tilfælde er det kun URL-knapperne, der fungerer ved at omdirigere til den URL-adresse, der er konfigureret i flowet.

    ![Eksempler på adaptive kort](media/adaptive-cards/top.png)
 
- **Send et adaptivt kort som flowrobotten til en Teams-bruger, og vent på et svar**  
  Denne handling sender et adaptivt kort som en flowrobot til en bestemt bruger i tråd med det scenarie, der blev præsenteret tidligere i denne artikel. I dette tilfælde fortsætter flowkørslen dog ikke efter afsendelsen, før modtageren svarer på det input, der er påkrævet i henhold til kortet. Flowet fortsætter, når modtageren svarer. Flowet returnerer dynamisk indhold for ét (1) svar pr. modtager og pr. kort.
 
## <a name="directing-content-to-teams-channels"></a>Omdirigering af indhold til **Teams-kanaler**
 
- **Send dit eget adaptive kort som flowrobot til en kanal**  
  Denne handling sender et adaptivt kort som en flowrobot til en bestemt Teams-kanal. I dette tilfælde vil du blive bedt om at angive en instans af Teams og en kanal, som kortet skal sendes til. Flowopretteren skal have adgang til Teams-instansen for at kunne sende et adaptivt kort. I dette tilfælde er det kun URL-knapperne, der fungerer ved at omdirigere til den URL-adresse, der er konfigureret i flowet.
 
- **Send et adaptivt kort som flowrobot til en Teams-kanal, og vent på et svar**  
  Denne handling sender et adaptivt kort som en flowrobot til en bestemt Teams-kanal som i tilfældet ovenfor. I dette tilfælde fortsætter flowet dog ikke, før en person på kanalen har svaret med det input, der er påkrævet i henhold til kortet. Flowet fortsætter, når en person i Teams-kanalen har svaret, men returnerer kun dynamisk indhold for ét (1) svar pr. respondent og pr. kort.
 
     ![](media/adaptive-cards/bottom.png)

     >[!TIP]
     >Når du bruger dette kort, venter flowet på et svar fra et Teams-medlem.
 
 
## <a name="known-issues"></a>Kendte problemer
 
- Det er ikke muligt at indsamle data fra adaptive kort, medmindre de er oprettet ved hjælp af en af handlingerne for "Vent på svar". Adaptive kort, der ikke venter, returnerer en fejl for alle knaphandlinger, undtagen OpenURL. Få mere at vide om [OpenURL-knapper](https://adaptivecards.io/explorer/Action.OpenUrl.html). 

- Valg af Action.Submit-knapper på et kort, der ikke omfatter suffikset "Vent på et svar", udløser en fejl.
 
- Adaptive kort, der er oprettet ved hjælp af handlinger af typen "Vent på svar", kan kun sendes én gang pr. kort. Kørslen af flowet fortsætter efter det første svar, og yderligere afsendelser ignoreres.
 
- Kun oplysningerne inden for inputfeltet "Opdater meddelelse" (se billede 3) vises på erstatningskortet, når forbrugerne har sendt kortet.

  Ekstra oplysninger som f.eks. bruger-id for den person, der har sendt kortet, er tilgængelige i det dynamiske indhold i handlinger, der efterfølger handlingen "Vent på svar". Det kan dog være nødvendigt at inkludere Office 365-brugerconnectoren for at udfylde de ønskede profiloplysninger for den bruger, der sendte kortet.
 
- Når adaptive kort med "Vent på svar"-handlingen sendes, nulstilles kortet og ser præcis ud som før, medmindre meddelelsesområdet for erstatning/opdatering er konfigureret. Opdateringsmeddelelser er den bedste fremgangsmåde og anbefales, så du kan opdatere andre, men også for at forhindre forbrugerne i at forsøge at sende kortet mere end én gang.
 
   ![Opdater meddelelse](media/adaptive-cards/update-message.png) 
 
>[!TIP]
>Inputtene **Opdater meddelelse** og **Bør opdatere kortet** skal være konfigureret, hvis der ønskes et erstatningskort.
 
- Power Automate benytter de unikke funktioner og tjenester i Microsofts adaptive kort til at håndtere kortene i en hvilken som helst vært. Denne artikel har til formål at tydeliggøre de specifikke oplysninger, der er forbundet med flowhandlinger. Du kan også bruge hele dokumentationen til [at oprette adaptive kort](https://docs.microsoft.com/adaptive-cards/).
 
## <a name="learn-more"></a>Få mere at vide 
 
- Opret dit [første adaptive kort](https://docs.microsoft.com/power-automate/create-adaptive-cards)
- Komplet dokumentation til [Microsoft Teams-connectoren](https://docs.microsoft.com/connectors/teams/)
- Komplet dokumentation til [Adaptive kort IO](https://docs.microsoft.com/adaptive-cards) 

