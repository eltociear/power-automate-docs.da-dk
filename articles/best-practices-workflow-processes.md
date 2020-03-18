---
title: De bedste fremgangsmåder til administration af arbejdsprocesser | MicrosoftDocs
description: Forstå de anbefalede måder at bruge arbejdsprocesser på
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f3d02ca92b94752a8bbe6e3458fa8639de917dd8
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193996"
---
# <a name="best-practices-for-workflow-processes"></a>De bedste fremgangsmåder for arbejdsprocesser


Dette emne indeholder de bedste fremgangsmåder til oprettelse og administration af arbejdsprocesser.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Undgå uendelige løkker  
 Det er muligt at oprette logik i en arbejdsproces, der starter en uendelig løkke, hvilket forbruger serverressourcer og påvirker ydeevnen. Den typiske situation, hvor der kan opstå en uendelig løkke, er, hvis du har en arbejdsproces, der er konfigureret til at starte, når en attribut er blevet opdateret og derefter opdaterer den pågældende attribut i arbejdsproceslogikken. Opdateringshandlingen udløser den samme arbejdsproces, der opdaterer posten og udløser arbejdsprocessen igen og igen.  
  
 De arbejdsprocesser, du opretter, omfatter logik til at registrere og stoppe uendelige løkker. Hvis en arbejdsproces kører mere end et bestemt antal gange for en bestemt post i et kort tidsrum, mislykkes processen med følgende fejl: **Dette arbejdsprocesjob blev annulleret, fordi den arbejdsproces, der startede det, indeholdt en uendelig løkke. Ret arbejdsproceslogikken, og prøv igen**. Det maksimale antal gange er 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Brug af arbejdsprocesskabeloner  
 Hvis du har arbejdsprocesser, der ligner hinanden, og du forventer at oprette flere arbejdsprocesser, der følger det samme mønster, kan du gemme din arbejdsproces som en arbejdsprocesskabelon. Næste gang du så skal oprette en lignende arbejdsproces, kan du oprette arbejdsprocessen ved hjælp af skabelonen og undgå at angive alle betingelserne og handlingerne fra bunden.  
  
 I dialogboksen **Opret proces** skal du vælge **Ny proces fra en eksisterende skabelon (vælg på liste)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Brug underordnede arbejdsprocesser  
 Hvis du anvender den samme logik i forskellige arbejdsprocesser eller betingede grene, skal du definere logikken som en underordnet arbejdsproces, så du ikke behøver at replikere denne logik manuelt i hver arbejdsproces eller i hver betingede forgrening. Dette er med til at gøre det lettere at vedligeholde dine arbejdsprocesser. I stedet for at undersøge mange arbejdsprocesser, der muligvis anvender den samme logik, kan du blot opdatere én arbejdsproces.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Slet automatisk fuldførte arbejdsprocesjob
I forbindelse med arbejdsprocesser, der kører i baggrunden, anbefaler vi at vælge indstillingen **Slet automatisk fuldførte arbejdsprocesjob (for at spare plads på harddisken)** i arbejdsprocesdefinitionen. Markering af dette afkrydsningsfelt gør det muligt for systemet at slette arbejdsproceslogge for vellykkede kørsler for at spare plads. Bemærk, at logge fra mislykkede arbejdsprocesudførelser altid gemmes i fejlfindingsøjemed.  

![Opbevaring af arbejdsproces](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Opbevar logge for arbejdsprocesjob, hvor der opstod fejl  
I forbindelse med arbejdsprocesser, der ikke kører i baggrunden (synkront), anbefaler vi, at markere indstillingen **til at opbevare logge for arbejdsprocesjob, hvor der opstod fejl** i arbejdsprocesdefinitionen. Når du vælger denne indstilling, gemmes logge fra mislykkede arbejdsprocesudførelser altid i fejlfindingsøjemed. Logge fra vellykkede synkrone arbejdsprocesudførelser slettes altid for at spare plads.   

![Indstillingen til opbevaring af logge for mislykkede arbejdsprocesser](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Begræns antallet af arbejdsprocesser, der opdaterer det samme objekt
Kørsel af mere end én arbejdsproces, der opdaterer det samme objekt, kan forårsage ressourcelåsproblemer. Forestil dig, at flere arbejdsprocesser kører, hvor hver mulighed for opdatering udløser en opdatering for den tilknyttede konto. Flere forekomster af disse arbejdsprocesser, der kører og forsøger at opdatere den samme kontopost på samme tid, kan resultere i ressourcelåsproblemer. Arbejdsprocesfejl opstår, og en fejlmeddelelse som f.eks **SQL Timeout: Lås på ressource kunne ikke hentes _ressourcenavn_** , registreres. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Brug noter til at holde styr på ændringer  
 Når du redigerer arbejdsprocesser, skal du bruge fanen Noter til at skrive, hvad du gjorde, og hvorfor du gjorde det. Dette gør det muligt for andre at forstå de ændringer, du har foretaget.  
  
## <a name="next-steps"></a>Næste trin  
 [Oversigt over arbejdsprocesser](workflow-processes.md)   
 [Konfigurer arbejdsprocesser](configure-workflow-steps.md)   
 [Overvåg og administrer arbejdsprocesser](monitor-manage-processes.md)
   
