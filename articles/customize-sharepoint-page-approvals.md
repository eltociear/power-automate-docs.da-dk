---
title: Administrer SharePoint-sidegodkendelser med Power Automate | Microsoft Docs
description: Få mere at vide om, hvordan du administrerer SharePoint-sidegodkendelser med Power Automate.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 9a7e6b28f7080ea65141d9a68881a637cd68cb2d
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74362711"
---
# <a name="manage-sharepoint-page-approvals-with-power-automate"></a>Administrer SharePoint-sidegodkendelser med Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Administratorer af SharePoint-websteder kan bruge Power Automate til at kræve, at nye eller opdaterede webstedssider godkendes, før de publiceres.

I denne artikel får du mere at vide om, hvordan du konfigurerer dit SharePoint-websted til at bruge et flow for at kræve, at ændringer af webstedet godkendes, før de publiceres.

## <a name="configure-sharepoint-for-page-approvals"></a>Konfigurer SharePoint til sidegodkendelse

### <a name="prerequisites"></a>Forudsætninger 

Du skal være administrator af SharePoint-websteder for at kunne udføre aktiviteterne i denne artikel.

1. Log på SharePoint som administrator af webstedet.
1. Vælg **Sider** på navigationslinjen.

    ![Vælg flowet for sidegodkendelse](media/customize-sharepoint-page-approvals/pages.png)

1. Vælg **Flow**, og vælg derefter **Konfigurer flow for sidegodkendelse**.
    
    ![Vælg flowet for sidegodkendelse](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Angiv et **navn på flowet**, mindst ét navn i feltet **Godkendere**, og vælg derefter **Opret**.
    
    ![Vælg flowet for sidegodkendelse](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Det er det hele. Hver gang en side tilføjes eller redigeres nu, sendes der en godkendelsesanmodning til de **godkendere**, du har angivet i flowet.

Flowet for sidegodkendelse er ligesom et hvilket som helst andet flow, så det er angivet under fanen **Mine flow**.

![Vælg flowet for sidegodkendelse](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Indsend en side til godkendelse

Nu, hvor du har oprettet et flow for sidegodkendelse, skal alle, der tilføjer eller ændrer en side, gøre følgende:

 - Foretag en ændring af webstedet (tilføj f.eks. en ny side), og gem derefter ændringen.

     ![Indsend siden til godkendelse](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Vent på, at nogen godkender ændringen.
    
    ![Indsend siden til godkendelse](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Godkend en side

Godkendere modtager en mail, når der er en anmodning om godkendelse af en side. De kan enten godkende anmodningerne direkte i mailen (hvis deres mailklient understøtter meddelelser, der kan handles på), eller de kan åbne siden fra mailen for at gennemse og derefter godkende den i SharePoint.

## <a name="customize-page-approval-flows"></a>Tilpas flow for sidegodkendelse

Da sidegodkendelser bruger Power Automate i baggrunden, er flowet for godkendelse af sider tilgængeligt for webstedsejere, så de kan redigere og tilføje brugerdefineret forretningslogik i flowet. Hvis du vil redigere flowet, kan webstedsejeren vælge **Flow** og derefter vælge **Se dine flow** på bibliotekssiderne for at finde sidegodkendelsesflowet.

## <a name="learn-more"></a>Få mere at vide

- [Flow for sidegodkendelse](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Konfigurer sidegodkendelse](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
