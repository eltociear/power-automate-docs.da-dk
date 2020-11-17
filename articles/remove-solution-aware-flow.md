---
title: Få mere at vide om, hvordan du fjerner eller sletter løsningsorienterede flow | Microsoft Docs
description: Få mere at vide om, hvordan du kan fjerne løsningsorienterede flows fra løsninger eller slette dem i miljøer.
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
ms.date: 10/12/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a3bb56c6b145a8ec6923ee274005ecd5cfe49289
ms.sourcegitcommit: a881042f3de3cce8087986174fed53fd26b163f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/02/2020
ms.locfileid: "4365176"
---
# <a name="remove-a-solution-aware-flow"></a>Fjern et løsningsorienteret flow

Du kan enten fjerne et flow fra en løsning eller helt slette flowet i et miljø.

|Handling|Resultat|
|------|-----------|
|Fjern fra denne løsning|Flowet fjernes fra den valgte løsning, men det forbliver i miljøet, og du kan bruge det i andre løsninger i miljøet på et senere tidspunkt.|
|Slet fra dette miljø|Flowet slettes. Det er ikke tilgængeligt i miljøet.|

## <a name="remove-a-flow-from-a-solution"></a>Fjerne et flow fra en løsning

1. Log på Power Automate, og vælg derefter **Løsninger** fra den venstre navigationslinje.
1. Vælg den løsning, der indeholder det flow, du vil fjerne.
1. Vælg **Flere kommandoer** (...) for flowet, vælg **Fjern**, og vælg derefter **Fjern fra denne løsning**.

>[!IMPORTANT]
>Når du fjerner et flow, flyttes det til **Common Data Service-standardløsningen**, hvor du kan redigere eller slette flowet eller føje det til en anden løsning. 

## <a name="delete-a-flow-from-an-environment"></a>Slette et flow i et miljø

1. Log på Power Automate, og vælg derefter **Løsninger** fra den venstre navigationslinje.
1. Vælg den løsning, der indeholder det flow, du vil slette i miljøet.
1. Vælg **Flere kommandoer** (...) for flowet, vælg **Fjern**, og vælg derefter **Slet fra dette miljø**.

## <a name="learn-more"></a>Flere oplysninger

- [Opret en løsning](./overview-solution-flows.md)
- [Opret et flow i en løsning](./create-flow-solution.md)
- [Eksportere en løsning](./export-flow-solution.md)
- [Importere en løsning](./import-flow-solution.md)
- [Rediger et løsningsorienteret flow](./edit-solution-aware-flow.md)
