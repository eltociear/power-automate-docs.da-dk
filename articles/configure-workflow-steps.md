---
title: Konfigurer faser og trin for arbejdsprocesser i Power Apps | MicrosoftDocs
description: Få mere at vide om, hvordan du konfigurerer trin for arbejdsprocesser
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5aa5d43617a0b60f02a0e8b7f58a597b2f0de5f3
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297247"
---
# <a name="configure-workflow-stages-and-steps"></a>Konfigurer faser og trin for arbejdsprocesser


Når du designer arbejdsprocesser, har du mulighed for at inkludere den logik, du vil udføre, i faser og trin.  
  
 **Faser**  
 Faser gør arbejdsproceslogikken nemmere at læse og forklarer arbejdsproceslogikken. Faser påvirker imidlertid ikke logikken i eller funktionsmåden for arbejdsprocesser. Hvis en proces indeholder faser, skal samtlige trin i processen være indeholdt i en fase.  
  
 **Trin**  
 Trinnene er en samlet forretningslogik i en arbejdsproces. Trin kan omfatte betingelser, handlinger, andre trin eller en kombination af disse elementer.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Handlinger, som processer i arbejdsprocessen kan udføre  

 Processer i arbejdsprocessen kan udføre de handlinger, der vises i følgende tabel.  
  
|Handling|Beskrivelse|  
|------------|-----------------|  
|**Opret post**|Opretter en ny post for et objekt og tildeler værdier, du vælger, til attributter.|  
|**Opdater post**|Du kan opdatere den post, som arbejdsprocessen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin.|  
|**Tildel post**|Du kan tildele den post, som arbejdsprocessen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin.|  
|**Send mail**|Sender en mail. Du kan vælge at oprette en ny mail eller bruge en mailskabelon, der er konfigureret for objektet for den post, som arbejdsprocessen kører på, eller alle objekter, som har en N:1-relation med objektet, eller objektet for alle poster, der er oprettet i tidligere trin.|  
|**Start en underordnet arbejdsproces**|Starter en proces i en arbejdsproces, der er konfigureret som en underordnet arbejdsproces.|  
|**Skift status**|Ændrer status for den post, som processen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin.|  
|**Stop arbejdsproces**|Standser den aktuelle arbejdsproces. Du kan angive en status til enten **Fuldført** eller **Annulleret** og angive en statusmeddelelse.<br /><br /> Når arbejdsprocesser i realtid er konfigureret for en hændelse, og du standser en arbejdsproces med statussen Annulleret, kan hændelsen ikke fuldføres. Du kan finde flere oplysninger under [Bruge arbejdsprocesser i realtid](configure-workflow-steps.md#BKMK_SynchronousWorkflows).|  
|**Brugerdefineret trin**|Udviklere kan oprette brugerdefinerede arbejdsprocestrin, der definerer handlinger. Der er ikke nogen tilgængelige brugerdefinerede trin som standard.|  
  
### <a name="setting-record-values"></a>Angivelse af postværdier  

 Når du opretter en post, kan du angive værdier for posten. Når du opdaterer en post, kan du angive, tilføje, forøge, formindske, multiplicere eller fjerne værdier.  
  
 Når du vælger **Angiv egenskaber**, åbnes en dialogboks, der viser dig standardformularen for objektet.  
  
 Nederst i dialogboksen kan du se en liste over yderligere felter, der ikke kan ses formularen.  
  
 For alle felter kan du angive en statisk værdi, som angives af arbejdsprocessen.  
  
 I højre side af dialogboksen **Formularassistent** kan du angive eller vedhæfte dynamiske værdier fra den aktuelle post. Dette omfatter værdier fra relaterede poster, der kan opnås adgang til fra N:1-relationer (mange til en) for objektet.  
  
 De tilgængelige indstillinger i **Formularassistent** afhænger af det felt, du har valgt i formularen. Når du angiver en dynamisk værdi, kan du se en gul pladsholder, der kaldes "slug", som viser, hvor dynamiske data medtages. Hvis du vil fjerne værdien, skal du blot vælge sluggen og slette den. For tekstfelter kan du bruge en kombination af statiske og dynamiske data.  
  
 I forbindelse med dynamiske værdier kan du ikke vide, om et felt eller et relateret objekt har den værdi, du vil angive. Du kan angive en række felter, du kan prøve, og angive værdien og sortere dem ved hjælp af de grønne pile. Hvis første felt ikke har data, prøves det andet felt osv. Hvis ingen af felterne indeholder data, du kan angive en standardværdi, som skal benyttes.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Angive betingelser for arbejdsproceshandlinger  

 De handlinger, du vil anvende, afhænger ofte af betingelser. I processer i arbejdsprocessen kan du angive betingelser og oprette en fordelingslogik for at få de ønskede resultater på flere måder. Du kan kontrollere værdier for den post, som arbejdsprocessen proces kører mod, de poster, der er knyttet til den pågældende post med en N:1-relation, eller værdier i selve processen  
  
|Betingelsestype|Beskrivelse|  
|--------------------|-----------------|  
|**Kontrollér betingelse**|En logisk "if-\<betingelse> then"-sætning.<br /><br /> Du kan kontrollere de aktuelle værdier for den post, som arbejdsprocessen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin. Afhængigt af disse værdier, kan du definere yderligere trin, når betingelsen er sand.<br /><br /> I sætningen "if-\<betingelse> then" kan du bruge følgende operatorer: **Er lig med**, **Er ikke lig med**, **Indeholder data**, **Indeholder ikke data**, **Under** og **Ikke under**. **Bemærk:** **Under** og **Ikke under** er hierarkiske operatorer. De kan kun bruges på de objekter, som har et defineret hierarkisk forhold. Hvis du forsøger at bruge disse operatorer på de objekter, som ikke har en defineret hierarkisk relation, vises fejlmeddelelsen: "Du bruger en hierarkisk operator på et objekt, der ikke har et defineret hierarkisk forhold. Enten skal du gøre objektet hierarkisk (ved at markere en relation som hierarkisk), eller også skal du bruge en anden operator". Du kan finde flere oplysninger om hierarkiske relationer, i [Definer og opret forespørgsel om hierarkisk relaterede data](/powerapps/maker/common-data-service/define-query-hierarchical-data). Et skærmbillede, der følger tabellen, er et eksempel på definitionen på arbejdsprocessen, som bruger de hierarkiske operatorer **Under** og **Ikke under**.|  
|**Betinget forgrening**|En logisk "else-if-then"-sætning, hvor editoren bruger teksten "Otherwise, if \<betingelse> then":<br /><br /> Vælg en kontrolbetingelse, som du tidligere har defineret, og du kan tilføje en betinget forgrening for at definere yderligere trin, når kontrollen af betingelsen returnerer false.|  
|**Standardhandling**|En logisk "else"-sætning. editoren bruger teksten "Otherwise:"<br /><br /> Vælg en kontrolbetingelse, betinget forgrening, vent-betingelse eller parallel vent-gren, du tidligere har defineret, og du kan bruge en standardhandling til at definere trin for alle de sager, som ikke stemmer overens med kriterierne, som er defineret i betingelses- eller grenelementerne.|  
|**Vent-betingelse**|Gør det muligt for en arbejdsproces i baggrunden at afbryde sig selv midlertidigt, indtil de kriterier, der er defineret i betingelsen, er opfyldt. Arbejdsprocessen starter igen automatisk, når kriterierne i vent-betingelsen er opfyldt.<br /><br /> Arbejdsprocesser i realtid kan ikke bruge vent-betingelser.|  
|**Parallel vent-gren**|Definerer en alternativ vent-betingelse for en arbejdsproces i baggrunden med et tilsvarende sæt ekstra trin, der kun skal udføres, når det første kriterium opfyldes. Du kan bruge parallelle vent-grene til at oprette tidsgrænser i arbejdsproceslogikken. De kan være med til at forhindre, at arbejdsprocessen venter på ubestemt tid på, at de kriterier, der er defineret i en vent-betingelse, opfyldes.|  
|**Brugerdefineret trin**|Udviklere kan oprette brugerdefinerede arbejdsprocestrin, der definerer betingelser. Der er ikke nogen tilgængelige brugerdefinerede trin som standard.|  
  
 Følgende skærmbillede indeholder et eksempel på arbejdsprocesdefinitionen med de hierarkiske operatorer **Under** og **Ikke under**. I dette eksempel anvender vi to forskellige rabatter for to grupper af konti. I **Tilføj trin**, vi har valgt **Kontrollér betingelse** for at angive den **if-then**-betingelse, der indeholder operatoren **Under** eller **Ikke under**. Den første **if-then**-betingelse gælder for alle konti, der er **Under** kontoen Alpine Ski House. Disse konti få 10 % rabat på købte varer og tjenester. Den anden **if-then**-betingelse gælder for alle konti, der er **Ikke under** kontoen Alpine Ski House, og de modtager en rabat på 5 %. Derefter valgte vi **Opdater post** for at definere den handling, der skal udføres på baggrund af betingelsen.  
  
 ![Arbejdsproces med Under/Ikke under-operatorer](media/wfp-under-not-under.PNG "Arbejdsproces med Under/Ikke under-operatorer")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Bruge arbejdsprocesser i realtid  

 Du kan konfigurere arbejdsprocesser i realtid, men du skal være opmærksom, når du bruger dem. Arbejdsprocesser i baggrunden anbefales som regel, da de giver systemet mulighed for at anvende dem som ressourcer på serveren. Det er med til at gøre det arbejde, som serveren skal udføre, mere problemfrit, og er med til at opretholde den bedste ydeevne for alle, der bruger systemet. Ulempen er, at handlinger, der er defineret af arbejdsprocesser i baggrunden, ikke sker omgående. Du kan ikke forudsige, hvornår de anvendes, men det tager typisk et par minutter. I forbindelse med automatisering af forretningsprocesser er dette som regel fint, da brugere af systemet ikke behøver at vide, at processen kører.  
  
 Brug arbejdsprocesser i realtid, når en forretningsproces kræver, at en bruger skal kunne se resultaterne af processen straks, eller hvis du vil have mulighed for at annullere en handling. Du vil f.eks. angive bestemte standardværdier for en post første gang, den gemmes, eller du vil sikre, at visse poster ikke slettes.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Konvertere mellem arbejdsprocesser i realtid og i baggrunden  

 Du kan ændre en arbejdsproces i realtid til en arbejdsproces i baggrunden ved at vælge **Konvertér til en arbejdsproces i baggrunden** på værktøjslinjen.  
  
 Du kan ændre en arbejdsproces i baggrunden til en arbejdsproces i realtid ved at vælge **Konvertér til en arbejdsproces i realtid** på værktøjslinjen. Hvis arbejdsprocessen i baggrunden bruger en vent-betingelse, bliver den ugyldig, og du kan ikke aktivere den, før du fjerner vent-betingelsen.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Starte arbejdsprocesser i realtid, før eller efter status ændres  

 Når du konfigurerer **Indstillinger for automatiske processer** for arbejdsprocesser i realtid, kan du i indstillingerne for **Start når** for statusændring vælge **Efter** eller **Før** for at angive, hvordan status skal ændres. Standardindstillingen er **Efter**.  
  
 Når du vælger **Før** angiver du, at logikken i arbejdsprocessen skal anvendes, før status for dataændring gemmes. Dette giver dig mulighed for at kontrollere værdierne, før en anden logik er anvendt efter handlingen og forhindrer, at yderligere logik udføres. Du har f.eks. yderligere logik i en plug-in eller en brugerdefineret arbejdsproceshandling, som kan starte handlinger på et andet system. Ved at standse videre behandling kan du undgå tilfælde, hvor eksterne systemer påvirkes. Anvendelse af arbejdsprocesser i realtid før denne hændelse betyder også, at andre arbejdsproces- eller plug-in-handlinger, der muligvis har gemt data, ikke skal annulleres, når handlingen annulleres.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Bruge arbejdsproceshandlingen Stop med arbejdsprocesser i realtid  

 Når du anvender handlingen **Stop arbejdsproces** i en arbejdsproces, har du mulighed for at angive en statusbetingelse, der enten kan være **Fuldført** eller **Annulleret**. Når du angiver status til annulleret, forhindrer du, at handlingen udføres. Brugeren får vist en fejlmeddelelse med teksten fra statusmeddelelsen for stop-handlingen med overskriften **Fejl i forretningsproces**.  
  
## <a name="next-steps"></a>Næste trin  
 [Opret brugerdefineret forretningslogik via processer](guide-staff-through-common-tasks-processes.md)   
 [Oversigt over arbejdsprocesser](workflow-processes.md)   
 [Overvåg og administrer arbejdsprocesser](monitor-manage-processes.md)   
 [Anbefalede fremgangsmåder for arbejdsprocesser](best-practices-workflow-processes.md)
