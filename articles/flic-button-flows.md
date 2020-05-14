---
title: Start flows med Flic-knapper | Microsoft Docs
description: Start nemt knapflows med fysiske Flic-knapper fra Shortcut Labs.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/19/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 65d9a93215030905f41e082d38789592a4267404
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297401"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Kør dine flows ved at trykke på en Flic-smartknap

Udløs dine flows ved at trykke på en fysisk knap, kaldet Flic, fra Shortcut Labs. Du kan for eksempel trykke på en Flic-knap for at registrere arbejdstimer, blokere din kalender, tælle antal deltagere ved et arrangement eller gemme geografiske lokationer.

> [!IMPORTANT]
> Konfigurer alle Flic-egenskaber ved hjælp af Flic-mobilappen til [Android](https://play.google.com/store/apps/details?id=io.flic.app) eller [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8), før du opretter dit flow.
> 
> 

## <a name="prerequisites"></a>Forudsætninger
For at bruge Flics sammen med Power Automate skal du have:

* Adgang til [Power Automate](https://flow.microsoft.com).
* Downloadet Flic-mobilappen til [Android](https://play.google.com/store/apps/details?id=io.flic.app) eller [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) og bruge den til at parre en eller flere Flics.

## <a name="configure-flic-properties"></a>Konfigurer Flic-egenskaber
Brug Flic-mobilappen til at programmere Flic-hændelser. Der er følgende hændelser:

* click (klik, et hurtigt tryk)
* double-click (dobbeltklik, to hurtige tryk)
* hold (et langt tryk)

I dette skærmbillede kan du se eksempler på, hvordan konfigurationen af Flic-knapper kan se ud:

![Konfigurer Flic-knapper](./media/flic-button-flows/configure-flic-actions.png)

Når du har knyttet en Flic-hændelse til Power Automate, kan du derefter vælge den pågældende Flic som udløser for dine flows. Du skal vælge udløseren senere i denne gennemgang.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Opret et flow, der udløses af en Flic-knap
I denne gennemgang bruger vi en Flic-knap til at køre et flow, som optager, hvor lang tid en kunde bruger hos hver kunde. Konsulenten trykker på sin Flic-knap, når han ankommer hos kunden, og han trykker på den igen, når han forlader kunden. Hvert tryk på Flic-knappen kører det flow, som knappen er knyttet til. Flowet gemmer derefter det aktuelle klokkeslæt i Google Sheets og sender en meddelelse i en mail. Mailen indeholder detaljer om kørslen af flowet.

Bemærk! Husk, at du skal have brugt Flic-mobilappen til at parre og konfigurere mindst én **klik**-handling for at udløse Power Automate. I dette skærmbillede har jeg konfigureret **klik**-handlingen til at udløse Power Automate. Senere i denne gennemgang konfigurerer vi vores flow til at blive udløst, når der trykkes én gang på Flic-knappen (et klik).

   ![flic-konfiguration](./media/flic-button-flows/flic-configured-for-flow.png)

Lad os komme i gang med at oprette vores flow.

### <a name="start-with-a-template"></a>Start med en skabelon
1. Log på [Power Automate](https://flow.microsoft.com).
   
    ![log på](./media/flic-button-flows/sign-into-flow.png)
2. Skriv **flic** i søgefeltet, og vælg derefter søgeikonet.
   
    ![søg efter flic](./media/flic-button-flows/search-flic.png)
3. Vælg skabelonen **Track your working hours with Flic smart button**.
   
    ![vælg skabelon](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Opret et regneark i Google Sheets
1. Gennemse detaljerne i skabelonen, og vær opmærksom på, at skabelonen kræver et regneark i Google Sheets.
   
   ![gennemse skabelondetaljer](./media/flic-button-flows/flic-template-details.png)
2. I Google Sheets kan du oprette et regneark, der indeholder et ark med kolonner med navnene **Kliktype** og **Tidspunkt**.
   
      Tip! Du kan skrive kolonnenavne øverst i kolonnen i Google Sheets. Dit regneark skal se ud som dette skærmbillede:
   
   ![Google Sheets](./media/flic-button-flows/flic-google-sheet.png)
   
   Bemærk! Du skal bruge regnearket senere i gennemgangen.

### <a name="add-the-flic-trigger-to-your-flow"></a>Føj Flic-udløseren til dit flow
1. Log på skabelontjenesterne, og vælg derefter **Fortsæt**.
   
     **Fortsæt** aktiveres, når du har logget på alle de tjenester, der kræves til skabelonen.
   
    ![angiv legitimationsoplysninger](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Skriv **flic** i søgefeltet, og vælg derefter udløseren **Flic - When a Flic is pressed**.
   
    ![søg efter flic-udløser](./media/flic-button-flows/flic-search-trigger.png)
3. Vælg den Flic, du vil bruge, på listen **Flic button** på kortet **Flic - When a Flic is pressed**.
4. Vælg **click** på listen **Hændelser** for at angive, at du vil udløse flowet, når der trykkes én gang på Flic-knappen.
   
    ![vælg flic-handling](./media/flic-button-flows/select-flic.png)
   
   Du kan eventuelt vælge **any** for at angive, at hver Flic-hændelse (click, double-click eller hold) udløser flowet.
   
   **Double-click** indikerer, at flowet udløses, når der trykkes to gange på Flic-knappen. **Hold** indikerer, at Flic udløser flowet, når knappen holdes trykket ned.
   
   Du kan selv oprette andre flows og udløse dem ved hjælp af de andre hændelser på listen **Hændelser**. Du kan f.eks. bruge hændelsen **double-click** til at registrere, hvornår du forlader kunden.

### <a name="configure-the-sheet"></a>Konfigurer arket
   På kortet **Insert row**:

1. Vælg det regneark, du oprettede tidligere, på listen **Fil**.
2. Vælg arket på listen **Regneark**.
   
   Bemærk! Der vises to ekstra felter på kortet **Insert row**, når du har valgt arket. Disse felter repræsenterer de to kolonner i det regneark, du oprettede tidligere.
3. Vælg feltet **Kliktype**, og vælg derefter tokenet **Kliktype**.
4. Vælg feltet **Tidspunkt**, og vælg derefter tokenet **Kliktidspunkt**.
   
    ![konfigurer Google Sheets-data](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Kontrollér, at mailindstillingerne er korrekte
1. Bekræft, at kortet **Send me an email notification** ser ud som i dette skærmbillede.
   
    ![bekræft mailmeddelelse](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Gem og test dit flow
1. Giv dit flow et navn, og gem det.
   
    ![gem dit flow](./media/flic-button-flows/save.png)

Hvis du har fulgt med i vejledningen, kan du trykke på Flic-knappen én gang for at udløse flowet. Flowet registrerer derefter kliktypen og det aktuelle klokkeslæt i arket og sender en mail til dig.

1. Tryk på Flic-knappen én gang.
2. Åbn dit regneark i Google Sheets. Du skulle nu gerne se, at kolonnerne **Kliktype** og **Tidspunkt** er udfyldt med henholdsvis "click" og klokkeslættet.
   
    ![se kørselsresultaterne](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Du kan også se resultatet af kørslen fra websitet for Power Automate eller mobilappen Power Automate. Her er et skærmbillede af min testkørsel
   
    ![gem dit flow](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Sådan ser brødteksten i mailmeddelelsen, som jeg har modtaget fra kørslen af flowet, ud.
   
    ![gem dit flow](./media/flic-button-flows/flic-email-body.png)

Som en øvelse kan du prøve at udvide dit flow til automatisk at registrere din placering (længdegrad og breddegrad), når du trykker på Flic-knappen.

## <a name="more-information"></a>Flere oplysninger
* [Del knapflows](share-buttons.md).
* Se, hvordan du kan bruge [knapudløsertokens](introduction-to-button-trigger-tokens.md) til at sende aktuelle data, når dine knapflows eksekveres.
* Installer Power Automate-mobilappen for [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).

