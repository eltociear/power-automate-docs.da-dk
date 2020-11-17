---
title: Få mere at vide om, hvordan du opretter flow for brugergrænsefladen for websteder | Microsoft Docs
description: Lær, hvordan du automatiserer webapps ved hjælp af flow for brugergrænsefladen.
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
ms.date: 02/28/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 83900272265c19b517343da122ce863c391cca1f
ms.sourcegitcommit: af414863b5d3a401102746043dbfe2bd93356d48
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/21/2020
ms.locfileid: "4058121"
---
# <a name="create-and-test-your-web-ui-flows"></a>Oprette og teste flow for brugergrænsefladen på internettet

Følg disse trin for at oprette et simpelt flow for brugergrænsefladen på internettet.

## <a name="create-a-web-ui-flow"></a>Oprette et flow for brugergrænsefladen på internettet

1. Åbn [Microsoft Edge (version 80 eller nyere)](https://www.microsoft.com/edge) eller Google Chrome, og naviger derefter til [Power Automate](https://flow.microsoft.com/).

1. Log på med din arbejds- eller skolekonto, hvis det er nødvendigt.

1. Vælg **Mine flow** > **Flow for brugergrænseflade** > **Nyt**.

   ![Oprette et nyt flow for brugergrænsefladen](../media/create-windows-ui-flow/create-new.png "Oprette et nyt flow for brugergrænsefladen")

1. Vælg **Webapp** > **Næste**
    
   ![Vælg Webapp](../media/create-web-ui-flow/select-web-app.png "Vælg Webapp")

1. Angiv et navn på dit flow for brugergrænsefladen i feltet **Navn på flow**.

1. Angiv URL-adressen på det websted, du vil automatisere, i feltet **URL-basisadresse**, og vælg derefter **Start optager**.

   ![Angiv et navn og en URL-adresse](../media/create-web-ui-flow/give-a-name.png "Angiv et navn og en URL-adresse") 

   Selenium IDE starter.

   >[!TIP] 
   >Tip: Du kan optage handlinger på tværs af flere HTTP- eller HTTPS-websteder under den samme fane.  

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

Bekræft, at du bruger den [nyeste version](https://go.microsoft.com/fwlink/?linkid=2102613&clcid=0x409)

**Midlertidig brugerprofil til afspilning**

Selenium IDE-optagelser udføres med den aktuelle brugers profil, men afspilningen udføres ved hjælp af en midlertidig brugerprofil. Det betyder, at der muligvis ikke bedes om legitimationsoplysninger under en optagesession for websteder, der skal bruge godkendelse, men godkendelsestrinnene skal udføres under afspilning. 

For at løse problemet skal brugeren manuelt redigere scriptet for at indsætte de kommandoer, der skal bruges til logonprocessen.

**Andre begrænsninger**

-   Optagelse af skrivebordsprogrammer under en optagesession på internettet. Hvis du har brug for at automatisere både internet- og skrivebordsprogrammer, kan du oprette et separat flow for brugergrænsefladen for hver type og derefter kombinere dem i et flow.

-   Multifaktorgodkendelse (MFA – Multi-Factor Authentication) understøttes ikke. Brug en lejer, der ikke kræver MFA.

-   Disse Selenium IDE-kommandoer understøttes ikke: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, Echo, MouseOut, MouseUpAt og MouseDownAt.

- Flow for brugergrænseflade understøtter ikke Selenium IDE-handlinger eller trin, der tager mere end ét minut at køre.  Brug [Power Automate Desktop](./desktop/introduction.md) i stedet.

-   Højreklik understøttes ikke. 

-   Yderligere input til flow for brugergrænsefladen på internettet genereres, når du bruger Foreach-kommandoer. Du kan løse dette problem ved at angive en vilkårlig værdi i de ekstra felter. Det påvirker ikke afspilningen.

-   Hvis .side-filen indeholder flere testprojekter, er det kun den første, der blev oprettet, som kører. 

     >[!TIP]
     >Bemærk, at Selenium IDE rangerer testene efter navn og ikke efter oprettelsesdato, så den første test, der blev oprettet, er måske ikke den første på listen.

-   Afspilning direkte i Selenium IDE fungerer muligvis ikke efter hensigten. Afspilning ved kørsel via infrastrukturen for flow for brugergrænsefladen fungerer dog korrekt.

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [kører flow for brugergrænseflade](run-ui-flow.md).

- Hvis du vil foretage dig mere med flow for brugergrænseflade, kan du også afprøve flow for brugergrænseflade med [input- og output](inputs-outputs-web.md)-parametre.

 
