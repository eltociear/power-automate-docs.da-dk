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
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194272"
---
# <a name="configure-workflow-stages-and-steps"></a>Konfigurer faser og trin for arbejdsprocesser


Når du designer arbejdsprocesser, har du mulighed for at inkludere den logik, du vil udføre, i faser og trin.  
  
 **Faser**  
 Faser gør det nemmere at læse og forklare arbejdsproceslogikken. Faser påvirker dog ikke logikken eller funktionsmåden for arbejdsprocesser. Hvis en proces har faser, skal alle trin i processen være indeholdt i en fase.  
  
 **Trin**  
 Trin er en enhed i forretningslogik i en arbejdsproces Trin kan omfatte betingelser, handlinger og andre trin eller en kombination af disse elementer.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Handlinger, som arbejdsprocesser kan udføre  

 Arbejdsprocesser kan udføre de handlinger, der er angivet i følgende tabel.  
  
|Handling|Beskrivelse|  
|------------|-----------------|  
|**Opret post**|Opretter en ny post for et objekt, og tildeler værdier, som du vælger, til attributter.|  
|**Opdater post**|Du kan opdatere den post, som arbejdsprocessen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin.|  
|**Tildel post**|Du kan tildele den post, som arbejdsprocessen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin.|  
|**Send mail**|Sender en mail. Du kan vælge at oprette en ny mail eller bruge en mailskabelon, der er konfigureret for objektet for den post, som arbejdsprocessen kører for, eller alle objekter, der har en N:1-relation med objektet, eller objektet for alle de poster, der er oprettet af tidligere trin.|  
|**Start en underordnet arbejdsproces**|Starter en arbejdsproces, der er konfigureret som en underordnet arbejdsproces.|  
|**Skift status**|Ændrer statussen for den post, som processen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin.|  
|**Stop arbejdsproces**|Stopper den aktuelle arbejdsproces. Du kan angive en status til enten **Lykkedes** eller **Annulleret** og angive en statusmeddelelse.<br /><br /> Når arbejdsprocesser i realtid er konfigureret for en hændelse, forhindres hændelseshandlingen i at blive afsluttet, hvis du stopper en arbejdsproces med statussen Annulleret. Se [Brug af arbejdsprocesser i realtid](configure-workflow-steps.md#BKMK_SynchronousWorkflows) for at få flere oplysninger.|  
|**Brugerdefineret trin**|Udviklere kan oprette brugerdefinerede arbejdsprocestrin, der definerer handlinger. Der er ingen brugerdefinerede trin tilgængelige som standard.|  
  
### <a name="setting-record-values"></a>Angivelse af postværdier  

 Når du opretter en post, kan du angive værdier for posten. Når du opdaterer en post, kan du angive, vedhæfte, forøge, mindske, multiplicere eller fjerne værdier.  
  
 Når du vælger **Angiv egenskaber**, åbnes en dialogboks, som viser dig standardformularen for objektet.  
  
 Du kan se en liste over yderligere felter, der ikke findes i formularen, nederst i dialogboksen.  
  
 Du kan angive en statisk værdi for et felt, som efterfølgende angives af arbejdsprocessen.  
  
 I højre side af dialogboksen giver **Formularassistant** dig mulighed for at angive eller tilføje dynamiske værdier fra konteksten for den aktuelle post. Dette omfatter værdier fra relaterede poster, der kan åbnes fra N:1-relationer (mange til én) for objektet.  
  
 De tilgængelige indstillinger i **Formularassistant** afhænger af det felt, du har valgt i formularen. Når du angiver en dynamisk værdi, kan du se en gul pladsholder, der kaldes en 'slug', som viser, hvor de dynamiske data inkluderes. Hvis du vil fjerne værdien, skal du blot vælge slug'en og slette den. I tekstfelter kan du bruge en kombination af statiske og dynamiske data.  
  
 I forbindelse med dynamiske værdier ved du ikke med sikkerhed, om et felt eller et relateret objekt har den værdi, du vil angive. Du kan faktisk angive et antal felter for at prøve at angive værdien og sortere dem i rækkefølge ved hjælp af grønne pile. Hvis det første felt ikke indeholder data, forsøges der med det andet felt osv. Hvis ingen af felterne indeholder data, kan du angive en standardværdi, der skal bruges.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Angivelse af betingelser for arbejdsproceshandlinger  

 De handlinger, som du vil anvende, afhænger ofte af betingelser. Arbejdsprocesser giver dig flere måder at angive betingelser og oprette forgreningslogik på for at få de ønskede resultater. Du kan kontrollere værdierne for den post, som arbejdsprocessen kører imod, de poster, der er knyttet til den pågældende post med en N:1-relation, eller værdier i selve processen  
  
|Betingelsestype|Beskrivelse|  
|--------------------|-----------------|  
|**Kontrolbetingelse**|En logisk sætning: "if-\<betingelse > then".<br /><br /> Du kan kontrollere de aktuelle værdier for den post, som arbejdsprocessen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin. På baggrund af disse værdier kan du definere yderligere trin, når betingelsen er true.<br /><br /> I sætningen "if -\<condition > then" kan du bruge følgende operatorer: **Er lig med**, **Er ikke lig med**, **Indeholder data**, **Indeholder ikke data**, **Under** og **Ikke under** . **Bemærk**!  **Under** og **Ikke under** er hierarkiske operatorer. De kan kun bruges på de objekter, der er defineret en hierarkisk relation for. Hvis du forsøger at bruge disse operatorer på de objekter, der ikke har et defineret hierarkisk forhold, får du fejlmeddelelsen: "Du bruger en hierarkisk operator på et objekt, der ikke har et defineret hierarkisk forhold. Enten skal du gøre objektet hierarkisk (ved at markere en relation som hierarkisk), eller også skal du bruge en anden operator". Du kan finde flere oplysninger om hierarkiske relationer, i [Definer og opret forespørgsel om hierarkisk relaterede data](/powerapps/maker/common-data-service/define-query-hierarchical-data). Skærmbilledet efter tabellen er et eksempel på definitionen af en arbejdsproces, der bruger de hierarkiske operatorer **Under** og **Not Under**.|  
|**Betinget forgrening**|En logisk "else-if-then"-sætning. Editoren bruger teksten "Otherwise, if \<betingelse > then:"<br /><br /> Vælg en Kontrollér betingelse, som du tidligere har defineret, hvorefter du kan tilføje en betinget forgrening for at definere yderligere trin, når Kontrollér betingelse returnerer false.|  
|**Standardhandling**|En logisk "else"-sætning. Editoren bruger teksten "Otherwise:"<br /><br /> Vælg en kontrolbetingelse, betinget forgrening, vent-betingelse eller en parallel vent-forgrening, som du tidligere har defineret, hvorefter du kan bruge en standardhandling til at definere trin for alle sager, der ikke opfylder de kriterier, der er defineret i betingelses- eller forgreningselementer.|  
|**Vent-betingelse**|Gør det muligt for en arbejdsproces, der kører i baggrunden, til midlertidigt at afbryde sig selv, indtil de kriterier, der er defineret af betingelsen, er opfyldt. Arbejdsprocessen starter igen automatisk, når kriterierne i vent-betingelsen er blevet opfyldt.<br /><br /> Arbejdsprocesser i realtid kan ikke bruge vent-betingelser.|  
|**Parallel vent-forgrening**|Definerer en alternativ vent-betingelse for en arbejdsproces, der kører i baggrunden, med et tilsvarende sæt yderligere trin, der kun udføres, når det første kriterium er opfyldt. Du kan bruge parallelle vent-forgreninger til at oprette tidsgrænser i din arbejdsproceslogik. De hjælper med at forhindre, at arbejdsprocessen venter på ubestemt tid, indtil de kriterier, der er defineret i en vent-betingelse, er opfyldt.|  
|**Brugerdefineret trin**|Udviklere kan oprette brugerdefinerede arbejdsprocestrin, der definerer handlinger. Der er ingen brugerdefinerede trin tilgængelige som standard.|  
  
 Følgende skærmbillede indeholder et eksempel på definitionen af en arbejdsproces, der bruger de hierarkiske operatorer **Under** og **Not Under**. I dette eksempel anvender vi to forskellige rabatter for to grupper konti. I **Tilføj trin** valgte vi **Kontrollér betingelse** for at angive betingelsen **if-then**, der indeholder operatorerne **Under** eller **Not Under**. Den første **if-then**-betingelse gælder for alle de konti, der er **Under** Alpine Ski House-kontoen. Disse konti får 10 % rabat på købte varer og tjenester. Den anden **if-then**-betingelse gælder for alle de konti, der er **Not Under** Alpine Ski House-kontoen, og de får en rabat på 5 %. Derefter valgte vi **Opdater post** for at definere den handling, der skal udføres på baggrund af betingelsen.  
  
 ![Arbejdsproces med operatorerne Under og Ikke under](media/wfp-under-not-under.PNG "Arbejdsproces med operatorerne Under og Ikke under")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Brug af arbejdsprocesser i realtid  

 Du kan konfigurere arbejdsprocesser i realtid, men du skal bruge dem med omhu. Arbejdsprocesser i baggrunden anbefales generelt, fordi de tillader, at systemet anvender dem, når der er tilgængelige ressourcer på serveren. Dette hjælper med at fordele det arbejde, som serveren skal foretage, og med at bevare den bedste ydeevne for alle, der bruger systemet. Ulempen er, at handlinger, der er defineret af arbejdsprocesser i baggrunden, ikke anvendes øjeblikkeligt. Du kan ikke forudsige, hvornår de bliver anvendt, men den vil generelt tage et par minutter. For de fleste automatiseringer af forretningsprocesser fungerer dette fint, fordi de personer, der benytter systemet, ikke behøver at være opmærksomme på, at processen kører.  
  
 Brug arbejdsprocesser i realtid, hvis en forretningsproces kræver, at en person med det samme får vist resultaterne af processen, eller hvis du vil have mulighed for at annullere en handling. Hvis du f.eks. vil angive bestemte standardværdier for en post, første gang posten gemmes, eller du vil sikre, at nogle poster ikke slettes.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Konvertering mellem arbejdsprocesser i realtid og i baggrunden  

 Du kan ændre en arbejdsproces i realtid til en arbejdsproces i baggrunden ved at vælge **Konvertér til en arbejdsproces i baggrunden** på værktøjslinjen.  
  
 Du kan ændre en arbejdsproces i baggrunden til en arbejdsproces i realtid ved at vælge **Konvertér til en arbejdsproces i realtid** på værktøjslinjen. Hvis arbejdsprocessen i baggrunden bruger en vent-betingelse, bliver den ugyldig, og du kan ikke aktivere den, før du fjerner vent-betingelsen.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Igangsættelse af arbejdsprocesser i realtid før eller efter statusændringer  

 Når du konfigurerer **indstillinger for automatiske processer** for arbejdsprocesser i realtid, kan du med indstillingerne for **Start, når** for statusændringshændelser vælge **Efter** eller **Før**, når statussen ændres. Standardindstillingen er **Efter**.  
  
 Når du vælger **Før**, anvendes logikken i arbejdsprocessen, før de data, der ændrer statussen, gemmes. Det giver dig mulighed for at kontrollere værdierne, før anden logik anvendes efter handlingen, og forhindre, at der udføres yderligere logik. Du kan f.eks. have yderligere logik i et plug-in eller i en brugerdefineret arbejdsproces, som kunne starte handlinger i et andet system. Du kan undgå tilfælde, hvor eksterne systemer påvirkes, ved at stoppe yderligere behandling. Anvendelse af arbejdsprocesser i realtid før denne hændelse betyder også, at andre arbejdsproces- eller plug-in-handlinger, der muligvis har gemt data, ikke behøver at blive annulleret, når handlingen er blevet annulleret.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Brug af Stop arbejdsproces ved arbejdsprocesser i realtid  

 Når du anvender **Stop arbejdsproces** i en arbejdsproces, har du mulighed for at angive en statusbetingelse, der kan være enten **Lykkedes** eller **Annulleret**. Når du angiver status til Annulleret, kan du forhindre handlingen. En fejlmeddelelse, der indeholder teksten fra statusmeddelelsen for stop-handlingen, vises til brugeren med overskriften **Fejl i forretningsproces**.  
  
## <a name="next-steps"></a>Næste trin  
 [Opret brugerdefineret forretningslogik via processer](guide-staff-through-common-tasks-processes.md)   
 [Oversigt over arbejdsprocesser](workflow-processes.md)   
 [Overvåg og administrer arbejdsprocesser](monitor-manage-processes.md)   
 [Bedste fremgangsmåder for arbejdsprocesser](best-practices-workflow-processes.md)
