---
title: Send vedhæftede filer med godkendelsesanmodninger | Microsoft Docs
description: Få mere at vide om, hvordan du opretter flow, der sender vedhæftede filer med godkendelsesanmodninger.
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
ms.date: 12/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1506902cdd6afe90d7e12a910e2e14519cae7554
ms.sourcegitcommit: c6c4150daadbcc38ef1a33a5903df531b8461ace
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/14/2020
ms.locfileid: "75942994"
---
# <a name="create-approval-flows-with-attachments"></a>Opret godkendelsesflow med vedhæftede filer

Nogle gange har du brug for at få en fil godkendt til forretningsmæssige formål. Det kan du heldigvis bruge Power Automate-godkendelser til. Lad os f.eks. sige, at du er revisor, og du vil have en faktura godkendt. Det kan du oprette et øjeblikkeligt flow til, som gør det muligt for dig at sende filen til godkendelse ved blot at trykke på en knap og vælge den fil, der skal sendes.

I denne artikel får du mere at vide om, hvordan du opretter et godkendelsesflow, der sender en vedhæftet fil, som godkenderen skal gennemgå, før vedkommende beslutter sig for, om anmodningen skal godkendes.

## <a name="create-the-flow"></a>Opret flowet

1. Log på Power Automate.
1. Vælg **Mine flow** > **Ny** > **Øjeblikkeligt fra bunden**.

    ![Nyt flow øjeblikkeligt fra bunden](./media/approval-attachments/new-instand-blank.png)

1. Giv dit flow et navn > søg efter, og vælg derefter **Udløs et flow manuelt**, og vælg derefter **Opret**.

    ![Navngiv dit flow, og vælg en udløser](./media/approval-attachments/name-flow-trigger.png)

1. Vælg udløseren **Udløs et flow manuelt** > **Tilføj et input** > **Fil**.

     Under de forrige trin konfigureres dit flow, så der, når det kører, anmodes om en fil fra brugeren for at udløse dit flow.

1. Vælg **Nyt trin**
1. Søg efter **Godkendelser**, og vælg derefter **Start og vent på en godkendelse**.
1. Vælg **Godkend/afvis – første til at reagere** på listen **Godkendelsestype** for kortet **Start, og vent på godkendelse**.
1. Angiv følgende oplysninger på kortet **Start, og vent på godkendelse**:

   - **Titel** – en kort beskrivelse, der fortæller godkenderen, hvad anmodningen handler om.
   - **Tildelt til** – den person, anmodningen er sendt til.
   - **Detaljer** – den tekst, der vises i godkendelsesanmodningen.

     ![Kortet med godkendelsesanmodningen](./media/approval-attachments/approval-request-card.png)

1. Vælg **Vis avancerede indstillinger** for at få vist de felter, hvor du angiver oplysninger om den fil, der er vedhæftet anmodningen.
1. Angiv et filnavn under **Navn på vedhæftede filer – 1**

   >[!TIP]
   >Du skal inkludere det filtypenavn, der stemmer overens med den uploadede filtype.

1. Angiv indholdet af den fil, der skal sendes til godkenderen, i feltet **Indhold i vedhæftede filer – 1**. 

   Det kan du nemt gøre ved at bruge elementet **Filindhold** fra listen over dynamisk indhold, der vises, når du vælger feltet **Indhold i vedhæftede filer – 1**.

     ![Avancerede indstillinger for kortet med godkendelsesanmodning](./media/approval-attachments/approval-request-card-advanced-options.png)

1. Vælg **Gem** for at gemme dit flow.

## <a name="test-your-flow"></a>Test dit flow

Du kan teste dit flow ved at vælge **Test** og derefter uploade en. xlsx-fil.

1. Vælg **Test**.
1. Vælg **Jeg vil udføre udløserhandlingen**.

     ![Test dit flow](./media/approval-attachments/test-flow.png)

1. Vælg **Test** > **Fortsæt** for at starte testen.
1. Vælg **Importér**.

     ![](./media/approval-attachments/import-file.png)
1. Find filen, markér den, og vælg derefter **Åbn** for at uploade den fil eller det billede, du sender til godkendelse.

1. Vælg **Kør flow**.

   Du kan se, at testkørslen starter.

     ![Testen starter](./media/approval-attachments/test-started.png)

1. Vælg **siden Flowkørsler** for at overvåge status for testen.

## <a name="approve-the-request"></a>Godkend anmodningen

Den person, du sender godkendelsesanmodningen til, modtager en mail, der svarer til dette billede, hvor vedkommende kan se den vedhæftede fil og derefter **godkende** eller **afvise** anmodningen:

![Få vist mailen med anmodningen](./media/approval-attachments/approval-request-mail.png)

>[!TIP]
>Godkendere kan også gennemse anmodninger i godkendelsescenteret.

## <a name="learn-more"></a>Få mere at vide

I de fleste godkendelsesflow vil du give den person besked, som anmoder om godkendelse af beslutningen. Følg [artiklen om moderne godkendelser](modern-approvals.md#add-an-email-action-for-approvals) for at få mere at vide om, hvordan du føjer en **betingelse** til et godkendelsesflow for at udføre bestemte handlinger på baggrund af anmodningens **resultat**.

