---
title: Opret flows ved hjælp af Power Apps-appen i Microsoft Teams (prøveversion) | Microsoft Docs
description: Opret flows ved hjælp af Power Apps-appen i Teams.
author: msftman
manager: kvivek
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/22/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7cdc6bc5298e656b193df890fd014cfe7b43c570
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900282"
---
# <a name="create-flows-using-the-power-apps-app-in-microsoft-teams-preview"></a>Opret flows ved hjælp af Power Apps-appen i Microsoft Teams (prøveversion)

[!INCLUDE [cc-beta-prerelease-disclaimer.md](../includes/cc-beta-prerelease-disclaimer.md)]

Du kan opbygge flows for at tilpasse og føje yderligere værdi til Teams fra den nye Power Apps-app i Teams. Du kan oprette [øjeblikkelige](../introduction-to-button-flows.md), [planlagte](../run-scheduled-tasks.md) og [automatiske](../get-started-logic-flow.md) flows med adgang til mere end 350 connectorer. Det omfatter også en connector, der kan bruges til at arbejde med [Project Oakdale-tabeller](/powerapps/teams/overview-data-platform#tables-in-project-oakdale) i Teams.

> [!NOTE]
> - Dette er en eksempelvisningsfunktion.
> - [!INCLUDE [cc-preview-features-definition.md](../includes/cc-preview-features-definition.md)]
> - Du skal have [Power Automate-licens](https://flow.microsoft.com/pricing/) for at få adgang til alle Power Automate-[connectorer](https://docs.microsoft.com/Connectors/connector-reference/), herunder premium-connectorer. Brugere med en Microsoft 365-licens kan bruge alle standard-connectorer.

## <a name="prerequisites"></a>Forudsætninger 

- Power Apps-appen skal installeres, før du kan oprette flows i Teams. Flere oplysninger: [Installer den personlige Power Apps-app i Microsoft Teams](/powerapps/teams/install-personal-app)

- Før du kan bruge Power Apps-appen i Teams til at oprette et flow, skal der allerede findes et Project Oakdale-miljø for det pågældende team. Et Project Oakdale-miljø klargøres automatisk, når du [opretter din første app i Teams](/powerapps/teams/create-first-app).

## <a name="create-a-flow-in-teams"></a>Opret et flow i Teams

1. Gå til fanen **Byg** i Power Apps-appen, og vælg derefter **Se alle**.

1. Vælg **Nyt**, vælg **Flow**, og vælg derefter på den flowtype, du vil oprette. Du kan kun oprette følgende flowtyper: [øjeblikkelig](../introduction-to-button-flows.md), [planlagt](../run-scheduled-tasks.md) og [automatiseret](../get-started-logic-flow.md).
 
   ![Opret et flow](..\media\overview-teams-flows\new-flow.png)

1. Hvis dette er første gang, du opretter et flow, skal du vælge dit land/område og derefter vælge **Start her**.

   ![Vælg din lokation](..\media\overview-teams-flows\select-location.png)

1. Billedet **Byg et automatiseret flow** vises, hvor du kan vælge en udløser og oprette og gemme dit flow.

   >[!NOTE]
   >Den skærm, der vises her, varierer, afhængigt af om du har valgt **Øjeblikkelig** eller **Planlagt** i trin 2 tidligere.

   ![Visning af designeren](..\media\overview-teams-flows\build-automated-flow.png)

## <a name="work-with-your-flows"></a>Arbejde med dine flows

Sådan finder du dine gemte flows:

1. Log på Teams.

1. Vælg **Power Apps** i venstre rude.

   ![Vælg Power Apps](..\media\overview-teams-flows\select-power-apps.png)

1. Vælg det team, hvor du har oprettet flowet, under fanen **Byg**, og vælg derefter **Vis alle** i trævisningen. 

   ![Alle flow](..\media\overview-teams-flows\all-flows.png)

## <a name="customize-a-flow"></a>Tilpas et flow

I Teams kan du have erhvervet flows fra en installeret app, eller du har måske oprettet dem selv. Du kan opdatere eller tilpasse en af disse flowtyper. 

1. Hvis du vil opdatere et flow, skal du vælge fanen **Byg** og derefter vælge **Vis alle** for at se alle apps og flows i dette team.

1. Vælg det flow, du vil redigere, og vælg derefter **Rediger**.  

   ![Vælg Rediger](..\media\overview-teams-flows\customize-flow.png)

## <a name="view-details-and-run-history"></a>Vis detaljer, og kør oversigten

1. Hvis du vil have vist detaljer om og køre oversigten for et flow, skal du vælge fanen **Byg** og derefter vælge **Vis alle**.

1. Vælg det flow, du vil have vist detaljer om, og vælg derefter **Detaljer**.

   ![Se detaljerne om flow](..\media\overview-teams-flows\view-details-history.png)

## <a name="related-articles"></a>Relaterede artikler

[Brug den nye Power Apps-app i Microsoft Teams](/powerapps/teams/create-app-overview)<br/>
[Hvad er Project Oakdale?](/powerapps/teams/overview-data-platform)<br/>
[Om Project Oakdale-miljøet ](/power-platform/admin/about-teams-environment)
