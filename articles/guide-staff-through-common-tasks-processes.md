---
title: Opret brugerdefineret forretningslogik via processer med Power Apps | MicrosoftDocs
description: Du kan få mere at vide om de forskellige typer forretningslogik, du kan bruge i din app
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: af51cc703dbb42296493237bdd25387c6c15720c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194732"
---
# <a name="create-custom-business-logic-through-processes"></a>Opret brugerdefineret forretningslogik via processer


En af det vigtigste grunde til at bruge modeldrevne apps er, at du kan definere og gennemtvinge forretningsprocesser konsekvent. Konsistente processer er med til at sikre, at brugerne af systemet kan fokusere på deres arbejde og ikke på at huske at skulle udføre et række manuelle trin. Processer kan være simple eller avancerede og kan ændre sig over tid.  
  
Power Apps indeholder flere typer processer, der alle er udviklet til et bestemt formål:  
  
-   Forretningsprocesforløb  
  
-   Mobilopgaveprocesser  
  
-   Arbejdsprocesser  
  
-   Handlinger  
  
 I lighed med processer kan du også oprette forretningsregler og -anbefalinger. Du kan finde flere oplysninger i [Opret forretningsregler og -anbefalinger for at anvende logik i en formular](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  Brug af processer kan påvirke licenskravene til Power Apps og flow. Du kan finde flere oplysninger i [Licenskrav til enheder](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Hvornår kan du bruge forretningsprocesforløb?  
 Brug et forretningsprocesforløb, når du gerne vil have, at medarbejderne skal gennemgå de samme faser og følge de samme trin, når de interagerer med en kunde. Du kan f.eks. bruge et forretningsprocesforløb, hvis du vil have alle til at håndtere anmodninger om kundeservice på samme måde, eller hvis medarbejderne skal have godkendt en faktura, før de afgiver en ordre.  
  
 Dit miljø inkluderer flere forretningsprocesforløb, der er klar til brug, til fælles salgs-, service- og marketingopgaver, som du kan bruge ved at foretage nogle få ændringer eller slet ingen. Eller du kan oprette dit eget. Se følgende emne for at få flere oplysninger om forretningsprocesforløb:  
  
-   [Opret et forretningsprocesforløb](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Hvornår kan du bruge arbejdsprocesser?  
 Du kan bruge arbejdsprocesser til at automatisere forretningsprocesser i baggrunden. Arbejdsprocesser igangsættes typisk af systemhændelser, så brugeren ikke behøver at være opmærksom på, at de kører. Arbejdsprocesser, der kører i baggrunden, er "asynkrone". Arbejdsprocesser kan også være konfigureret, så de skal igangsættes manuelt. Du kan også automatisere almindelige opgaver, f.eks sende en mail automatisk med en bekræftelse til en kunde, når en ordre sendes. Arbejdsprocesser, der kører i realtid, er "synkrone". Du kan finde flere oplysninger om arbejdsprocesser i [Arbejdsprocesser](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Hvornår kan du bruge handlinger?  
 Brug handlinger, når du vil automatisere en serie kommandoer i systemet. Handlinger udvider den ordliste, der er tilgængelig for udviklere til at udtrykke forretningsprocesser. De vigtige verber som f.eks. Opret, Opdater, Slet og Tildel leveres af systemet, og en handling bruger disse vigtige verber til at oprette mere sigende verber som f.eks. Godkend, Eskaler, Distribuer eller Planlæg. Hvis definitionen af en forretningsproces ændres, kan en person, der ikke er udvikler, redigere handlingen, så koden ikke behøver at blive ændret.  Du kan finde flere oplysninger om handlinger under [Handlinger](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-power-automate"></a>Hvornår du skal bruge Power Automate  
 Du kan bruge Power Automate, når du har brug for at oprette automatiserede arbejdsprocesser, der udfører handlinger mellem dit miljø og din foretrukne app eller tjeneste som f.eks. Dynamics 365, Twitter, Dropbox, Google-tjenester, Office 365 og SharePoint. Du kan udløse et flow baseret på en bestemt handling, eller du kan kalde det fra din app. Flere oplysninger: [Brug Power Automate til at automatisere processer på tværs af tjenester](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Hvor kan jeg oprette processer?  
 Der er to stier til at navigere til processer:  
  
- Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og gå til **Komponenter > Processer.** Denne sti giver nem adgang, når du udfører andre tilpasningsopgaver i tilpasningsværktøjerne.  

- **[Indstillinger](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processer.** Denne sti giver dig mulighed for at bruge de visninger, der er defineret for procesenheden, herunder alle brugerdefinerede visninger.  
  
 Individuelle forretningsprocesforløb kan også redigeres ved hjælp af knappen **Rediger proces** på kommandolinjen for den formular, hvor forretningsprocesforløbet er aktivt.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Hvem kan oprette processer?  
 Kun personer med rollen som systemadministrator, systemtilpasser eller administrerende direktør kan oprette processer, der gælder for hele miljøet. Personer med andre roller kan oprette processer med begrænset adgang. Brugere med adgangsniveauet Bruger kan f.eks. oprette arbejdsprocesser til eget brug med poster, som de ejer.  
  
 I følgende tabel vises adgangsniveauet for processer, der er baseret på standardsikkerhedsroller.  
  
|||  
|-|-|  
|**Sikkerhedsrolle**|**Adgangsniveau**|  
|Administrerende direktør|Organisation|  
|Systemadministrator|Organisation|  
|Systemtilpasser|Organisation|  
|Marketingdirektør|Overordnet: Underordnede afdelinger|  
|Salgsdirektør|Overordnet: Underordnede afdelinger|  
|Servicechef|Forretningsenhed|  
|Marketingchef|Forretningsenhed|  
|Salgschef|Forretningsenhed|  
|Planlægningschef|Forretningsenhed|  
|Kundeservicemedarbejder|Bruger|  
|Marketingmedarbejder|Bruger|  
|Sælger|Bruger|  
|Planlægger|Bruger|  
  
> [!NOTE]
>  Selvom personer muligvis kan oprette forretningsprocesforløb, arbejdsprocesser i realtid eller handlingsprocesser, skal til have tilladelse til at **aktivere forretningsprocesforløb** eller **aktivere processer i realtid** for at aktivere dem.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Yderligere oplysninger om arbejdsprocesser og handlinger  
 Processer kan kontrollere betingelser, anvende forgreningslogik og udføre handlinger. De udfører disse handlinger i en række trin. I følgende tabel beskrives de trin, der er tilgængelige i arbejdsprocesser og handlingsprocesser. Se emnerne for hver type proces for at få flere oplysninger.  
  
|Trin|Procestype|Beskrivelse|  
|----------|------------------|-----------------|  
|**Fase**|Arbejdsproces, handling|Faser gør det nemmere at læse og forklare arbejdsproceslogikken. Faser påvirker dog ikke logikken eller funktionsmåden for arbejdsprocesser. Hvis en proces har faser, skal alle trin i processen være indeholdt i en fase.|  
|**Kontrolbetingelse**|Arbejdsproces, handling|En logisk sætning: "if -\<betingelse > then".<br /><br /> Du kan kontrollere værdierne for den post, som arbejdsprocessen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin. På baggrund af disse værdier kan du definere yderligere trin, når betingelsen er `true`.|  
|**Betinget forgrening**|Arbejdsproces, handling|En logisk "else-if-then"-sætning. Editoren bruger teksten "Otherwise, if \<betingelse > then:"<br /><br /> Vælg en kontrolbetingelse, som du tidligere har defineret, hvorefter du kan tilføje en betinget forgrening for at definere yderligere trin, når kontrolbetingelsen returnerer `false`.|  
|**Standardhandling**|Arbejdsproces, handling|En logisk "else"-sætning. Editoren bruger teksten "Otherwise:"<br /><br /> Vælg en kontrolbetingelse, betinget forgrening, vent-betingelse eller en parallel vent-forgrening, som du tidligere har defineret, hvorefter du kan bruge en standardhandling til at definere trin for alle sager, der ikke opfylder de kriterier, der er defineret i betingelses- eller forgreningselementer.|  
|**Vent-betingelse**|Kun arbejdsproces i baggrunden|Gør det muligt for en arbejdsproces, der kører i baggrunden, til midlertidigt at afbryde sig selv, indtil de kriterier, der er defineret af betingelsen, er opfyldt. Arbejdsprocessen starter igen automatisk, når kriterierne i vent-betingelsen er blevet opfyldt.|  
|**Parallel vent-forgrening**|Kun arbejdsproces i baggrunden|Definerer en alternativ vent-betingelse for en arbejdsproces, der kører i baggrunden, med et tilsvarende sæt yderligere trin, der kun udføres, når det første kriterium er opfyldt. Du kan bruge parallelle vent-forgreninger til at oprette tidsgrænser i din arbejdsproceslogik. De hjælper med at forhindre, at arbejdsprocessen venter på ubestemt tid, indtil de kriterier, der er defineret i en vent-betingelse, er opfyldt.|  
|**Tildel værdi**|Handling|Angiver en værdi til en variabel eller en outputparameter i processen.|  
|**Opret post**|Arbejdsproces, handling|Opretter en ny post for et objekt og tildeler værdier til attributter.|  
|**Opdater post**|Arbejdsproces, handling|Du kan opdatere den post, som arbejdsprocessen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin.|  
|**Tildel post**|Arbejdsproces, handling|Du kan tildele den post, som arbejdsprocessen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin.|  
|**Send mail**|Arbejdsproces, handling|Sender en mail. Du kan vælge at oprette en ny mail eller bruge en mailskabelon, der er konfigureret for objektet for den post, som arbejdsprocessen kører for, eller alle objekter, der har en N:1-relation med objektet, eller objektet for alle de poster, der er oprettet af tidligere trin.|  
|**Start en underordnet arbejdsproces**|Arbejdsproces, handling|Starter en arbejdsproces, der er konfigureret som en underordnet arbejdsproces.|  
|**Skift status**|Arbejdsproces, handling|Ændrer statussen for den post, som processen kører for, de poster, der er knyttet til denne post i en N:1-relation, eller alle poster, der er oprettet af tidligere trin.|  
|**Stop arbejdsproces**|Arbejdsproces, handling|Stopper den aktuelle arbejdsproces eller handling. Du kan angive en status som enten **Lykkedes** eller **Annulleret** og angive en statusmeddelelse.|  
|**Brugerdefineret trin**|Arbejdsproces, handling|Indeholder udvidelser til de logiske elementer, der er tilgængelige som standard. Trin kan omfatte betingelser, handlinger og andre trin eller en kombination af disse elementer. Udviklere kan oprette brugerdefinerede trin til arbejdsprocestrin. Som standard er der ingen brugerdefinerede trin tilgængelige.|

  

