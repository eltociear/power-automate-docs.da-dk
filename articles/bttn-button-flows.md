---
title: Start flows med bttns | Microsoft Docs
description: Få mere at vide om, hvordan du starter dine flows med en bttn
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
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4eaafb1a551cc3333cde2058aebc41076b0267bd
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297137"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Kør dine flows med fysiske bttns fra The Button Corporation (prøveversion)

Udløs dine flows ved at trykke på en bttn (en fysisk knap, der er oprettet af [The Button Corporation](https://my.bt.tn/)). Du kan f.eks. trykke på en bttn, der udløser et flow, for at udføre følgende opgaver:

* kontakter helpdesk med placeringsoplysninger
* sender en mail til dit team
* blokerer din kalender
* genbestiller artikler

> [!IMPORTANT]
> Du skal [registrere](https://my.bt.tn/) din bttn, før du kan bruge den i et flow.
> 
> [!TIP]
> Konfigurer alle bttn-egenskaber, f.eks. navn, placering og mailadresse, på [bttn-webstedet](https://my.bt.tn/), før du opretter dit flow.
> 
> 

Du kan også udløse et flow ved hjælp af en [fysisk Flic-knap](flic-button-flows.md).

## <a name="prerequisites"></a>Forudsætninger
* Adgang til [Power Automate](https://flow.microsoft.com).
* Mindst én [registreret bttn](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Opret et flow, der udløses af en bttn
I denne gennemgang bruger vi en helpdeskskabelon til at oprette et flow, som du kan udløse med et enkelt tryk på en [bttn](https://my.bt.tn/). Når der køres flows, oprettes der en anmodning om support, som derefter sendes til helpdesk. Supportanmodningen oplyser helpdesk om placeringen af det lokale, hvor der er brug for hjælp. Denne gennemgang viser, hvordan du opretter dette flow ud fra en skabelon, men du kan bruge den tomme skabelon, hvor du selv kan styre alle aspekter i dit flow.

Du kan bruge en hvilken som helst af disse skabeloner til hurtigt at oprette flows for din bttn og oprette forbindelse til bl.a. Zendesk, Google og SharePoint:

![bttn-skabeloner](./media/bttn-button-flows/bttn-templates.png)

Tip! I forbindelse med denne gennemgang skal du give din bttn et navn, der repræsenterer et mødelokale i en typisk kontorbygning.

Indstillingerne for din bttn skal ligne dette eksempel (fra bttn-webstedet):

![bttn-skabeloner](./media/bttn-button-flows/bttn-config.png)

Nu, hvor du har registreret og konfigureret din bttn, kan vi komme i gang med at oprette vores flow.

### <a name="sign-in-and-select-a-template"></a>Log på, og vælg en skabelon
1. Log på [Power Automate](https://flow.microsoft.com).
   
    ![log på](./media/bttn-button-flows/sign-into-flow.png)
   
    Bemærk! Du kan også oprette flows i Power Automate-mobilappen til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).
2. Skriv **bttn** i søgefeltet, og vælg derefter søgeikonet.
   
    ![søg](./media/bttn-button-flows/bttn-search-template.png)
   
    Når du har valgt søgeikonet, vises alle skabeloner, du kan bruge med bttns.
3. Vælg skabelonen **Brug Bttn til at ringe til teknisk support for mødelokale**.
   
    ![supportskabelon](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-power-automate-to-connect-to-your-bttn"></a>Tillad Power Automate at oprette forbindelse til din bttn
1. Hvis du bliver bedt om det, skal du logge på bttn og Office 365 Outlook-tjenester, og dermed aktiveres knappen **Fortsæt**.
   
    ![legitimationsoplysninger](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Når du logger på bttn-tjenesten, skal du give Power Automate tilladelse til at bruge dine bttns.
   
    **Vigtigt!** Hvis du ikke giver Power Automate tilladelse til at bruge dine bttns, kan du ikke se eller oprette forbindelse til dem fra Power Automate.
   
    ![giv tilladelse](./media/bttn-button-flows/authorize-bttn.png)
3. Når du er logget på begge tjenester, skal du vælge **Fortsæt**.
   
    ![Fortsæt](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Vælg den bttn, der udløser flowet
1. På kortet **Når der trykkes på en bttn** skal du åbne listen over bttn-id'er og derefter vælge den bttn, du vil bruge.
   
    ![vælg bttn](./media/bttn-button-flows/bttn-id.png)
   
    Dit flow skal se ud som i dette eksempel.
   
    ![oversigt over flow](./media/bttn-button-flows/bttn-done.png)
2. Navngiv dit flow, og vælg derefter **Opret flow** for at gemme det.
   
    ![gem flow](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Test dit flow, og tjek resultaterne
1. Tryk på knappen på din bttn.
2. Se kørselsoversigten for dit flow for at bekræfte, at den blev kørt.
   
    Du kan kontrollere kørselsoversigten på webstedet Power Automate eller på din mobilenhed.
   
    Bemærk! Kørselsstatus er angivet til **kører**, indtil en bruger vælger **Bekræft** i mailen med supportanmodningen.
3. Du kan også bekræfte, at mailen er sendt til supportteamet.
   
    Hvis du har fulgt med, ser supportmailen ud som i dette eksempel:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Fejlfinding
* Hvis dit flow ikke blev udløst, skal du logge på webstedet for The Button Corporation og bekræfte, om knapaktiviteten (tryk på knappen) registreres.
* Du kan også analysere kørselsaktiviteten på webstedet for Power Automate og kontrollere, om der er fejlmeddelelser.

## <a name="more-information"></a>Flere oplysninger
* [Del knapflows](share-buttons.md).
* Se, hvordan du kan bruge [knapudløsertokens](introduction-to-button-trigger-tokens.md) til at sende aktuelle data, når dine knapflows køres.
* [Installer Power Automate-appen for Android](https://aka.ms/flowmobiledocsandroid).
* [Installer Power Automate-appen for iOS](https://aka.ms/flowmobiledocsios).

