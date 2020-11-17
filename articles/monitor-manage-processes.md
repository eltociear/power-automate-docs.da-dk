---
title: Overvåg og administrer baggrundsarbejdsprocesser med Power Apps | MicrosoftDocs
ms.custom: To monitor and manage processes, you must locate the process, evaluate the status, and perform any actions necessary to address problems.
ms.date: 07/27/2020
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 37d02ad3b0e81a748172b0bb1f48dd1bda0dc194
ms.sourcegitcommit: dbe05fc5136f724705e66ad795a9391ec47414e1
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973177"
---
# <a name="monitor-and-manage-background-workflow-processes"></a>Overvåg og administrer baggrundsarbejdsprocesser


For at kunne overvåge og administrere processer skal du lokalisere processen, evaluere status og udføre eventuelle nødvendige handlinger for at løse problemer.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Overvåge baggrundsarbejdsprocesser  
Baggrundsarbejdsprocesser genererer systemjobposter til registrering af deres status. Du kan få adgang til oplysninger om disse systemjob flere forskellige steder i programmet:  
  
- **[Indstillinger](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Systemjob**  

  Dette omfatter alle typer af systemjob. Du skal filtrere posterne efter dem, hvor **Systemjobtype** er **Arbejdsproces**.  
  
- **Fra baggrundsarbejdsprocessen**  

  Åbn baggrundsarbejdsprocesdefinitionen, og gå til fanen **Processession**. Dette vises kun systemjob for denne arbejdsproces i baggrunden.  
  
- **Fra posten**  

  Du kan redigere objektformularen, så navigationen indeholder relationen **Baggrundsprocesser**. Dette viser alle de systemjob, der er startet i forbindelse med posten.  
  
> [!NOTE]
> Hvis et asynkront systemjob (arbejdsproces) mislykkes flere gange i træk, begynder systemet at udskyde udførelsen af jobbet med længere og længere tidsintervaller imellem, så administratoren eller appopretteren kan undersøge og løse problemet. Når jobbet startes efterfølgende igen, genoptager det afvikling normalt.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Handlinger på kørende baggrundsarbejdsprocesser  
Mens en baggrundsarbejdsproces kører, kan du vælge indstillingerne **Annuller**, **Pause** eller **Udskyd**. Hvis du tidligere har sat en arbejdsproces på pause, kan du vælge **Genoptag**.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-background-workflow-processes"></a>Status for baggrundsarbejdsprocesser  
Når du får vist en liste over baggrundsarbejdsprocesser, kan hver enkelt proces have en af følgende værdier for **Status** og **Statusårsag**:  
  
|Område|Statusårsag|  
|-----------|-------------------|  
|Klar|Venter på ressourcer|  
|Afbrudt|Venter|  
|Låst|I gang<br /><br /> Afbrudt midlertidigt<br /><br /> Annullerer|  
|Fuldførte|Gennemført<br /><br /> Mislykket<br /><br /> Annullerede|  

## <a name="deleting-process-log-records"></a>Sletning af proceslogposter

Hvis din organisation bruger arbejdsprocesser i baggrunden eller forretningsprocesforløb, der kører ofte, kan mængden af proceslogposter blive så stor, at det medfører problemer med ydeevnen samt forbruger store mængder lagerplads. Hvis du vil slette proceslogposter, der ikke er slettet tilstrækkeligt af standardjobbene til massesletning af poster, kan du bruge funktionen til massesletning af systemjob til at oprette et brugerdefineret job til massesletning af poster.

1. Gå til **Indstillinger** > **Dataadministration** > **Massesletning af poster**.
2. Vælg **Ny** i området **Massesletning af poster**. 
3. Vælg **Næste** på startsiden i **Guiden Massesletning**.
4. Vælg **Systemjob** på listen **Søg efter**.
5. Følgende betingelser bruges til at oprette et job til massesletning af poster for at slette proceslogposter: 
   - **Systemjobtype er lig med arbejdsproces.** Dette sigter mod baggrundsarbejdsprocesposter. 
   - **Status er lig med Fuldført.** Jobbet kan kun køres mod fuldførte arbejdsprocesser.
   - **Statusårsag er lig med fuldført.** Slet vellykkede, annullerede og mislykkede job.
   - **Fuldført for ældre end X dage 30.** Brug feltet Fuldført den, hvis du kun vil slette baggrundsarbejdsproceslogposter, der er ældre end 30 dage.

   ![Skærmbillede, der viser indstillinger for oprettelse af et job til massesletning af poster.](media/custom-bulk-record-deletion.png)
 
6. Vælg **Næste**.
7. Angiv, hvor hyppigt massesletningsjobbet skal køre. Du kan planlægge, at jobbet kører med faste intervaller, eller oprette et job til enkeltstående massesletning ved at [bruge indstillingen Omgående](#using-the-immediately-option). I dette eksempel er et tilbagevendende job angivet til at køre den 21. maj 2018 og hver 30. dag derefter. 

   ![Skærmbillede, der viser indstillinger for massesletning af poster.](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Brug af indstillingen Omgående

Bemærk, at du har mulighed for at udføre en øjeblikkelig synkron massesletning af poster ved at vælge indstillingen **Omgående**. Denne sletning udføres med direkte udførelse af SQL Server i stedet for at føre hver post gennem en slet hændelse-pipeline, hvilket kan reducere den negative påvirkning af systemets ydeevne. Dette er en god mulighed, hvis du hurtigt vil fjerne de ekstra baggrundsarbejdsprocesposter i stedet for, at massesletningsjobbet venter på behandling i den asynkrone kø. 

Indstillingen **Omgående** er aktiveret, når følgende betingelser er opfyldt: 
- Massesletning af job er for systemjobobjektet.
- Søgekriterierne har betingelsen Systemjobtype er lig med arbejdsproces. 
- Den bruger, der opretter massesletningsjobbet, har global sletteadgang til objektet AsyncOperation. Sikkerhedsrollen Systemadministrator har denne rettighed.  

Den synkrone massesletning sletter kun AsyncOperation-poster med tilstanden fuldført. Der kan maksimalt behandles 1 million poster for hvert kald. Du skal udføre jobbet flere gange, hvis dit miljø har mere end 1 million poster, der skal fjernes.  
  
## <a name="next-step"></a>Næste trin   
[Bedste praksis for arbejdsprocesser i baggrunden](best-practices-workflow-processes.md) <br />

