---
title: Automatiser let arbejdsprocesser til godkendelse. | Microsoft Docs
description: Automatiser arbejdsprocesser til godkendelse, som kan integreres med SharePoint, Dynamics CRM, Salesforce, OneDrive for Business, Zendesk eller WordPress.
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
ms.date: 08/27/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e536612ab2cd3bba2f478d5ce38861ec24310a0b
ms.sourcegitcommit: 71dd515fb482312e2878c3eb8642441780290cb5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/01/2020
ms.locfileid: "3742446"
---
# <a name="create-and-test-an-approval-workflow-with-power-automate"></a>Opret og test en godkendelsesarbejdsproces med Power Automate

Med Power Automate kan du styre godkendelse af dokumenter eller processer hen over flere tjenester, herunder SharePoint, Dynamics 365, Salesforce, OneDrive for Business, Zendesk eller WordPress.

Hvis du vil oprette en arbejdsproces til godkendelse, skal du tilføje handlingen **Godkendelser – Start en godkendelse** for et vilkårligt flow. Når du tilføjer denne handling, kan dit flow administrere godkendelse af dokumenter eller processer. Du kan for eksempel oprette dokumentgodkendelsesflows, der godkender fakturaer, arbejdsordrer eller salgstilbud. Du kan også oprette procesgodkendelsesflows, der godkender anmodninger om ferie, overarbejde eller rejseplaner.

Godkendere kan svare på anmodninger fra deres mailindbakke, [godkendelsescentret](https://flow.microsoft.com/manage/approvals/received/) på websitet for Power Automate eller Power Automate-appen.

## <a name="create-an-approval-flow"></a>Oprette et godkendelsesflow
Her er et overblik over det flow, vi opretter og tester:

   ![oversigt over flow](./media/modern-approvals/create-flow-overview.png)

Flowet udfører følgende trin:

1. Starter, når en medarbejder opretter en anmodning om ferie på en SharePoint Online-liste.
1. Føjer ferieanmodningen til godkendelsescentret og sender derefter en mail med anmodningen til godkenderen.
1. Sender en mail til den person, der har anmodet om ferie, når godkenderen har truffet en beslutning.
1. Opdaterer SharePoint Online-listen med godkenderens afgørelse og kommentarer.

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="prerequisites"></a>Forudsætninger

For at fuldføre denne gennemgang, skal du have adgang til:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

At oprette disse kolonner på SharePoint Online-listen:

| Søjle | Skriv |
| ------ | ------ |
| Titel | Enkelt tekstlinje |
|Startdato | Dato og klokkeslæt |
| Slutdato | Dato og klokkeslæt |
| Kommentarer | Enkelt tekstlinje |
| Godkendt | Ja/Nej |
| Kommentarer fra ledere | Enkelt tekstlinje |

Noter navnet og URL-adressen på SharePoint Online-listen. Du skal bruge disse elementer senere, når du konfigurerer udløseren **SharePoint – Når der oprettes et element**.

## <a name="create-your-flow-from-the-blank-template"></a>Oprette dit flow fra den tomme skabelon
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tilføj en udløser

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

**Webstedsadressen** og **listenavnet** er de elementer, du noterede tidligere under denne gennemgang.

![SharePoint-oplysninger](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Tilføje en profilhandling

1. Vælg **+Nyt trin**, og skriv derefter **profil** i søgefeltet **Vælg en handling**.

1. Find, og vælg derefter handlingen **Office 365-brugere – Hent min profil**.

    ![søge efter profil](./media/modern-approvals/search-for-profile.png)

1. Vælg de felter fra din profil, du vil inkludere i flowet, og klik derefter på **Opret** for at gemme det arbejde, du har udført indtil videre.

## <a name="add-an-approval-action"></a>Tilføje en godkendelseshandling

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Denne handling sender godkendelsesanmodningen til mailadressen i feltet **Tildelt til**.
>
> Hvis dit scenarie kræver det, kan du vedhæfte filer til dine godkendelsesanmodninger, der bruger Common Data Service.

## <a name="add-a-condition"></a>Tilføj en betingelse

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Tilføje en mailhandling for godkendelser

Følg disse trin for at sende en mail, hvis ferieanmodningen er godkendt:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![konfigurere godkendt mail-skabelon](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Tilføje en opdateringshandling for godkendte anmodninger

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> **Webstedsadresse**, **Listenavn**, **Id** og **Titel** er påkrævet.

![opdater elementkonfiguration](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Tilføje en mailhandling for afvisninger

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![konfiguration af afviste anmodninger](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Tilføje opdateringshandling for afviste anmodninger

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > **Webstedsadresse**, **Listenavn**, **Id** og **Titel** er påkrævet.

   ![opdater elementkort](./media/modern-approvals/configure-update-item-no.png)

4. Vælg **Gem** for at gemme det arbejde, vi har udført.

Hvis du har fulgt med, skal dit flow ligne dette skærmbillede:

![oversigt over flow](./media/modern-approvals/completed-flow.png)

Nu, hvor vi har oprettet flowet, er det tid til at teste det.

## <a name="request-an-approval"></a>Anmod om en godkendelse

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Oprette langvarige godkendelser

Hvis det er sandsynligt, at dit flow skal køre i mere end 30 dage, bør du overveje at gemme dine godkendelser i Common Data Service. Dette gør det muligt for dig at oprette flows, der reagerer på svar på godkendelsesanmodninger, selv efter at den oprindelige flowkørsel får timeout. Det kan du gøre ved at bruge to flows, det ene til at sende en godkendelsesanmodning og det andet til at køre forretningslogik på svarene på godkendelsesanmodningen baseret på handlingen **Opret en godkendelse (v2)**. Få mere at vide om [langvarige godkendelser](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/increased-run-duration).

>[!TIP]
> Hvis du bruger moderne mailklienter, behøver du ikke at bekymre dig om, om der stadig kræves en anmodning, da Power Automate automatisk opdaterer mailen for at indikere, at godkendelsen er fuldført.

## <a name="cancel-an-approval-requests"></a>Annullere en godkendelsesanmodning

Nogle gange vil du måske annullere en godkendelsesanmodning, som du har sendt. Du har måske lavet en fejl i anmodningen, eller den er ikke længere relevant. I begge tilfælde kan den person, der har sendt anmodningen, annullere den ved at følge disse trin:

1. Vælge godkendelsen
1. Vælg **Annuller godkendelse** i sideruden.

>[!TIP]
>Du kan altid vælge fanen **Oversigt** for at få vist de godkendelsesanmodninger, du har annulleret.

>[!NOTE]
> Annulleringsfunktionen understøttes for handlingen **Opret en godkendelse (v2)**.

## <a name="request-approvals-from-guest-users"></a>Anmode om godkendelser fra gæstebrugere

Du kan sende godkendelsesanmodninger til personer uden for din organisation. Til dette formål kan du bruge Azure Active Directory (Azure AD)-gæstebrugere ved at [invitere brugere fra andre lejere som gæster](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite).

Når du tildeler en rolle til en gæst, giver dette gæsten den tilladelse, der kræves for at deltage i godkendelsesprocessen.

Nu, hvor du har oprettet og testet dit flow, skal du sørge for, at andre ved, hvordan de bruger det.

## <a name="learn-more"></a>Få mere at vide

* Få vist og administrere [ventende godkendelsesanmodninger](approve-reject-requests.md)
* Oprette [sekventielle godkendelsesflows.](sequential-modern-approvals.md)
* Oprette [parallelle godkendelsesflows.](parallel-modern-approvals.md)
* Installer Power Automate-mobilappen for [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).
