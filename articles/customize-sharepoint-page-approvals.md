---
title: Administrer sidegodkendelser for SharePoint med Power Automate | Microsoft Docs
description: Få mere at vide om at administrere sidegodkendelser for SharePoint med Power Automate.
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
ms.date: 04/06/2020
ms.author: deonhe
ms.openlocfilehash: 8d7432ee33ec468e9958cbdd09e805db8ed043a0
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/15/2020
ms.locfileid: "3696999"
---
# <a name="manage-sharepoint-page-approvals-with-power-automate"></a>Administrer sidegodkendelser for SharePoint med Power Automate


Administratorer af SharePoint-websitet kan bruge Power Automate til at kræve, at nye eller opdaterede websitesider godkendes, før de publiceres.

I denne artikel får du mere at vide om, hvordan du konfigurerer dit SharePoint-website til at bruge et flow for at kræve, at ændringer af websitet godkendes, før de publiceres.

## <a name="configure-sharepoint-for-page-approvals"></a>Konfigurer SharePoint til sidegodkendelser

### <a name="prerequisites"></a>Forudsætninger 

Du skal være administrator af SharePoint-websitet for at kunne udføre aktiviteterne i denne artikel.

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

1. Log på SharePoint som administrator af websitet.
1. Vælg **Sider** på navigationslinjen.

    ![Vælge flow for sidegodkendelse](media/customize-sharepoint-page-approvals/pages.png)

1. Vælg **Automatiser** > **Power Automate** > **Konfigurer flow for sidegodkendelse**.
    
    ![Vælge flow for sidegodkendelse](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Vælg **Opret flow**.

1. Du kan eventuelt få brug for at logge på de tjenester, som denne Power Automate-skabelon bruger.

1. Vælg **Fortsæt**.

1. Angiv et **navn på flowet**, mindst ét navn i feltet **Godkendere**, og vælg derefter **Opret**.
    
    ![Vælge flow for sidegodkendelse](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Det var det! Hver gang en side tilføjes eller redigeres nu, sendes der en godkendelsesanmodning til de **godkendere**, du har angivet i flowet.

Flowet for sidegodkendelse er ligesom et hvilket som helst andet flow, så det er angivet under fanen **Mine flow**.

![Vælge flow for sidegodkendelse](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Indsend en side til godkendelse

Nu, hvor du har oprettet et flow for sidegodkendelse, skal alle, der tilføjer eller ændrer en side, gøre følgende:

 - Foretag en ændring af webstedet (tilføj f.eks. en ny side), og gem derefter ændringen.

     ![Indsende siden til godkendelse](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Vent på, at nogen godkender ændringen.
    
    ![Indsende siden til godkendelse](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Godkende en side

Godkendere modtager en mail, når der er en anmodning om godkendelse af en side. De kan enten godkende anmodningerne direkte i mailen (hvis deres mailklient understøtter meddelelser, der kan handles på), eller de kan åbne siden fra mailen for at gennemse og derefter godkende den i SharePoint.

## <a name="customize-page-approval-flows"></a>Tilpasse flow for sidegodkendelse

Da sidegodkendelser bruger Power Automate i baggrunden, er flowet for sidegodkendelse tilgængeligt for websiteejere, så de kan redigere og tilføje brugerdefineret forretningslogik i flowet. Hvis du vil redigere flowet, kan webstedsejeren vælge **Flow** og derefter vælge **Se dine flow** på bibliotekssiderne for at finde sidegodkendelsesflowet.

## <a name="learn-more"></a>Få mere at vide

- [Flow for sidegodkendelse](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Konfigurere sidegodkendelse](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
