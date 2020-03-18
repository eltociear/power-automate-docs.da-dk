---
title: Brug udtryk sammen med betingelser. | Microsoft Docs
description: Brug avancerede udtryk, f.eks. "og", "eller", "tom", "mindre" og "større" sammen med Power Automate-betingelser.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c1eb0f208f964f2a41e26ca831c60edef0d747c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195956"
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>Brug udtryk i betingelser til at kontrollere flere værdier

I denne gennemgang får du mere at vide om, hvordan du bruger udtryk og **betingelser** til at sammenligne flere værdier i **avanceret tilstand**.

Når du opretter et flow, kan du bruge kortet [**Betingelse**](add-condition.md#add-a-condition) i grundlæggende tilstand til hurtigt at sammenligne en enkelt værdi med en anden værdi. Der vil dog nogle gange være behov for at sammenligne flere værdier. Det kan f.eks. være, at du vil kontrollere værdien af et par kolonner i et regneark eller en databasetabel.

Du kan bruge en vilkårlig kombination af følgende logiske udtryk i dine betingelser.

Udtryk|Beskrivelse|Eksempel
--------|-----------|-------
|[og](#use-the-and-expression)|Kræver to argumenter og returnerer sand, hvis begge værdier er sande.<br><b>Bemærk!</b> Begge argumenter skal være booleske værdier.|Udtrykket returnerer falsk: <br>og (større end(1,10), lig med(0,0))
|[eller](#use-the-or-expression)|Kræver to argumenter og returnerer sand, hvis et af argumenterne er sande. <br><b>Bemærk!</b> Begge argumenter skal være booleske værdier.|Udtrykket returnerer sand:<br>eller(større end(1,10),lig med(0,0))
|er lig med|Returnerer sand, hvis to værdier er ens.|Hvis parameter1 f.eks. er someValue, returnerer udtrykket sand:<br>lig med(parameters('parameter1'), 'someValue')
|[mindre end](#use-the-less-expression)|Kræver to argumenter og returnerer sand, hvis det første argument er mindre end det andet argument. <br><b>Bemærk!</b> De understøttede typer er heltal, flydende og streng.|Udtrykket returnerer sand:<br>less(10,100)
|lessOrEquals|Kræver to argumenter og returnerer sand, hvis det første argument er mindre end eller lig med det andet argument. <br><b>Bemærk!</b> De understøttede typer er heltal, flydende og streng.|Udtrykket returnerer sand:<br>lessOrEquals(10,10)
|[større](#use-the-greater-expression)|Kræver to argumenter og returnerer sand, hvis det første argument er større end det andet argument. <br><b>Bemærk!</b> De understøttede typer er heltal, flydende og streng.|Udtrykket returnerer falsk:<br>større(10,10)
|greaterOrEquals|Kræver to argumenter og returnerer sand, hvis det første argument er større end eller lig med det andet argument. <br><b>Bemærk!</b> De understøttede typer er heltal, flydende og streng.|Udtrykket returnerer falsk:<br>greaterOrEquals(10,100)
|[tom](#use-the-empty-expression)|Returnerer sand, hvis objektet, matrixen eller strengen er tom.|Udtrykket returnerer sand:<br>tom('')
|ikke|Returnerer det modsatte af en boolesk værdi. |Udtrykket returnerer sand:<br>ikke(indeholder ("200 fuldført", "Mislykkedes"))
|hvis|Returnerer en bestemt værdi, hvis udtrykket resulterer i sand eller falsk.|Udtrykket returnerer "ja":<br>hvis(lig med(1, 1), "ja", "nej")

## <a name="prerequisites"></a>Forudsætninger
* Adgang til Power Automate.
* Et regneark med de tabeller, der er beskrevet senere i denne gennemgang. Sørg for at gemme regnearket på en placering som f.eks. Dropbox eller Microsoft OneDrive, så Power Automate kan få adgang til det.
* Microsoft Office 365 Outlook (når vi bruger Office 365 Outlook, kan du bruge de understøttede mailtjenester i dine flows).

## <a name="use-the-or-expression"></a>Brug udtrykket OR
Nogle gange må arbejdsprocessen udføre en handling, hvis værdien af et element er valueA **eller** valueB. Det kan f.eks. være, at du sporer status for opgaver i en tabel i et regneark. Antag, at tabellen har en kolonne med navnet *Status*, og at de mulige værdier i denne *Status*-kolonne er:

* **fuldført**
* **blokeret**
* **unødvendig**
* **ikke startet**

Her følger et eksempel på, hvordan regnearket kan se ud:

![eksempelregneark](./media/use-expressions-in-conditions/spreadsheet-table.png)

Med det foregående regneark vil du bruge Power Automate til at fjerne alle rækker med en *Status*-kolonne, der er angivet til *fuldført* eller *unødvendig*.

Lad os oprette flowet.

### <a name="start-with-a-blank-flow"></a>Start med et tomt flow
1. Log på [Power Automate](https://flow.microsoft.com).

    ![log på](includes/media/modern-approvals/sign-in.png)
2. Vælg fanen **Mine flow**.

    ![vælg mine flow](includes/media/modern-approvals/select-my-flows.png)
3. Vælg **Opret fra bunden**.

    ![opret fra bunden af](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Føj en udløser til dit flow
1. Søg efter **Tidsplan**, og vælg derefter udløseren **Tidsplan - Gentagelse**

    ![udløseren tidsplan](includes/media/schedule-trigger/schedule-trigger.png)
2. Angiv, at tidsplanen skal køres én gang dagligt.

    ![angiv tidsplan](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Vælg regnearket, og hent alle rækker
1. Vælg **Nyt trin** > **Tilføj en handling**.

    ![nyt trin](includes/media/new-step/action.png)
2. Søg efter **rækker**, og vælg derefter **Excel - Hent rækker**.

    Bemærk! Vælg den handling af typen "hent rækker", som svarer til det regneark, du bruger. Hvis du f.eks. bruger Google Sheets, skal du vælge **Google Sheets – Hent rækker**.

    ![hent rækker](includes/media/new-step/get-excel-rows.png)
3. Vælg mappeikonet i feltet **Filnavn**, og gennemse og vælg derefter det regneark, der indeholder dine data.

    ![vælg regneark](includes/media/new-step/select-spreadsheet.png)
4. Vælg den tabel, der indeholder dine data, på listen **Tabelnavn**.

    ![vælg tabel](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Kontrollér statuskolonnen for hver række
1. Vælg **Nyt trin** > **Mere** > **Tilføj en "anvend på hver"** .

    ![vælg tabel](includes/media/new-step/apply-to-each.png)
2. Føj tokenet **Værdi** til feltet **Vælg et output fra de tidligere trin**.

    ![vælg tabel](includes/media/apply-to-each/add-value-token.png)
3. Vælg **Tilføj en betingelse** > **Rediger i avanceret tilstand**.
4. Tilføj følgende **OR**-udtryk. Dette **OR**-udtryk kontrollerer værdien af hver række i tabellen (en række kaldes et element, når den åbnes i et udtryk). Hvis værdien af kolonnen **Status** er *fuldført* **eller** *unødvendig*, evalueres udtrykket **OR** til "sand".

    Udtrykket **OR** vises som angivet her:

    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````

    Kortet **Betingelse** ligner denne afbildning:

    ![afbildning af udtrykket OR](./media/use-expressions-in-conditions/or-expression.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Slet matchende rækker fra regnearket
1. Vælg **Tilføj en handling** på grenen **HVIS JA, GØR INTET** på betingelsen.
2. Søg efter **Slet række**, og vælg derefter **Excel – Slet række**.

    ![Slet rækkeafbildning](includes/media/new-step/select-delete-excel-row.png)
3. I feltet **Filnavn** skal du søge efter og vælge den regnearksfil, som indeholder de data, du vil slette.
4. Vælg den tabel, der indeholder dine data, på listen **Tabelnavn**.
5. Placer tokenet **Række-id** i feltet **Række-id**.

    ![regnearksfil](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Navngiv flowet, og gem det
1. Navngiv dit flow, og vælg derefter knappen **Opret flow**.

    ![gem dit flow](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>Kør flowet med udtrykket OR
Flowet køres, når du har gemt det. Hvis du har oprettet det regneark, der blev vist tidligere i denne gennemgang, vil det se sådan ud, når kørslen er fuldført:

![Udtrykket OR fuldføres](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

Bemærk, at alle data fra de rækker, der havde "fuldført" eller "unødvendig" i kolonnen Status, er slettet.

## <a name="use-the-and-expression"></a>Brug udtrykket AND
Antag, at du har en regnearkstabel med to kolonner. Kolonnenavnene er Status og Tildelt. Antag desuden, at du vil slette alle rækker, hvis værdien i kolonnen Status er "blokeret", og værdien i kolonnen Tildelt er "John Wonder".  For at udføre denne opgave skal du følge alle tidligere trin i denne gennemgang, når du redigerer kortet **Betingelse** i avanceret tilstand og bruge det **AND**-udtryk, der er vist her:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

Kortet **Betingelse** ligner denne afbildning:

![afbildning af udtrykket AND](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>Kør flowet med udtrykket AND
Hvis du har fulgt gennemgangen, ligner dit regneark denne afbildning:

![før og køres](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

Når dit flow er kørt, ligner dit regneark denne afbildning:

![efter kørsler af og](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>Brug udtrykket EMPTY
Bemærk, at der nu er adskillige tomme rækker i regnearket. Hvis du vil fjerne dem, skal du bruge udtrykket **EMPTY** til at identificere alle de rækker, der ikke har nogen tekst i kolonnerne Tildelt og Status.

For at udføre denne opgave skal du følge alle trin i afsnittet **Brug udtrykket AND** tidligere i denne gennemgang, men når du redigerer kortet **Betingelse** i avanceret tilstand, skal du bruge udtrykket EMPTY på følgende måde:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

Kortet **Betingelse** ligner denne afbildning:

![afbildning af udtrykket EMPTY](./media/use-expressions-in-conditions/empty-expression.png)

Når dit flow er kørt, ligner regnearket denne afbildning:

![efter kørsler af tom](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

Bemærk, at ekstra linjer er fjernet fra tabellen.

## <a name="use-the-greater-expression"></a>Brug udtrykket GREATER
Forestil sig, at du har købt billetter til en sportsbegivenhed for dine kollegaer, og at du bruger et regneark til at sikre, at du bliver refunderet af hver enkelt person. Du kan hurtigt oprette et flow, der sender en daglig mail til hver person, som ikke har betalt hele beløbet.

Brug udtrykket **GREATER** til at identificere de medarbejdere, som ikke har betalt hele beløbet. Du kan derefter automatisk sende en venlig påmindelse via mail til dem, der ikke har betalt hele beløbet.

Her er et overblik over regnearket:

![visning af regneark](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

Her er implementeringen af udtrykket **GREATER**, der identificerer alle de personer, som har betalt mindre end det beløb, de skylder:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>Brug udtrykket LESS
Forestil sig, at du har købt billetter til en sportsbegivenhed for dine kollegaer, og at du bruger et regneark til at sikre, at du bliver refunderet af hver enkelt person inden en aftalt dato. Du kan oprette et flow, der sender en mail med en påmindelse til hver person, som ikke har betalt det fulde beløb, hvis dags dato er mindre end én dag fra forfaldsdatoen.

Brug udtrykket **AND** sammen med udtrykket **LESS**, da der er to betingelser, der valideres:


|          Betingelse, der skal valideres          | udtryk, der skal bruges |                    Eksempel                     |
|-----------------------------------------|-------------------|------------------------------------------------|
|   Er hele det skyldige beløb blevet betalt?    |      større      |   @greater(element()?["Forfalden"], element()?["Betalt"])    |
| Er der mindre end én dag til forfaldsdatoen? |       mindre        | @less(element()?["DueDate"], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>Kombiner udtrykkene GREATER og LESS i et AND-udtryk
Brug udtrykket **GREATER** til at identificere de medarbejdere, der har betalt mindre end det fulde beløb, og brug udtrykket **LESS** til at afgøre, om forfaldsdatoen for betalingen er mindre end én dag fra dags dato. Derefter kan du bruge handlingen **Send en mail** til at sende en mail med en venlig påmindelse til dem, der ikke har betalt det fulde beløb, når der er mindre end én dag til forfaldsdatoen.

Her er en visning af regnearkstabellen:

![visning af regneark](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

Her er implementering af udtrykket **AND**, der identificerer alle de personer, som har betalt mindre end det beløb, de skylder, og hvor forfaldsdatoen er mindre end én dag fra dags dato:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="use-functions-in-expressions"></a>Brug funktioner i udtryk

Nogle udtryk henter deres værdier fra runtime-handlinger, som muligvis ikke findes endnu, når et flow begynder at køre. Hvis du vil henvise til eller arbejde med disse værdier i udtryk, kan du bruge de funktioner, som Workflow Definition Language indeholder. Flere oplysninger: [Henvisning til funktioner for Workflow Definition Language i Power Automate](https://docs.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference)
