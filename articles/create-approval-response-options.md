---
title: Opret godkendelsesflow med brugerdefinerede svar | Microsoft Docs
description: Opret godkendelsesflow med brugerdefinerede svar.
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
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: 7b7db352244a08d05e5b23fbbb2cefe46a55d67a
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/15/2020
ms.locfileid: "3697143"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Opret brugerdefinerede svarmuligheder for godkendelsesflow


Lad os sige, at du vil sende en godkendelsesanmodning, hver gang en medarbejder uploader en udgiftsrapport til SharePoint, og derefter vil tillade, at godkenderen svarer med en af følgende tre muligheder: Acceptér, Der kræves flere oplysninger eller Afvis.


## <a name="prerequisites"></a>Forudsætninger

- En Power Automate-konto.
- En SharePoint-liste, hvor medarbejderne kan angive deres udgiftsrapporter.

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="create-approval-flow"></a>Opret godkendelsesflow
1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flows** på navigationslinjen til venstre.
1. Vælg **Ny** > **Automatiseret – fra bunden**.

    ![Muligheden Opret fra bunden](media/create-approval-response-options/create-approval-response-options.png)

1. Angiv et navn til flowet i **Flownavn**på den skærm, der vises. 
  
1. Søg efter **SharePoint** i **Vælg flowetsudløser**, vælg **Når der oprettes et element** på listen over udløsere, og Vælgderefter **Opret**.

   ![Vælg Opret fra bunden](media/create-approval-response-options/create-from-blank.png)

1. Angiv **Websiteadresse** og **Listenavn** for SharePoint. 

   >[!TIP]
   >Vælg **Angiv brugerdefineret værdi** i feltet **Websiteadresse**, før du indtaster tekst i **Websiteadresse**.

1. Vælg **Nyt trin**, søg efter **Godkendelse**, og vælg derefter **Start, og vent på en godkendelse**.

1. På kortet **Start og vent på en godkendelse** skal du vælge listen **Godkendelsestype**.

1. Vælg **Brugerdefinerede svar – Vent på et svar**.

    ![Godkendelsestype](media/create-approval-response-options/select-approval-type.png)

    Derefter skal du oprette de brugerdefinerede svar, som dine godkendere skal bruge, når de besvarer en godkendelsesanmodning for en medarbejderudgift.


1. I feltet **Element for svarmuligheder** skal du angive **Acceptér** og derefter vælge **Tilføj et nyt element**. 

    ![Brugerdefineret svar 1](media/create-approval-response-options/enter-response-1.png)

1. I feltet **Element for svarmuligheder** skal du angive **Afvis** og derefter vælge **Tilføj et nyt element**.

1. I feltet **Element for svarmuligheder** skal du angive **Der kræves flere oplysninger**.

    ![Brugerdefineret svar 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Angiv en **Titel**, **Tildelt til** (mail til godkenderen) og **Oplysninger** (oplysningerne skal være indeholdt i godkendelsesanmodningen).

    Her er et eksempel på, hvad du kan inkludere for din organisation.

    ![Oplysninger om brugerdefinerede svar](media/create-approval-response-options/enter-title-assigned-to-details.png)


Nu, hvor du har oprettet dine brugerdefinerede svar, kan det være en god idé at udføre forskellige ting i dit flow, afhængigt af svaret fra godkenderen.


## <a name="use-approval-responses"></a>Brug godkendelsessvar 

Hvis svaret på anmodningen er **Acceptér**, kan det være en god idé at sende en mail til regnskabsafdelingen, hvor de bliver bedt om at refundere medarbejderen for udgiften. 

Hvis svaret er **Afvis**, kan det være en god idé at sende en mail til medarbejderen, så vedkommende kan se, at anmodningen blev afvist.

Og endelig, hvis svaret fra godkenderen er **Angiv flere oplysninger**, kan det være en god idé at sende en mail til medarbejderen, hvor du anmoder om at få flere oplysninger.

Hvis du vil gøre noget af dette i flowet, skal du tilføje en [**Betingelse**](add-condition.md) eller en handling af typen **Skift** til dit flow og derefter vælge feltet **Resultat** i godkendelsesanmodningen fra den dynamiske indholdsvælger. Sørg for at bekræfte, om værdien er Acceptér, Angiv flere oplysninger eller Afvis.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Besvar godkendelsesanmodninger med et brugerdefineret svar

Godkendere modtager godkendelsesanmodninger via mail. Anmodningerne vises også i godkendelsescenteret i Power Automate. 

![Mail med godkendelsesanmodning](media/create-approval-response-options/approval-request-email.png)

## <a name="limitations"></a>Begrænsninger

Der er en grænse på fem brugerdefinerede svar i forbindelse med meddelelser i Outlook og Outlook Web Access (OWA), der kan udføres. Det betyder, at det kun er de fem første svar, der defineres i løbet af flowet, der kan ses i sektionen med brugbare muligheder i Power Automate-godkendelsesmails. Du kan sende de resterende indstillinger via en HTML-mail, der ikke kan reageres på, Power Automate-godkendelsescenter, Power Automate-mobilprogram eller teams.

>[!NOTE]
>I forbindelse med godkendelser, der bruger et enkelt brugerdefineret svar, kan Outlook og OWA udvide svarfeltet, så brugerne ikke behøver at vælge en knap, før de kan svare, som når der er flere godkendelsesmuligheder.

## <a name="learn-more"></a>Få mere at vide
- Opret [enkelte godkenderflows](modern-approvals.md)
- Opret [fortløbende godkenderflows](sequential-modern-approvals.md)
