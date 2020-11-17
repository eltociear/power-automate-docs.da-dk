---
title: Oversigt over brug af flow med SharePoint| Microsoft Docs
description: Indeholder en oversigt over de mange måder, du kan bruge flow sammen med SharePoint-lister og -filer.
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
ms.date: 06/08/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7a0916c4d1637a6d0b35d72d54e4807afd39ec9f
ms.sourcegitcommit: a881042f3de3cce8087986174fed53fd26b163f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/02/2020
ms.locfileid: "4365152"
---
# <a name="use-sharepoint-and-power-automate-to-build-workflows"></a>Bruge SharePoint og Power Automate til at oprette arbejdsprocesser

Power Automate er dybt integreret med SharePoint. Du kan starte med en af de mere end [100 SharePoint-skabeloner](https://flow.microsoft.com/templates/) eller oprette dit eget flow, der kan integreres med SharePoint, fra bunden.

## <a name="top-sharepoint-workflow-scenarios"></a>Typiske SharePoint-arbejdsprocesscenarier

Her er nogle af de mest populære scenarier, hvor du kan bruge Power Automate sammen med SharePoint:

- Administrere godkendelsesflow
- Arbejde med filer og lister
- Overføre fra arbejdsprocesser til Power Automate

### <a name="manage-approval-flows"></a>Administrere godkendelsesflow

- Tilpas [SharePoint-sidegodkendelser](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/customize-page-approvals), så de opfylder dine behov.
- Kræv [godkendelse af dokumenter](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/require-doc-approval) i SharePoint ved hjælp af Power Automate.
- Distribuer færdige dokumenter til et [team til godkendelse](./customize-sharepoint-page-approvals.md).

### <a name="work-with-files-and-lists"></a>Arbejde med filer og lister

- Administrer [listeelement- og filtilladelser](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/manage-list-item-file-permissions).
- [Flyt filer til andre mapper](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/migrate-from-classic-workflows-to-power-automate-flows), når de er godkendt i SharePoint.
- [Opret et element i SharePoint](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/migrate-from-classic-workflows-to-power-automate-flows), når en ny ordre tilføjes i Salesforce.
- [Hent elementer fra lister, eller hent filer fra biblioteker](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/working-with-get-items-and-get-files).
- Opret et [flow for en liste eller et bibliotek i SharePoint eller OneDrive](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).
- [Rediger et flow](https://support.microsoft.com/office/edit-a-flow-for-a-list-in-sharepoint-b6678daa-2c82-44eb-be3f-2a9cb56301e8).

### <a name="other-top-scenarios"></a>Andre vigtige scenarier

- Brug [HTTP-anmodninger](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/working-with-send-sp-http-request) til at administrere lister og biblioteker.
- Opret [SharePoint-påmindelsesflow](create-sharepoint-reminder-flows.md).

## <a name="sharepoint-triggers-and-actions"></a>SharePoint-udløsere og -handlinger

Du kan bruge SharePoint-udløsere til at start flows, der overvåger de ændringer, der er foretaget af en SharePoint-liste eller et bibliotek. Du kan finde en komplet liste ved at gå til [SharePoint-udløsere](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers#sharepoint-triggers).

![Et skærmbillede, der viser nogle SharePoint-udløsere, f.eks. "Når et element oprettes"](./media/overview-sharepoint/sharepoint-triggers.png)

Så snart flowet starter, kan du bruge en af de mere end [40 *handlinger*](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/sharepoint-connector-actions-triggers#sharepoint-actions) til at håndtere dine SharePoint-lister.

![Et skærmbillede, der viser nogle SharePoint-handlinger, f.eks. "Tilføj vedhæftet fil" og "Tjek en fil ind"](./media/overview-sharepoint/sharepoint-actions.png)

## <a name="migrate-from-workflows-to-power-automate"></a>Overføre fra arbejdsprocesser til Power Automate

-  Overfør fra [klassiske arbejdsprocesser til Power Automate-flow](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/guidance/migrate-from-classic-workflows-to-power-automate-flows) i SharePoint.

## <a name="next-steps"></a>Næste trin

- Introduktion til [Power Automate og SharePoint](https://docs.microsoft.com/sharepoint/dev/business-apps/power-automate/get-started/create-your-first-flow). 
- Introduktion til [godkendelser](https://docs.microsoft.com/power-automate/get-started-approvals).
- Opret moderne [godkendelsesflow](use-expressions-in-conditions.md) i avancerede tilstandsbetingelser.
