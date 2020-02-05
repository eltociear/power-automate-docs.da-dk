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
ms.openlocfilehash: d33b1e78678c7029d441bcf00f6c066d7f492a66
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74359238"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Opret brugerdefinerede svarmuligheder for godkendelsesflow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Lad os sige, at du vil sende en godkendelsesanmodning, hver gang en medarbejder uploader en udgiftsrapport til SharePoint, og derefter vil tillade, at godkenderen svarer med en af følgende tre muligheder: Acceptér, Angiv flere oplysninger eller Afvis.


## <a name="prerequisites"></a>Forudsætninger

- En Power Automate-konto.
- En SharePoint-liste, hvor medarbejderne kan angive deres udgiftsrapporter.

## <a name="create-approval-flow"></a>Opret godkendelsesflow
1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** på navigationslinjen til venstre.
1. Vælg **Nyt** > **Opret fra bunden**.

    ![Muligheden Opret fra bunden](media/create-approval-response-options/create-approval-response-options.png)

1. På den skærm, der åbnes, skal du vælge **Opret fra bunden**. 

    ![Vælg Opret fra bunden](media/create-approval-response-options/create-from-blank.png)

1. Søg efter **SharePoint**, og vælg derefter **Når der oprettes et element** på listen over udløsere. 

1. Angiv **Webstedsadressen** og **Navnet på listen** på SharePoint. 

1. Vælg **Nyt trin**, søg efter **Godkendelse**, og vælg derefter **Start, og vent på en godkendelse (v2)** .

1. På kortet **Start, og vent på et godkendelse (v2)** skal du vælge listen **Godkendelsestype**.

    ![Godkendelsestype](media/create-approval-response-options/select-approval-type.png)

1. Vælg **Brugerdefinerede svar – Vent på et svar (Premium)** .

    ![Brugerdefinerede svar](media/create-approval-response-options/select-custom-responses.png)

    Derefter skal du oprette de brugerdefinerede svar, som dine godkendere skal bruge, når de besvarer en godkendelsesanmodning for en medarbejderudgift.


1. I feltet **Element for svarmuligheder – 1** skal du angive **Acceptér** og derefter vælge **Tilføj et nyt element**. 

    ![Brugerdefineret svar 1](media/create-approval-response-options/enter-response-1.png)

1. I feltet **Element for svarmuligheder – 2** skal du angive **Afvis** og derefter vælge **Tilføj et nyt element**.

    ![Brugerdefineret svar 2](media/create-approval-response-options/enter-response-2.png)

1. I feltet **Element for svarmuligheder – 3** skal du angive **Angiv flere oplysninger**.

    ![Brugerdefineret svar 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Angiv en **Titel**, **Tildelt til** (mail til godkenderen) og **Oplysninger** (oplysningerne skal være indeholdt i godkendelsesanmodningen).

    Her er et eksempel på, hvad du kan inkludere for din organisation.

    ![Oplysninger om brugerdefinerede svar](media/create-approval-response-options/enter-title-assigned-to-details.png)


Nu, hvor du har oprettet dine brugerdefinerede svar, kan det være en god idé at udføre forskellige ting i dit flow, afhængigt af svaret fra godkenderen.


## <a name="use-approval-responses"></a>Brug godkendelsessvar 

Hvis svaret på anmodningen er **Acceptér**, kan det være en god idé at sende en mail til regnskabsafdelingen, hvor de bliver bedt om at refundere medarbejderen for udgiften. 

Hvis svaret er **Afvis**, kan det være en god idé at sende en mail til medarbejderen, så vedkommende kan se, at anmodningen blev afvist.

Og endelig hvis svaret fra godkenderen er **Angiv flere oplysninger**, kan det være en god idé at sende en mail til medarbejderen, hvor du anmoder om at få flere oplysninger.

Hvis du vil gøre noget af dette i flowet, skal du føje en [**Betingelse**](add-condition.md) eller en handling af typen **Skift** til dit flow og derefter vælge feltet **Resultat** i godkendelsesanmodningen fra den dynamiske indholdsvælger. Sørg for at bekræfte, om værdien er Acceptér, Angiv flere oplysninger eller Afvis.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Besvar godkendelsesanmodninger med et brugerdefineret svar

Godkendere modtager godkendelsesanmodninger via mail. Anmodningerne vises også i godkendelsescenteret i Power Automate. 

![Godkendelsesanmodning i mail](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Få mere at vide
- Opret [enkelte godkenderflow](modern-approvals.md)
- Opret [fortløbende godkenderflow](sequential-modern-approvals.md)
