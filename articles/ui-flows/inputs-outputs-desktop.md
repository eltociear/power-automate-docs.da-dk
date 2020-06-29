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
ms.openlocfilehash: bf7f21915b63087911edbdbbe181bb5073ffbfb9
ms.sourcegitcommit: aefd1ebedfbd8c6cc3d08397ac171cb4ba5b5315
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412928"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Brug input og output i flow for brugergrænsefladen på skrivebordet

Brug input til at overføre oplysninger fra en ekstern kilde, f.eks. en database eller en hvilken som helst understøttet connector til den ældre software, som automatiseres vha. flow for brugergrænsefladen.

Du kan f.eks. bruge kundeoplysninger fra en SharePoint-liste som en kilde til input i din ældre regnskabssoftware. Du kan også overføre følsomt input som f.eks. et brugernavn eller en adgangskode, der kræves for at logge på et ældre program ved hjælp af **følsomme tekstinput**.

## <a name="define-inputs-in-the-ui-flows"></a>Definer input til flow for brugergrænseflade

1. Vælg **Tekst** for at definere et input, eller vælg **Følsom tekst** for at definere et følsomt tekstinput. 

   ![Vælge ny](../media/inputs-outputs-desktop/text-input.png)

1. Føj et navn, eksempeldata og en beskrivelse til dit input.

    - Eksempeldata bruges under optagelsen eller testen.

    - Beskrivelsen er nyttig til at adskille de input, du har oprettet.

    - Eksempelværdien er skjult for følsomme tekstinput og er ikke permanent, når der er gemt

   ![Inputfelter](../media/inputs-outputs-desktop/text-input.png)

1.  Når dine input er oprettet, kan du klikke på Næste for at bruge dem i en optagelse.

>[!TIP]
>Du kan bruge tastekombinationen **CTRL + ALT + L** til at indsætte tekst, som du kan overføre til eller fra det program, der bruges i flowet for brugergrænsefladen. Denne tastekombination fungerer for følsom og statisk tekst samt output- og inputtekst. 

## <a name="use-inputs-to-pass-information-to-the-application"></a>Brug input til at overføre oplysninger til programmet

1. Mens du optager, kan du bruge et input i et program ved at vælge **Brug inputs**.

1. Du kan vælge mellem tre muligheder på listen:

    - Vælg et af de input, du har defineret under trinnet **Konfigurer inputs**.

      >[!TIP]
      >Du kan nemt identificere følsomme tekstinput, da de har et andet ikon end input via tekst.

    - Brug et tidligere defineret output (se afsnittet Output). Det er nyttigt, hvis du vil overføre oplysninger mellem forskellige programmer i det samme flow for brugergrænsefladen.

    - Opret et nyt tekst- eller følsomt tekstinput, mens du optager ved hjælp af indstillingen **Nyt input**. Du finder det igen under trinnet **Konfigurer input**.

   ![Vælg inputtype](../media/inputs-outputs-desktop/select-input-type.png)

1. Vælg den placering, hvor du vil bruge inputtet. Den eksempelværdi, du har defineret, bruges automatisk. I nedenstående eksempel er "WingTip Toys" eksempelværdien for inputnavnet "Fakturakonto", som føjes til programmet.  
    
    ![Vælg placering af input](../media/inputs-outputs-desktop/select-location-for-input.png)

1. Under **Optag og rediger trin** i Power Automate kan du udvide de handlinger, der bruger input, for at få vist, hvilket et der er valgt.

    I følgende eksempel kan du se, at "Fakturakonto" bruges som værdi.

   ![Udvid handlinger](../media/inputs-outputs-desktop/expand-actions.png)


   >[!NOTE]
   >Hvis du også har brugt et følsomt tekstinput, vises en handling med et låseikon øverst til højre for at angive, at du har brugt følsom tekstinput.


   ![Udvid handlinger](../media/inputs-outputs-desktop/lock-action.png)

1. Når du udløser dit flow for brugergrænsefladen, kan du ændre inputværdien, når du vil.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Brug output til at udtrække oplysninger fra appen

Med output kan du overføre oplysninger fra den ældre software, som automatiseres af flow for brugergrænsefladen, til en ekstern destination, f.eks. en database eller en hvilken som helst [understøttet connector](https://flow.microsoft.com/connectors/).

Du kan f.eks. udtrække kundeoplysninger fra din gamle regnskabssoftware og føje dem til en SharePoint-liste.

Der kan kun oprettes output, mens du optager dit flow for brugergrænsefladen.

1. Vælg **Output** under en optagelse.

   ![Hent output](../media/inputs-outputs-desktop/get-output.png)

1. Vælg **Vælg tekst**.

   ![Vælg tekst](../media/inputs-outputs-desktop/select-text.png)

1. Vælg et element i brugergrænsefladen for at hente teksten til outputtet. Tekstværdien registreres automatisk. Du kan derefter angive et navn på og en beskrivelse af outputtet.

   ![Vælg element i brugergrænsefladen](../media/inputs-outputs-desktop/select-ui-element.png)

1. Angiv et navn på og en beskrivelse af outputtet.

1. Vælg **Gem**. 

Dit output er nu tilgængeligt i det dedikerede område i guiden.

   ![Output er tilgængeligt](../media/inputs-outputs-desktop/output-available.png)

Hvert output har:

-  Et outputnavn, som blev defineret under optagelsen.
-  En beskrivelse: Dette felt kan være meget nyttigt, når du definerer mange output under en optagelse og gerne vil identificere dem på et senere tidspunkt.
-  Et handlingsnavn: Den handling, som outputtet er defineret i, i dit flow for brugergrænsefladen.

## <a name="use-clipboard-content-to-define-outputs"></a>Brug indhold i udklipsholderen til at definere output 

Under en optagelse er det muligt at kopiere tekst i udklipsholderen på computeren og definere den som en outputtet i flowet i brugergrænsefladen.

1. Under optagelsen skal du kopiere en strengværdi  

1. Vælg **Hent tekst fra Udklipsholder**. Indholdet af udklipsholderen vises i feltet **Eksempelværdi** 

   ![Udklipsholderoutput](../media/inputs-outputs-desktop/get-output-clipboard.png)

1. Definer et navn til og en beskrivelse af outputtet (som beskrevet ovenfor), og vælg **Gem.** 

    ![Udklipsholderoutput](../media/inputs-outputs-desktop/get-output-clipboard-2.png)

## <a name="delete-an-output-from-a-ui-flow"></a>Slet et output fra et flow for brugergrænsefladen

Hvis du ikke længere har brug for et output, kan du slette det ved at gå til den tilknyttede handling og fjerne navnet på outputtet i den dynamiske værdi.

## <a name="test-your-ui-flow"></a>Test dit flow for brugergrænsefladen

Når du tester flow for brugergrænsefladen, kan du validere dine ændringer og den relevante afspilningsfunktion.

1. (Valgfrit) Angiv en værdi i inputfeltet. 

   >[!NOTE]
   >For eventuelle følsomme tekstinput, der er oprettet i optageren, skal eksempelværdien angives igen, før der testes.
    
    ![Ny testværdi](../media/inputs-outputs-desktop/new-test-value.png)

1. Vælg **Test nu** for at se, hvordan den ældre software automatiseres. Du kan se, at de trin, du har optaget, afspilles automatisk i flow for brugergrænseflade. **Undlad at interagere med din enhed under afspilningen.**

1. Når afspilningen er fuldført, vises kørselsstatus for dit flow for brugergrænsefladen:

    - For hver handling viser en statusindikator, at testen fungerede godt sammen med de tilknyttede input.

      ![En vellykket kørsel](../media/inputs-outputs-desktop/successful-run.png)

   - For hver handling, der bruger et **Følsomt tekst**input, vises inputværdien ikke.

      ![Et andet billede](../media/inputs-outputs-desktop/sensitive-text-not-displayed.png)

   - Værdien af de output, der er hentet til denne test, vises også nederst i designeren. 

      ![Et andet billede](../media/inputs-outputs-desktop/outputs-value.png)

   - Hvis der opstår en fejl, kan du se, hvilket trin der forårsager problemet sammen med et skærmbillede i det øjeblik, fejlen opstod.

## <a name="learn-more"></a>Få mere at vide

- Få mere at vide om [udløsning af flow for brugergrænseflade](run-ui-flow.md).



