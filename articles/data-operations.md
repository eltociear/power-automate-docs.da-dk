---
title: Forstå datahandlinger | Microsoft Docs
description: Få mere at vide om at udføre handlinger, f.eks. oprette en HTML-tabel, oprette en CSV-tabel, skrive en meddelelse, joinforbinde, vælge og filtrere en matrix med Power Automate.
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
ms.date: 09/18/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 040f666b15d3e8845336b3724e07749c9e2e7a7f
ms.sourcegitcommit: bad509705b7d32f8fc20913573547e65e54cee5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/03/2020
ms.locfileid: "3958320"
---
# <a name="use-data-operations-with-power-automate"></a>Brug datahandlinger med Power Automate

I denne gennemgang får du mere at vide om nogle af de almindelige datahandlinger i Power Automate, f.eks. at skrive meddelelse, joinforbinde, vælge, filtrere matrix, oprette tabeller og fortolke JSON, som er tilgængelige for redigering af data, når du opretter flows.

## <a name="prerequisites"></a>Forudsætninger

* Adgang til Power Automate.
* Et værktøj som [PostMan](https://www.getpostman.com/postman) til at sende HTTP POST-anmodninger med en JSON-matrix til dit flow.

## <a name="use-the-compose-action"></a>Bruge handlingen for sammensætning

Brug **Datahandling - Opret** <!--note from editor: Here and throughout, you don't need to repeat the name of the action. The name in the UI isn't confusing, but these parenthetical phrases kind of are. Edits to the rest of this sentence are suggested.-->som handling, så du ikke selv skal angive de samme data flere gange, mens du designer et flow. I dette eksempel skal du angive en matrix af cifre – `[0,1,2,3,4,5,6,7,8,9]` – flere gange, mens du designer flowet. Du kan bruge handlingen Opret til at gemme matrixen, som beskrevet i følgende procedure.

1. Søg efter **Opret**, og vælg derefter handlingen **Datahandling - Opret**.

    ![Søg efter og vælg handlingen Opret](./media/data-operations/search-select-compose-2.png)

2. Angiv matrixen i feltet **Input**, som du vil henvise til senere.

    ![Konfigurer handlingen Opret](./media/data-operations/add-array-compose-2.png)

> [!TIP]
> Du kan gøre det nemmere at finde kortet **Opret** senere ved at omdøbe det ved at vælge teksten **Opret** på kortets titellinje og skrive et navn, der er let at huske.

Når du har brug for at få adgang til indholdet af handlingen Opret, skal du gøre det ved at benytte følgende fremgangsmåde:

1. Tilføj en handling, f.eks. **Datahandling – Joinforbind**.

1. Vælg det kontrolelement, hvor du vil tilføje det indhold, du har gemt i handlingen Opret.

   Skærmen **Tilføj dynamisk indhold fra de apps og forbindelser, der anvendes i dette flow** åbnes.

1. Vælg **Output** i sektionen **Opret** under fanen **Dynamisk indhold**.

    ![Brug output fra handlingen Opret](./media/data-operations/use-compose-output-2.png)

## <a name="use-the-join-action"></a>Bruge handlingen for joinforbindelse

Brug handlingen **Datahandling – Joinforbind** til at afgrænse en matrix med en separator efter eget valg. Dit flow modtager f.eks. en webanmodning, der omfatter følgende matrix med mailadresser: `["d@example.com", "k@example.com", "dal@example.com"]`. Dit mailprogram kræver imidlertid, at adresser skal være formateret i en enkelt streng adskilt med semikolon. Du skal bruge handlingen **Datahandling – Joinforbind** til at ændre kommaafgrænseren (,) til et semikolon (;) ved at følge disse trin:

1. Tilføj en ny handling, søg efter **Joinforbind**, og vælg derefter **Datahandling – Joinforbind**.

    ![Søg efter og vælg handlingen Joinforbind](./media/data-operations/search-select-join-2.png)

2. Angiv matrixen i feltet **Fra**, og brug feltet **Joinforbind med** til at indtaste et semikolon (**;**).

    ![Konfigurer handlingen Joinforbind](./media/data-operations/add-array-join-2.png)

3. Gem dit flow, og kør det derefter

4. Når flowet er kørt, vil resultatet af handlingen **Datahandling – Joinforbind** være en streng med de adresser, der er joinforbundet af semikoloner, som vist i følgende billede.

    ![Input af adresser, der er adskilt af kommaer, en joinforbindelse med værdien semikolon og output af disse adresser adskilt af semikolon](./media/data-operations/join-output-2.png)

## <a name="use-the-select-action"></a>Bruge handlingen for valg

Brug handlingen **Datahandling – Vælg** til at transformere formen af objekter i en matrix. Du kan f.eks. tilføje, fjerne eller omdøbe elementer i hvert objekt i en matrix.

> [!NOTE]
> Mens du kan tilføje eller fjerne elementer med brug af den valgte handling, kan du ikke ændre antallet af objekter i matrixen.

I dette eksempel kommer dataene ind i dit flow via en webanmodning i følgende format:

``` JSON
[ { "first": "Eugenia", "last": "Lopez" }, { "first": "Elizabeth", "last": "Moore" } ]
```

Du vil omforme de indgående data ved at omdøbe `first` til `FirstName` og `last` til `FamilyName` og tilføje et nyt medlem med navnet `FullName`, der kombinerer `first` og `last` (adskilt med mellemrum).

``` JSON
[ { "FirstName": "Eugenia", "FamilyName": "Lopez", "FullName": "Eugenia Lopez" }, { "FirstName": "Elizabeth", "FamilyName": "Moore", "FullName": "Elizabeth Moore" } ]
```

Dette gør du på denne måde:

1. Tilføj udløseren **Når en HTTP-anmodning modtages** i dit flow.

2. Vælg **Brug eksempelnyttedata til at oprette skema**.

   ![Vælg eksempelnyttedata](./media/data-operations/request-trigger.png)

3. I det felt, der vises, skal du indsætte et eksempel på matrixen med dine kildedata og derefter vælge knappen **Udført**.

4. Tilføj handlingen **Datahandling – Vælg**, og konfigurer den som på følgende billede.

   :::image type="complex" source="./media/data-operations/select-card-2.png" alt-text="Konfigurer handlingen Vælg":::
   Skærmbillede, der viser handlingen Vælg. Fra er angivet til Brødtekst. I sektionen Tilknytning angives FirstName til first, FamilyName er angivet til last, og FullName er angivet til first og last, der er adskilt med mellemrum.:::image-end:::

   > [!TIP]
   > Outputtet fra handlingen for valg er en matrix, der indeholder de objekter, der netop er formet. Du kan derefter bruge denne matrix i enhver anden handling, f.eks. Opret, som beskrevet tidligere.

## <a name="use-the-filter-array-action"></a>Bruge handlingen for filtermatrix

Brug handlingen **Datahandling – Filtermatrix** til at reducere antallet af objekter i en matrix til en delmængde, der svarer til de kriterier, som du angiver.

> [!NOTE]
>
> * Du kan ikke bruge filtermatrixhandlingen til at ændre objektets form i matrixen.
> * Der skelnes mellem store og små bogstaver i den tekst, du filtrerer efter.

I dette eksempel skal du bruge filtermatrixhandlingen på denne matrix:

``` JSON
[ { "first": "Eugenia", "last": "Lopez" }, { "first": "Elizabeth", "last": "Moore" } ]
```

til at oprette en ny matrix, der udelukkende indeholder objekter, hvor `first` er angivet til `Eugenia`.

Lad os gøre dette.

1. Find og tilføj derefter **Filtermatrix**-handlingen i flowet.
2. Konfigurer handlingen filtermatrix som på følgende billede.
   
    ![I sektionen Fra er den første linje angivet til Brødtekst. På den anden linje er first indstillet til lig med Eugenia](./media/data-operations/add-configure-filter-array-2.png)
3. Gem og kør derefter dit flow.
   
    Du kan bruge [PostMan](https://www.getpostman.com/postman) til at oprette en webanmodning, der sender en JSON-matrix til dit flow.
4. Når flowet køres, ligner outputtet følgende matrix. Bemærk, at det kun er objekter, hvor `first` er angivet til `Eugenia`, der medtages i resultatet af handlingen.

    ``` JSON
    [ { "first": "Eugenia", "last": "Lopez" }]
    ```

## <a name="use-the-create-csv-table-action"></a>Brug handlingen Opret CSV-tabel

Brug handlingen **Datahandling – Opret CSV-tabel** til at ændre et JSON-matrixinput til en kommasepareret værditabel (CSV). Du kan bevare overskrifterne synlige i CSV-outputtet. I dette eksempel skal du konvertere følgende matrix til en CSV-tabel:

``` JSON
[ { "first": "Eugenia", "last": "Lopez" }, { "first": "Elizabeth", "last": "Moore" } ]
```

1. Find, tilføj og konfigurer derefter handlingen **Datahandling – Opret CSV-tabel**, så den ligner følgende billede.
   
    ![Konfigurer handlingen Opret CSV-tabel. Fra er angivet til Brødtekst, og Kolonner er indstillet til Automatisk](./media/data-operations/create-csv-table-2.png)
   
    Tokenet **Brødtekst** i denne afbildning kommer fra handlingen **Når der modtages en HTTP-anmodning**, men du kan dog få input til handlingen **Opret CSV-tabel** fra outputtet fra en eventuel tidligere handling i dit flow, eller du kan angive det direkte i feltet **Fra**.
2. Gem og kør derefter dit flow.

Når flowet kører, viser handlingen **Opret CSV-tabel** det output, der vises i følgende billede.

![Output fra handlingen Opret CSV-tabel, som viser "first,last" i den første række efterfulgt af "Eugenia,Lopez" og "Elizabeth,Moore"](./media/data-operations/create-csv-table-output-2.png)

## <a name="use-the-create-html-table-action"></a>Brug handlingen Opret HTML-tabel

Brug handlingen **Datahandling – Opret HTML-tabel** til at ændre et JSON-matrixinput til en HTML-tabel. Du kan bevare overskrifterne synlige i HTML-outputtet.

Det kan du gøre ved at følge de trin, der er beskrevet i forrige afsnit, når du skal oprette en CSV-tabel, men du kan bruge handlingen **Datahandling – Opret HTML-tabel** i stedet for **Opret CSV-tabel**.

> [!TIP]
> Hvis du planlægger at sende HTML-tabellen via mail, skal du huske at vælge **IsHtml** i mailhandlingen.
