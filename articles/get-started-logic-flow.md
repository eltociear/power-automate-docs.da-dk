---
title: Automatiser opgaver ved at oprette et flow | Microsoft Docs
description: Opret et flow, der automatisk udfører en eller flere handlinger, f.eks. afsendelse af mail, når der indtræffer hændelser, f.eks. at en person føjer en række til en SharePoint-liste.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 569408367130c6f5121b30d2c8c14833b142b934
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74368783"
---
# <a name="create-a-flow-in-power-automate"></a>Opret et flow i Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Opret et flow, der automatisk udfører en eller flere handlinger, når det er udløst af en hændelse. Opret f.eks. et flow, der giver dig besked via mail, når nogen sender et tweet, der indeholder et nøgleord, som du angiver. I dette eksempel er afsendelsen af et tweet hændelsen, og afsendelsen af mail er handlingen.

## <a name="prerequisites"></a>Forudsætninger

* En konto på [flow.microsoft.com](https://flow.microsoft.com)
* En Twitter-konto
* Office 365-legitimationsoplysninger

## <a name="specify-an-event-to-start-the-flow"></a>Angiv en hændelse for at starte flowet

Først skal du skal vælge, hvilken hændelse eller *udløser* der starter dit flow.

1. På [flow.microsoft.com](https://flow.microsoft.com) skal du vælge **Mine flows** på den øverste navigationslinje og derefter vælge **Opret fra bunden**.

    ![Indstillingen Flows i den venstre navigationslinje](./media/get-started-logic-flow/create-logic-flow.png)
1. Markér afkrydsningsfeltet **Søg blandt hundredvis af forbindelser og udløsere** nederst på skærmen, angiv **Twitter** i feltet **Søg i alle forbindelser og udløsere**, og markér derefter **Twitter – Når der postes et nyt tweet**.

    ![Twitter-hændelse](./media/get-started-logic-flow/twitter-search.png)

   >[!TIP]
   >Connectors understøtter flere godkendelsestyper. SQL Server understøtter f.eks. Azure AD, SQL Server-godkendelse, Windows-godkendelse og SQL-forbindelsesstreng. Brugere vælger, hvilken type godkendelse de vil bruge til at konfigurere en connector.

1. Hvis du ikke allerede har oprettet forbindelse mellem din Twitter-konto og Power Automate, skal du vælge **Log på Twitter** og derefter angive dine legitimationsoplysninger.

1. I feltet **Søgetekst** skal du skrive det nøgleord, du vil finde.

    ![Twitter-nøgleord](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Angiv en handling

1. Vælg **Nyt trin**, og vælg derefter **Tilføj en handling**.

    ![Tilføj handling](./media/get-started-logic-flow/add-action-icon.png)

1. I feltet **Søg i alle forbindelser og handlinger** skal du skrive eller indsætte **send mail**, og derefter skal du vælge **Office 365 Outlook – send en mail**.

    ![Liste over handlinger](./media/get-started-logic-flow/send-email.png)

1. Hvis du bliver bedt om det, skal du klikke på knappen Log på og derefter angive dine legitimationsoplysninger.

1. I den viste formular skal du skrive eller indsætte din mailadresse i feltet **Til** og derefter vælge dit navn på den viste liste over kontakter.

    ![Tom mail](./media/get-started-logic-flow/blank-email.png)
1. I feltet **Emne** skal du skrive eller indsætte **Nyt tweet fra:** og derefter angive et mellemrum.

    ![Emnelinje med pladsholder](./media/get-started-logic-flow/message-token.png)
1. På listen over tokens skal du vælge tokenet **Tweetet af** for at tilføje en pladsholder for den.

    ![Tilføj parameter](./media/get-started-logic-flow/add-parameter.png)
1. Markér afkrydsningsfeltet **Meddelelsestekst**, og klik derefter på tokenet **Tweettekst** for at tilføje en pladsholder for den.
1. (valgfrit) Føj flere tokens, andet indhold eller begge dele til brødteksten i mailen.
1. Angiv et navn til dit flow i den øverste del af skærmen, og vælg derefter **Opret flow**.

    ![Klik på knappen Opret flow](./media/get-started-logic-flow/create-button.png)
1. Vælg **Udført** for at opdatere listen over flows.

     ![Vælg knappen Udført](./media/get-started-logic-flow/done-button.png)
1. Send et tweet vha. det angivne nøgleord, eller vent på, at en anden poster et sådant tweet.

     Inden for et minut efter tweetet er postet, får du besked om det nye tweet via mail.

> [!TIP]
> Brug handlingen **Send mail (v2)** til at formatere en mail, hvor du tilpasser skrifttypen, bruger fed, kursiv eller understregning, tilpasser farve og fremhævninger og opretter lister eller links med mere.

![Detaljeret redigering af mail](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Administrer et flow

1. På [flow.microsoft.com](https://flow.microsoft.com) skal du vælge **Mine flows** på den øverste navigationslinje.
1. På listen over flows kan du gøre følgende:

   * Indstil til/fra-knappen for et flow til **Fra** for at afbryde det midlertidigt.

       ![Afbryd flow midlertidigt](./media/get-started-logic-flow/pause-flow.png)
   * Indstil til/fra-knappen for et flow til **Til** for at fortsætte det.

       ![Fortsæt flow](./media/get-started-logic-flow/resume-flow.png)
   * Hvis du vil redigere et flow, skal du vælge blyantsikonet, der svarer til det flow, du vil redigere.

       ![Vælg flow](./media/get-started-logic-flow/select-flow.png)
   * Hvis du vil slette et flow, skal du vælge ikonet **...** , vælge **Slet** og derefter vælge **Slet** i den meddelelsesboks, der vises.

       ![Ikonet Slet](./media/get-started-logic-flow/delete-icon.png)
   * For at få vist kørselsoversigten i et flow skal du vælge flowet fra siden **Mine flows** og derefter få vist historikken i afsnittet **KØRSELSOVERSIGT** på siden, der åbnes.

       ![kørselsoversigt](./media/get-started-logic-flow/run-history.png)

     Vælg en kørsel af flow på listen over kørsler for at se input og output for hvert trin.

> [!NOTE]
> Du kan have op til 600 flow på din konto. Hvis du allerede har 600 flow, skal du slette et, før du kan oprette et nyt.
>
>

## <a name="next-steps"></a>Næste trin

* [Tilføj trin](multi-step-logic-flow.md), f.eks. forskellige måder at få meddelelser på, til dit flow.
* [Kør opgaver efter en tidsplan](run-scheduled-tasks.md), når du ønsker, at en handling skal foregå hver dag, på en bestemt dato eller efter et bestemt antal minutter.
* [Føj et flow til en app](https://powerapps.microsoft.com/tutorials/using-logic-flows/), så din app kan igangsætte logik i cloudmiljøet.
* [Kom i gang med teamflows](create-team-flows.md), og inviter andre til at samarbejde med dig om at designe flows.
