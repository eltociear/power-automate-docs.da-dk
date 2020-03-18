---
title: Overvåg og administrer arbejdsprocesser med Power Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.openlocfilehash: e4042b71e6913f1008f506697fa39291b3cbf59a
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/13/2020
ms.locfileid: "79224279"
---
# <a name="monitor-and-manage-workflow-processes"></a>Overvåg og administrer arbejdsprocesser


Hvis du vil overvåge og styre processer, skal du finde processen, evaluere statussen og udføre de handlinger, der er nødvendige for at løse problemerne.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Overvågning af arbejdsprocesser i baggrunden  
 Arbejdsprocesser i baggrunden genererer systemjobposter for at spore processernes status. Du kan få adgang til oplysninger om disse systemjob flere forskellige steder i programmet:  
  
 **[Indstillinger](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Systemjob**  
 Dette omfatter alle typer systemjob. Du skal filtrere poster for dem, hvor **Systemjobtype** er **Arbejdsproces**.  
  
 **Fra arbejdsprocessen**  
 Åbn definitionen af arbejdsprocessen i baggrunden, og gå til fanen **Processession**. Her vises kun systemjob for den pågældende arbejdsproces i baggrunden.  
  
 **Fra posten**  
 Du kan redigere objektformularen, så navigationen omfatter relationen **Baggrundsprocesser**. Her vises alle de systemjob, der er startet i konteksten for posten.  
  
> [!NOTE]
>  Hvis et asynkront systemjob (arbejdsproces) mislykkes flere gange i træk, begynder systemet at udskyde udførelsen af jobbet med længere og længere tidsintervaller imellem, så administratoren eller appopretteren kan undersøge og løse problemet. Når jobbet starter igen, udføres det normalt.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Handlinger på aktive arbejdsprocesser i baggrunden  
 Mens en arbejdsproces i baggrunden kører, har du mulighed for at **annullere**, **afbryde den midlertidigt** eller **udsætte** arbejdsprocessen. Hvis du tidligere har afbrudt en arbejdsproces midlertidigt, kan du **genoptage** den.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Overvågning af arbejdsprocesser i realtid og handlinger  
 Arbejdsprocesser i realtid og handlinger bruger ikke systemjobposter, fordi de opstår med det samme. De fejl, der måtte opstå, vises til brugeren i programmet med overskriften **Fejl i forretningsproces**.  
  
 Der er ingen logge for fuldførte handlinger. Du kan aktivere logføring af fejl ved at markere afkrydsningsfeltet **Bevar logge for arbejdsprocesjob, hvor der opstod fejl**  i området **Opbevaring af arbejdsproceslog** nederst på fanen **Administration** for processen.  
  
 Hvis du vil have vist en log over fejl for en bestemt proces, skal du åbne definitionen af arbejdsprocessen i realtid eller handlingen og gå til fanen **Processession**. Her vises kun de eventuelle fejl, der er logget for denne proces.  
  
 Hvis du vil have vist alle fejl for en proces, skal du gå til **Avanceret søgning** og oprette en visning med fejl på processionsessionsobjektet.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Status over arbejdsprocesser  
 Når du får vist en liste over arbejdsprocesser, kan den enkelte proces have en af følgende værdier **Fase** eller **Statusårsag**:  
  
|Stat|Statusårsag|  
|-----------|-------------------|  
|Klar|Venter på ressourcer|  
|Suspenderet|Venter|  
|Låst|Igangværende<br /><br /> Afbrudt midlertidigt<br /><br /> Annullerer|  
|Fuldført|Lykkedes<br /><br /> Mislykket<br /><br /> Annulleret|  

## <a name="deleting-process-log-records"></a>Sletning af proceslogposter

Hvis din organisation bruger arbejdsprocesser i baggrunden eller forretningsprocesforløb, der kører ofte, kan mængden af proceslogposter blive så stor, at det medfører problemer med ydeevnen samt forbruger store mængder lagerplads. Hvis du vil slette proceslogposter, der ikke er slettet tilstrækkeligt af standardjobbene til massesletning af poster, kan du bruge funktionen til massesletning af systemjob til at oprette et brugerdefineret job til massesletning af poster.

1. Gå til **Indstillinger** > **Dataadministration** > **Massesletning af poster**.
2. Vælg **Ny** i området **Massesletning af poster**. 
3. Vælg **Næste** på startsiden i **Guiden Massesletning**.
4. Vælg **Systemjob** på listen **Søg i**.
5. Følgende betingelser bruges til at oprette et job til massesletning af poster for at slette proceslogposter. 
 - **Systemjobtypen er lig med Arbejdsproces**. Dette er målrettet arbejdsprocesposter. 
 - **Status er lig med Fuldført**. Jobbet kan kun køres mod fuldførte arbejdsprocesser.
 - **Statusårsag er lig med Lykkedes**. Slet vellykkede, annullerede og mislykkede job.
 - **Fuldført for ældre end X dage 30**. Brug feltet Fuldført for, hvis du kun vil slette arbejdsproceslogposter, der er ældre end 30 dage.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. Klik på **Næste**.
7. Angiv, hvor hyppigt massesletningsjobbet skal køre. Du kan planlægge, at jobbet kører med faste intervaller, eller oprette et job til enkeltstående massesletning [ved at bruge indstillingen Omgående](#using-the-immediately-option). I dette eksempel er en tilbagevendende opgave angivet til at køre den 21. maj 2018 og hver 30. dag derefter. 
![Indstillinger for massesletning af poster](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Brug af indstillingen Omgående

Bemærk, at du har mulighed for at udføre en øjeblikkelig synkron massesletning af poster ved at vælge indstillingen **Omgående**. Denne sletning udføres med direkte udførelse af SQL Server i stedet for at føre hver post gennem en slet hændelse-pipeline, hvilket kan reducere den negative påvirkning af systemets ydeevne. Dette er en god mulighed, hvis du hurtigt vil fjerne de ekstra arbejdsprocesposter i stedet for, at massesletningsjobbet venter på behandling i den asynkrone kø. 

Indstillingen **Omgående** er aktiveret, når følgende betingelser er opfyldt: 
- Massesletning af job er for systemjobobjektet.
- Søgekriterierne har betingelsen, at systemjobtype er lig med arbejdsproces. 
- Den bruger, der opretter massesletningsjobbet, har global sletteadgang til objektet AsyncOperation. Systemadministratorens sikkerhedsrolle har denne rettighed.  

Den synkrone massesletning sletter kun AsyncOperation-poster med tilstanden fuldført. Der kan maksimalt behandles en million poster for hver aktivering. Du skal udføre jobbet flere gange, hvis dit miljø har mere end en million poster, der skal fjernes.  
  
## <a name="next-steps"></a>Næste trin   
 [Bedste fremgangsmåder for arbejdsprocesser](best-practices-workflow-processes.md) <br />

