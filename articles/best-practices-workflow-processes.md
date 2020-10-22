---
title: De bedste fremgangsmåder til administration af arbejdsprocesser i baggrunden | MicrosoftDocs
description: Om de anbefalede metoder til brug af arbejdsprocesser
ms.custom: ''
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
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bb652591c0f16b4247875fc7c6f58c9dbf6635a9
ms.sourcegitcommit: 6aead6aa695ef3dd09a397f7e2df85e3f480071f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/11/2020
ms.locfileid: "3795005"
---
# <a name="best-practices-for-background-workflow-processes"></a>Om de bedste fremgangsmåder for arbejdsprocesser i baggrunden


Dette emne indeholder bedste praksis for oprettelse og administration af arbejdsprocesser i baggrunden.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Undgå uendelige løkker  
 Du kan oprette logik i en baggrundsarbejdsproces, som starter en uendelig løkke, der forbruger serverressourcer og påvirker ydeevne. Den situation, en uendelig løkke typisk kan opstå i, er, hvis en baggrundsarbejdsproces er konfigureret til at starte, når en attribut opdateres, og attributten derefter opdateres i logikken for arbejdsprocessen. Opdateringshandlingen udløser samme baggrundsarbejdsproces, der opdaterer posten og udløser baggrundsarbejdsprocessen igen og igen.  
  
 De arbejdsprocesser, du opretter, inkluderer logik, der kan registrere og standse uendelige løkker. Hvis en baggrundsarbejdsproces køres mere end et bestemt antal gange på en bestemt post i en kort periode, lykkes processen ikke på grund af følgende fejl: **Dette arbejdsprocesjob blev annulleret, fordi den arbejdsproces, der startede det, indeholdt en uendelig løkke. Ret arbejdsproceslogikken, og prøv igen**. Grænsen for antal gange er 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-background-workflow-templates"></a>Bruge skabeloner til baggrundsarbejdsproces  
 Hvis du har arbejdsprocesser, der ligner hinanden, og du regner med at skulle oprette flere arbejdsprocesser, der følger samme mønster, kan du gemme baggrundsarbejdsprocessen som en arbejdsprocesskabelon. Næste gang du skal oprette en lignende arbejdsproces, kan du oprette baggrundsarbejdsprocessen ved hjælp af skabelonen og undgå at angive alle betingelser og handlinger fra bunden.  
  
 I dialogboksen **Opret proces** skal du vælge **Ny proces ud fra en eksisterende skabelon (vælg på listen )**.  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Bruge underordnede arbejdsprocesser  
 Hvis du anvender samme logik i forskellige arbejdsprocesser eller i betingede forgreninger, kan du definere logikken som en underordnet arbejdsproces, så du ikke behøver at kopiere logikken manuelt i hver baggrundsarbejdsproces eller hver betinget forgrening. Derved bliver arbejdsprocesserne nemmere at vedligeholde. I stedet for at undersøge mange arbejdsprocesser, der kan anvende samme logik, kan du bare opdatere én arbejdsproces.  
  
## <a name="automatically-delete-completed-background-workflow-jobs"></a>Slette fuldførte baggrundsarbejdsprocesjob automatisk
I forbindelse med arbejdsprocesser, der kører i baggrunden, anbefaler vi at vælge indstillingen **Slet automatisk fuldførte arbejdsprocesjob (for at spare plads på harddisken)** i definitionen af baggrundsarbejdsprocessen. Markering af dette afkrydsningsfelt gør det muligt for systemet at slette logge over baggrundsarbejdsprocesser for vellykkede kørsler for at spare plads. Bemærk, at logge fra mislykkede udførelser af baggrundsarbejdsprocesser altid gemmes i fejlfindingsøjemed.  

![Opbevaring af arbejdsprocesjob](media/workflow-job-retention.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Begrænse antallet af arbejdsprocesser, der opdaterer det samme objekt
Kørsel af mere end én baggrundsarbejdsproces, der opdaterer det samme objekt, kan forårsage problemer med låsning af ressourcer. Forestil dig flere kørende arbejdsprocesser, hvor alle opdateringer af salgsmuligheder udløser en opdatering af det tilknyttede firma. Flere forekomster af disse arbejdsprocesser, der kører og forsøger at opdatere den samme firmapost på samme tid, kan medføre, at ressourcelåsningsproblemer. Fejl opstår i baggrundsarbejdsprocesser, og en fejlmeddelelse, f.eks. **SQL Timeout: Kan ikke hente lås på ressourcen _ressourcenavn_**, registreres. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Bruge noter til at holde styr på ændringerne  
 Når du redigerer arbejdsprocesser, skal du bruge fanen Noter og skrive, hvad du har gjort, og hvorfor du har gjort det. Dermed kan en anden bruger forstå alle ændringer, du har foretaget.  
  
## <a name="next-steps"></a>Næste trin  
 <!-- [Workflow processes overview](workflow-processes.md)    -->
 [Konfigurere baggrundsarbejdsprocesser](configure-workflow-steps.md)   
 [Overvåg og administrer baggrundsarbejdsprocesser](monitor-manage-processes.md)
   
