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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fd4200c98df4a60318b5d95ab590d4ec59e6bef3
ms.sourcegitcommit: bba5bd4ae3879b6bf1521d8ed636374fe09709e7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524833"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Brug input og output i flow for brugergrænsefladen på skrivebordet

Brug input til at overføre oplysninger fra en ekstern kilde, f.eks. en database eller en hvilken som helst understøttet connector til den ældre software, som automatiseres ved hjælp af flow for brugergrænsefladen.

Du kan f.eks. bruge kundeoplysninger fra en SharePoint-liste som en kilde til input i din ældre regnskabssoftware.

## <a name="define-inputs-in-the-ui-flows-wizard"></a>Definer input i guiden til flow for brugergrænseflade

1. Vælg **Nyt input**

   ![Vælg ny](../media/inputs-outputs-desktop/select-new.png)

1. Føj et navn, eksempeldata og en beskrivelse til dit input.

    - Eksempeldata bruges under optagelsen eller testen.

    - Beskrivelsen er nyttig til at adskille de input, du har oprettet.

   ![Inputfelter](../media/inputs-outputs-desktop/input-fields.png)

1.  Når dine input er oprettet, kan du klikke på Næste for at bruge dem i en optagelse.

>[!TIP]
>Du kan bruge tastekombinationen **CRTL + ALT + L** til at indsætte tekst, som du kan overføre til eller fra det program, der bruges i flowet for brugergrænsefladen. Denne tastekombination fungerer for følsom og statisk tekst samt output- og inputtekst. 

## <a name="use-inputs-to-pass-information-to-the-application"></a>Brug input til at overføre oplysninger til programmet

1. Mens du optager, kan du bruge et input i et program ved at vælge **Brug input**.

1. Du kan vælge mellem tre muligheder på listen:

    - Vælg et af de input, du har defineret under trinnet **Konfigurer inputfelter**.

    - Brug et tidligere defineret output (se afsnittet Output). Dette er nyttigt, hvis du vil overføre oplysninger mellem forskellige programmer i det samme flow for brugergrænsefladen.

    - Opret et nyt input, mens du optager. Du finder det igen under trinnet **Konfigurer inputfelter**.

   ![Vælg inputtype](../media/inputs-outputs-desktop/select-input-type.png)

1. Vælg den placering, hvor du vil bruge inputtet. Den eksempelværdi, du har defineret, bruges automatisk. I nedenstående eksempel er "Hello World" eksempelværdien for inputnavnet "Mit input", som føjes til siden i Microsoft Word.  
    
    ![Vælg placering af input](../media/inputs-outputs-desktop/select-location-for-input.png)

1. Under **Optag og rediger trin** i Power Automate kan du udvide de handlinger, der bruger input, for at få vist, hvilket et der er valgt.

   ![Udvid handlinger](../media/inputs-outputs-desktop/expand-actions.png)

1. Når du udløser dit flow for brugergrænsefladen, kan du ændre inputværdien, når du vil.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Brug output til at udtrække oplysninger fra programmet

Med output kan du overføre oplysninger fra den ældre software, som automatiseres af Flow for brugergrænseflade, til en ekstern destination, f.eks. en database eller en hvilken som helst [understøttet connector](https://flow.microsoft.com/connectors/).

Du kan f.eks. udtrække kundeoplysninger fra din gamle regnskabssoftware og føje dem til en SharePoint-liste.

Der kan kun oprettes output, mens du optager dit flow for brugergrænsefladen.

1. Under en optagelse skal du vælge **Hent output**.

   ![Hent output](../media/inputs-outputs-desktop/get-output.png)

1. Vælg **Vælg tekst**.

   ![Vælg tekst](../media/inputs-outputs-desktop/select-text.png)

1. Klik på et element i brugergrænsefladen for at hente teksten til outputtet. Tekstværdien registreres automatisk.

   <!-- ![Get element output](../media/inputs-outputs-desktop/get-element-output.png) -->

   ![Vælg element i brugergrænsefladen](../media/inputs-outputs-desktop/select-ui-element.png)

1. Angiv et navn på og en beskrivelse af outputtet.

   ![Angiv et navn og en beskrivelse](../media/inputs-outputs-desktop/name-description.png)

1. Vælg **Gem**. 

Dit output er nu tilgængeligt i det dedikerede område i guiden.

   ![Output er tilgængeligt](../media/inputs-outputs-desktop/output-available.png)

Hvert output har:

-  Et outputnavn, som blev defineret under optagelsen.
-  En beskrivelse: Dette felt kan være meget nyttigt, når du definerer mange output under en optagelse og gerne nemt vil identificere dem senere.
-  Et handlingsnavn: Den handling, som outputtet er defineret i, i dit flow for brugergrænsefladen.

## <a name="delete-an-output-from-a-ui-flow"></a>Slet et output fra et flow for brugergrænsefladen

Hvis du ikke længere har brug for et output, kan du slette det ved at gå til den tilknyttede handling og fjerne navnet på outputtet i den dynamiske værdi.

## <a name="test-your-ui-flow"></a>Test dit flow for brugergrænsefladen

Når du tester flow for brugergrænsefladen, kan du validere dine ændringer og den relevante afspilningsfunktion.

1. (Valgfrit) Angiv en ny værdi i inputfeltet. 
    
    ![Ny testværdi](../media/inputs-outputs-desktop/new-test-value.png)

1. Klik på **Test nu** for at se, hvordan den ældre software automatiseres. Du kan se, at de trin, du har optaget, afspilles automatisk i Flow for brugergrænseflade. **Undlad at interagere med din enhed under afspilningen.**

1. Når afspilningen er fuldført, kan du se kørselsstatus for dit flow for brugergrænsefladen:

    - For hver handling viser en statusindikator, at testen fungerede godt sammen med de tilknyttede input.

    - Værdien af de output, der blev hentet for denne test.

    - Hvis der opstår en fejl, kan du se, hvilket trin der forårsager problemet sammen med et skærmbillede af det øjeblik, fejlen opstod.

   ![En vellykket kørsel](../media/inputs-outputs-desktop/successful-run.png)

## <a name="learn-more"></a>Få mere at vide

- Få mere at vide om [udløsningen af flow for brugergrænsefladen](run-ui-flow.md).



