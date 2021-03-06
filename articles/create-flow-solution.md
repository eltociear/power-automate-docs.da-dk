---
title: Få mere at vide om, hvordan du opretter løsningsorienterede flow | Microsoft Docs
description: Få mere at vide om, hvordan du opretter løsningsorienterede flow.
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
ms.date: 10/11/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fe2fdf5b1eb5dc20597a0d086ad70c810e7908e7
ms.sourcegitcommit: ad8c043d9ad0c188237c0fc3bbd8fd0c7cec83c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/12/2020
ms.locfileid: "3988244"
---
# <a name="create-a-flow-in-a-solution"></a>Opret et flow i en løsning


Flow, du opretter i en løsning, kaldes *løsningsorienterede* flow. Følg disse trin for at oprette et løsningsorienteret flow.

## <a name="prerequisites"></a>Forudsætninger

Du skal have mindst én løsning, før du kan oprette et løsningsorienteret flow.

## <a name="create-the-flow"></a>Opret flowet 

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Løsninger** på navigationslinjen.

   ![Skærmen, der viser den venstre navigationslinje med indstillingen Løsninger fremhævet](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Vælg den løsning, du opretter dit flow i.

   ![Skærmvisning af en liste over løsninger](./media/create-flow-solution/new-solution-created.png)

1. Vælg **Nyt**, og vælg derefter **Flow**.

   ![Skærmbillede, der viser de forskellige typer elementer, der kan oprettes, med flow fremhævet](./media/create-flow-solution/select-new-flow.png)

   Power Automate åbnes.

1. Brug de tilgængelige connectorer og udløsere til at bygge dit flow.

   I dette eksempel opretter vi et enkelt flow, der sender en besked, når der modtages en mail i din indbakke.
1. Søg efter og vælg derefter **Office 365 Outlook**.
1. Vælg udløseren **Når en ny mail modtages (V3)**.
1. Vælg **Nyt trin**.
1. Søg efter ordet "meddelelse", og vælg derefter handlingen **Send mig en mobilmeddelelse**.
1. Føj det dynamiske token **Emne** til feltet **Tekst** i feltet **Send mig en mobilmeddelelse**.
1. Giv dit flow et navn, og gem flowet.

   Dit flow skal se ud som følger:

   ![Skærmbillede, der viser det flow, der er oprettet](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Vælg **Løsninger** for at se dit flow i løsningen:

   ![Skærmbillede, der viser flowet inde i løsningen](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Flere oplysninger

* [Opret en løsning](./overview-solution-flows.md)
* [Eksportere en løsning](./export-flow-solution.md)
* [Importere en løsning](./import-flow-solution.md)
* [Rediger et løsningsorienteret flow](./edit-solution-aware-flow.md)
* [Fjern et løsningsorienteret flow](./remove-solution-aware-flow.md)
