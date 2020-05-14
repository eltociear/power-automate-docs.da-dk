---
title: Kør flow efter en tidsplan | Microsoft Docs
description: Automatiser gentagne opgaver ved at køre flows efter en tidsplan, f.eks. hver dag eller hver time.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4970554dee8e031a746cf604e2a628f41056b46c
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296631"
---
# <a name="run-flows-on-a-schedule"></a>Kør flows efter en tidsplan

Opret et flow, der udfører en eller flere handlinger (f.eks afsendelse af en rapport i en mail):

* en gang om dagen, i time eller i minuttet
* på en dato, du angiver
* efter et antal dage, timer eller minutter, du angiver

## <a name="create-a-recurring-flow"></a>Opret et tilbagevendende flow
1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter **Mine flows** på den øverste navigationslinje.
   
    ![Indstilling for Mine flows](./media/run-scheduled-tasks/create-flow.png)
2. Vælg **Opret fra bunden**.
   
    ![Opret en proces fra bunden](./media/run-scheduled-tasks/create-from-blank.png)
3. I feltet **Søg i alle forbindelser og udløsere** skal du skrive **Gentagelse** og derefter vælge **Tidsplan – Gentagelse**.
   
    ![Find udløser for gentagelse](./media/run-scheduled-tasks/select-recurrence.png)
4. I dialogboksen **Gentagelse** skal du angive, hvor ofte flowet skal køres.
   
    Angiv f.eks. **2** under **Interval** og **Uge** under **Hyppighed**, hvis flowet skal køres hver anden uge.
   
    ![Angiv gentagelse](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Angiv avancerede indstillinger
1. Følg trinnene i forrige afsnit, og vælg derefter **Vis avancerede indstillinger**.
   
    **Bemærk**! Disse indstillinger ændres på baggrund af de værdier, der er angivet for **Interval** og **Frekvens**. Hvis dit skærmbillede ikke svarer til nedenstående grafik, skal du kontrollere, at **Interval** og **frekvens** er angivet til samme værdier som vist i grafikken.
2. Vælg en **Tidszone** for at angive, om **Starttidspunktet** afspejler en lokal tidszone, Universal Coordinated Time (UTC) osv.
3. Angiv et **Starttidspunkt** i følgende format:
   <br>YYYY-MM-DDTHH:MM:SSZ
4. Hvis du har angivet **Dag** under **Frekvens**, skal du angive det tidspunkt på dagen, hvor flowet skal køres.
5. Hvis du har angivet **Uge** under **Frekvens**, skal du angive den eller de dage i ugen, som flowet skal køre samt det klokkeslæt eller de gange om dagen, hvor flowet skal køres.
   
    Konfigurer f.eks. de indstillinger, som vises, for at starte et flow tidligere end middag (Pacific time) mandag den 1. januar 2018, og kør det hver anden uge på tirsdag kl. 17:30 (Pacific time).
   
    ![Angiv avancerede indstillinger](./media/run-scheduled-tasks/advanced-options.png)
6. Tilføj den eller de handlinger, flowet skal udføre, som beskrevet under [Opret et flow fra bunden](get-started-logic-flow.md).

## <a name="delay-a-flow"></a>Udskyd et flow
1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter **Mine flows** på den øverste navigationslinje.
   
    ![Opret en proces fra bunden](./media/run-scheduled-tasks/create-flow.png)
2. Vælg **Opret fra bunden**.
   
    ![Opret en proces fra bunden](./media/run-scheduled-tasks/create-from-blank.png)
3. Angiv en hændelse som beskrevet under [Opret et flow fra bunden](get-started-logic-flow.md).
4. Vælg **Nyt trin**, og vælg derefter **Tilføj en handling**.
   
    ![Mulighed for at føje en handling til et flow](./media/run-scheduled-tasks/add-action.png)
5. Benyt en af følgende fremgangsmåder på listen over handlinger:
   
   * Vælg **Forsinkelse**, angiv et **Antal**, og angiv en **Enhed** for tidsrum, f.eks. sekund, minut eller time.
   * Vælg **Udskyd til**, og angiv derefter en dato i dette format.<br>YYYY-MM-DDTHH:MM:SSZ
     
     ![Tilføj en forsinkelse](./media/run-scheduled-tasks/add-delay.png)
     ![Angiv forsinkelse i tidsenheder](./media/run-scheduled-tasks/delay.png)
     ![Angiv forsinkelse indtil](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Få mere at vide

Få mere at vide om de [avancerede indstillinger](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence), og hvordan du konfigurerer dem.

