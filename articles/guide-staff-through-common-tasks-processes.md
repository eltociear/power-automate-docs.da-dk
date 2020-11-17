---
title: Oprette brugerdefineret forretningslogik via processer med Power Apps | MicrosoftDocs
description: Få mere at vide om de forskellige typer forretningslogik, der kan bruges i din app
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: 2eb9b35a0ba00accb553275aa9995184190a2678
ms.sourcegitcommit: dbe05fc5136f724705e66ad795a9391ec47414e1
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973273"
---
# <a name="create-custom-business-logic-through-processes"></a>Oprette brugerdefineret forretningslogik gennem processer


Definering og gennemtvingelse af ensartede forretningsprocesser er en af hovedårsagerne til, at folk bruger modelstyrede apps. Ensartede processer er med til at sikre, at brugerne af systemet kan fokusere på deres arbejde og ikke på at huske at udføre en række manuelle trin. Processerne kan være enkle eller komplekse og kan ændres løbende.  
  
Power Apps omfatter adskillige typer processer, som hver er udviklet til forskellige formål:  
  
-   Forretningsprocesforløb  
  
-   Mobile opgaveprocesser  
  
-   Arbejdsprocesser  
  
-   Handlinger  
  
Som det gælder for processer, kan du også oprette forretningsregler og anbefalinger. Du kan finde flere oplysninger i [Oprette forretningsregler og anbefalinger til anvendelse af logik i en formular](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
> Brug af processer kan påvirke licenskravene til Power Apps og flows. Flere oplysninger: [Objektlicenskrav](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses) 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Hvornår bruges forretningsprocesforløb  
Brug et forretningsprocesforløb, når du vil have medarbejdere til at gå gennem de samme faser og følge de samme trin, når de kommunikerer med en kunde. Brug f.eks. et forretningsprocesforløb, hvis du vil have alle til at håndtere kundeserviceforespørgsler på samme måde eller til at kræve, at medarbejdere får godkendt en faktura, før de sender en ordre.  
  
Dit miljø indeholder flere standardforretningsprocesforløb til almindelige salgs-, service- og marketingopgaver, som du kan bruge med kun få eller ingen ændringer. Du kan også oprette dit eget. Flere oplysninger: [Oprette et forretningsprocesforløb](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Hvornår bruges arbejdsprocesser

Brug arbejdsprocesser til at automatisere forretningsprocesser bag kulisserne. Arbejdsprocesser igangsættes typisk af systemhændelser, så brugeren behøver ikke vide, at de kører. Arbejdsprocesser, der kører i baggrunden, er "asynkrone". Arbejdsprocesser kan også konfigureres, så personer kan starte dem manuelt, når du ønsker at automatisere almindelige opgaver, f.eks. automatisk afsendelse af en bekræftelse via mail til en kunde, når en ordre leveres. Arbejdsprocesser, der kører i realtid, er "synkrone". Du kan finde flere oplysninger i [Arbejdsprocesser](workflow-processes.md)  
 
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-power-automate"></a>Hvornår bruges Power Automate


Brug Power Automate, når du skal oprette automatiserede arbejdsprocesser, der udfører handlinger mellem dit miljø og din foretrukne app eller tjeneste, f.eks. Dynamics 365, Twitter, Dropbox, Google-tjenester, Microsoft 365 eller SharePoint. Du kan udløse et forløb baseret på en bestemt handling, eller du kan starte den fra din app. Flere oplysninger: [Brug Power Automate til at automatisere processer på tværs af tjenester](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Hvor kan jeg oprette processer?  
Der findes to stier til at navigere til processerne:  
  
- Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og gå til **Komponenter** > **Processer**. Denne sti giver nem adgang, når du udfører anden tilpasning i tilpasningsværktøjerne.  

- **[Indstillinger](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Processer**. Denne sti giver dig mulighed for at bruge de visninger, der er defineret for procesenheden, herunder alle brugerdefinerede visninger.  
  
Individuelle forretningsprocesforløb kan også redigeres vha. knappen **Rediger proces** i kommandolinjen for formularen, hvor forretningsprocesforløbet er aktivt.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Hvem kan oprette processer?  
Kun personer med rollen som systemadministrator, systemtilpasser eller administrerende direktør kan oprette processer, der gælder for hele miljøet. Brugere med andre roller kan oprette processer med begrænset adgangsniveau. Personer med adgangsniveauet Bruger kan f.eks. oprette arbejdsprocesser til eget brug sammen med poster, de ejer.  
  
I den følgende tabel vises adgangsniveauet for processer baseret på standardsikkerhedsroller.  
  
|||  
|-|-|  
|**Sikkerhedsrolle**|**Adgangsniveau**|  
|Administrerende direktør|Organisation|  
|Systemadministrator|Organisation|  
|Systemtilpasser|Organisation|  
|Vicedirektør for marketing|Overordnet: underafdelinger|  
|Salgsdirektør|Overordnet: underafdelinger|  
|Servicechef i|Afdeling|  
|Marketingdirektør|Afdeling|  
|Salgschef|Afdeling|  
|Planlægningsleder|Afdeling|  
|Kundeservicemedarbejder|Bruger|  
|Marketingmedarbejder|Bruger|  
|Sælger|Bruger|  
|Planlægger|Bruger|  
  
> [!NOTE]
> Selvom en bruger kan oprette forretningsprocesforløb, realtidsarbejdsprocesser eller handlingsprocesser, skal vedkommende alligevel have rettighederne **Aktivér forretningsprocesforløb** eller **Aktivér processer i realtid** for at aktivere dem.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Mere om arbejdsprocesser og handlinger  
Processer kan kontrollere betingelser, anvende fordelingslogik og udføre handlinger. De udfører disse handlinger i en række trin. I den følgende tabel beskrives de tilgængelige trin i arbejdsprocesser og handlingsprocesser. Du kan finde flere detaljer i emnerne for hver type af proces.  
  
|Trin|Procestype|Beskrivelse|  
|----------|------------------|-----------------|  
|**Fase**|Arbejdsproces, handling|Faser gør arbejdsproceslogikken nemmere at læse og forklarer arbejdsproceslogikken. Faserne påvirker imidlertid ikke logikken i eller funktionsmåden for arbejdsprocesser. Hvis en proces indeholder faser, skal samtlige trin i processen være indeholdt i en fase.|  
|**Kontrollér betingelse**|Arbejdsproces, handling|En logisk "if \<condition> then"-sætning.<br /><br /> Du kan kontrollere værdier for den post, som arbejdsprocessen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin. Afhængigt af disse værdier kan du definere yderligere trin, når betingelsen er sand `true`.|  
|**Betinget forgrening**|Arbejdsproces, handling|En logisk "else-if-then"-sætning. Editoren bruger teksten "Otherwise, if \<condition> then:"<br /><br /> Vælg en kontrol af en betingelse, som du tidligere har defineret, og du kan tilføje en betinget forgrening for at definere yderligere trin, når kontrollen af betingelsen returnerer `false`.|  
|**Standardhandling**|Arbejdsproces, handling|En logisk "else"-sætning. Editoren bruger teksten "Otherwise:"<br /><br /> Vælg en kontrol af en betingelse, betinget forgrening, vent-betingelse eller parallel vent-gren, du tidligere har defineret, og du kan bruge en standardhandling til at definere trin for alle de sager, som ikke stemmer overens med kriterierne, som er defineret i betingelses- eller grenelementerne.|  
|**Vent-betingelse**|Kun baggrundsarbejdsproces|Gør det muligt for en arbejdsproces i baggrunden at afbryde sig selv midlertidigt, indtil de kriterier, der er defineret i betingelsen, er opfyldt. Arbejdsprocessen starter igen automatisk, når kriterierne i vent-betingelsen er opfyldt.|  
|**Parallel vent-gren**|Kun baggrundsarbejdsproces|Definerer en alternativ vent-betingelse for en arbejdsproces i baggrunden med et tilsvarende sæt ekstra trin, der kun skal udføres, når det første kriterium opfyldes. Du kan bruge parallelle vent-grene til at oprette tidsgrænser i arbejdsproceslogikken. De kan være med til at forhindre, at arbejdsprocessen venter på ubestemt tid på, at de kriterier, der er defineret i en vent-betingelse, opfyldes.|  
|**Tildel værdi**|Handling|Angiver en værdi til en variabel eller outputparameter i processen.|  
|**Opret post**|Arbejdsproces, handling|Opretter en ny post for et objekt og tildeler værdier til attributter.|  
|**Opdater post**|Arbejdsproces, handling|Du kan opdatere den post, som arbejdsprocessen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin.|  
|**Tildel post**|Arbejdsproces, handling|Du kan tildele den post, som arbejdsprocessen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin.|  
|**Send mail**|Arbejdsproces, handling|Sender en mail. Du kan vælge at oprette en ny mail eller bruge en mailskabelon, der er konfigureret for objektet for den post, som arbejdsprocessen kører på, eller alle objekter, som har en N:1-relation med objektet, eller objektet for alle poster, der er oprettet i tidligere trin.|  
|**Start en underordnet arbejdsproces**|Arbejdsproces, handling|Starter en proces i en arbejdsproces, der er konfigureret som en underordnet arbejdsproces.|  
|**Skift status**|Arbejdsproces, handling|Ændrer status for den post, som processen kører på, de poster, der er knyttet til denne post i en N:1-relation, eller poster, der er oprettet i tidligere trin.|  
|**Stop arbejdsproces**|Arbejdsproces, handling|Standser den aktuelle arbejdsproces eller handling. Du kan angive en status til enten **Fuldført** eller **Annulleret** og angive en statusmeddelelse.|  
|**Brugerdefineret trin**|Arbejdsproces, handling|Leverer udvidelser til de tilgængelige logiske standardelementer. Trin kan omfatte betingelser, handlinger, andre trin eller en kombination af disse elementer. Udviklere kan oprette brugerdefinerede arbejdsprocestrin. Som standard er der ikke nogen tilgængelige brugerdefinerede trin.|

  

