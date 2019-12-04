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
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7379cb966be58edfa75cd20c3ad70cf9fff2407a
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74362642"
---
# <a name="create-a-flow-in-a-solution"></a>Opret et flow i en løsning
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Flow, du opretter i en løsning, kaldes *løsningsorienterede* flow. Følg disse trin for at oprette et løsningsorienteret flow.

## <a name="prerequisites"></a>Forudsætninger

Du skal have mindst én løsning, før du kan oprette et løsningsorienteret flow.

## <a name="create-the-flow"></a>Opret flowet 

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Løsninger** på navigationslinjen.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Vælg den løsning, du opretter dit flow i.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Vælg **+ Ny**, og vælg derefter **Flow**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Power Automate åbnes.

1. Brug de tilgængelige forbindelseskomponenter og udløsere til at bygge dit flow.

   I dette eksempel opretter vi et enkelt flow, der sender en besked, når der modtages en mail i din indbakke.
1. Søg efter og vælg derefter **Office 365 Outlook**.
1. Vælg udløseren **Når en ny mail modtages**.
1. Vælg **+ Nyt trin**.
1. Vælg handlingen **Send mig en mobilbesked**.
1. Føj det dynamiske token **Emne** til feltet **Tekst** i feltet **Send mig en mobilbesked**.
1. Giv dit flow et navn, og gem flowet.

   Dit flow skal se ud som følger:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Vælg **Løsninger** for at se dit flow i løsningen:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Få mere at vide

* [Opret en løsning](./overview-solution-flows.md)
* [Eksportér en løsning](./export-flow-solution.md)
* [Importér en løsning](./import-flow-solution.md)
* [Rediger et løsningsorienteret flow](./edit-solution-aware-flow.md)
* [Fjern et løsningsorienteret flow](./remove-solution-aware-flow.md)
