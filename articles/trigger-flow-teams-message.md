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
ms.author: hamenon
ms.openlocfilehash: 0e6e1ede6491e376c19397aa0d35f17ff270e016
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900474"
---
# <a name="trigger-a-flow-from-any-message-in-microsoft-teams"></a>Udløser et flow fra enhver meddelelse i Microsoft Teams

Du kan bruge meddelelser til at udløse processer i Teams. Du kan f.eks. bruge en Teams-meddelelse som udgangspunkt for at oprette et arbejdselement i Azure DevOps eller oprette en salgsmulighed i Dynamics 365. 

Brug udløseren **For en valgt meddelelse** i Teams-connectoren til at udløse et flow direkte fra Teams.

## <a name="create-the-flow"></a>Opret flowet

1. Log på Power Automate, og vælg derefter **Mine flows** > **Nyt** > **Øjeblikkelig – fra tom**.
1. Angiv et navn til dit flow.
1. Vælg udløseren **For en valgt meddelelse**.

   ![Udløseren For valgt meddelelse](media/trigger-flow-teams-message/trigger-for-a-selected-message.png)

1. Vælg **Opret**.

>[!NOTE]
>Du skal logge på Teams, hvis du ikke allerede er logget på.

Udløseren **For en valgt meddelelse** omfatter en valgfri inputfunktion i form af et tilpasset kort. Brug et tilpasset kort til at oprette en formular for at indsamle oplysninger fra den bruger, der udløser flowet. Hvis flowet f.eks. opretter en opgave, kan du bruge et tilpasset kort til at indsamle oplysninger, f.eks. titlen på opgaven og beskrivelsen.

## <a name="collect-information-from-the-user"></a>Indsamle oplysninger fra brugeren

Brugerne kan indsamle oplysninger fra brugeren ved hjælp af en formular ved at vælge **Opret tilpasset kort** i udløseren.

![Opret tilpasset kort](media/trigger-flow-teams-message/create-adaptive-card.png)

Her vises en indbygget editor til tilpassede kort, hvor du kan trække kortelementer for at oprette din egen formular.

![Formulardesigner for tilpassede kort](media/trigger-flow-teams-message/ac-card-designer.png)

Hvert input i den tilpassede kortformular har et id. Du kan bruge id'et senere i flowet gennem dynamiske tokens til at referere til input, som en bruger kan have angivet som led i at køre flowet.

### <a name="use-the-message-details-within-the-flow"></a>Bruge meddelelses detaljer i løbet af flowet

Mange meddelelseselementer er tilgængelige som et udløseroutput til brug i flowet. Her er en oversigt over nogle af egenskaberne:

* **Meddelelsesindhold**: Hele HTML-indholdet i Teams-meddelelsen.
* **Almindeligt tekstmeddelelsesoutput**: Den almindelige tekstvariation i Teams-meddelelsen.
* **Link til meddelelse**: En direkte URL-adresse til en reference til meddelelsen.
* **Afsenders viste brugernavn, afsender-id**: Detaljer om den bruger, der har sendt meddelelsen.
* **Oprindeligt brugers viste navn, det oprindelige bruger-id**: Detaljer om den bruger, der kaldte flowet.

![Output for valgt meddelelse](media/trigger-flow-teams-message/dynamic-outputs.png)

Du kan finde flere oplysninger ved at gå til den [komplette liste over udløseroutput](https://docs.microsoft.com/connectors/teams/).

## <a name="trigger-the-flow"></a>Udløs flowet

>[!IMPORTANT]
>Du skal oprette disse flows i *standardmiljøet*, for at de vises i Teams.

>[!IMPORTANT]
>Hvis du ikke kan se de flows, du opretter med udløseren **Til valgte meddelelse i Teams**, skal du bede administratoren om at bekræfte, at Power Automate-appen Handlinger er aktiveret i Teams Administration https://admin.teams.microsoft.com/policies/manage-apps. 

Ethvert flow, der bruger udløseren **For en valgt meddelelse**, vises som en meddelelseshandling i Teams-meddelelsen i menuen **Flere handlinger** for flowet.<!--note from editor: I assume Joni Sherman, Isaiah Langer, and Megan Bowen are names from sample data?-->

![Udløser fra Teams](media/trigger-flow-teams-message/more-actions-menu.png)

>[!IMPORTANT]
>Navnet på flowet bruges til at henvise til flowet i Teams, så du skal sørge for at angive et sigende navn til det.

## <a name="best-practices"></a>Bedste praksis

Sørg for at inkludere en formular for bekræftelse af brugeren, når flowet er fuldført. Det anbefales, at du bruger **Send en meddelelse som Flow-robot til en bruger** eller **Send en meddelelse som Flow-robot til en kanal** for at give brugeren besked i Teams, når et udløst flow er fuldført.

Her er et eksempel på et flow, der opretter et arbejdselement i Azure DevOps og derefter sender en bekræftelse til den oprindelige bruger.<!--note from editor: This image needs more detailed alt text to describe what's going on. It probably will take more than 150 characters, so this might be a good place to use the new image extension.-->

![Oprette en opgaveproces](media/trigger-flow-teams-message/complete-flow.png)

## <a name="known-issues-and-limitations"></a>Kendte problemer og begrænsninger

Du skal oprette disse flows i standardmiljøet for at sikre, at de bliver vist i Teams.
