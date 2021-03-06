---
title: Vente på godkendelse i et flow | Microsoft Docs
description: Flow kan vente på, at en ekstern hændelse opstår, f.eks. at en bruger godkender eller afviser en ændring, før der udføres en handling, f.eks. afsendelse af en meddelelse om beslutningen.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4cd78984e505843277e76b8e8c54636b0b001f71
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/15/2020
ms.locfileid: "3696879"
---
# <a name="wait-for-approval-in-power-automate"></a>Vent på godkendelse i Power Automate


> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>

Opret et flow, der, hvis du opretter et element i SharePoint, sender mail til godkendelse og underretter dig om, hvorvidt elementet blev godkendt eller afvist. For at følge dette selvstudium nøjagtigt, skal du oprette en enkel SharePoint-liste som en udløserhandling, men du kan bruge en anden datakilde, f.eks. Dropbox eller OneDrive.

## <a name="prerequisites"></a>Forudsætninger

* Opret en enkel SharePoint-liste, der hedder **Projektsporing**, tilføj en kolonne med navnet **Titel**, og tilføj derefter en person- eller gruppekolonne med navnet **Tildelt til**.

   ![Billede af SPO-listen Projektsporing](./media/wait-for-approvals/project-tracker.png)

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="add-an-event-to-trigger-the-flow"></a>Tilføje en begivenhed, der udløser flowet

1. Log på [Power Automate](https://flow.microsoft.com), vælg **Mine flows** på den øverste navigationslinje, og vælg derefter **Opret fra bunden**.

1. Markér afkrydsningsfeltet **Søg blandt hundredvis af connectorer og udløsere**, angiv **nyt element**, og gå derefter til **SharePoint – når et element oprettes**.

1. Log på SharePoint, hvis du bliver bedt om det.
1. Under **Websiteadresse** skal du angive URL-adressen på det SharePoint-website, der indeholder din liste.

1. Under **Listenavn** skal du vælge den liste, du oprettede tidligere. Hvis du følger med, er navnet **Projejektsporing**.

    ![Billede af SPO-listenavn](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Tilføje den resulterende handling

1. Vælg knappen **Nyt trin**, og vælg derefter **Tilføj en handling.**

1. I feltet **Søg i alle connectorer og handlinger** skal du skrive eller indsætte **send mail**, og derefter skal du vælge **Office 365 Outlook – send en mail med valgmuligheder**.

1. Log på Office 365 Outlook, hvis du bliver bedt om det.

1. Vælg feltet **Til**, og vælg derefter tokenet **Tildelt til mail**.

    Brugeren i kolonnen **Tildelt til** modtager mailen for at godkende eller afvise elementer. Når du opretter et element for at teste flowet, skal du angive dig selv i dette felt. På den måde godkender eller afviser du ikke blot elementet, men du modtager også meddelelsesmailen.

    > [!NOTE]
    > Du kan tilpasse felterne **Emne** og **Brugerindstillinger**, så de passer til dine behov.

    ![Billede af feltet Send godkendelsesmail](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Tilføj en betingelse

1. Vælg knappen **Nyt trin**, og vælg derefter **Tilføj en betingelse**.

    ![Billede af Tilføj en betingelse](./media/wait-for-approvals/add-a-condition.png)
1. Markér det første afkrydsningsfelt, og vælg derefter tokenet **SelectedOption**.
1. Markér det sidste afkrydsningsfelt, og skriv derefter **Godkend**.

    ![Billede af betingelseskortet](./media/wait-for-approvals/condition-card-2.png)

1. Vælg **Tilføj en handling** i området **Hvis ja**.

1. I feltet **Søg i alle connectorer og handlinger** skal du skrive eller indsætte **send mail**, og derefter skal du vælge **Office 365 Outlook – send en mail**.

1. I feltet **Til** skal du angive en modtager. f.eks. **Oprettet via mail**.

1. Angiv et emne i feltet **Emne**.

    Vælg f.eks. **Tildelt til DisplayName**, skriv **har godkendt** med et mellemrum på hver side, og vælg derefter **Titel**.

1. I feltet **Meddelelsestekst** skal du angive en meddelelsestekst til mailen, f.eks. **Gå videre til næste fase af projektet.**

    > [!NOTE]
    > Den person, der oprettede elementet på SharePoint-listen får besked om, hvorvidt projektet blev godkendt eller forkastet.

    ![Billede af ja-send-mail](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. I området **Hvis nej** skal du gentage de sidste fem trin, du skal blot ændre **emnet** og **meddelelsesteksten**, så de afspejler, at projektet blev afvist.

     ![Billede af nej-send-mail](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Afslutte og teste dit flow

1. Navngiv dit flow, og vælg derefter **Opret flow**.

     ![Billede af opret-flow](./media/wait-for-approvals/create-flow.png)
1. Opret et element på SharePoint-listen.

    Der er sendt en godkendelsesmail til den modtager, du har angivet. Når modtageren vælger **Godkend** eller **Afvis** i den pågældende mail, modtager du en mail, der angiver svaret.

## <a name="learn-more"></a>Få mere at vide

* [Gennemgang af en enkelt godkenders moderne godkendelse](modern-approvals.md)
* Oprette [sekventielle godkendelser](sequential-modern-approvals.md)
* Oprette [parallelle godkendelser](parallel-modern-approvals.md)
* Godkende [anmodninger, mens du er på farten](mobile-approvals.md)
