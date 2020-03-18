---
title: Få mere at vide om, hvordan du opretter og administrerer flow i Microsoft Teams | Microsoft Docs
description: Opret og administrer flow for at sende meddelelser efter behov, @mention brugere og kanaler, postkort med svarmuligheder og meget mere.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 1fbd0c6b1f6a7cd453f6c1a336f5ce450e236c5e
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195652"
---
# <a name="power-automate-in-teams"></a>Power Automate i Teams


### <a name="prerequisites"></a>Forudsætninger

1. Adgang til Microsoft Teams.
1. Adgang til Power Automate.

## <a name="install-the-power-automate-app-in-teams"></a>Installér Power Automate-appen i Teams

Følg disse trin for at installere Power Automate-appen i Microsoft Teams.

1. Log på Microsoft Teams.

1. Tryk på ikonet **Apps** nederst til venstre på Teams-navigationslinjen.

    ![Vælg apps](media/flows-teams/apps.png)

1. Vælg appen **Flow**. Du skal måske søge efter **Flow**, hvis du ikke kan se den.

    ![Vælg appen Flow](media/flows-teams/select-flow-app.png)

1. Vælg **Installér**.

    ![Installationsknap](media/flows-teams/select-install.png)

1. Power Automate er nu installeret.

    ![Installeret](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Opret et flow i Teams

1. Log på Microsoft Teams.

1. Vælg linket **Flere tilføjede apps** (...) på navigationslinjen, og vælg derefter appen **Flow**.

    ![Ikonet Tilføjede apps](media/flows-teams/added-apps-icon.png)

1. Hvis du ikke har gjort det tidligere, skal du muligvis logge på og tildele tilladelser.

    ![Log på](media/flows-teams/grant-permissions-sign-in.png)


    Bemærk følgende faner:

    ![Landingssiden for Flow](media/flows-teams/flow-landing-page.png)

    Navn|Formål
    ----|-----|
    Samtale|Interager med Flow-robotten.
    Flow|Opret og administrer flow.
    Godkendelser|Viser modtagne og sendte godkendelsesanmodninger.
    Om|Viser version og andre oplysninger om Power Automate.


    Du kan nu se alle de flow, du har oprettet, via Power Automate-designeren (hvis der er nogen). 

    Du kan også oprette flow ud fra en brugerdefineret skabelon eller en tom skabelon på samme måde som med Power Automate-designer. 

## <a name="manage-approvals"></a>at administrere godkendelser

Du kan administrere [godkendelser](modern-approvals.md) i Microsoft Teams, på samme måde som du ville gøre i Power Automate. Følg disse trin for at administrere dine godkendelser:

1. Log på Microsoft Teams.
1. Vælg fanen **Godkendelser**.

    ![Fanen Godkendelser](media/flows-teams/approvals-tab.png)

    Du vil se følgende underfaner:

    Fane|Formål
    ----|-----|
    Modtaget|Viser de godkendelsesanmodninger, du har modtaget, og som afventer handling fra dig.
    Sendt|Viser de godkendelsesanmodninger, du har sendt, og som afventer handling fra andre.
    Oversigt|Viser modtagne og sendte godkendelsesanmodninger.
    Opret godkendelsesflow|Opret godkendelsesflow.

1. Vælg fanerne **Modtaget**, **Sendt** eller **Oversigt** for at få mere at vide.

    ![Fanen Godkendelser](media/flows-teams/approvals-tab-2.png)

1. Vælg **Opret godkendelsesflow** for at oprette et godkendelsesflow.

    ![Fanen Godkendelser](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Brug robotten med flow

### <a name="list-and-launch-flows-with-the-bot"></a>Vis og start flow med robotten

> [!TIP]
> Robotten viser og kører flow, der udløses af en tidsplan eller udløses manuelt uden brugerinput.

1. Log på Microsoft Teams.
1. Vælg linket **Flere tilføjede apps** (...) på navigationslinjen, og vælg derefter appen **Flow**.

    ![Ikonet Tilføjede apps](media/flows-teams/added-apps-icon.png)
    
1. Vælg fanen **Samtale**.

    ![Fanen Samtale](media/flows-teams/conversations-tab.png)

Under fanen **Samtale** kan du sende kommandoer til robotten, der svarer ved at udføre de handlinger, du beordrer den til. Hvis du f.eks. vil angive dine flow på en liste og køre flowet med indeks 1, så skal du køre følgende kommandoer:

- ```List flows``` – Robotten viser en liste over dine flow med et indeksnummer foranstillet.
- ```Run flow 1``` – Kører flownummer 1. Her er *1* indeksnummeret for det flow, du vil køre.

   ![Robotkommandoer](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Hent beskrivelsen af flow

Hvis du vil hente beskrivelsen af flowet med indeks 1 fra listen over flow, skal du køre ```describe flow 1```. Robotsvaret vil ligne følgende billede:

   ![Beskriv flow](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Hent listen over kommandoer til robotten

Hvis du vil hente listen over de kommandoer, som robotten kan håndtere, skal du spørge den med denne kommando: ```learn more``` 

Robotsvaret vil ligne følgende billede:

![Beskriv flow](media/flows-teams/bot-learn-more.png) 
