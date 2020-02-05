---
title: Tilføj en avanceret indstilling og flere handlinger | Microsoft Docs
description: Udvid et flow for at inkludere en avanceret indstilling, f.eks. at angive en mail til høj prioritet og tilføje en anden handling for den samme hændelse.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fbc18e31b571149164b7316bdaa02d2840686995
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74376327"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Føj flere handlinger og avancerede indstillinger til et flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Tilpas et flow ved at tilføje en eller flere avancerede indstillinger og flere handlinger for den samme udløser. Tilføj f.eks. en avanceret indstilling, der sender en mail med høj prioritet. Udover at sende en mail, hvor et element er føjet ti len SharePoint-liste, kan du oprette en fil i Dropbox, der indeholder de samme oplysninger.

## <a name="prerequisites"></a>Forudsætninger
* [Opret et flow](get-started-logic-flow.md)

## <a name="add-another-action"></a>Tilføj en anden handling
I denne procedure skal du tilføje en handling midt i flowet. Denne handling gemmer en fil i din Dropbox og arkiverer elementet på listen.

1. På [flow.microsoft.com](https://flow.microsoft.com) skal du vælge **Mine flows** på den øverste navigationslinje.
2. Vælg det flow, du vil redigere, på listen over flows.
3. Vælg **Nyt trin**, og vælg derefter **Tilføj en handling**.
   
    ![Skjult tilføjelse](./media/multi-step-logic-flow/add-action.png)
4. På listen over mulige handlinger skal du søge efter **Opret fil** og derefter vælge **Dropbox – Opret fil**.
   
    ![søg opret fil](./media/multi-step-logic-flow/create-file-search.png)
5. Hvis du bliver bedt om det, skal du angive dine legitimationsoplysninger til Dropbox.
6. Vælg mappeikonet på højre side af feltet **Mappesti**.
7. Find og vælg derefter den mappe, hvor du vil placere den nye fil.
   
    ![søg opret fil](./media/multi-step-logic-flow/create-file-folder.png)
8. Angiv navnet på den nye fil i feltet **Filnavn**. Sørg for at tilføje et filtypenavn, f.eks. ".txt" til filnavnet. Her bruger vi **TweetId'et** i filnavnet for at sikre, at filerne er entydige. Du skal muligvis vælge **Se mere** for at finde tokenet **TweetId**.
9. Tilføj den tekst, du ønsker, at filen skal indeholde, ved at skrive i feltet **Filindhold**. Du kan også tilføje tokens i feltet **Filindhold**.
   
    ![filnavn og indhold](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Hvis du giver filen et navn, der svarer til navnet på en eksisterende fil (i den markerede mappe), overskrives den eksisterende fil.
   > 
   > 
10. Vælg **Opdater flow**, som findes i menuen øverst i skærmbilledet.
11. Send en tweet, der indeholder det angivne nøgleord.
    
     Inden for et minut oprettes en fil under din Dropbox-konto.

## <a name="reorder-or-delete-an-action"></a>Skift rækkefølgen, eller slet en handling
* Hvis du vil modtage en mail, når filen er oprettet i Dropbox, skal du flytte Dropbox-handlingen ved at trække titellinjen over mailhandlingen. Slip Dropbox-handlingen over pilen mellem udløseren (**Når der slås et nyt tweet op**) og mailhandlingen. (Markøren angiver, om handlingen er placeret korrekt).
  
  > [!NOTE]
  > Du kan ikke flytte et trin før et andet, hvis du bruger output fra det pågældende trin.
  > 
  > 
  
    ![Slet menuen](./media/multi-step-logic-flow/draggingaction.png)
* Hvis du vil slette en handling, skal du vælge ellipsen (...) i nærheden af kanten til højre på titellinjen for den handling, du vil slette. Derefter skal du vælge **Slet** og derefter vælge **OK**.
  
    ![Slet menuen](./media/multi-step-logic-flow/deletemenu.png)
  
     **Bemærk!** Du kan ikke slette en handling, hvis du bruger output fra den et eller andet sted i flowet. Du skal først fjerne disse output fra felterne, før du kan slette handlingen.


## <a name="copy-and-paste-actions"></a>Kopiér og indsæt handlinger

Hvis du vil kopiere handlinger, mens du designer et flow, kan du kopiere og indsætte dem. Hvis du f.eks. opretter en betingelse og ønsker tilsvarende handlinger på **If yes**-siden og **If no**-siden, kan du oprette den første handling på den ene side og derefter kopiere den til den anden side i stedet for at oprette begge handlinger fra bunden.


### <a name="to-copy-an-action"></a>Sådan kopierer du en handling
1. Vælg handlingsmenuen (... øverst til højre for handlingen).
1. Vælg **Kopiér til min udklipsholder**. 
1. Vælg **Nyt trin**, hvor handlingen skal indsættes. 

     Bemærk, at du under fanen **Min udklipsholder** kan vælge blandt alle de handlinger, du har kopieret.
1. Vælg det element, du vil indsætte.

## <a name="add-advanced-options"></a>Tilføj avancerede indstillinger
Start med et flow, der har handlingen **Send en mail**.

1. Vælg **Vis avancerede indstillinger**, som er placeret i bunden af kortet **Send en mail**.
   
     Derefter kan du se de avancerede indstillinger til at sende en mail.
   
    ![SharePoint-udløsere](./media/multi-step-logic-flow/advanced.png)
2. Vælg **Høj** på listen **Vigtighed**, og vælg derefter **Skjul avancerede indstillinger** for at skjule de avancerede indstillinger.
3. Vælg **Opdater flow**, som findes i menuen øverst i skærmbilledet.
   
     Dette trin gemmer dine ændringer.

