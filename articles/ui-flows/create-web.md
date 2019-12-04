---
title: Få mere at vide om, hvordan du opretter flow for brugergrænsefladen for websteder | Microsoft Docs
description: Lær, hvordan du automatiserer webprogrammer ved hjælp af flow for brugergrænsefladen.
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
ms.openlocfilehash: 06a27a495a008542208cd56230ad8c21b5e5b938
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74372371"
---
# <a name="create-and-test-your-web-ui-flows"></a>Opret og test flow for brugergrænsefladen på internettet

[Dette emne er foreløbig dokumentation og kan ændres].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Følg disse trin for at oprette et simpelt flow for brugergrænsefladen på internettet:

## <a name="create-a-web-ui-flow"></a>Opret et flow for brugergrænsefladen på internettet

1. Åbn den [nyeste version af Microsoft Edge](https://www.microsoftedgeinsider.com/) eller Google Chrome, og naviger derefter til [Power Automate](https://flow.microsoft.com/).

1. Log på med din arbejds- eller skolekonto, hvis det er nødvendigt.

1. Vælg **Mine flow** > **Flow for brugergrænseflade (prøveversion)** > **Ny**.

   ![Opret et nyt flow for brugergrænsefladen](../media/create-windows-ui-flow/create-new.png "Opret et nyt flow for brugergrænsefladen")

1. Vælg **Webprogram** > **Næste**
    
   ![Vælg webprogram](../media/create-web-ui-flow/select-web-app.png "Vælg webprogram")

1. Angiv et navn på dit flow for brugergrænsefladen i feltet **Navn på flow**.

1. Angiv URL-adressen på det websted, du vil automatisere, i feltet **URL-basisadresse**, og vælg derefter **Start optager**.

   ![Angiv et navn og en URL-adresse](../media/create-web-ui-flow/give-a-name.png "Angiv et navn og en URL-adresse") 

   Selenium IDE starter.

   >[!TIP] 
   >Tip! Du kan optage handlinger på tværs af flere HTTP- eller HTTPS-websteder under den samme fane.  

1. I Selenium IDE skal du vælge knappen **REC** øverst til højre på skærmen for at starte optageren.

   Den URL-adresse, du valgte i forrige trin, åbnes.

   ![Vælg Rec](../media/create-web-ui-flow/select-rec.png "Vælg Rec")

1.  Udfør de handlinger, du vil optage, på webstedet. 
    
    >[!TIP]
    >Nederst til højre kan du se optagestatussen.

    ![Optagestatus](../media/create-web-ui-flow/recording-status.png "Optagestatus")

1.  Når du er færdig med at optage, skal du vælge den røde **stopknap** i øverste højre hjørne af Selenium IDE.

    ![Knappen Stop](../media/create-web-ui-flow/stop-button.png "Knappen Stop" )

1. Vælg knappen **Kør aktuel test** øverst til venstre på skærmen for at se det flow for brugergrænsefladen, du netop har kørt.

    ![Kør aktuel test](../media/create-web-ui-flow/run-test.png "Kør aktuel test")

   >[!TIP]
   >Du kan angive ventetiden mellem trin for at sinke den lokale afspilning med henblik på test. Denne indstilling er kun til testformål og har ingen indvirkning, når dit flow for brugergrænsefladen udrulles.  
  
1. Vælg knappen **Gem projekt** øverst til højre i Selenium IDE. Dermed lukkes og uploades projektet.

Nu, hvor du har oprettet et flow for brugergrænsefladen på internettet, kan du bruge det i dine andre flow.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Begrænsninger og kendte problemer i forbindelse med flow for brugergrænsefladen på internettet

>[!WARNING]
>**Adgangskoder i Selenium IDE gemmes som almindelig tekst.**  


**Windows-programmer optages og afspilles ikke længere i flow for brugergrænsefladen, når der er installeret en ny version.**

Du skal fjerne den tidligere version, før du installerer en ny.

Det gør du ved at åbne menuen Start, gå til **Indstillinger** > **Programmer**, søge efter **Flow for brugergrænseflade** på listen over programmer > **Flow for brugergrænseflade (prøveversion)** og derefter vælge "Fjern". Guiden fører dig gennem processen.

**Midlertidig brugerprofil til afspilning**

Selenium IDE-optagelser udføres med den aktuelle brugers profil, men afspilningen udføres ved hjælp af en midlertidig brugerprofil. Det betyder, at der muligvis ikke bedes om legitimationsoplysninger under en optagesession for websteder, der skal bruge godkendelse, men godkendelsestrinnene skal udføres under afspilning. 

For at løse problemet skal brugeren manuelt redigere scriptet for at indsætte de kommandoer, der skal bruges til logonprocessen.

**Andre begrænsninger**

-   Optagelse af skrivebordsprogrammer under en optagesession på internettet. Hvis du har brug for at automatisere både internet- og skrivebordsprogrammer, kan du oprette et separat flow for brugergrænsefladen for hver type og derefter kombinere dem i et flow.

-   Multifaktorgodkendelse (MFA – Multi-Factor Authentication) understøttes ikke. Brug en lejer, der ikke kræver MFA.

-   Disse Selenium IDE-kommandoer understøttes ikke: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, Echo, MouseOut, MouseUpAt og MouseDownAt.

-   Højreklik understøttes ikke. 

-   Yderligere input til flow for brugergrænsefladen på internettet genereres, når du bruger Foreach-kommandoer. Du kan løse dette problem ved at angive en vilkårlig værdi i de ekstra felter. Det påvirker ikke afspilningen.

-   Hvis .side-filen indeholder flere testprojekter, er det kun den første, der blev oprettet, som kører. 

     >[!TIP]
     >Bemærk, at Selenium IDE rangerer testene efter navn og ikke efter oprettelsesdato, så den første test, der blev oprettet, er måske ikke den første på listen.

-   Afspilning direkte i Selenium IDE fungerer muligvis ikke efter hensigten. Afspilning ved kørsel via infrastrukturen for flow for brugergrænsefladen fungerer dog korrekt.

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [kører flow for brugergrænsefladen](run-ui-flow.md).

- Hvis du vil udføre mere med flow for brugergrænsefladen, kan du også afprøve flow for brugergrænsefladen med [input- og output](inputs-outputs-web.md)parametre.

