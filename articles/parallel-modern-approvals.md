---
title: Opret en arbejdsproces for en parallel, moderne godkendelse | Microsoft Docs
description: Opret en arbejdsproces for en parallel, moderne godkendelse
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 223ca24325ee9aed2476d1da6ad9e986c09306d7
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74375591"
---
# <a name="create-parallel-approval-workflows-with-power-automate"></a>Opret arbejdsprocesser for parallel godkendelse med Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I en arbejdsproces for parallel godkendelse skal flere personer godkende elementer, f.eks. fakturaer, indkøbsordrer, anmodninger om ferie osv. De enkelte personers godkendelse er uafhængig af alle andre godkendere.

I denne gennemgang bruger vi Power Automate til at oprette et flow, som kan automatisere en arbejdsproces for parallel godkendelse. I dette flow automatiseres processen for en medarbejders anmodning om ferie, der kræver godkendelse af alle personer (eller team), som medarbejderen jævnligt arbejder under. Medarbejderne bruger en [SharePoint-liste](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) til at anmode om ferie. Ferie skal godkendes af medarbejderens direkte chef, salgsteamet og personaleafdelingen. De enkelte anmodninger om ferie sendes til de enkelte godkendere for at blive afgjort. Flowet sender en mail med statusændringer, og derefter opdateres SharePoint med afgørelserne.

## <a name="prerequisites"></a>Forudsætninger

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Den SharePoint Online-liste, som du opretter, skal indeholde følgende kolonner:

   ![Kolonner i SharePoint-liste](./media/parallel-modern-approvals/sharepoint-columns.png)

Noter navnet og URL-adressen på SharePoint Online-listen. Vi skal bruge disse elementer senere til at konfigurere udløseren **SharePoint – Når der oprettes et element**.

## <a name="create-your-flow-from-the-blank-template"></a>Opret dit flow fra den tomme skabelon

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tilføj en udløser

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint-oplysninger](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Hent chefen til den person, der har oprettet anmodningen om ferie

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Navngiv og gem dit flow

1. Angiv et navn til dit flow, og vælg derefter ikonet **Gem** for at gemme det arbejde, vi har udført hidtil.

   ![gem flow](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Vælg med jævne mellemrum ikonet **Gem** for at gemme ændringer af dit flow.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Tilføj en godkendelseshandling for den direkte chef

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Denne handling sender anmodningen om ferie til mailadressen i feltet **Tildelt til** og indsætter derefter tokenet **Mail** fra listen **Hent leder (v2)** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Indsæt en handling for parallel godkendelse af forgrening for salgsteamet

1. Vælg pil ned, som er placeret mellem kortene **Hent leder (v2)** og **Start en godkendelse**.
2. Vælg plustegnet, der vises på pil ned, når du har valgt den.
3. Vælg **Tilføj en parallel forgrening**.
4. Vælg **Tilføj en handling**.

    ![hent chef-konfiguration](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Søg efter, vælg og konfigurer derefter en handling af typen **Start en godkendelse**, der sender anmodningen om ferie til salgsteamet. Se [trinnene under Tilføj en godkendelseshandling for den direkte chef](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager), hvis du ikke er sikker på, hvordan du tilføjer handlingen **Start en godkendelse**.

> [!IMPORTANT]
> Brug salgsteamets mailadresse i feltet **Tildelt til** for handlingen **Start en godkendelse 2**.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Indsæt en handling for parallel godkendelse af forgrening for personaleafdelingen

1. Gentag trinnene under [Indsæt en parallel forgrening for salgsteamet](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) for at tilføje og derefter konfigurere en handling af typen **Start en godkendelse** for at sende anmodninger om ferie til personaleafdelingen.

> [!IMPORTANT]
> Brug personaleafdelingens mailadresse i feltet **Tildelt til** for handlingen **Start en godkendelse 3**.
> 
> 

Hvis du har fulgt med, skal dit flow se ud som i dette eksempel:

   ![flow med parallelle forgreninger](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Indstillinger, når der er tilføjet parallelle forgreninger

Når du har føjet handlinger til parallelle forgreninger, har du to valgmuligheder for at føje flere trin til dit flow:

1. Brug den lille knap **Indsæt et nyt trin** (den runde plusknap, der vises, når du vælger et blanktegn på en forgrening eller i området umiddelbart under en forgrening). Denne knap føjer et trin til den **specifikke forgrening**. Trin, som du tilføjer med denne knap, køres, når denne specifikke forgrening er fuldført.
1. Brug den større knap **Nyt trin** nederst i hele arbejdsprocessen. Trin, som du tilføjer med denne knap, køres, når alle forgreninger er fuldført.

I følgende afsnit skal vi bruge den lille knap **Indsæt et nyt trin** for at udføre disse trin på de enkelte forgreninger:

* Tilføj en betingelse, der undersøger, om anmodningen om ferie blev godkendt eller afvist.
* Send en mail, der giver medarbejderen besked om afgørelsen.
* Opdater anmodningen om ferie i SharePoint med afgørelsen om godkendelse.

Vi bruger derefter den større knap **Nyt trin** til at sende en mail, der opsummerer alle de afgørelser, der er truffet om anmodningen om ferie.

Lad os fortsætte:

## <a name="add-a-condition-to-each-branch"></a>Føj en betingelse til de enkelte forgreninger

1. Vælg et hvilket som helst blanktegn i forgreningen **Start en godkendelse**.
2. Vælg den lille knap **Indsæt et nyt trin** (den runde plusknap, der vises, når du har valgt blanktegnet i forrige trin).
3. Vælg **Tilføj en betingelse** i den menu, der vises.
4. Markér det første felt på kortet **Betingelse**, og vælg derefter tokenet **Svar** fra kategorien **Start en godkendelse** på listen over dynamisk indhold.

    ![betingelse for flow med parallelle forgreninger](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Bekræft, at listen (midt på **kortet Betingelse**) er angivet til **er lig med**.
6. Skriv **Godkend** (der skelnes mellem store og små bogstaver) i det sidste felt.
7. Dit betingelseskort skal se ud som i dette eksempel:

    ![betingelse for flow med parallelle forgreninger](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Denne betingelse undersøger svaret fra handlingen **Start en godkendelse**, der sendes til medarbejderens chef.
   > 
   > 
8. Gentag de efterfølgende trin på forgreningerne **Start en godkendelse 2** (godkendelsesanmodningen til salgsafdelingen) og **Start en godkendelse 3** (godkendelsesanmodningen til personaleafdelingen).

## <a name="add-email-actions-to-each-branch"></a>Føj mailhandlinger til de enkelte forgreninger

Udfør følgende trin på siden **HVIS JA** i forgreningen **Betingelse**.

   Bemærk! Dit flow bruger disse trin til at sende en mail, når anmodningen er godkendt:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![konfigurer forhåndsgodkendt mailskabelon](includes/media/parallel-modern-approvals/yes-email-config.png)

Hvis du vil sende en mail, når en anmodning er afvist, skal du bruge siden **HVIS NEJ** for forgreningen **Betingelse** og derefter gentage de efterfølgende trin for at tilføje en skabelon for afvisningsmailen.

Gentag de efterfølgende trin på forgreningerne **Start en godkendelse 2** (godkendelsesanmodningen til salgsafdelingen) og **Start en godkendelse 3** (godkendelsesanmodningen til personaleafdelingen).

## <a name="update-the-vacation-request-with-the-decision"></a>Opdater anmodningen om ferie med afgørelsen

Udfør følgende trin for at opdatere SharePoint, når der er foretaget en afgørelse.

   Bemærk! Husk at udføre disse trin både på siden **HVIS JA** og siden **HVIS NEJ** for forgreningen.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![opdater elementkonfiguration](./media/parallel-modern-approvals/configure-update-item.png)

Gentag de efterfølgende trin på forgreningerne **Start en godkendelse 2** og **Start en godkendelse 3**.

## <a name="complete-the-flow"></a>Fuldfør flowet

1. Vælg **Nyt trin** > **Tilføj en handling**

    ![opdater elementkonfiguration](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Brug de trin, der er angivet tidligere, til at sende en mail, der opsummerer resultaterne af hver godkendelse. Send denne mail til den medarbejder, der har anmodet om ferie. Kortet ser måske ud som i dette eksempel:

   ![opdater elementkonfiguration](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Få mere at vide om moderne godkendelse

[Introduktion til moderne godkendelse](modern-approvals.md)

