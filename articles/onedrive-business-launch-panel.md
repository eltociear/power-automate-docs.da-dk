---
title: Opret flows fra OneDrive for Business-startpanelet | Microsoft Docs
description: Opret flows fra OneDrive for Business-startpanelet.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/06/2020
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 84cd5b0f6f0adf8bdbcc5d077bc48a3878e2c83e
ms.sourcegitcommit: 6714fe9d5217e6aaa07656c7048c1c82ba7312c1
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/18/2020
ms.locfileid: "3821052"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Opret flows fra OneDrive for Business-startpanelet


Ligesom med Power Automate-[startpanelet i SharePoint](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) kan du køre flow for bestemte filer i OneDrive for Business. 

Denne funktion giver den person, der kører flowet, mulighed for at bruge sine egne legitimationsoplysninger, hvilket især gælder for flow, der er oprettet af en it-afdeling. 

Brugerne kan også få vist prompter for kørselsinput såsom **Godkender** eller **Meddelelse**, som kan være af typen tekst, fil, boolesk eller tal.

I denne gennemgang opretter vi et enkelt flow, hvor en af de mange [OneDrive for Business-skabeloner](https://flow.microsoft.com/search/?q=OneDrive) bruges til at anmode om godkendelse af en fil fra lederen for anmoderen.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Opret et flow, der anmoder om lederens godkendelse af en fil i OneDrive for Business

1. Log på OneDrive for Business.
1. Find og vælg derefter den fil, du vil oprette flowet for.
1. Vælg linket **Vis handlinger** (tre prikker).
1. Vælg **Automatiser** > **Power Automate** > **Opret et flow**.

     ![Opret flow](./media/onedrive-launch-panel/create-flow.png) 

1. Vælg en af skabelonerne:

    I dette eksempel skal du vælge skabelonen **Anmod om min leders godkendelse af den valgte fil**.

     >[!TIP]
     >Log på alle connectorer, der anmoder om, at du logger på.

1. Vælg **Fortsæt**.
1. Foretag de ønskede ændringer af skabelonen, og gem derefter flowet med et navn, som du nemt kan huske.

## <a name="run-the-flow"></a>Køre flowet

1. Log på OneDrive for Business.
1. Find og vælg derefter den fil, du vil anmode om chefgodkendelse for.
1. Vælg linket **Vis handlinger** (tre prikker).
1. Vælg **Flow**. Du kan se det flow, du oprettede tidligere.
1. Vælg det flow, du oprettede tidligere.

     ![Kør dit flow](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Selvom denne gennemgang viser, hvordan du opretter et flow ud fra en skabelon, kan du også oprette et flow fra bunden af for at bruge en af de hundredvis af connectorer, der er tilgængelige i Power Automate.

## <a name="learn-more"></a>Flere oplysninger

- [Introduktion til Power Automate](getting-started.md) 
- [Byg flow med flere trin](multi-step-logic-flow.md)
