---
title: Forstå datahandlinger | Microsoft Docs
description: Få mere at vide om at udføre handlinger, f.eks. oprette en HTML-tabel, oprette en CSV-tabel, skrive, forbinde, vælge og filtrere matrix med Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d40b59ea6f4e185ee1ccab8c973012e00f9e6f62
ms.sourcegitcommit: 9cd1eee32594e9b68c920c13e80515c3dcb55c1d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/21/2020
ms.locfileid: "3609836"
---
# <a name="use-data-operations-with-power-automate"></a>Brug datahandlinger med Power Automate

I denne gennemgang får du mere at vide om nogle af de populære datahandlinger i Power Automate, f.eks. at skrive, forbinde, vælge, filtrere matrix, oprette tabel og fortolke JSON-tekst, som er tilgængelig, for at håndtere data, når du opretter flows.

## <a name="prerequisites"></a>Forudsætninger
* Adgang til Power Automate.
* Et værktøj som [PostMan](https://www.getpostman.com/postman) til at sende HTTP POST-anmodninger med en JSON-matrix til dit flow.

## <a name="use-the-compose-action"></a>Bruge handlingen for sammensætning
Brug handlingen **Datahandlinger – Sammensæt** (compose), så du undgår at skulle angive identiske data flere gange, når du designer et flow. Hvis du f.eks. skal angive en matrix af cifre: ````[0,1,2,3,4,5,6,7,8,9]```` flere gange, mens du designer flowet, kan du bruge handlingen for sammensætning til at gemme matrixen på følgende måde:

1. Søg efter **Sammensæt**, og vælg derefter handlingen **Datahandling – Sammenæt** (compose).
   
    ![søge efter og vælge handlingen for sammensætning](./media/data-operations/search-select-compose-2.png)
2. Angiv matrixen i feltet **Input**, som du vil henvise til senere:
   
    ![konfigurere handlingen for sammensætning](./media/data-operations/add-array-compose-2.png)

> [!TIP]
> For nemmere at kunne henvise til kortet senere, skal du omdøbe kortet **Sammensæt** ved at klikke på teksten "Sammensæt" på titellinjen i kortet **Sammensæt**.
> 
> 

Når du har brug for at få adgang til indholdet af sammensætningshandlingen, kan du gøre det via tokenet **Output** på listen **Tilføj dynamisk indhold fra de apps og connectorer, der anvendes i dette flow** ved at følge denne fremgangsmåde:

1. Tilføj en handling, f.eks. **Datahandling – Forbind**.
2. Vælg det kontrolelement, hvor du vil tilføje det indhold, du har gemt i handlingen for sammensætning.
   
    **Tilføj dynamisk indhold fra de apps og forbindelser, der anvendes i dette flow** åbnes.
3. I **Tilføj dynamisk indhold fra de apps og forbindelser, der anvendes i dette flow** skal du vælge **Output**-tokenet, som findes under kategorien **Sammensæt** under fanen **Dynamisk indhold**.
   
    ![bruge output fra handlingen for sammensætning](./media/data-operations/use-compose-output-2.png)

## <a name="use-the-join-action"></a>Bruge handlingen for joinforbindelse
Brug handlingen **Datahandling – Joinforbind** (join) til at afgrænse en matrix med en separator efter eget valg. Antag, at dit flow f.eks. modtager en webanmodning, der omfatter følgende matrix med mailadresser: ````["d@example.com", "k@example.com", "dal@example.com"]````. Dit mailprogram kræver imidlertid, at adresser skal være en enkelt streng adskilt med semikolon. Hvis du vil gøre dette, skal du bruge handlingen **Datahandling – Joinforbind** (join) for at ændre kommaseparatoren til semikolon ";" ved at følge denne fremgangsmåde:

1. Tilføj en ny handling, søg efter **Joinforbind**, og vælg derefter **Datahandling – Joinforbind** (join).
   
    ![søge efter og vælge handlingen for joinforbindelse](./media/data-operations/search-select-join-2.png)
2. Angiv matrixen i feltet **Fra**, og angiv derefter den nye separator, du vil bruge, i feltet **Joinforbind med**.
   
    Her har jeg brugt semikolon (;) som den nye separator.
   
    ![konfigurere handlingen for joinforbindelse](./media/data-operations/add-array-join-2.png)
3. Gem dit flow, og kør det derefter.
4. Når dit flow er kørt, vil outputtet af handlingen **Datahandling – Joinforbind** være:
   
    ![joinforbinde output](./media/data-operations/join-output-2.png)

## <a name="use-the-select-action"></a>Bruge handlingen for valg
Brug **Datahandling – Vælg** (select) til at transformere formen på objekter i en matrix. Du kan f.eks. tilføje, fjerne eller omdøbe elementer i hvert objekt i en matrix.

> [!NOTE]
> Mens du kan tilføje eller fjerne elementer med den valgte handling, kan du ikke ændre antallet af objekter i matrixen.
> 
> 

Du kan f.eks. bruge den valgte handling, hvis data overføres til dit flow via en webanmodning i dette format:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

og du vil omforme de indgående data ved at omdøbe "first" til "FirstName", "last" til "LastName" og tilføje et nyt medlem med navnet og tilføje et nyt medlem kaldet "FamilyName", der kombinerer "first" og "last" (adskilt med et mellemrum):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Dette gør du på denne måde:

1. Tilføj udløseren **Når en HTTP-anmodning er modtaget** (request) til dit flow.
2. Vælg **Anvend eksempel på nyttedata til at generere skema** fra kortet **Anmodning**.
![vælge eksempel på nyttedata](./media/data-operations/request-trigger.png)
3. I det felt, der vises, skal du indsætte et eksempel på matrixen for dine kildedata og derefter vælge knappen **Udført**.
![eksempel på indsætning](./media/data-operations/paste-sample.png)
4. Tilføj handlingen **Datahandling – Vælg** (select), og konfigurer det derefter som i følgende billede.
   
    ![konfigurere handlingen for valg](./media/data-operations/select-card-2.png)
   
   > [!TIP]
   > Outputtet fra handlingen for valg er en matrix, der indeholder de objekter, der netop er formet. Du kan derefter bruge denne matrix i en enhver anden handling, f.eks. **Sammensæt** som beskrevet tidligere.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Bruge handlingen for filtermatrix
Brug **Datahandling – Filtermatrix** (filter array) til at reducere antallet af objekter i en matrix til en delmængde, der svarer til de kriterier, som du angiver.

> [!NOTE]
> Filtermatrixen kan ikke bruges til at ændre formen på objekterne i en matrix. Desuden skelnes der også mellem store og små bogstaver i den tekst, du filtrerer efter.
> 
> 

Du kan f.eks. bruge filtermatrixen til denne matrix:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

til at oprette en ny matrix, der udelukkende indeholder objekter, hvor *first* er angivet til "Deon".

Lad os gøre dette.

1. Find og tilføj derefter handlingen **Filtermatrix** (filter array) til dit flow.
2. Konfigurer handlingen for filtermatrix som i følgende billede.
   
    ![konfigurere handlingen for filtermatrix](./media/data-operations/add-configure-filter-array-2.png)
3. Gem og kør derefter dit flow.
   
    Du kan bruge [PostMan](https://www.getpostman.com/postman) til at oprette en webanmodning, der sender en JSON-matrix til dit flow.
4. Når dit flow køres, og det antages, at JSON-inputtet ser ud som denne matrix:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    outputtet ser ud som denne matrix (bemærk, at kun objekter, hvor *first* er angivet til "Deon", er medtaget i outputtet fra denne handling):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Bruge handlingen til oprettelse af csv-tabel
Brug **Datahandling – Opret CSV-tabel** (create csv table) til at ændre et JSON-matrixinput til en kommasepareret værditabel (CSV). Du kan også vælge at bevare overskrifterne synlige i CSV-outputtet. Du kan f.eks. konvertere følgende matrix til en CSV-tabel ved hjælp af handlingen **Opret CSV-tabel**:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Find, tilføj og konfigurer derefter handlingen **Datahandling – Opret CSV-tabel**, så den ligner følgende billede.
   
    ![konfigurere handlingen for oprettelse af csv-tabel](./media/data-operations/create-csv-table-2.png)
   
    Bemærk! Tokenet **Brødtekst** i dette billede stammer fra en handling af typen **når en HTTP-anmodning er modtaget**, men du kan dog få input til handlingen **Opret CSV-tabel** fra outputtet fra en tidligere handling i flowet, eller du kan angive det direkte i feltet **Fra**.
2. Gem og kør derefter dit flow.
   
    Når dit flow kører, ser output fra **Opret CSV-tabel** ud som dette billede:
   
    ![output fra oprettelse af csv-tabel](./media/data-operations/create-csv-table-output-2.png)

## <a name="use-the-create-html-table-action"></a>Bruge handlingen for oprettelse af html-tabel
Brug **Datahandling – Opret HTML-tabel** til at ændre et JSON-matrixinput til en HTML-tabel. Du kan også vælge at bevare overskrifterne synlige i HTML-outputtet.

Det gør du ved at følge denne fremgangsmåde i [afsnittet for oprettelse af en csv-tabel](#use-the-create-csv-table-action) for et detaljeret eksempel. Sørg for at bruge handlingen **Datahandling – Opret HTML-tabel** og ikke handlingen **Datahandling – Opret CSV-tabel**.

> [!TIP]
> Hvis du planlægger at sende HTML-tabellen via mail, skal du huske at vælge "IsHtml" i mailhandlingen.
> 
> 

