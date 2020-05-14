---
title: Oversigt over løsningsorienterede flow | Microsoft Docs
description: Få mere at vide om fordelene ved at oprette flow i løsninger.
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
ms.openlocfilehash: 56b90ebdf7f3655763b7e40c60b985f06604c47b
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298281"
---
# <a name="overview"></a>Oversigt


Når du er vært for dine flow i en [løsning](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), bliver de mobile, hvilket gør det nemt at flytte dem og alle deres komponenter fra ét miljø til et andet. Et typisk scenarie er en uafhængig softwareproducent (ISV), der udvikler flow i et sandkassemiljø og derefter flytter disse flow til et testmiljø. Efter at have testet disse flow flytter softwareproducenten dem til et produktionsmiljø for klienter, der køber disse flow. Denne proces er meget nemmere, når du opretter dine flow i løsninger og derefter flytter løsningerne og deres indhold.

Flow, du opretter i en løsning, kaldes *løsningsorienterede* flow. Du kan tilføje flere flow i en enkelt løsning.

> [!NOTE] 
> Du kan ikke flytte ikke-løsningsorienterede flow (flow, der ikke er oprettet i en løsning) til en løsning.

## <a name="prerequisites"></a>Forudsætninger

Du skal have følgende komponenter for at oprette løsninger og løsningsorienterede flow:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Et miljø med version 9.1.0.267 eller nyere.

  Du kan undersøge, hvilken version du har, ved at gå til [Power Automate Administration](https://admin.flow.microsoft.com), vælge **Miljøer**, vælge det miljø, du er interesseret i, og derefter vælge fanen **Oplysninger**.

## <a name="create-a-solution"></a>Opret en løsning

Følg disse trin for at oprette en løsning:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Løsninger** på navigationslinjen.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Vælg **+ Ny løsning**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Angiv alle de nødvendige oplysninger for din nye løsning, herunder **Vist navn**, **Udgiver**, **Version** og **Navn**. Det er også en god ide at angive en beskrivelse af din løsning.

   ![](./media/overview-solution-flows/new-solution.png)

1. Vælg **Gem og luk** i menuen øverst.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   Din nye løsning ser muligvis ud som på dette billede:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Vælg **Løsninger** for at opdatere listen over løsninger, hvis din nye løsning ikke vises.

## <a name="learn-more"></a>Få mere at vide

- [Opret et flow i en løsning](./create-flow-solution.md)
- [Eksportere en løsning](./export-flow-solution.md)
- [Importere en løsning](./import-flow-solution.md)
- [Rediger et løsningsorienteret flow](./edit-solution-aware-flow.md)
- [Fjern et løsningsorienteret flow](./remove-solution-aware-flow.md)
