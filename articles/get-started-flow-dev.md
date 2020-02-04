---
title: Opret brugerdefinerede connectorer, og integrer flows | Microsoft Docs
description: Opret en brugerdefineret connector, del den, integrer et flow, og foretag dig meget andet end det.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: feca66dc9148d6416e2bac8a6e690cee62d6aa9b
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74369082"
---
# <a name="start-to-build-with-power-automate"></a>Begynd at oprette vha. Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Her er nogle af de måder, du kan udvide dit program på med Power Automate:

* Skab og opret forbindelse til en brugerdefineret connector.
* Del din brugerdefinerede connector med alle Power Automate-brugere.
* Integrer flowoplevelsen i en app.
* Fremhæv alle brugerdefinerede connectors, så brugerne kan interagere med Power Automate på den måde, der er bedst for dem.

## <a name="prerequisites"></a>Forudsætninger

* En [Power Automate](https://flow.microsoft.com)-konto.

## <a name="create-a-custom-connector"></a>Opret en brugerdefineret connector

Hvis du har en webtjeneste, som du vil oprette forbindelse til via Power Automate, skal du først oprette en brugerdefineret connector. Når du registrerer en brugerdefineret connector, kan du lære Power Automate om egenskaberne i webtjenesten, herunder den godkendelse, den kræver, de udløsere og handlinger, den understøtter, samt parametrene og outputtene for hver af disse handlinger.

Følg dette selvstudium for at få mere at vide om, hvordan du [registrerer og anvender brugerdefinerede connectorer](https://powerapps.microsoft.com/tutorials/register-custom-api/). Når du har registreret din brugerdefinerede connector, kan du dele den i din organisation til testformål.

## <a name="share-a-custom-connector-with-all-power-automate-users"></a>Del en brugerdefineret connector med alle Power Automate-brugere.

Når du har testet den brugerdefinerede connector fuldt ud, skal du starte [evalueringsprocessen](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) for at få den godkendt af Microsoft til deling med alle andre Power Automate-brugere.

Her er, hvad du skal bruge til evalueringsprocessen:

* En OpenAPI-fil, der repræsenterer din API og eventuelle godkendelsesoplysninger.
* Et ikon for din connector.
* En beskrivelse af din connector.
* Cirka ti idéer til, hvordan din connector kan være en fordel for andre brugere via skabeloner.

Når du har indsendt disse oplysninger, begynder Microsoft at vurdere din APIs funktionalitet i Power Automate og Microsoft Power Apps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Integrer flowoplevelsen på dit websted eller i din app

Du kan [integrere](developer/embed-flow-dev.md) Power Automate i din app for at aktivere dyb integration i kontekst mellem din app og alle de andre tjenester, som understøttes af Power Automate. Du kan f.eks.:

* Gennemse alle de skabeloner, der er relateret til tjenesten, og lad brugerne vælge en skabelon.
* Administrer de flows, brugerne har relateret til din app.

## <a name="next-steps"></a>Næste trin

Få mere at vide om, hvordan du [integrerer](developer/embed-flow-dev.md) Power Automate i din app.
