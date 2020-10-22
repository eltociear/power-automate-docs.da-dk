---
title: Oversigt over løsningsorienterede flows | Microsoft Docs
description: Få mere at vide om fordelene ved at oprette flows i løsninger.
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
ms.date: 08/14/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a0e986c9d98d8a928cde139f9e21a78331c4f039
ms.sourcegitcommit: c748e9804f4f03d18f3c81d40f1d6fc5862a24c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/07/2020
ms.locfileid: "3968739"
---
# <a name="overview"></a>Oversigt


Når du er vært for dine flows i en [løsning](/power-platform/alm/solution-concepts-alm), bliver de mobile, hvilket gør det nemt at flytte dem og alle deres komponenter fra ét miljø til et andet. Et typisk scenarie er en uafhængig softwareproducent (ISV), der udvikler flows i et sandkassemiljø og derefter flytter disse flows til et testmiljø. Efter at have testet disse flows flytter softwareproducenten dem til et produktionsmiljø for klienter, der køber disse flows. Denne proces er meget nemmere, når du opretter dine flows i løsninger og derefter flytter løsningerne og deres indhold.

Flows, der er oprettet i en løsning, kaldes *løsningsorienterede* flows. Du kan tilføje flere flows i en enkelt løsning. Du kan ikke flytte ikke-løsningsorienterede flows (flows, der ikke er oprettet i en løsning) til en løsning.

> [!NOTE]
> Du kan finde detaljerede oplysninger om løsningsbegreber og implementering af en sund administration af applikationens livscyklus (ALM) i organisationen under [Administration af applikations livscyklus (ALM) med Microsoft Power Platform](/power-platform/alm/).

## <a name="prerequisites"></a>Forudsætninger

Du skal have følgende komponenter for at oprette løsninger og løsningsorienterede flows:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Et miljø med version 9.1.0.267 eller nyere.

  Du kan undersøge, hvilken version du har, ved at gå til [Power Platform Administration](https://admin.powerplatform.microsoft.com/), vælge **Miljøer**, vælge det miljø, du er interesseret i, og derefter vælge fanen **Oplysninger**.

## <a name="create-a-solution"></a>Opret en løsning

Følg disse trin for at oprette en løsning:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Løsninger** på navigationslinjen.

1. Vælg **+ Ny løsning**.

   ![Vælge en ny løsning](./media/overview-solution-flows/select-new-solution.png "Skærm, der viser ny løsning")

1. Angiv alle de nødvendige oplysninger for din nye løsning, herunder **Vist navn**, **Udgiver**, **Version** og **Navn**. Det er også en god ide at angive en beskrivelse af din løsning.

   ![Vælge ny løsning](./media/overview-solution-flows/new-solution.png "skærmbillede af egenskaber for ny løsning").

1. Vælg **Gem og luk** i menuen øverst.

  
   Din nye løsning ser muligvis ud som på dette billede:


   ![Viser den nye løsning](./media/overview-solution-flows/new-solution-created.png "Ny løsning, der vises på skærmbilledet *Løsninger*")


  
## <a name="learn-more"></a>Få mere at vide

- [Opret et flow i en løsning](./create-flow-solution.md)
- [Eksportere en løsning](./export-flow-solution.md)
- [Importere en løsning](./import-flow-solution.md)
- [Rediger et løsningsorienteret flow](./edit-solution-aware-flow.md)
- [Fjern et løsningsorienteret flow](./remove-solution-aware-flow.md)
