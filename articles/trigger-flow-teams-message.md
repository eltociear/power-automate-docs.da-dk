---
title: Udløser et flow fra enhver meddelelse i Microsoft Teams | Microsoft Docs
description: Få mere at vide om, hvordan du opretter og udløser en øjeblikkeligt flow fra enhver meddelelse i Microsoft Teams
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
ms.date: 07/16/2020
ms.author: hamenon-ms
ms.openlocfilehash: 002ee947d89f4a1b4e826ac61948350f0c94c7ac
ms.sourcegitcommit: 3642d485c5f66141d990a0fd69cbd0b2b55fd2f5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/21/2020
ms.locfileid: "3610194"
---
# <a name="trigger-a-flow-from-any-message-in-microsoft-teams"></a>Udløser et flow fra enhver meddelelse i Microsoft Teams

Du kan bruge meddelelser til at udløse processer i Microsoft Teams. Du kan f.eks. bruge en Teams-meddelelse som udgangspunkt for at oprette et arbejdselement i Azure DevOps eller oprette en salgsmulighed i Dynamics. 

Brug udløseren **For en valgt meddelelse** i Teams-connectoren til at udløse et flow direkte fra Teams.

## <a name="create-the-flow"></a>Opret flowet

1. Log på **Power Automate**, og vælg derefter > **Mine flows** > **Ny** > **Øjeblikkeligt fra tom**.
1. Giv dit flow et navn.
1. Vælg udløseren **For en valgt meddelelse**.

   ![Udløseren For valgt meddelelse](media/trigger-flow-teams-message/trigger-for-a-selected-message.png)

1. Vælg **Opret**.

>[!NOTE]
>Du skal logge på Teams, hvis du ikke allerede er logget på.

Udløseren **For en valgt meddelelse** omfatter en valgfri inputfunktion i form af et tilpasset kort. Brug et tilpasset kort til at oprette en formular for at indsamle oplysninger fra den bruger, der udløser flowet. Hvis flowet f.eks. opretter en opgave, kan du bruge et tilpasset kort til at indsamle oplysninger, f.eks. titlen på opgaven og beskrivelsen.

## <a name="collect-information-from-the-user"></a>Indsamle oplysninger fra brugeren

Brugerne kan indsamle oplysninger fra brugeren ved hjælp af en formular ved at vælge knappen **Opret tilpasset kort** i udløseren.

![Knappen Tilpasset kort](media/trigger-flow-teams-message/create-adaptive-card.png)

Her vises en indbygget editor for tilpassede kort, som kan bruges til at trække og slippe kortelementer for at opbygge din egen formular.

![Formulardesigner for tilpassede kort](media/trigger-flow-teams-message/ac-card-designer.png)

Hvert input i formularen for tilpassede kort har et Id. Du kan bruge-id'et senere i flowet gennem dynamiske tokens til at referere til input, som en bruger kan have angivet som led i kørslen af flowet.

### <a name="use-the-message-details-within-the-flow"></a>Bruge meddelelses detaljer i løbet af flowet

Der findes mange meddelelseselementer som udløserens output til brug i flowet. Her er en oversigt over nogle af egenskaberne:

* Meddelelsesindhold – Hele HTML-indholdet i Teams-meddelelsen.
* Almindeligt tekstmeddelelsesoutput – Den almindelige tekstvariation i Teams-meddelelsen.
* Link til meddelelse – En direkte URL-adresse som henvisning til meddelelsen.
* Afsenders visningsnavn, afsenders id – Detaljerne om den bruger, der har sendt meddelelsen.
* Oprindelig brugers visningsnavn, oprindelig brugers id – Detaljer om den bruger, der aktiverede flowet.

   ![Output for valgt meddelelse](media/trigger-flow-teams-message/dynamic-outputs.png)

Her er den [komplette liste over udløsers output](https://docs.microsoft.com/connectors/teams/).

## <a name="trigger-the-flow"></a>Udløs flowet

Ethvert flow, der bruger udløseren **For en valgt meddelelse**, vises som en meddelelseshandling i Teams-meddelelsen i menuen **Flere handlinger** for flowet. 

![Udløser fra Microsoft Teams](media/trigger-flow-teams-message/more-actions-menu.png)

>[!IMPORTANT]
>Navnet på flowet bruges til at henvise til flowet i Teams, så du skal sørge for at angive et beskrivende navn til flowet.

>[!IMPORTANT]
>Du skal oprette disse flows i standardmiljøet for at sikre, at de bliver vist i Teams.

## <a name="best-practices"></a>Bedste praksis

Sørg for at inkludere en form for bekræftelse af brugeren, når flowet er fuldført. Det anbefales, at du bruger **Send en meddelelse som flow-botten til en bruger** eller **Send en meddelelse som flow-botten til en kanal** for at give brugeren besked i Teams, når et udløst flow er fuldført.

Her er et eksempel på et flow, der opretter et arbejdselement i Azure Devops og derefter sender en bekræftelse til den oprindelige bruger.

![Oprette en opgaveproces](media/trigger-flow-teams-message/complete-flow.png)

## <a name="known-issues-and-limitations"></a>Kendte problemer og begrænsninger

Du skal oprette disse flows i standardmiljøet for at sikre, at de bliver vist i Teams.