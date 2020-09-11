---
title: Oprette en arbejdsproces for en parallel, moderne godkendelse | Microsoft Docs
description: Oprette en arbejdsproces for en parallel, moderne godkendelse
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
ms.date: 08/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f338e4fd96dd0ff34c618e9bbe3ab97163990145
ms.sourcegitcommit: a7a7f603d44a12e989efcbc138acda6956a8273c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/25/2020
ms.locfileid: "3720661"
---
# <a name="create-parallel-approval-workflows-with-power-automate"></a>Opret arbejdsprocesser for parallel godkendelse med Power Automate

I en arbejdsgang med parallel godkendelse kræves der flere personer til at godkende varer som fakturaer, indkøbsordrer, ferieanmodninger osv. Hver persons godkendelse er uafhængig af alle andre godkendere.

I denne gennemgang bruger vi Power Automate til at oprette et flow, som kan automatisere en arbejdsproces for parallel godkendelse. I dette flow automatiseres processen for en medarbejders anmodning om ferie, der kræver godkendelse af alle personer (eller team), som medarbejderen jævnligt arbejder under. Medarbejderne bruger en [SharePoint-liste](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) til at anmode om ferie. Ferie skal godkendes af medarbejderens direkte chef, salgsteamet og personaleafdelingen. De enkelte anmodninger om ferie sendes til de enkelte godkendere for at blive afgjort. Flowet sender en mail med statusændringer, og derefter opdateres SharePoint med afgørelserne.

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="prerequisites"></a>Forudsætninger

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]


Den SharePoint Online-liste, som du opretter, skal indeholde følgende kolonner:

| Titel                   | Enkelt tekstlinje    |
|-------------------------|------------------------|
| Kommentarer fra medarbejdere       | Enkelt tekstlinje    |
| Kommentarer fra direkte ledere | Flere linjers tekst |
| Kommentarer fra salgsteam     | Flere linjers tekst |
| Kommentarer fra HR-team        | Flere linjers tekst |
| Direkte leder godkendt | Ja/Nej                 |
| Salgsteam godkendt     | Ja/Nej                 |
| HR-team godkendt        | Ja/Nej                 |
| Feriens startdato     | Dato og klokkeslæt          |
| Feriens slutdato       | Dato og klokkeslæt          |

Noter navnet og URL-adressen på SharePoint Online-listen. Vi skal bruge disse elementer senere til at konfigurere udløseren **SharePoint – Når der oprettes et element**.

## <a name="create-your-flow-from-the-blank-template"></a>Oprette dit flow fra den tomme skabelon

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tilføj en udløser

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint-oplysninger](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Hent chefen til den person, der har oprettet anmodningen om ferie

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Navngive dit flow, og gem det

Angiv et navn til dit flow, og vælg derefter **Gem** for at gemme det arbejde, vi har udført hidtil.

   > [!NOTE]
   > Vælg med jævne mellemrum ikonet **Gem** for at gemme ændringer af dit flow.

## <a name="add-an-approval-action-for-immediate-manager"></a>Tilføje en godkendelseshandling for den direkte leder

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

   > [!IMPORTANT]
   > Denne handling sender anmodningen om ferie til mailadressen i feltet **Tildelt til** og indsætter derefter tokenet **Mail** fra listen **Hent leder (v2)**.

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Indsætte en handling for godkendelse af parallelgren for salgsteamet

1. Vælg pil ned, som er placeret mellem kortene **Hent leder (v2)** og **Start, og vent på en godkendelse**.
1. Vælg plustegnet, der vises på pil ned, når du har valgt den.
1. Vælg **Tilføj en parallel forgrening**.

    ![hente leder-konfiguration](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Søg efter, vælg og konfigurer derefter en handling af typen **Start, og vent på en godkendelse**, der sender anmodningen om ferie til salgsteamet. Se [trinnene under Tilføj en godkendelseshandling for den direkte chef](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager), hvis du ikke er sikker på, hvordan du tilføjer handlingen **Start, og vent på en godkendelse**.

   > [!IMPORTANT]
   > Brug salgsteamets mailadresse i feltet **Tildelt til** for handlingen **Start en godkendelse 2**.

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Indsætte en handling for godkendelse af parallelgren for personaleafdelingen

Gentag trinnene under [Indsætte en parallelgren for salgsteamet](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) for at tilføje og derefter konfigurere en handling af typen **Start en godkendelse** for at sende anmodninger om ferie til personaleafdelingen.

> [!IMPORTANT]
> Brug personaleafdelingens mailadresse i feltet **Tildelt til** for handlingen **Start en godkendelse 3**.

Hvis du har fulgt med, skal dit flow se ud som i dette eksempel:

   ![flow med parallelgrene](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Indstillinger, når der er tilføjet parallelgrene

Når du har føjet handlinger til parallelgrene, har du to valgmuligheder for at føje flere trin til dit flow:

* **Indsætte et trin i en forgrening:** Brug knappen *Indsæt et nyt trin* (**+**) over eller under kortet.  Denne knap, der vises, når du vælger en forgrening eller holder markøren over forbindelsespilen. Denne knap føjer et trin til den **specifikke forgrening**. Denne knap vises her: ![Indsætte et nyt trin](./media/parallel-modern-approvals/Insert-new-step.png "Bruge knappen + til at indsætte et trin i forgreningen.")

* **Føje et trin til flowet:** Brug knappen **+Nyt trin** nederst i hele arbejdsprocessen. Trin, som du tilføjer med denne knap, køres, når alle tidligere forgreninger er fuldført.  Denne knap vises her: ![Tilføje et nyt trin](./media/parallel-modern-approvals/new-step.png "Bruge knappen +Nyt trin til at føje et trin til hele flowet")

I følgende sektioner tilføjer vi trin i hver forgrening:

* Tilføj en betingelse, der undersøger, om anmodningen om ferie blev godkendt eller afvist.
* Send en mail, der giver medarbejderen besked om afgørelsen.
* Opdater anmodningen om ferie i SharePoint med afgørelsen om godkendelse.

Vi bruger derefter den større knap *+Nyt trin* til at sende en mail, der opsummerer alle de afgørelser, der er truffet om anmodningen om ferie.

Lad os fortsætte:

## <a name="add-a-condition-to-each-branch"></a>Føje en betingelse til de enkelte forgreninger

1. Vælg den første forgrening **Start, og vent på en godkendelse**.
1. Vælg den lille knap *Indsæt et nyt trin* (**+**) under kortet (den cirkulære plusknap, der vises, når du holder markøren over forbindelsespilen).
1. Vælg **Tilføj en handling** i den menu, der vises, og vælg derefter **Betingelse** på listen over handlinger.
1. Markér det første felt på kortet **Betingelse**, og vælg derefter tokenet **Svar** fra kategorien **Start, og vent på en godkendelse** på listen over dynamisk indhold.

    ![betingelse for flow med parallelgrene](./media/parallel-modern-approvals/configure-approval-condition.png)
1. Bekræft, at listen (midt på **kortet Betingelse**) er angivet til **er lig med**.
1. Skriv **Godkend** (der skelnes mellem store og små bogstaver) i det sidste felt.
1. Dit betingelseskort skal se ud som i dette eksempel:

    ![betingelse for flow med parallelgrene](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Denne betingelse undersøger svaret fra handlingen **Start en godkendelse**, der sendes til medarbejderens chef.

1. Gentag de efterfølgende trin på forgreningerne **Start en godkendelse 2** (godkendelsesanmodningen til salgsafdelingen) og **Start en godkendelse 3** (godkendelsesanmodningen til personaleafdelingen).

## <a name="add-email-actions-to-each-branch"></a>Føj mailhandlinger til de enkelte forgreninger

Udfør følgende trin på siden **HVIS JA** i forgreningen **Betingelse**.

   Bemærk! Dit flow bruger disse trin til at sende en mail, når anmodningen er godkendt:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

![konfigurer forhåndsgodkendt mailskabelon](includes/media/parallel-modern-approvals/yes-email-config.png)

Hvis du vil sende en mail, når en anmodning er afvist, skal du bruge siden **HVIS NEJ** for forgreningen **Betingelse** og derefter gentage de efterfølgende trin for at tilføje en skabelon for afvisningsmailen.

Gentag de efterfølgende trin på forgreningerne **Start, og vent på en godkendelse 2** (godkendelsesanmodningen til salgsafdelingen) og **Start, og vent på en godkendelse 3** (godkendelsesanmodningen til personaleafdelingen).

## <a name="update-the-vacation-request-with-the-decision"></a>Opdatere anmodningen om ferie med afgørelsen

Udfør følgende trin for at opdatere SharePoint, når der er foretaget en afgørelse.

   Bemærk! Husk at udføre disse trin både på siden **HVIS JA** og siden **HVIS NEJ** for forgreningen.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

  ![opdater elementkonfiguration](./media/parallel-modern-approvals/configure-update-item.png)

Gentag de efterfølgende trin på forgreningerne **Start en godkendelse 2** og **Start en godkendelse 3**.

## <a name="complete-the-flow"></a>Fuldfør flowet

1. Vælg **+Nyt trin**
1. Brug de trin, der er angivet tidligere, til at sende en mail, der opsummerer resultaterne af hver godkendelse. Send denne mail til den medarbejder, der har anmodet om ferie. Kortet ser måske ud som i dette eksempel:

    ![opdater elementkonfiguration](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Få mere at vide om moderne godkendelse

[Introduktion til moderne godkendelse](modern-approvals.md)
