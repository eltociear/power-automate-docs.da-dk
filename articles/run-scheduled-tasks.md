---
title: Køre flow efter en tidsplan | Microsoft Docs
description: Automatiser gentagne opgaver ved at køre flow efter en tidsplan, f.eks. hver dag eller hver time.
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
ms.date: 08/29/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 86633b3f976107aeaa8138405aecb2f2b493e9e4
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900258"
---
# <a name="run-flows-on-a-schedule"></a>Kør flow efter en tidsplan

Opret et flow, der udfører en eller flere handlinger (f.eks afsendelse af en rapport i en mail):

* En gang om dagen, i timen eller i minuttet
* På en dato, du angiver
* Efter et antal dage, timer eller minutter, du angiver

## <a name="create-a-recurring-flow"></a>Opret et tilbagevendende flow

1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter fanen **Mine flow** i venstre navigationsrude.
1. Vælg **Nyt**, og vælg derefter **Planlagt fra bunden**.
    ![Opret et flow fra tom](./media/run-scheduled-tasks/create-flow.png)
1. Angiv, hvornår flowet skal starte, ved at redigere felterne **Start**, og angiv flowets gentagelse ved at redigere felterne **Gentag hver**, og vælg derefter **Opret**.
    ![Angiv gentagelse](./media/run-scheduled-tasks/select-recurrence.png)

## <a name="configure-advanced-options"></a>Konfigurer avancerede indstillinger

1. Følg trinnene i forrige sektion. Og vælg derefter **Gentagelse** > **Vis avancerede indstillinger**.

    ![Vis avancerede indstillinger for gentagelse](./media/run-scheduled-tasks/select-recurrence1.png)

   > [!NOTE]
   > Disse indstillinger ændres på baggrund af de værdier, der er angivet for **Interval** og **Frekvens**. Hvis dit skærmbillede ikke svarer til nedenstående grafik, skal du kontrollere, at **Interval** og **frekvens** er angivet til samme værdier som vist i grafikken.
1. Vælg en **Tidszone** for at angive, om **Starttidspunktet** afspejler en lokal tidszone, Universal Coordinated Time (UTC) osv.
1. Angiv et **Starttidspunkt** i følgende format:
   <br>YYYY-MM-DDTHH:MM:SSZ
1. Hvis du har angivet **Dag** under **Frekvens**, skal du angive det tidspunkt på dagen, hvor flowet skal køres.
1. Hvis du har angivet **Uge** under **Frekvens**, skal du angive den eller de dage i ugen, som flowet skal køre samt det klokkeslæt eller de gange om dagen, hvor flowet skal køres.

    Konfigurer f.eks. de indstillinger, som vises, for at starte et flow tidligere end middag (Pacific time) mandag den 1. januar 2018, og kør det hver anden uge på tirsdag kl. 17:30 (Pacific time).

    ![Angiv avancerede indstillinger](./media/run-scheduled-tasks/advanced-options.png)
1. Tilføj den eller de handlinger, flowet skal udføre, som beskrevet under [Opret et flow fra bunden](get-started-logic-flow.md).

## <a name="learn-more"></a>Få mere at vide

Få mere at vide om de [avancerede indstillinger](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence), og hvordan du konfigurerer dem.
