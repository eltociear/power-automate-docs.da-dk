---
title: Få mere at vide om redigering af flow for brugergrænsefladen på skrivebordet | Microsoft Docs
description: Få mere at vide om redigering af flow for brugergrænsefladen på skrivebordet.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/31/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3fc36a47a64aa6d8825d55bf79adc3dcaab8aa9e
ms.sourcegitcommit: e1cd564043ecd234050e4cd5c5b8e6ed627d8b78
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/12/2020
ms.locfileid: "3688475"
---
# <a name="edit-desktop-ui-flows"></a>Redigere flow for brugergrænsefladen på skrivebordet

Windows-skrivebordsprogrammer automatiseres i flow for brugergrænsefladen på skrivebordet. Se [Kendte problemer](create-desktop.md#known-issues-and-solutions) for at få mere at vide om de problemer, der kan opstå, løsninger på disse problemer og scenarier, der ikke understøttes i denne udgivelse.

## <a name="prerequisites"></a>Forudsætninger
Et flow for brugergrænsefladen på skrivebordet. [Opret et flow for brugergrænsefladen på skrivebordet nu](create-desktop.md#create-and-test-desktop-ui-flows), hvis du ikke har et, der skal redigeres.

## <a name="edit-actions"></a>Redigere handlinger

![Redigere handlinger](../media/edit-desktop/edit-actions.png "Redigere handlinger")

Du kan redigere din optagelse for at gøre følgende:

-   Redigere værdien for handlinger, der understøtter den.
-   Slette et trin.
-   Slette optagelsen.
-   Ændre rækkefølgen af handlinger ved hjælp af træk og slip. Vær forsigtig med dette, da det kan ødelægge sammenhængen af optagelsen.

Avancerede parametre giver dig mulighed for at ændre følgende:

-  Forsinkelsen, efter handlingen blev udført. Du kan f.eks. tilføje en forsinkelse på ét sekund ved at ændre PT0S til PT1S. Dette kan være nyttigt, når destinationsprogrammet har en langsom svartid, der ikke fuldføres før næste trin i dit flow for brugergrænsefladen. Du kan også [tilføje forsinkede handlinger](edit-desktop.md#add-a-delay) direkte, så de f.eks. kan bruges i løkker.
-   [Vælgeren](edit-desktop.md#set-the-selector) for elementet i brugergrænsefladen for målbrugeren.


## <a name="add-a-recording"></a>Tilføje en optagelse

Det kan være en god idé at optage dit flow for brugergrænsefladen i flere sessioner. Når du har fuldført din første optagelse, kan du fortsætte på følgende måde:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** > **Flow for brugergrænseflade**.
1. Vælg det flow for brugergrænsefladen, du vil redigere.

   ![Billede, der viser det flow for brugergrænseflade, der skal redigeres](../media/edit-desktop/select-ui-flow.png)

1. Vælg **Rediger**. 
1. Vælg **Nyt trin**.

   ![Nyt trin](../media/edit-desktop/new-step.png "Nyt trin")

1. Vælg **Optagerapp** på listen over handlinger.

   ![Optagerapp](../media/edit-desktop/select-record-ui-actions.png "Optagerapp")

1. Vælg **Start optager**.

   ![Vælg Start optager](../media/create-windows-ui-flow/select-launch-recorder.png "Vælg Start optager")

   Optagerkontrolelementet vises øverst på skærmen.

   ![Optagerkontrolelementet](../media/create-windows-ui-flow/recorder-control.png "Optagerkontrolelementet")

1. Start den app, du vil optage.

     >[!TIP]
     >Når du holder musen over kontrolelementer i appen, kan du se en blå kontur rundt om hvert enkelt kontrolelement. Vent altid på den blå kontur, før du vælger et kontrolelement.
     >
     >Hvis elementet ikke er fremhævet med blåt, optages det muligvis ikke korrekt.

1. Vælg **Optag** i optagerkontrolelementet.

1. Udfør trinnene i brugergrænsefladen for den app, du er ved at optage, og vælg derefter **Udført** i optagerkontrolelementet.
1. Vælg **Gem**, og test derefter dit flow for brugergrænseflade.

## <a name="provide-command-line-arguments-at-launch"></a>Angiv kommandolinjeargumenter ved start

Når du har optaget dine handlinger for flow for brugergrænseflade, kan du angive kommandolinjeargumenter for de apps, som dit flow for brugergrænseflade starter. 

Følg disse trin for at føje kommandolinjeargumenter til de apps, som dit flow for brugergrænseflade starter:

1.  Optag et flow for brugergrænseflade med en skrivebordsoptager. 
1.  Vælg **Udført** på optageren, og vælg handlingen for programstart for at udvide den.
   
    Skærmbilledet bruger Notepad++ som et eksempel. 

    ![Viser trinnet for programstart](../media/edit-desktop/cmd-line-app-launch-step.png "Viser trinnet for programstart")


1. Vælg **Vis avancerede indstillinger**.

   ![Vælg dette link for at få vist de avancerede indstillinger](../media/edit-desktop/cmd-args-advanced.png "Vælg dette link for at få vist de avancerede indstillinger")

1. Angiv kommandolinjeargumenterne her:

   ![Viser tekstfeltet for kommandolinjeargumenterne](../media/edit-desktop/cmd-args.png "Viser tekstfeltet for kommandolinjeargumenterne")

1.  Du kan angive et hvilket som helst gyldigt kommandolinjeargument for dit program.

   >[!Important]
   >Send ikke følsom tekst såsom adgangskoder via kommandolinjeargumenter.


## <a name="add-a-variable"></a>Tilføje en variabel

Du kan bruge variabler til at udføre flere handlinger i dine flows for brugergrænsefladen. Du kan f.eks. bruge en variabel til at tælle, hvor mange gange en handling blev udført i en løkke. Du kan også bruge en variabel til at oprette en strengmatrix, hvor skærmaflæsningerne udføres i en løkke.

>[!TIP]
>Du kan bruge variabeldatatyperne heltal, flydende, boolesk, streng, matrix og objekt. 

Når du har oprettet en variabel, kan du f.eks. udføre andre opgaver:

- Du kan øge eller mindske variablen med en konstant værdi, der også kaldes forøgelse og formindskelse.
- Indsæt eller tilføj variabelværdien som det sidste element i en streng eller matrix.
- Tildel en anden værdi til en variabel.

Benyt følgende fremgangsmåde for at oprette og bruge variabler i et flow for brugergrænsefladen:

1. Gå til starten af flowet for brugergrænsefladen, og vælg **Tilføj en handling**.

   ![Vælge Tilføj en handling](../media/edit-desktop/add-variable-add-action.png "Vælge Tilføj en handling")

1. Søg efter ordet *variabel*, og vælg derefter handlingen **Initialiser variabel** under den indbyggede kategori.

   ![Vælge handlingen for initialisering af variabel](../media/edit-desktop/add-variable-initialize-variable.png "Vælge handlingen for initialisering af variabel")

1. Initialiser den variabel, der opfylder dine behov.

   ![Initialisere den variabel, der opfylder dine behov](../media/edit-desktop/add-variable-initialize-value.png "Initialisere den variabel, der opfylder dine behov")

>[!TIP]
>Hvis dit scenarie for automatisering af brugergrænsefladen indebærer, at du læser værdier fra en skærm i en løkke. Det er muligt ved at initialisere variablen som en matrixtype. 
>
>Derefter skal du vælge variabelhandlingen **Tilføj til matrix** og derefter bruge outputtet fra handlingen **Hent tekst** fra listen med dynamisk indhold.

   ![Du kan føje til en matrix i en løkke](../media/edit-desktop/add-variable-add-loop.png "Du kan føje til en matrix i en løkke")

## <a name="copy-and-paste-steps"></a>Trin til at kopiere og indsætte

Du kan kopiere handlinger og områder ved at bruge **Tilføj en handling** for at vælge de kopierede handlinger og områder fra **Min udklipsholder** og derefter sætte dem ind på en anden placering i det samme flow for brugergrænseflade.  

Flow for brugergrænseflade omdøber automatisk de kopierede handlinger og områder med et entydigt navn. Hvis det kopierede område indeholder et andet område, bevares den indlejrede struktur, når du indsætter det fra **Min udklipsholder**. 

>[!IMPORTANT]
>Denne funktion understøtter kopiering og tilføjelse af handlinger inden for det samme område. Det er ikke muligt at indsætte handlinger i andre områder eller flow for brugergrænseflade.

Følg disse trin for at kopiere og derefter indsætte handlinger og områder:

1. Vælg **...**, og vælg derefter **Kopiér til min udklipsholder** for den handling eller det område, du vil kopiere.

   ![Visning af udklipsholder for kopiering](../media/edit-desktop/copy-action.png "Visning af udklipsholder for kopiering")

1. Hold musen over destinationsplaceringen, og vælg derefter **Tilføj en handling**. 

   >[!TIP]
   >Du kan vælge **Tilføj en handling** direkte, hvis den ligger sidst i området eller flowet for brugergrænseflade.
      
   ![Tilføj en handling er valgt](../media/edit-desktop/add-copied-action.png "Tilføj en handling er valgt.").

1.  Vælg **Min udklipsholder**, og vælg derefter den handling eller det område, du kopierede.

    ![Vælg den kopierede handling](../media/edit-desktop/select-action.png "Vælge den kopierede handling")

1. Bemærk, at flow for brugergrænseflade indsætter handlingskortet med et entydigt navn.

   ![Få vist det nye navn på den kopierede handling](../media/edit-desktop/action-unique-name.png "Få vist det nye navn på den kopierede handling")

1. Bemærk også, at handlinger med skærmbilleder også bevarer dem med henblik på hurtig reference. 

   ![Få vist bevarede skærmbilleder](../media/edit-desktop/copied-screenshots.png "Få vist bevarede skærmbilleder")

   ![Flere bevarede skærmbilleder](../media/edit-desktop/retained-screen-shorts.png "Få vist bevarede skærmbilleder")


## <a name="paste-a-scope-immediately-after-itself"></a>Indsætte et område umiddelbart efter sig

>[!NOTE]
>Hvis et område ikke har en **Luk program**-handling, og brugeren kopierer området og derefter indsætter området umiddelbart efter det eksisterende område, udføres de indsatte handlinger kun i den første programforekomst. 

   ![Indsætte et område](../media/edit-desktop/paste-scope-after-itself.png "Indsætte et område")


I dette eksempel udføres de fremhævede handlinger **Venstreklik 11** og **Gentag tastetryk** i det første Notesblok-program, og der startes en anden Notesblok-forekomst. 

Brugerne kan vælge mellem to muligheder for at løse problemet med denne forekomst:

1. Hvis du kun vil udføre handlingen/handlingerne i den første programforekomst, kan du kopiere og indsætte udelukkende de relevante handlinger i det første område. Hvis du vil kopiere og indsætte hele området på én gang, skal du fjerne Start-handlingen i det indsatte område for at forhindre, at der startes en overflødig programforekomst.

   ![Kun relevante handlinger](../media/edit-desktop/copy-paste-relevant-actions-only.png "Kun relevante handlinger")

1. Hvis du vil udføre handlingen/handlingerne i en separat programforekomst, kan du tilføje en **Luk program**-handling i det første område, så det andet område får sin egen forekomst. 

   ![Separat programforekomst](../media/edit-desktop/paste-scope-different-application.png "Separat programforekomst")


## <a name="add-a-loop"></a>Tilføj en løkke

Flow for brugergrænseflade understøttes af matrix. Brug en matrix til at tilføje en løkke for at udføre gentagne trin i et flow for brugergrænseflade. Du kan overføre forskellige typer matrixer fra et flow til din flow for brugergrænseflade, herunder komplekse matrixer på en SharePoint-liste f. eks.

>[!NOTE]
>Du skal redigere et eksisterende flow for brugergrænseflade for at tilføje en løkke.

Her er trinene til at oprette en løkke i et flow for brugergrænseflade:

1. Rediger det flow for brugergrænseflade, du vil føje løkken til.

   ![Vælg knappen Rediger for flow for brugergrænseflade](../media/edit-desktop/edit-ui-flow-loop.png "Vælg knappen Rediger for flow for brugergrænseflade")

1. Gå til input-afsnittet i guiden, og vælg **Konfigurer input**.

   ![Vælg Konfigurer input](../media/edit-desktop/loops-input-section.png "Vælg Konfigurer input")
   

1. Vælg **Matrix** for at angive, at du vil oprette en matrix-inputtype.

   ![Vælg matrix](../media/edit-desktop/loop-select-array-type.png "Vælg matrix")

1. Angiv detaljerne for matrixen, herunder et navn, en matrix i JSON-format, og en beskrivelse af matrixen.

   ![Detaljer for matrix](../media/edit-desktop/loop-array-data.png "Detaljer for matrix")

   >[!TIP]
   >Hvis du bruger en kompleks matrix på en SharePoint-liste, behøver du ikke at oprette matrixen manuelt. Du kan kopiere matrixen fra et flow og indsætte den i det midterste felt.

1. Vælg **Næste**.

1. Vælg **Tilføj en handling**.

1. Søg efter "til hver enkelt" > **Indbygget** > og vælg derefter **Anvend for hver enkelt**.

   ![Vælg handlingen anvend for hver enkelt](../media/edit-desktop/loop-apply-to-each.png "Vælg handlingen anvend for hver enkelt")

1. Angiv **Vælg et output fra forrige trin**, vælg den matrix, du definerede tidligere fra det dynamiske indhold.

   ![Tilføj matrixen fra det dynamisk indhold](../media/edit-desktop/loop-add-array-step.png "Tilføj matrixen fra det dynamisk indhold")

1. Træk de handlinger, du vil gentage, og slip dem på kortet **Anvend for hver enkelt**.

   Jeg har f. eks. lagt **LeftClick 4** på **Anvend på hver enkelt**-kort i følgende billede.

   ![Træk det trin, du vil gentage, til matrixen fra dynamisk indhold](../media/edit-desktop/loop-drag-apply-to-each.png "Træk det trin, du vil gentage, til matrixen fra dynamisk indhold")

1. Erstat de input-tokens, der er oprettet under optagelsen, med de matrix-inputværdier, der er behov for. 

>[!TIP]
>Hvis matrixen er en simpel streng eller en matrix af typen heltal, kan du bruge det **aktuelle element** direkte fra det dynamiske indhold, f. eks. følgende billede. Du kan også bruge udtryk.

![Brug aktuelt element](../media/edit-desktop/loop-use-current-item.png)


### <a name="known-limitations"></a>Kendte begrænsninger:
1.  Løkker kræver statiske vælgere. Det betyder, at det brugergrænsefladeelement (UX), hvor den gentagne handling sker, ikke må ændres. 
1.  Output-handlinger understøttes ikke i øjeblikket.
1.  I forbindelse med komplekse matrix-objekter, der skal overføres fra et flow, f. eks. en SharePoint-liste, skal du angive et eksempel på data for det pågældende objekt. Du kan hente dataene ved at køre flowet uden trinnet med flow til brugergrænseflade og derefter kopiere outputtet til midten af tekstfeltet (Tilføj eksempeldata), når du definerer matrixen.
1.  Du skal bruge udtryk til komplekse matrix-objekttyper. Du kan f. eks. bruge **udtrykselementerne ('gælder for hvert') ['<value>']**, hvor <value> er navnet på det specifikke objekt i inputmatrixen.

## <a name="add-a-delay"></a>Tilføje en forsinkelse

Du kan tilføje forsinkelse i flows for brugergrænsefladen for bedre at kunne styre kørslen af flowet for brugergrænsefladen.

Benyt denne fremgangsmåde for at føje en forsinkelse til et flow for brugergrænsefladen, som du har optaget.

1. Hold markøren over pilen på det ønskede sted, og vælg **Indsæt et nyt trin**. Du kan også vælge **Tilføj en handling** direkte for at tilføje den i slutningen af området eller flowet for brugergrænsefladen. 

   ![Indsætte et forsinkelsestrin](../media/edit-desktop/insert-new-step-delay.png)

1. Vælg **Tilføj en handling**.

   ![Tilføje handlingen for forsinkelse](../media/edit-desktop/add-delay-action.png)

1. Vælg **Indbygget**, og søg efter "forsinkelse". 
   Du kan også vælge **Planlæg** > **Forsinkelse**.

   ![Søge efter handlingen for forsinkelse](../media/edit-desktop/search-delay.png)

1. Indtast **antallet**, f.eks. "2", der repræsenterer nummeret på **enheden**.
1. Vælg **Enhed**, f.eks. **minutter**, for at angive varigheden af forsinkelsen.

   Følgende billede viser en forsinkelse på to minutter. 

   ![Definere forsinkelsen](../media/edit-desktop/delay-details.png)

   Forsinkelseshandlingen føjes til flowet for brugergrænsefladen. Når flowet kører, vil der være en forsinkelse, sådan som du har defineret den, før den næste handling køres.


## <a name="add-a-retry-policy"></a>Tilføj en prøv igen-politik

Som standard anmoder flows for brugergrænseflade automatisk om nye forsøg for mislykkede trin til brugergrænseflade ved hjælp af standardindstillingerne for nye forsøg og timeoutværdien.

Benyt følgende fremgangsmåde for at angive dine egne gentagelsespolitikker for bestemte trin, når du har registreret flow for brugergrænseflade.

1. Vælg **...** på det trin, hvor du vil ændre politikken for nyt forsøg.
1. Vælg **Indstillinger**.

   Indstillingskortet for trinnet åbnes.

   ![Åbn kortindstillinger](../media/edit-desktop/open-retry-settings.png)
   

1. Tilføj en timeoutværdi i feltet **Varighed**. 

   Varighed af timeout kan være mellem ét minut og 24 timer. Du skal f. eks. angive timeoutvarighed i dette format: **PT1M** for at repræsentere en timeoutvarighed på et minut eller en **PT24H**, der repræsenterer en timeout på 24 timer.

   ![Forsøg igen-politikkort](../media/edit-desktop/retry-policy-card.png)

   Timeout er en værdi, du kan angive for at vælge, hvor lang tid flow for brugergrænseflade skal forsøge at udføre en handling, som den ikke kan udføre, før den annulleres. Når handlingen er annulleret, starter forsøg igen-politikken et nyt forsøg. Standardværdien for timeout er fem minutter. 

   Der findes tre typer nye forsøg i flow for brugergrænseflade

   - Standard
   - Intet 
   - Brugerdef,
   
Denne **standard**-indstilling er valgt som standard. Denne standardværdi er angivet som forsøg igen 9 gange. Herunder det første forsøg betyder det, at der i alt er ti forsøg. Der er et interval på 1 sekund mellem nye forsøg.

Hvis du vælger indstillingen **Ingen**, udføres der ingen forsøg igen på dette trin.

Hvis du vil angive en brugerdefineret politik for nyt forsøg, skal du vælge indstillingen **Brugerdefineret** og angive en værdi for **Antal forsøg**  og **Længden af intervaller**.                    


>[!NOTE]
>Forsøg igen-politikken er ikke tilgængelig for alle trin. Hvis du ikke kan se indstillingerne for nyt forsøg, betyder det, at politikken ikke er tilgængelig for det specifikke trin.

## <a name="add-a-manual-action"></a>Tilføje en manuel handling

Når du har optaget et program med mindst én handling, kan du manuelt tilføje en af følgende handlinger for det pågældende program.

| **Handling**          | **Kommentar**                                                       |
|---------------------|-------------------------------------------------------------------|
| Luk program   |                                                                   |
| Højreklik         |                                                                   |
| Send tastetryk           | Send tastetryk og tastekombinationer, f.eks. CTRL + C.                             |
| Venstreklik          |                                                                   |
| Hent tekst            | Læs teksten fra et element i brugergrænsefladen, og brug det derefter som et output. |
| Angiv tekst          |                                                                   |
| Få element aktiveret | Kontrollér, om et element i brugergrænsefladen er aktiveret eller deaktiveret.         |
| Ryd element       | Ryd værdien i et redigerbart element i brugergrænsefladen.             |
| Vent et par sekunder    | Vent, før du fortsætter til næste trin.                           |

Følg disse trin for at tilføje en manuel handling:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** > **Flow for brugergrænseflade**.
1. Vælg det flow for brugergrænsefladen, du vil redigere.

   ![Det flow til brugergrænseflade, der skal redigeres](../media/edit-desktop/select-ui-flow.png)

1. Vælg **Rediger**. 
1. Vælg det optagekort, der indeholder de trin, som du vil føje et nyt trin til.
   Kortet udvides, og de optagede trin vises.

   ![Vælg optagekort](../media/edit-desktop/manual-select-recording-card.png)

1. Vælg **Tilføj en handling** på optagekortet lige under det seneste optagede trin.
   Du kan se listen over manuelle handlinger, der er angivet tidligere i denne gennemgang. 

1. Vælg den handling, du vil tilføje. Her har jeg valgt **Få element aktiveret**, men du kan vælge en hvilken som helst handling, der giver mening for dit scenarie.

   ![Vælg handling, der skal tilføjes.png](../media/edit-desktop/select-action-to-add.png)

Når handlingen er tilføjet, skal du angive **Vælgeren** under avancerede indstillinger for handlingen.

![Avancerede indstillinger for handling](../media/edit-desktop/action-advanced-options.png "Avancerede indstillinger for handling")

### <a name="set-the-selector"></a>Angiv vælgeren

Vælgeren identificerer elementet i brugergrænsefladen, som handlingen udføres på under afspilning. Vi anbefaler, at du kopierer/indsætter disse oplysninger fra et separat trin, der er målrettet det samme element i brugergrænsefladen, hvis det er muligt.

Vælgeren har følgende format:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Du skal angive dataene for felterne **elementStack** og **elementXPath** i vælgerelementet.

Her er et eksempel på, hvordan **elementStack** kan se ud.

![ElementStack](../media/edit-desktop/elementstack.png "ElementStack")

Du kan indlæse **elementXPath** ved hjælp af [Optageren for brugergrænsefladen WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![WAD-værktøj](../media/edit-desktop/wad-tool.png "WAD-værktøj")

Fjern det første element (alt før /Window), før du bruger resultatet i **elementXPath** i vælgeren.

Test dit flow for brugergrænsefladen for at bekræfte, at vælgeren fungerer korrekt.

## <a name="use-advanced-controls"></a>Bruge avancerede kontrolelementer

Du kan inkorporere avancerede kontrolelementer, f.eks. handlinger af typen **betingelser**, **skift sager** og **afslut** i dine flow for brugergrænseflade.

Du kan udføre disse avancerede handlinger ved at udføre følgende trin i et eksisterende flow for brugergrænseflade.

1. Vælg det flow for brugergrænseflade, du har oprettet > **Flere kommandoer** (...) > **Rediger**.

1. Vælg **+** > **Tilføj en handling** i rullemenuen i det flow for brugergrænsefladen, som du vil føje logik til.

   ![Tilføj en handling](../media/edit-desktop/add-action.png)

1. Vælg **Indbygget**, og vælg derefter en af de kontrolhandlinger, der er tilgængelige.

   ![Indbygget](../media/edit-desktop/select-built-in.png)

1. Fuldfør det udtryk, der skal evalueres. Du kan bruge dynamisk indhold og udtryk til at evaluere din betingelse og skifte kontrolelementer. Du kan desuden bruge et hvilket som helst output, der er genereret fra de forrige trin i flowet for brugergrænseflade.

   ![Betingelseskort](../media/edit-desktop/condition-card.png)


## <a name="add-a-recording-of-a-remote-computer-using-image-recognition-preview"></a>Tilføje en optagelse af en fjerncomputer ved hjælp af billedgenkendelse (prøveversion)

[!INCLUDE[cc-beta-prerelease-disclaimer](../includes/cc-preview-features-expect-changes.md)]

Billedgenkendelse i flow for brugergrænseflade er en prøveversionsfunktion, der i øjeblikket er tilgængelig, når en fjerncomputer optages via appen Forbindelse til fjernskrivebord (RDC).
 

## <a name="what-is-image-recognition"></a>Hvad er billedgenkendelse?

I øjeblikket optages flow for brugergrænsefladen på skrivebordet primært ved hjælp af API'er for tilgængelighed (UI Automation og WinAppDriver) til registrering af kontrolelementerne i Microsoft Windows-brugergrænsefladetræet. Træet er undertiden ikke tilgængeligt, f.eks. med webbaserede eller Java-apps. Træet kan muligvis være upålideligt, f.eks. når id'erne for et kontrolobjekt ændres ofte eller mellem sessioner. 

Med billedgenkendelse kan du klikke på placeringer og andre detaljer, der afstemmes visuelt under afspilningen, hvilket er en stor udvidelse af det antal programmer, der kan automatiseres.

## <a name="use-image-recognition-to-record-a-remote-computer"></a>Bruge billedgenkendelse til at registrere en fjerncomputer

1. Gå til fanen Input i et nyt eller eksisterende flow for brugergrænseflade, og opret to nye **følsomme tekst**-input, ét til brugernavnet og ét til den adgangskode, der bruges til at logge på fjernenheden. Følsomme tekstinput giver dig mulighed for at overføre værdierne dynamisk, når du tester eller kalder flow for brugergrænseflade fra et andet flow, uden at de gemmes eller logges af selve flowet for brugergrænsefladen.

   ![Følsom tekst ](../media/create-remote-desktop/ir-sensitive-text.png)

1. Følg trinnene i **Tilføje en optagelse** for at starte optagerkontrolelementet for et nyt eller eksisterende flow for brugergrænseflade.

1. Brug appen Fjernskrivebord til at oprette forbindelse til fjerncomputeren.

1. Udvid vinduet Fjernskrivebord til fuld skærm.

1. Vælg **Optag** fra optagerkontrolelementet, og vælg **Forstået** i den viste besked.

   ![Pop op-vindue](../media/create-remote-desktop/popup.png)

1. Udfør trinnene på fjerncomputeren, og vælg derefter **Udført** på optagerkontrolelementet.

1. Find handlingen **Start Fjernskrivebord** i din optagelse, og angiv derefter de følsomme tekstinput for brugernavnet og adgangskoden.

![Brugernavn og adgangskode som følsom tekst](../media/create-remote-desktop/ir-launch-emote_desktop-session.png)

1. Vælg **Gem**, og test derefter dit flow for brugergrænsefladen.

>[!IMPORTANT]
>Når du kalder dette flow for brugergrænseflade fra et automatiseret flow, anbefales du at bruge en nøgleadministrationsløsning, f.eks. en [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), til at hente brugernavnet og adgangskoden og derefter sende dem til de **følsomme tekst**-input i flow for brugergrænseflade dynamisk i stedet for at gemme dem i selve flowet. 

>[!TIP]
> Aktivér **Sikre input** i menuen **Indstillinger** for **Kør et flow for brugergrænsefladen på skrivebordet**-handlingen i det flow, der kalder flow for brugergrænseflade. Derved sikres, at input ikke gemmes i historik over kørsel.

## <a name="use-image-recognition-to-record-on-citrix"></a>Brug billedgenkendelse til at optage på Citrix

Der findes to indstillinger for optagelse på Citrix med flows for brugergrænsefladen.

### <a name="option-1-record-a-citrix-application-or-desktop-already-open-on-your-machine"></a>Mulighed 1: Optag en Citrix-applikation eller -skrivebord, som allerede er åbent på computeren

1.  Følg trinnene i [Tilføje en optagelse](#add-a-recording) for at starte optagerkontrolelementet for et nyt eller eksisterende flow for brugergrænseflade.
1.  Brug Citrix-appen eller fjernskrivebordet til at oprette forbindelse til fjerncomputeren.

   ![Visning af Citrix-appen](../media/edit-desktop/citrix-app-remote.png)

1.  Hvis du bruger Citrix-fjernskrivebordet, skal du udvide vinduet til fuld skærm.
1.  Vælg **Optag** fra optagerens kontrolelement, og vælg derefter **Forstået** i den viste advarsel.
1.  Udfør trinnene på Citrix, og vælg derefter **Udført** i optagerens kontrolelement.

>[!TIP]
>Flows for brugergrænsefladen kan optage flere Citrix-apps i samme session. Åbn alle applikationer, før du starter optagelsen, hvis du ikke har optaget starten af dit Citrix-arbejdsområde.

### <a name="option-2-record-the-launch-of-your-citrix-application--desktop-from-your-citrix-workspace"></a>Mulighed 2: Optag starten af Citrix-applikationen eller -skrivebordet fra Citrix-arbejdsområdet

1.  Følg trinnene i [Tilføje en optagelse](#add-a-recording) for at starte optagerkontrolelementet for et nyt eller eksisterende flow for brugergrænseflade.
1.  Åbn Citrix-arbejdsområdet fra proceslinjen.
1.  Angiv din adgangskode, og vælg derefter **Log på**.
  
    >[!TIP]
    >Hvis du ikke vil vælge **Husk adgangskode**, skal du bruge input af typen **Tekst med forskel på store og små bogstaver**.

    ![Angive adgangskoden for Citrix-appen](../media/edit-desktop/citrix-app-password.png)

1. Vælg den app eller det skrivebord, du vil optage.

   ![Viser en liste over apps, du kan vælge at optage](../media/edit-desktop/citrix-select-app-record.png)

1.  Udfør trinnene på Citrix, og vælg derefter **Udført** i optagerens kontrolelement.

   >[!IMPORTANT]
   >Hvis du har indspillet logon-trinnet, vises der tre Citrix-applikationer i designeren. Det er forventelig, da vinduet for logon er en anden applikation fra Citrix-arbejdsområdet.

   >[!TIP]
   >Kontrollér, at dit Citrix-arbejdsområde er lukket, inden du afspiller flowet for brugergrænsefladen, i testtilstand og automatiseret tilstand. Højreklik på Citrix-ikonet i meddelelseslinjen, og vælg **Afslut** for at lukke arbejdsområdet.


#### <a name="troubleshooting"></a>Fejlfinding

Hvis du har problemer med tekst med forskel på store og små bogstaver i vinduet for logon:
1. Åbn inputmenuen fra optageren.
1. Vælg feltet for adgangskoden.
1. Vælg din tekst med forskel på store og små bogaver (i dette eksempel "adgangskode") i inputmenuen.

   ![Bruge tekst med forskel på store og små bogstaver til adgangskoden](../media/edit-desktop/citrix-app-sensitive-text.png)


## <a name="use-ocr-to-extract-text-from-images"></a>Brug OCR til at udtrække tekst fra billeder

1. Når du optager dine trin, skal du navigere til placeringen af den tekst, du vil indlæse.

1. Vælg **Output** > **Udtræk tekst fra billede** fra optagerens kontrolelementet.

1. Følg anvisningerne for at vælge et **ankerområde** (en sektion på skærmen, der ikke forventes at blive ændret, f.eks. navnet ud for et felt).

    ![Ankerområde](../media/create-remote-desktop/ir-anchors.png)

1.  Vælg **målområdet** (det område, som tekst skal udtrækkes fra, ved hjælp af optisk tegngenkendelse).

    ![Målområde](../media/create-remote-desktop/ir-targets.png)

1.  Angiv et navn til outputtet.

1.  Vælg **Udført** på optagerens kontrolelementet.

1.  Vælg **Gem**, og test derefter dit flow for brugergrænsefladen.


### <a name="known-issues-for-remote-desktop-recordings"></a>Kendte problemer i forbindelse med optagelser af Fjernskrivebord

1. Kontrollér, at alle krævede input (computernavn, brugernavn og adgangskode) er udfyldt og gemt, før du optager yderligere trin i det samme flow for brugergrænseflade.

1. Hvis du vil knytte til en eksisterende fjernskrivebordssession, skal sessionen være startet tidligere i det samme flow for brugergrænseflade.

1. Den anbefalede måde at starte forbindelse til Fjernskrivebord på (RDC) til optagelse er fra appen Forbindelse til Fjernskrivebord (mstc.exe) fra menuen Start. Hvis sikkerhedshandlinger i Windows optages sammen med handlingen **Start Fjernskrivebord**, skal de fjernes fra designeren, så afspilningen ikke afbrydes (dette kan ske, når fjernskrivebordssessionen startes fra en genvej).

1. Afspilningen kan mislykkes, hvis flow for brugergrænseflade blev optaget på en skærm med skærm skalering (Windows-indstillinger > Skalering af skærm) er indstillet til en anden værdi end 100 %. Du kan løse problemet ved at sikre, at skærmskalering er angivet til 100 % inden optagelsen.


## <a name="handle-error-conditions"></a>Håndtere fejlbetingelser

Der kan opstå uventede tilstande under afspilningen. Disse betingelser kan medføre, at flow for brugergrænseflade ikke fungerer korrekt. Du kan bruge avancerede funktioner til fejlhåndtering for at oprette alternative trin, når der opstår uventede betingelser. 

Det drejer sig om følgende trin.

1. Log på [Power Automate](https://powerautomate.microsoft.com) med din skole- eller arbejdskonto.
1. Vælg **Mine flow** > **Flow for brugergrænseflade**.
1. Vælg **Flere kommandoer** (de tre lodrette prikker for det flow for brugergrænseflade, du vil redigere).
1. Vælg **Rediger**.
1. Vælg pil ned umiddelbart inden det trin i flow for brugergrænseflade, du vil føje fejlhåndtering til, og vælg derefter **+** (Indsæt nyt trin).
   
   I følgende billede indsætter vi det nye trin før trinnet **PostElementText 1**. Det betyder, at hvis **PostElementText 1** mislykkes, køres de alternative trin, som du derefter definerer.

      ![Billede af Indsæt nyt trin](../media/edit-desktop/insert-new-step.png) 

1. Vælg **Tilføj en parallel forgrening**.

    ![Billede, der viser Tilføj en parallel forgrening og andre indstillinger](../media/edit-desktop/add-parallel-branch.png)

1. Vælg den handling, der skal udføres i den parallelle forgrening, hvis der opstår en fejl, når flow for brugergrænseflade køres.

   Du kan vælge **Optagerapp** for at foretage en ny optagelse af den parallelle forgrening eller vælge **Afbryd** via de **indbyggede** handlinger for at afslutte flow for brugergrænseflade på en ordentlig måde, hvis der opstår en fejl.

    ![Billede, der viser indstillingerne for den parallelle forgrening](../media/edit-desktop/add-parallel-branch.png)

   >[!NOTE]
   >Den handling, du tilføjer i den parallelle forgrening, kører som standard kun, hvis det foregående trin mislykkes. Du kan vælge **...** på den parallelle forgrening > **Konfigurer kørsel efter** for at ændre standardfunktionsmåden. 

      ![Billede, der viser indstillingerne, herunder Konfigurer kørsel efter](../media/edit-desktop/configure-run-after.png)

1.  På denne skærm kan du vælge den betingelse, som den parallelle forgrening skal udføres på. Du kan vælge mellem fire tilgængelige indstillinger.

    ![Billede, der viser indstillingerne for kørsel efter](../media/edit-desktop/run-after-options.png)

    Bemærk! Du kan ikke gemme et brugergrænsefladeflow, hvor både hovedforgreningen og den parallelle forgrening er angivet til at køre på samme betingelse.



## <a name="enable-coordinate-based-playback"></a>Aktivere koordinatbaseret afspilning

Koordinatbaseret afspilning bruger relative forskydninger af skærmkoordinater som et fallback, der hjælper flow for brugergrænseflade med at finde destinationsobjekter, som den automatiseringsstruktur, der anvendes som standard af Windows-brugergrænsefladen, ikke kan finde under afspilning. 

Her er nogle af årsagerne til, at den automatiseringsstruktur, der anvendes som standard af Windows-brugergrænsefladen, muligvis ikke kan finde målobjekter under afspilning:

- Det ældre program, som du automatiserer, bruger muligvis ikke programmeringsteknologier, der understøtter automatiseringsstrukturen, der anvendes af Windows-brugergrænsefladen.
- Programmet eller dets kontrolelementer har muligvis ikke en entydig XPath, et entydigt navn eller entydige id'er til brugergrænsefladen i forbindelse med automatisering. 
- Programmet har dynamiske kontrolelementer, hvis navne eller id'er kan ændres. 
- Programmet har kontrolelementer, der ikke har navne, id'er, entydige id'er osv.

>[!TIP]
>Brug den samme skalering og opløsning, og maksimer også destinationsprogrammet under optagelsen for at forbedre nøjagtigheden af koordinatbaseret afspilning.

Følg disse trin, når du har optaget et script til flow for brugergrænsefladen:

1. Udvid det trin, der starter eller tilknytter programmet.
   
   Dette er normalt det første trin i scriptet til optagelse.
1. Vælg **Vis avancerede indstillinger**.
1. Find egenskaben **Brug koordinat for afspilning**.
1. Vælg **Ja** på listen for at aktivere koordinatbaseret afspilning.

>[!TIP]
> Du kan aktivere eller deaktivere **Brug koordinat for afspilning** for hvert program for at anvende indstillingen på alle de trin, der udføres i forbindelse med det pågældende program.  


>[!WARNING]
>Med koordinatbaseret afspilning kan automatiseringen vælge kontrolelementer, der ikke er en del af destinationsprogrammet, af en række årsager, f.eks. når brugergrænsefladen i destinationsprogrammerne ændres drastisk.


## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [kører det flow for brugergrænsefladen](run-ui-flow.md), du lige har redigeret.

- Hvis du vil foretage dig mere med flow for brugergrænseflade, kan du også afprøve flow for brugergrænseflade med [input- og output](inputs-outputs-web.md)-parametre.

