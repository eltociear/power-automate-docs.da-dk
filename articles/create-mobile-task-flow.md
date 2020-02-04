---
title: Opret en mobilopgaveproces med Power Apps | MicrosoftDocs
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
ms.openlocfilehash: 22736d826c6e0448e3d1272aed1b3d4f78fdb23b
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74362067"
---
# <a name="create-a-mobile-task-flow"></a>Opret en mobilopgaveproces
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Opret en proces i Dynamics 365 til telefoner eller Dynamics 365 til tablets, der er baseret på almindelige opgaver, som dine brugere udfører. Hvis de f.eks. har brug for at udføre en række opfølgende trin regelmæssigt efter kundemøder, kan du oprette en opgaveproces. Når brugerne trykker på den nye opgave i deres mobilapp, bliver de ført igennem processen fra start til slut, så de ikke glemmer et vigtigt trin.  
  
 Opgaveprocesser kan bruge formularer med flere objekter og mere logik og kan have formularlogik, der kører på tværs af siderne i opgaveprocessen.  
  
## <a name="create-a-task-flow"></a>Opret en opgaveproces
  
1. Sørg for, at du har sikkerhedsrollen som systemadministrator eller systemtilpasser eller tilsvarende tilladelser. Sikkerhedsrollerne som chef, direktør eller administrerende direktør kan også oprette mobilopgaveprocesser. 
  
2. Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg **Processer**.  
  
3.  Vælg **Ny** på værktøjslinjen **Handlinger**.  
  
4.  I dialogboksen **Opret proces** skal du udfylde de obligatoriske felter:  
  
    -   Angiv et navn til processen.  
  
    -   På listen **Kategori** skal du vælge **Forretningsprocesforløb**.  
  
    -   Vælg det objekt, du vil bruge, på listen **Objekt**.  
  
5.  Vælg indstillingen **Kør processen som en opgaveprocess (Mobile Online)** .  
  
6.  Vælg **OK**.
  
     Opgaveprocesdesigneren åbnes i et nyt vindue.  
  
     ![Vindue for opgaveprocesdesigner](media/task-flow-designer-window.png "Vindue for opgaveprocesdesigner") 
  
7.  Hvis dine brugere gerne vil gå fra én side til en anden i rækkefølge, skal du trække komponenten **Side** fra fanen **Komponenter** i højre side af skærmen og slippe den på +-tegnet på det rette sted. Hvis du vil føje et navn til en side, skal du vælge siden, vælge fanen **Egenskaber**, skrive et nyt navn og derefter vælge **Anvend**.  
  
8.  Hvis du vil føje en forgrening til opgaveprocessen, skal du trække komponenten **Betingelse** fra fanen **Komponenter** og slippe den på +-tegnet på det rette sted. Du angiver egenskaber for betingelsen ved at vælge betingelsen, angive egenskaberne på fanen **Egenskaber** og derefter vælge **Anvend**.  
  
    > [!NOTE]
    >  Når du føjer sider og betingelser til opgaveprocessen, kan du se et kort i miniformat i nederste venstre hjørne af det vindue, der viser alle siderne og betingelserne i opgaveprocessen.  
  
9. Du føjer et felt, et navn eller en sektionsetiket til en side ved at trække **Felt**, **Etiket** eller **Sektionsetiket** fra fanen **Komponenter** til den relevante side. Du ændrer egenskaberne for et af disse elementer, ved at vælge elementet, angive egenskaberne på fanen **Egenskaber** og derefter vælge **Anvend**.  
  
10. Hvis du vil validere opgaveprocessen, skal du vælge **Valider** på handlingslinjen.  
  
11. Hvis du vil gemme processen som et udkast, skal du vælge **Gem** øverst på skærmen. (Så længe en proces er et udkast, kan andre ikke bruge den).  
  
12. Hvis du vil aktivere opgaveprocessen, så folk kan bruge den, skal du vælge **Aktivér**.  
  
> [!TIP]
>  Her er nogle tip, du kan bruge, når du arbejder med dit opgaveforløb i designervinduet:  
>   
> -  Hvis du vil tage et øjebliksbillede af alt i vinduet med opgaveprocessen, skal du vælge **Øjebliksbillede** på handlingslinjen.  
> -  Du opretter forbindelse mellem en gyldig komponent og en anden gyldig komponent i designeren ved at vælge **Connector** på handlingslinjen.  
> -  Du kan gøre billederne på skærmen større eller mindre ved at vælge knapperne til at **forøge zoomniveauet** eller **formindske zoomniveauet** i det øverste højre hjørne af skærmen. Vælg knappen **Tilpas til lærredet** for at forstørre billederne op til den største størrelse, der passer til skærmen.  
  
## <a name="next-steps"></a>Næste trin  
 [Opret et forretningsprocesforløb](create-business-process-flow.md)   

