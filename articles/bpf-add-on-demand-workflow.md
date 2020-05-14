---
title: Føj en arbejdsproces efter behov til et forretningsprocesforløb
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bb8ca7efb83a863f3031dd18d0d9bd67ae3c5c07
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297115"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Føj en arbejdsproces efter behov til et forretningsprocesforløb


Du kan udløse arbejdsprocesser efter behov inde i et forretningsprocesforløb. Du kan f.eks. føje en arbejdsproces efter behov til et forretningsprocesforløb, så der oprettes en aktivitet, f.eks. en opgave eller mail hver gang et trin er fuldført. 

En arbejdsproces bliver aktiveret, afhængigt af hvor du slipper arbejdsprocessen i designeren til forretningsprocesforløb.
- Procesfaser efter behov. Når arbejdsprocessen slippes i en fase i et forretningsprocesforløb, udløses processen, når fasen registreres, eller når fasen afsluttes. 
- Globale processer efter behov. Når arbejdsprocessen slippes i området **Globale arbejdsprocesser**, udløses arbejdsprocessen ved procesaktivering eller procesarkivering (når statussen går videre til en anvendt, fuldført, genaktiveret eller afbrudt fase). 

Bemærk følgende krav, når du føjer en arbejdsproces til et forretningsprocesforløb.
- For arbejdsprocesser, der føjes til en fase: Du kan kun bruge aktive arbejdsprocesser efter behov, der er oprettet for det samme objekt i den fase, hvor du tilføjer arbejdsprocessen.  
- For globale arbejdsprocesser: Du kan kun bruge aktive arbejdsprocesser efter behov, der er oprettet for det primære objekt for forretningsprocessen.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Føj en arbejdsproces efter behov til en fase i et forretningsprocesforløb

Du tilføjer en arbejdsproces efter behov fra designeren til forretningsprocesforløb ved at trække arbejdsproceskomponenten til en fase i processen eller til afsnittet globale arbejdsprocesser. 

På [PowerApps](https://make.powerapps.com)-webstedet skal du vælge **Modelbaseret** (i navigationsruden nederst til venstre). 

Åbn designeren til forretningsprocesforløb. Det kan du gøre på to måder.
- Hvis forretningsprocesforløbet allerede er føjet til en app, skal du gå til **Apps** og vælge **... ** ud for den relevante app og derefter vælge **Rediger**. I appdesigneren skal du vælge forretningsprocesforløbet og derefter vælge ![Åbn designer til forretningsprocesforløb](media/dynamics365-open-designer.PNG).  
- Du kan også åbne [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), vælge **Processer** i venstre navigationsrude og derefter vælge det relevante forretningsprocesforløb. 

Beslut, om arbejdsprocessen skal udløses af en af følgende hændelser i et forretningsprocesforløb. 
- Procesfaser efter behov. Udløser arbejdsprocessen ved registrering eller afslutning af fasen. 
- Globale processer efter behov. Udløser arbejdsprocessen ved procesaktivering eller procesarkivering (når statussen går videre til en anvendt, fuldført, genaktiveret eller afbrudt fase). 

I eksemplet nedenfor blev en arbejdsproces efter behov ved navn **Min arbejdsproces efter behov** føjet til **Fase 1** i forretningsprocesforløbet. 

1. Udvid Fase 1 for at få vist afsnittet **Udløst proces**. 
2. Vælg fanen **Komponenter**, og træk **Arbejdsproces** til afsnittet **Udløst proces**.
    ![Føj arbejdsprocessen til en fase](media/add-workflow-to-bpf-1.png) Du kan også trække **Arbejdsproces** til afsnittet **Globale arbejdsprocesser**, som udløser arbejdsprocessen enten ved procesaktivering eller procesarkivering.
 ![Føj arbejdsproces til procesaktivering eller -arkivering](media/add-workflow-to-bpf-global.png)
3. I søgefeltet på fanen **Egenskaber** skal du indtaste og søge efter navnet på den arbejdsproces efter behov, som du vil føje til forretningsprocesforløbet, og derefter vælge **Anvend**.
    ![Angiv navn, og vælg Anvend](media/add-workflow-to-bpf-2.png)
4. På fanen **Egenskaber** under fanen **Udløser** skal du enten vælge **Faseregistrering** eller **Faseafslutning**.  
    ![Vælg arbejdsprocesudløser](media/workflow-trigger.png)
   
    Når du slipper arbejdsprocessen i afsnittet **Globale arbejdsprocesser**, er indstillingerne for udløseren **Proces anvendt**, **Proces genaktiveret**, **Proces afbrudt** og **Proces fuldført**.

5. Vælg **Opdater** på værktøjslinjen i designeren til forretningsprocesforløbet.
 
## <a name="next-steps"></a>Næste trin
[Brug af arbejdsprocesser til at automatisere processer, der ikke kræver indgriben fra brugeren](workflow-processes.md) <br/>
[Selvstudium: Opret et forretningsprocesforløb for at standardisere processer](create-business-process-flow.md) <br/>
[Automatisering af forretningsprocesser i Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
