---
title: Erstat dialoger med forretningsprocesforløb eller lærredsapps | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
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
ms.openlocfilehash: 8d3ce37fee1a4650454cc2c47af0d19fe37da96d
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296697"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Erstat dialoger med forretningsprocesforløb eller lærredsapps


[Dialoger frarådes](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated), og de skal erstattes af forretningsprocesforløb eller lærredsapps. I dette emne beskrives forskellige funktioner i disse indstillinger samt situationer, hvor et forretningsprocesforløb eller en lærredsapp, der er integreret i en modeldreven formular, kan bruges til at erstatte en eksisterende dialog.

## <a name="feature-capability-comparison"></a>Sammenligning af funktionalitet

Denne tabel indeholder dialogfunktionerne og de tilsvarende funktioner i forretningsprocesforløb og lærredsapps.


|Dialogfunktionalitet  | Funktionalitet i forretningsprocesforløb?  | Funktionalitet i lærredsapps?  |
|---------|---------|---------|
|Side     | Ja <br/> (fase i forretningsproces)    | Ja <br/> (appskærm)        |
|Kun spørgsmål   |  No    |  Ja <br/> (etiketter)        |
|Spørgsmål og svar     |  Ja <br/> (kun enhedsattributter)    | Ja <br/> (etiketter og inputfelter)    |
|Inputargumenter     |  Begrænset <br/> (trin i fase i forretningsproces)    | Ja <br/> (parametre for forespørgselsstreng)     |
|Variabler   |  No     |  Ja       |
|Forespørgselsvariabler    |  No     |  Ja     |
|Betinget forgreningslogik    |  Ja     | Ja <br/>  (gå til en hvilken som helst skærm i appen)    |
|Genbrug <br/> (start som underordnet dialog)   |  No     | Ja <br/> (gå til en hvilken som helst skærm i appen, start en anden app i et nyt vindue)     |
|Kør arbejdsprocesser ved start/slut    |   Ja      |  No <br/> (brug et forløb i stedet)  |
|Kør arbejdsprocesser ved input    | Ja    | No <br/> (brug et forløb i stedet)   |
|Kør arbejdsprocesser ved sideovergang   |  Ja       | No <br/> (brug et forløb i stedet)    |
|Begynd at bruge en URL-adresse  |   No      |  Ja     |
|Logføring af session    |  Ja       |  No     |
|SDK-support   |  Ja     |  Ja     |

### <a name="additional-capabilities-with-business-process-flows"></a>Yderligere funktioner med forretningsprocesforløb
- Procesanalyse (visninger, diagrammer og tid, der bruges i en fase)
- Brugerdefinerede kontrolelementer

### <a name="additional-capabilities-with-canvas-apps"></a>Yderligere funktioner med lærredsapps
- Appanalyse (appforbrug og -ydeevne)
- Sidekomposition med flere enheder
- Kør forløb
- Dataconnectors (standard og brugerdefinerede)
- Start som en separat app
- Layout, der kan konfigureres

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Vælg mellem et forretningsprocesforløb og en lærredsapp
Når du vælger din erstatning for dialogen, er det vigtigt at tage højde for den brugeroplevelse, du ønsker at levere. Vær også opmærksom på, at næsten alle dialoger kan modelleres ved hjælp af en lærredsapp.

Forretningsprocesforløb er bedst egnede til at erstatte dialoger, der modellerer processer, som giver vejledning på tværs af en omfattende arbejdsstrøm, der kræver samarbejde på tværs af grupper af personer og sammen med Dynamics 365-apps. Det kan f.eks. være gennemsyn af tilbud og routing. 

Lærredsapps kan også bruges til at erstatte dialoger, der modellerer konkrete opgaver, f.eks. et opkaldsscript til bearbejdelse af kundeemne, eller til at forenkle brugeroplevelsen for andre opgaver, f.eks. opdatering af en salgsmulighed. Bemærk, at det også kan være en fordel at have en separat lærredsapp i disse scenarier. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Erstatning af dialoger i et scenarie med et forretningsprocesforløb
Forestil dig, at du har en dialog, der over flere sider anmoder om vigtige oplysninger fra brugeren, genererer et tilbud og sender en mail til reviewere om at acceptere eller afvise tilbuddet, før du sender det via mail til kunden. Denne form for proces bliver mere effektiv, når du bruger et forretningsprocesforløb. 

Hvis du vil erstatte dialogen, skal du starte med at identificere de vigtigste faser i processen. Disse kan omfatte fasen *Forbered indhold* for at sikre, at alle produkter vises, og at rabatterne anvendes, fasen *Generér tilbud* for at oprette tilbuddet og gennemse det for at kontrollere nøjagtigheden af format, fasen *Primær review* for at sende tilbuddet til review og godkendelse, fasen *Sekundær review* for at gennemse tilbuddet under visse omstændigheder og endelig fasen *Levér tilbud* for at sende tilbuddet til kunden.

Derefter skal du identificere de vigtigste trin, som brugerne skal udføre i processen. Fasen *Forbered indhold* kan f.eks. indeholde et simpelt trin af typen sandt eller falsk, hvor brugeren skal dobbelttjekke produkterne i tilbuddet, et obligatorisk opslagstrin, hvor der skal vælges en prisliste, og et numerisk trin, hvor der skal angives en rabat, inden brugeren går videre til næste fase. Fasen *Generér tilbud* har måske et [handlingstrin](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow), hvor der oprettes et tilbud, der er baseret på alle de oplysninger, der tidligere blev hentet i fasen *Forbered indhold* og den relaterede Dynamics 365-post. Faserne *Primær review* og *Sekundær review* har måske flere trin af typen sandt eller falsk, der fungerer som en vejledning til gennemsyn af tilbud, sammen med et påkrævet trin, hvor der opnås godkendelsesstatus, og det sikres, at processen kun kan gå videre til næste fase, når der er indhentet godkendelse. Konfigurer [sikkerhed på feltniveau](/customer-engagement/admin/field-level-security) på dette trin for at sikre, at det kun er autoriserede brugere, der kan godkende tilbuddet.  Der kan også føjes en arbejdsproces til faserne *Primær review* og *Sekundær review*, så der sendes en mail til alle reviewere ved åbning. 

Endelig skal du konfigurere faser og trin i dit forretningsprocesforløb sammen med den betingede logik for at guide procesforløbet. I dette eksempel kan du tilføje en [betingelsesforgrening](enhance-business-process-flows-branching.md) efter fasen *Primær review*, så hvis et trin angiver, at der er behov for endnu en review, er næste fase i processen fasen *Sekundær review*, og hvis ikke, er det fasen *Levér tilbud*.

Hvis du vil gøre dette forretningsprocesforløb tilgængeligt for brugere, skal du sikre, at de rette brugere har rettigheder til forretningsprocesforløbet, og derefter aktivere det.

Du kan finde flere oplysninger om, hvordan du opretter et forretningsprocesforløb, under [Selvstudium: Opret et forretningsprocesforløb for at standardisere processer](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Erstatning af dialog med et scenarie med lærredsapp

Antag, at du har en dialog som opfølgning på et opkaldsscript, der vejleder sælgere via uopfordrede opkald til kundeemner. Denne proces kan nemt overtages af en lærredsapp.

Start med at oprette forbindelse til de datakilder, du skal bruge for at læse og skrive data. I dette eksempel bruges der en [forbindelse til Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) til kundeemne, konto og kontaktoplysninger.

Start med at identificere antallet af skærmbilleder, der skal bruges. I dette eksempel kan du beslutte, at der skal være fem skærmbilleder. 
-   Skærmbillede 1. Her vælger du et kundeemne på en liste, du vil ringe til.
-   Skærmbillede 2. Til introduktion, kontrol af, om kunden er ledig for en samtale, og planlægning af et tilbagekald på et senere tidspunkt. 
-   Skærmbillede 3. Til fastlæggelse af budget, autoritet, behov og tidslinje. 
-   Skærmbillede 4. Til fastlæggelse af næste skridt og planlægning af opfølgende opkald. 
-   Skærmbillede 5. Tak kundeemnet for vedkommendes tid i slutningen af opkaldet.

Derefter skal du oprette de enkelte skærmbilleder. På første skærmbillede skal du [bygge et galleri](/powerapps/maker/canvas-apps/customize-layout-sharepoint) over kundeemner, der skal ringes til. På det andet skal du bruge etiketter til at angive en titel til skærmbilledet og angive opkaldsscriptet, mens du bruger kontrolelementer som alternativknapper til at finde ud af, om det er et godt tidspunkt for personen at tale. Hvis det er, skal du bruge betinget logik til at aktivere en knap for at gå til næste skærmbillede, og hvis ikke, kan du vist et script på samme skærmbillede, hvor du forsøger at planlægge et senere opkald til kunden. På samme måde skal du definere opkaldsscriptet på efterfølgende skærmbilleder.

Endelig skal du [definere navigation på skærmbillederne](/powerapps/maker/canvas-apps/functions/function-navigate). Ud over at navigere gennem skærmbillederne i rækkefølge kan du i dette tilfælde sende brugeren fra den anden skærm til den sidste skærm (slutningen af scriptet, hvor du takker kundeemnet for vedkommendes tid), hvis kundeemnet ikke er interesseret i en samtale.

Hvis du vil gøre denne app tilgængelig for brugere, skal du publicere appen. Overvej, hvordan et sådant scenarie kan transformeres, hvis det bliver tilgængelig som en separat app, der leverer opkaldsscripts og understøtter hurtig dataindtastning.

Forestil dig, at du vil integrere denne oplevelse i Dynamics 365 Sales. Hvis du vil gøre dette, skal du starte med at oprette en iframe i en Dynamics 365 Sales-formular. Derefter skal du gå til sektionen **Apps** i Power Apps-menuen, vælge den app, du netop har publiceret, kopiere weblinket under fanen **Detaljer** og indsætte det som URL-adressen til din iframe. 

Vi kan gå et skridt videre og antage, at du ønsker, at denne app bliver tilgængelig direkte fra kundeemnets hovedformular, og at den knyttes til kundeemnet, så appen ikke kræver, at brugeren vælger et kundeemne i det første skærmbillede. Hvis du vil sende relevante oplysninger til appen, kan du blot ændre iframe-URL-adressen for at tilføje en forespørgselsstreng, der indeholder disse oplysninger, f.eks. id for kundeemne eller konto, ved hjælp af JavaScript, som kører ved en bestemt hændelse, f.eks. ved indlæsning af formularen. Derefter skal du opdatere appen for at fjerne det første skærmbillede (til valg af kundeemne) og i stedet få adgang til de værdier, der er overført til appen via forespørgselsstrengen ved hjælp af [funktionen Param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Ofte stillede spørgsmål om erstatning af dialog

Kan afhængigheder af lærredsapps spores? 
- Afhængigheder af lærredsapps spores på samme måde som afhængigheder i Dynamics 365-apps.

Kan jeg starte en lærredsapp som en pop op fra en knap på kommandolinjen?
- Ja. Hvis du vil gøre dette, skal du bare indstille mål-URL-adressen til URL-adressen i din lærredsapp, som kan hentes fra sektionen **Oplysninger** i appen, som beskrevet tidligere.

Kan arbejdsprocesser kaldes fra en lærredsapp?
- Dette understøttes ikke. Vi anbefaler, at du i stedet bruger et forløb. Flere oplysninger: [Introduktion til knapflows med brugerinput](button-flow-with-user-input-tokens.md)

Kan jeg automatisk konvertere dialoger til forretningsprocesforløb eller lærredsapps?
- Du kan ikke automatisk konvertere dialoger til forretningsprocesforløb eller lærredsapps.


## <a name="see-also"></a>Se også
[Selvstudium: Opret et forretningsprocesforløb for at standardisere processer](create-business-process-flow.md) </br>
[Hvad er lærred-apps i Power Apps?](/powerapps/maker/canvas-apps/getting-started)


