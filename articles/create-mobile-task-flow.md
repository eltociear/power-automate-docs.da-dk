---
title: Opret en mobilopgaveproces med Power Apps | Microsoft Docs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 72a4e33dafd7c2237799357cc993d9815dd36012
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297005"
---
# <a name="create-a-mobile-task-flow"></a>Opret en mobilopgaveproces


Opret en proces i Dynamics 365 til telefoner eller Dynamics 365 til tablets, der er baseret på almindelige opgaver, som dine brugere udfører. Hvis de f.eks. har brug for at udføre en række opfølgende trin regelmæssigt efter kundemøder, kan du oprette en opgaveproces. Når brugere trykker på den nye opgave i mobilappen, vil det føre dem gennem fra start til slut, så de ikke glemmer et vigtigt skridt.  
  
 Opgaveprocesser kan bruge formularer med flere objekter og mere logik og kan have formularlogik, der kører på tværs af siderne i opgaveprocessen.  
  
## <a name="create-a-task-flow"></a>Opret en opgaveproces
  
1. Sørg for, at du har sikkerhedsrollen som systemadministrator eller systemtilpasser eller tilsvarende tilladelser. Sikkerhedsrollerne som chef, direktør eller administrerende direktør kan også oprette mobilopgaveprocesser. 
  
2. Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg **Processer**.  
  
3.  Vælg **Ny** på værktøjslinjen **Handlinger**.  
  
4.  I dialogboksen **Opret proces** skal du udfylde de krævede felter:  
  
    -   Angiv et procesnavn.  
  
    -   På listen **Kategori** skal du vælge **Forretningsprocesforløb**.  
  
    -   På listen **Objekt** skal du vælge det ønskede objekt.  
  
5.  Vælg indstillingen **Kør processen som en opgaveprocess (Mobile Online)**.  
  
6.  Vælg **OK**.
  
     Opgaveprocesdesigneren åbnes i et nyt vindue.  
  
     ![Vindue for opgaveprocesdesigner](media/task-flow-designer-window.png "Vindue for opgaveprocesdesigner") 
  
7.  Hvis brugerne vil gå fra én side til en anden i rækkefølge, kan du trække komponenten **Side** fra fanen **Komponenter** i højre side af skærmen og slippe den på plustegnet på det relevante sted. Hvis du vil tilføje et navn til en side, skal du vælge siden, vælge fanen **Egenskaber**, skrive et nyt navn og derefter vælge **Anvend**.  
  
8.  Hvis du vil tilføje en gren til opgaveprocessen, skal du trække komponenten **Betingelse** fra fanen **Komponenter** og slippe den på plustegnet på det relevante sted. Hvis du vil angive egenskaber for betingelsen, skal du vælge betingelsen, angive egenskaberne på fanen **Egenskaber** og derefter vælge **Anvend**.  
  
    > [!NOTE]
    >  Når du tilføjer sider og betingelser i opgaveprocessen, vises et minikort i nederste venstre hjørne af vinduet med alle sider og betingelser i opgaveprocessen.  
  
9. Hvis du vil tilføje et felt, en etiket eller en sektionsetiket til en side, skal du trække **Felt**, **Etiket** eller **Sektionsetiket** fra fanen **Komponenter** til den relevante side. Hvis du vil ændre egenskaber for et af disse elementer, skal du vælge elementet, angive egenskaberne på fanen **Egenskaber** og derefter vælge **Anvend**.  
  
10. Hvis du vil validere opgaveprocessen, skal du vælge **Valider** på handlingslinjen.  
  
11. Hvis du vil gemme processen som en kladde, skal du vælge **Gem** øverst på skærmen. (Så længe en proces er i kladdeform, vil brugere ikke kunne bruge den).  
  
12. Hvis du vil aktivere opgaveprocessen, så brugere kan bruge den, skal du vælge **Aktivér**.  
  
> [!TIP]
>  Her er nogle få tip at huske på, mens du arbejder på din opgaveproces i designervinduet:  
>   
> -  Hvis du vil tage et øjebliksbillede af alt i opgaveprocesvinduet, skal du vælge **Øjebliksbillede** på handlingslinjen.  
> -  Hvis du vil oprette forbindelse mellem en gyldig komponent og en anden komponent i designeren, skal du vælge **Connector** på handlingslinjen.  
> -  Du kan gøre billederne på skærmen større eller mindre ved at vælge knapperne **Forøg zoomniveauet** eller **Formindsk zoomniveauet** øverst til højre på skærmen. Vælg knappen **Tilpas til lærred** for at blæse billeder op til den største størrelse, der passer til skærmen.  
  
## <a name="next-steps"></a>Næste trin  
 [Oprette et forretningsprocesforløb](create-business-process-flow.md)   

