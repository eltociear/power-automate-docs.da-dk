---
title: Brug input og output i flow for brugergrænsefladen på skrivebordet | Microsoft Docs
description: Brug input og output i flow for brugergrænsefladen på skrivebordet.
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
ms.openlocfilehash: 391e977343617497328ff231d4808a0c78ceb154
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74371635"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Brug input og output i flow for brugergrænsefladen på skrivebordet

[Dette emne er foreløbig dokumentation og kan ændres].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Definer input

Med input kan du overføre oplysninger fra en ekstern kilde, f.eks. en database eller en hvilken som helst understøttet connector til den ældre software, som automatiseres ved hjælp af flow for brugergrænsefladen.

Du kan f.eks. bruge kundeoplysninger fra en SharePoint-liste som en kilde til input i din ældre regnskabssoftware.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Definer input i guiden til flow for brugergrænseflade

1. Vælg "Nyt input"

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Føj et navn, eksempeldata og en beskrivelse til dit input.

    - Eksempeldata bruges under optagelsen eller testen.

    - Beskrivelsen er nyttig til at adskille de input, du har oprettet.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Når dine input er oprettet, kan du klikke på Næste for at bruge dem i en optagelse.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Brug input til at overføre oplysninger til programmet

1. Mens du optager, kan du bruge et input i et program ved at vælge **Brug input**.

1. Du kan vælge mellem tre muligheder på listen:

    - Vælg et af de input, du har defineret under trinnet **Konfigurer inputfelter** i Flow for brugergrænseflade.

    - Brug et tidligere defineret output (se afsnittet Output). Dette er nyttigt, hvis du vil overføre oplysninger mellem forskellige programmer i det samme flow for brugergrænsefladen.

    - Opret et nyt input, mens du optager. Du finder det igen under trinnet **Konfigurer inputfelter** i Flow for brugergrænseflade.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Vælg den placering, hvor du vil bruge inputtet. Den eksempelværdi, du har defineret, bruges automatisk. I nedenstående eksempel er "Hello World" eksempelværdien for inputnavnet "Mit input", som føjes til siden i Microsoft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. Under **Optag og rediger trin** i Power Automate kan du udvide de handlinger, der bruger input, for at få vist, hvad der er valgt.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Når du udløser dit flow for brugergrænsefladen, kan du ændre inputværdien, når du vil. Du kan finde flere oplysninger under Brug input og output.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Brug output til at udtrække oplysninger fra programmet

Med output kan du overføre oplysninger fra den ældre software, som automatiseres af Flow for brugergrænseflade, til en ekstern destination, f.eks. en database eller en hvilken som helst [understøttet connector](https://flow.microsoft.com/connectors/).

Du kan f.eks. udtrække kundeoplysninger fra din gamle regnskabssoftware og føje dem til en SharePoint-liste.

Der kan kun oprettes output, mens du optager dit flow for brugergrænsefladen.

1. Under en optagelse skal du vælge knappen "Hent output" i optageren

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Vælg knappen "Vælg tekst" (det er den eneste outputtype, der er tilgængelig nu)

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Klik på et element i brugergrænsefladen for at markere teksten til outputtet. Værdien hentes automatisk.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Definer navnet på og beskrivelsen af outputtet.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Vælg **Gem**. 

Dit output er nu tilgængeligt i det dedikerede område i guiden

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Hvert output har:

-  Et outputnavn, som defineres under optagelsen
-  En beskrivelse: Dette felt kan være meget nyttigt, når du definerer mange output under en optagelse og gerne vil identificere dem nemt.
-  Et handlingsnavn: Den handling, hvor outputtet blev defineret i dit flow for brugergrænsefladen

## <a name="delete-an-output-from-a-ui-flow"></a>Slet et output fra et flow for brugergrænsefladen

Hvis du ikke længere har brug for et output, kan du slette det ved at gå tilbage til den tilknyttede handling og fjerne navnet på outputtet i den dynamiske værdi.

## <a name="test-your-ui-flow"></a>Test dit flow for brugergrænsefladen

Når du tester flow for brugergrænsefladen, kan du validere dine ændringer og den relevante afspilningsfunktion.

1. (Valgfrit) Angiv en ny værdi i inputfeltet. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Klik på **Test nu** for at se, hvordan den ældre software automatiseres. Du kan se, at de trin, du har optaget, afspilles automatisk i Flow for brugergrænseflade. **Undlad at interagere med din enhed under afspilningen.**

1. Når afspilningen er fuldført, kan du se udførelsesstatussen for dit flow for brugergrænsefladen:

    - For hver handling indikerer en status, at testen fungerede godt, og de tilknyttede input.

    - Værdien af de output, der blev hentet for denne test.

    - Hvis der genereres en fejl, kan du se, hvilket trin der var problematisk sammen med et skærmbillede af det øjeblik, hvor fejlen opstod.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Få mere at vide

- Få mere at vide om, hvordan du [udløser det flow for brugergrænsefladen](run-ui-flow.md), du netop har oprettet.

- Hvis du vil udføre mere med flow for brugergrænsefladen, kan du også afprøve flow for brugergrænsefladen med [input- og output](inputs-outputs-web.md)parametre.


