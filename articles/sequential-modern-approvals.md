---
title: Oprette en moderne arbejdsproces til godkendelse med flere godkendere | Microsoft Docs
description: 'Oprette en moderne arbejdsproces til godkendelse med flere godkendere '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/13/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 240d043eaa9d38b371bff9bc7bd736dee48033e8
ms.sourcegitcommit: 7b39517611bff350c760e76d0d6eed03739194a7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/20/2020
ms.locfileid: "3710700"
---
# <a name="manage-sequential-approvals-with-power-automate"></a>Administrer sekventielle godkendelser med Power Automate

Nogle arbejdsprocesser kræver forhåndsgodkendelse, før den endelige godkender skal godkende dem. Et firma kan f.eks. have en sekventiel godkendelsespolitik, der kræver forhåndsgodkendelse for fakturaer over DKK 1.000,00, før de kan godkendes af økonomiafdelingen.

I denne gennemgang opretter vi et sekventielt godkendelsesflow til administration af medarbejderes anmodning om ferie.

> [!NOTE]
> SharePoint bruges kun som et eksempel. Det er ikke nødvendigt for at oprette godkendelsesflows. Du kan bruge en af de mere end 200 tjenester, som Power Automate kan integreres med, til at køre dine flows. Hvis du bruger SharePoint 2010, skal du se [Tilbagetrækning af SharePoint 2010-arbejdsproces](https://go.microsoft.com/fwlink/?linkid=2138686)

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]


## <a name="detailed-steps-in-the-flow"></a>Detaljerede trin i flowet

Flowet:

1. Starter, når en medarbejder opretter en anmodning om ferie på en [SharePoint Online-liste](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
1. Tilføjer anmodningen om ferie i godkendelsescentret og sender derefter en mail med anmodningen til forhåndsgodkenderen.
1. Sender en mail med afgørelsen om forhåndsgodkendelse til medarbejderen.
1. Opdaterer SharePoint Online-listen med godkenderens tidlige afgørelse og kommentarer.
   Bemærk! Hvis anmodningen er forhåndsgodkendt, fortsætter flowet med disse trin:
1. Sender anmodningen til den endelige godkender.
1. Sender en mail med afgørelsen om den endelige godkendelse til medarbejderen.
1. Opdaterer SharePoint-listen med den endelige afgørelse.

I dette billede opsummeres ovenstående trin:

   ![Diagram over sekventielt godkendelsesflow](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Forudsætninger

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

I forbindelse med denne gennemgang skal SharePoint Online-listen, som du opretter, indeholde følgende kolonner:

Den SharePoint Online-liste, som du opretter, skal indeholde følgende kolonner:

| Titel                   | Enkelt tekstlinje    |
|-------------------------|------------------------|
| Ændret                | Dato og klokkeslæt          |
| Oprettet                 | Dato og klokkeslæt          |
| Feriens startdato     | Dato og klokkeslæt          |
| Feriens slutdato       | Dato og klokkeslæt          |
| Kommentarer                | Enkelt tekstlinje    |
| Godkendt                | Ja/Nej                 |
| Kommentarer fra ledere        | Flere linjers tekst |
| Ændret                | Dato og klokkeslæt          |
| Oprettet                 | Dato og klokkeslæt          |
| Godkendt på forhånd            | Ja/Nej                 |
| Oprettet af              | Person eller gruppe        |
| Redigeret af             | Person eller gruppe        |

Noter navnet og URL-adressen på SharePoint Online-listen. Vi bruger disse elementer senere, når du skal konfigurere udløseren **SharePoint – Når der oprettes et nyt element**.

## <a name="create-your-flow"></a>Opret dit flow

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tilføj en udløser

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![sharepoint-oplysninger](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Hent chefen til den person, der har oprettet anmodningen om ferie
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

   > [!NOTE]
   > Det er en god ide at gemme ændringer af flowet jævnligt undervejs.

## <a name="add-an-approval-action-for-pre-approvals"></a>Tilføj en godkendelseshandling for forhåndsgodkendelser
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Bemærk! Denne handling sender den anmodning, der skal forhåndsgodkendes, til mailadressen i feltet **Tildelt til**.

## <a name="add-a-condition"></a>Tilføj en betingelse
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Denne betingelse undersøger svaret fra handlingen **Start, og vent på en godkendelse**.
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Tilføj en mailhandling for forhåndsgodkendelser
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![konfigurer forhåndsgodkendt mailskabelon](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Tilføj en opdateringshandling for forhåndsgodkendte anmodninger
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![opdater elementkonfiguration](./media/sequential-modern-approvals/update-item-preapproval.png)

## <a name="get-the-pre-approvers-manager"></a>Hent forhåndsgodkenderens chef

1. Udfør trinnene i [Hent chefen til den person, der har oprettet anmodningen om ferie](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request), som vi udførte tidligere, for at tilføje og derefter konfigurere en anden **Hent chefen**-handling. Nu henter vi forhåndsgodkenderens chef.
2. Kortet **Hent chefen 2** skal se ud som på dette billede, når du er færdig. Sørg for at bruge tokenet **Mail** fra kategorien **Hent chefen** på kortet **Tilføj dynamisk indhold fra de apps og tjenester, der bruges i dette flow**.
   
   ![hent forhåndsgodkenderens chef](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Tilføj den endelige godkendelseshandling
1. Udfør trinnene i [Tilføj en godkendelseshandling for forhåndsgodkendelser](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals), som vi udførte tidligere, for at tilføje og derefter konfigurere en anden handling af typen **Start en godkendelse**. Denne handling sender en mailanmodning til endelig godkendelse.
2. Når du er færdig, skal kortet se ud som på dette billede:
   
    ![konfigurer godkendelsen](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Tilføj den endelige godkendelsesbetingelse
1. Gentag trinnene i [Tilføj en betingelse](sequential-modern-approvals.md#add-a-condition) for at tilføje og derefter konfigurere en **betingelse**, der kontrollerer den endelige godkenders afgørelse.

## <a name="send-email-with-final-approval"></a>Send mail med endelig godkendelse
1. Udfør trinnene i [Tilføj en mailhandling for forhåndsgodkendelser](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) for at tilføje og derefter konfigurere en handling, der sender en mail, når anmodninger om ferie godkendes.
2. Når du er færdig, skal kortet se ud som på dette billede:
   
   ![mailskabelon for endelig godkendelse](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Opdater SharePoint med godkendelse
1. Udfør trinnene i [Tilføj en opdateringshandling for forhåndsgodkendte anmodninger](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) for at tilføje og derefter konfigurere en handling, der opdaterer SharePoint, når anmodningen om ferie godkendes.
2. Når du er færdig, skal kortet se ud som på dette billede:
   
    ![opdater elementkonfiguration](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Send mail med afvisning af forhåndsgodkendelse
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![konfiguration af afviste anmodninger](./media/sequential-modern-approvals/configure-rejected-email.png)

Bemærk! Denne handling skal føjes til forgreningen **HVIS NEJ, GØR INTET** under kortet **Betingelse**.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Opdater SharePoint med afvisning af forhåndsgodkendelse
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![opdater SharePoint for afviste anmodninger](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Send mail med endelig afvisning
1. Udfør trinnene i [Send mail med afvisning af forhåndsgodkendelse](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) for at tilføje og derefter konfigurere en handling, der sender en mail, når anmodningen om ferie afvises af den endelige godkender.
   
    Bemærk! Denne handling skal føjes til forgreningen **HVIS NEJ, GØR INTET** under kortet **Betingelse 2**.
2. Når du er færdig, skal kortet se ud som på dette billede:
   
   ![konfiguration af afviste anmodninger](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Opdater SharePoint med endelig afvisning

1. Udfør trinnene i [Opdater SharePoint med afvisning af forhåndsgodkendelse](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) for at tilføje og derefter konfigurere en handling, der opdaterer SharePoint, hvis den endelige godkender afviser anmodningen om ferie.
1. Når du er færdig, skal kortet se ud som på dette billede:
   
   ![opdater elementkort](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
1. Vælg **Opdater flow** for at gemme det arbejde, vi har gjort.

Hvis du har fulgt med, skal dit flow se ud som på dette billede:

![oversigt over flow](./media/sequential-modern-approvals/completed-flow.png)

Nu, hvor vi har oprettet flowet, kan vi komme i gang.

## <a name="request-an-approval"></a>Anmod om en godkendelse

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Din anmodning skal ligne dette billede:

![anmodning om ferie](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Få vist ventende anmodninger om godkendelse

[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Forhåndsgodkend en anmodning

[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Godkend anmodningen

De trin, der skal udføres for at godkende en anmodning, er identiske med trinnene til [forhåndsgodkendelse af en anmodning](sequential-modern-approvals.md#pre-approve-a-request)

Bemærk! Den endelige godkender får kun anmodningen om ferie, når anmodningen er blevet forhåndsgodkendt.

## <a name="reject-a-request"></a>Afvis en anmodning

[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Flere oplysninger

[Gennemgang af en enkelt godkenders moderne godkendelse](modern-approvals.md)

