---
title: Føje en anmodet arbejdsproces til et forretningsprocesforløb
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
ms.openlocfilehash: 2c74e54c61e030bad788db97b14fca93f2a256fb
ms.sourcegitcommit: 2284143cf147beb7d6071fd8005a41298e51e493
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/19/2020
ms.locfileid: "3384983"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Føje en anmodet arbejdsproces til et forretningsprocesforløb


Du kan udløse arbejdsprocesser efter anmodning inde i et forretningsprocesforløb. Du kan f.eks. føje en arbejdsproces efter anmodning til et forretningsprocesforløb, så der oprettes en aktivitet, f.eks. en opgave eller mail hver gang et trin er fuldført. 

En arbejdsproces bliver aktiveret, afhængigt af hvor du slipper arbejdsprocessen i designeren til forretningsprocesforløb.
- Procesfaser efter anmodning. Når arbejdsprocessen slippes i en fase i et forretningsprocesforløb, udløses processen, når fasen registreres, eller når fasen afsluttes. 
- Globale processer efter anmodning. Når arbejdsprocessen slippes i området **Globale arbejdsprocesser**, udløses arbejdsprocessen ved procesaktivering eller procesarkivering (når statussen går videre til en anvendt, fuldført, genaktiveret eller afbrudt fase). 

Bemærk følgende krav, når du føjer en arbejdsproces til et forretningsprocesforløb.
- For arbejdsprocesser, der føjes til en fase: Du kan kun bruge aktive arbejdsprocesser efter anmodning, der er oprettet for det samme objekt i den fase, hvor du tilføjer arbejdsprocessen.  
- For globale arbejdsprocesser: Du kan kun bruge aktive arbejdsprocesser efter anmodning, der er oprettet for det primære objekt for forretningsprocesforløbet.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Føje en arbejdsproces efter anmodning til en fase i et forretningsprocesforløb

Du tilføjer en arbejdsproces efter anmodning fra designeren til forretningsprocesforløb ved at trække arbejdsproceskomponenten til en fase i processen eller til afsnittet for globale arbejdsprocesser. 

På [PowerApps](https://make.powerapps.com)-webstedet skal du vælge **Modelbaseret** (i navigationsruden nederst til venstre). 

Åbn designeren til forretningsprocesforløb. Det kan du gøre på to måder.
- Hvis forretningsprocesforløbet allerede er føjet til en app, skal du gå til **Apps** og vælge **...** ud for den relevante app og derefter vælge **Rediger**. I appdesigneren skal du vælge forretningsprocesforløbet og derefter vælge ![Åbn designer til forretningsprocesforløb](media/dynamics365-open-designer.PNG).  
- Du kan også åbne [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), vælge **Processer** i venstre navigationsrude og derefter vælge det relevante forretningsprocesforløb. 

Beslut, om arbejdsprocessen efter anmodning skal udløses af en af følgende hændelser i et forretningsprocesforløb. 
- Procesfaser efter anmodning. Udløser arbejdsprocessen ved start eller afslutning af fasen. 
- Globale processer efter anmodning. Udløser arbejdsprocessen ved procesaktivering eller procesarkivering (når statussen går videre til en anvendt, fuldført, genaktiveret eller afbrudt fase). 

I eksemplet nedenfor blev en arbejdsproces efter anmodning ved navn **Min arbejdsproces efter anmodning** føjet til **Fase 1** i forretningsprocesforløbet. 

1. Udvid Fase 1 for at få vist sektionen **Udløst proces**. 
2. Vælg fanen **Komponenter**, og træk **Arbejdsproces** til sektionen **Udløst proces**.
    ![Føj arbejdsprocessen til en fase](media/add-workflow-to-bpf-1.png) Du kan også trække **Arbejdsproces** til sektionen **Globale arbejdsprocesser**, som udløser arbejdsprocessen enten ved procesaktivering eller procesarkivering.
 ![Føj arbejdsproces til procesaktivering eller -arkivering](media/add-workflow-to-bpf-global.png)
3. I søgefeltet under fanen **Egenskaber** skal du indtaste og søge efter navnet på den arbejdsproces efter anmodning, som du vil føje til forretningsprocesforløbet, og derefter vælge **Anvend**.
    ![Angiv navn, og vælg Anvend](media/add-workflow-to-bpf-2.png)
4. Under fanen **Egenskaber** under fanen **Udløser** skal du enten vælge **Faseregistrering** eller **Faseafslutning**.  
    ![Vælg arbejdsprocesudløser](media/workflow-trigger.png)
   
    Når du slipper arbejdsprocessen i sektionen **Globale arbejdsprocesser**, er indstillingerne for udløseren **Proces anvendt**, **Proces genaktiveret**, **Proces afbrudt** og **Proces fuldført**.

5. Vælg **Opdater** på værktøjslinjen i designeren til forretningsprocesforløbet.
 
## <a name="next-steps"></a>Næste trin
[Bruge arbejdsprocesser til at automatisere processer, som ikke kræver brugerinteraktion](workflow-processes.md) <br/>
[Selvstudium: Oprette et forretningsprocesforløb for at standardisere processer](create-business-process-flow.md) <br/>
[Automatisering af forretningsprocesforløb i Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
