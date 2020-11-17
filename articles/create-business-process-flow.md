---
title: Oprette et forretningsprocesforløb i Power Apps | MicrosoftDocs
description: Lær, hvordan du opretter et forretningsprocesforløb
ms.custom: ''
ms.date: 09/24/2020
ms.reviewer: dean-haas
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: vashr
ms.author: vashr
ms.manager: KVIVEK
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8f1c8016ec76a61037d9cae5399c3b4691e2808
ms.sourcegitcommit: 9bf10fd76d178c257434b9401c19dc709ee240fc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/17/2020
ms.locfileid: "4035591"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Selvstudium: Oprette et forretningsprocesforløb for at standardisere processer


Dette selvstudium viser, hvordan du opretter et forretningsprocesforløb i Power Apps. Du kan finde flere oplysninger om, hvorfor du skal bruge forretningsprocesforløb, i [Oversigt over forretningsprocesforløb](business-process-flows-overview.md). Du kan finde oplysninger om oprettelse af en mobilopgaveproces under [Oprette en mobilopgaveproces](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Når en bruger starter et forretningsprocesforløb, vises faser og trin i processen i proceslinjen øverst i en formular:  
  
 ![Forretningsproces med faser](media/business-process-stages.png "Forretningsproces med faser")  
  
 > [!TIP]
 >  Når du har oprettet en definition til et forretningsprocesforløb, kan du angive kontrol over, hvem der kan oprette, læse, opdatere eller slette forekomster af forretningsprocesforløb. For servicerelaterede processer kan du f.eks. give fuld adgang til kundeservicemedarbejdere for at ændre forekomsten af forretningsprocesforløbet, men give skrivebeskyttet adgang til forekomsten for sælgere, så de kan overvåge eftersalgsaktiviteter for deres kunder. Hvis du vil angive sikkerhed for en definition til et forretningsprocesforløb, som du opretter, skal du vælge **Aktivér sikkerhedsroller** på handlingslinjen.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Forudsætninger

Du har brug for en [plan pr. bruger](https://preview.flow.microsoft.com/pricing/) for at kunne oprette forretningsprocesflows. Nogle Dynamics 365-licensplaner omfatter planen for hver bruger.

## <a name="create-a-business-process-flow"></a>Oprette et forretningsprocesforløb  
  
1. Åbn [løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
1. Vælg **Processer** i venstre navigationsrude. 
1. Vælg **Ny** på værktøjslinjen **Handlinger**.  
1. I dialogboksen **Opret proces** skal du udfylde de krævede felter:  
  
    - Angiv et procesnavn. Navnet på processen behøver ikke at være entydigt, men det skal være beskrivende for brugere, der skal vælge en proces. Du kan ændre dette senere.  
  
    - På listen **Kategori** skal du vælge **Forretningsprocesforløb**.  
  
         Når processen først er oprettet, kan kategorien ikke ændres.  
  
    - På listen **Objekt** skal du vælge det objekt, som du vil basere processen på.  
  
         Det objekt, du vælger, påvirker de felter, der er tilgængelige for de trin, der kan føjes til den første fase i procesforløbet. Hvis du ikke kan finde det objekt, du ønsker, skal du kontrollere, at indstillingen Forretningsprocesforløb (felter oprettes) er angivet for objektet i definitionen af objektet. Du kan ikke ændre dette, når du har gemt processen.  
1. Vælg **OK**.  
  
     Den nye proces oprettes, og forretningsprocesforløbsdesigneren åbnes med en enkelt fase, der er oprettet for dig.  
     ![Vinduet Forretningsprocesforløb, der viser hovedelementer](media/business-process-flow-window-showing-main-elements.png "Vinduet Forretningsprocesforløb, der viser hovedelementer")  
1. **Tilføj faser.** Hvis brugerne vil gå fra én virksomhedsfase til en anden i processen:
  
    1. Trække komponenten **Fase** fra fanen **Komponenter**, og slip den ved et plustegn (+) i designeren.  
  
        ![Trække en forretningsprocesfase](media/drag-business-process-stage.png "Trække en forretningsprocesfase")  
    1. Hvis du vil angive egenskaberne for en fase, skal du vælge fasen og derefter angive egenskaberne under fanen **Egenskaber** i højre side af skærmbilledet:  
  
        - Angiv et visningsnavn.  
        - Hvis du ønsker det, kan du vælge en kategori for fasen.  Kategorien (f.eks. **Kvalificer** eller **Udvikl**) vises som et vinkeltegn på proceslinjen.  
  
            ![Forretningsproceslinje chevron](media/business-process-bar-chevron.png "Forretningsproceslinje chevron")  
        - Når du er færdig med at ændre egenskaberne, skal du vælge knappen **Anvend**.  
1. **Tilføj trin i en fase.** For at få vist trinene i en fase skal du vælge **Detaljer** i nederste højre hjørne af fasen. Sådan tilføjes flere trin:  
  
    1. Træk komponenten **Trin** til fasen fra fanen **Komponenter**.  
  
        ![Føje et trin til en fase i en forretningsproces](media/add-step-stage-business-process.png "Føje et trin til en fase i en forretningsproces")  
  
    1. Vælg trinnet, og angiv derefter egenskaber under fanen **Egenskaber**:  
  
        1. Angiv et vist navn til trinnet.  
        1. Hvis du ønsker, at brugerne skal angive data for at fuldføre et trin, skal du vælge det rette felt på rullelisten.  
        1. Vælg **Krævet**, hvis brugerne skal udfylde feltet for at fuldføre trinnet, før de går til den næste fase i processen.  
        1. Vælg **Gem**, når du er færdig.  

     > [!NOTE]
     >
     > - Hvis du angiver et boolesk felt med to indstillinger som **Påkrævet**, kan brugerne ikke fortsætte, medmindre feltværdien er **Ja**. Brugeren skal markere feltet som fuldført, før brugeren går videre til næste fase.
     > - Hvis enten **Ja** eller **Nej** er acceptable feltværdier, skal du gøre feltet til en grupperet indstilling i stedet for et boolesk felt med to indstillinger.
  
1. **Føj en ny forgrening (betingelse) til processen.** Sådan tilføjes en forgreningsbetingelse:  
  
     1. Træk komponenten **Betingelse** fra fanen **Komponenter** til et plustegn (+) mellem to faser.
     
        ![Føje en betingelse til et forretningsprocesflow](media/add-condition-business-process-flow.png "Føje en betingelse til et forretningsprocesflow")
     1. Vælg betingelsen, og angiv derefter egenskaber under fanen **Egenskaber**. Du kan finde flere oplysninger om forgreningsegenskaber under [Forbedre forretningsprocesforløb med forgrening](enhance-business-process-flows-branching.md). Når du har angivet egenskaberne for betingelsen, skal du vælge **Anvend**.  
1. **Tilføj en arbejdsproces.** Sådan aktiverer du en arbejdsproces:  
  
    1. Træk komponenten **Arbejdsproces** fra fanen **Komponenter** til en fase eller til elementet **Global arbejdsproces** i designer.   Den, du kan føje til den, afhænger af følgende:  
  
        - **Træk den til en fase**, når arbejdsprocessen skal udløses ved start eller afslutning af fasen. Arbejdsproceskomponenten skal være baseret på det samme primære objekt som fasen.  
        - **Træk den til elementet Global arbejdsproces**, når arbejdsprocessen skal udløses, når processen er aktiveret, eller når processen er arkiveret (når status ændres til **Fuldført** eller **Afbrudt**). Arbejdsproceskomponenten skal være baseret på det samme primære objekt som processen.  
    1.  Vælg arbejdsprocessen, og angiv derefter egenskaber under fanen **Egenskaber**:  

        1. Angiv et visningsnavn.  
        1. Vælg, hvornår arbejdsprocessen skal udløses.  
        1. Søg efter en eksisterende anmodet arbejdsproces, der stemmer overens med faseobjektet, eller opret en ny arbejdsproces ved at vælge **Ny**.  
        1. Vælg **Gem**, når du er færdig.  
  
    Du kan finde flere oplysninger om arbejdsprocesser i [Arbejdsprocesser](/common-data-service/workflow-processes.md).  
  
1. Hvis du vil validere forretningsprocesforløbet, skal du vælge **Valider** på handlingslinjen.  
1. Hvis du vil gemme processen som en kladde, mens du fortsætter med at arbejde på den, skal du vælge **Gem** på handlingslinjen.  
  
    > [!IMPORTANT]
    >  Så længe en proces er i kladdeform, vil brugere ikke kunne bruge den.  
  
12. Hvis du vil aktivere processen og gøre den tilgængelig for dit team, skal du vælge **Aktiver** på handlingslinjen.  

13. Hvis du vil kunne styre, hvem der kan oprette, læse, opdatere eller slette forekomsten af forretningsprocesforløbet, skal du vælge **Rediger sikkerhedsroller** på kommandolinjen i designeren. For servicerelaterede processer kan du f.eks. give fuld adgang til kundeservicemedarbejdere for at ændre forekomsten af forretningsprocesforløbet, men give skrivebeskyttet adgang til forekomsten for sælgere, så de kan overvåge eftersalgsaktiviteter for deres kunder.

  På skærmbilledet **Sikkerhedsroller** skal du vælge navnet på en rolle for at åbne siden med oplysninger om sikkerhedsrollen. Vælg fanen Forretningsprocesforløb og tildel derefter relevante rettigheder til forretningsprocesforløbet for en sikkerhedsrolle.

  > [!NOTE]
  > Det er som standard kun sikkerhedsrollerne Systemadministrator og Systemtilpasser der har adgang til nye forretningsprocesforløb.

   ![Tildel rettigheder til et forretningsprocesforløb](media/bpf-assign-privileges.png)

  Angiv rettigheder ved at vælge de relevante alternativknapper, og klik på Gem. Du kan finde flere oplysninger om rettigheder under [Rettigheder for forretningsprocesforløb](business-process-flows-overview.md#BKMK_MultipleBPF).

  Derefter skal du tildele sikkerhedsrollen til de relevante brugere i organisationen.

> [!TIP] 
>  Her er nogle få tip at huske på, mens du arbejder på din opgaveproces i designervinduet:  
>   
> - Hvis du vil tage et øjebliksbillede af alt i vinduet med forretningsprocesforløbet, skal du vælge **Øjebliksbillede** på handlingslinjen. Dette er f.eks. nyttigt, hvis du vil dele og modtage kommentarer om processen fra et teammedlem.  
> - Brug minikortet til hurtigt at navigere til forskellige dele af processen. Dette er nyttigt, når du har en kompliceret proces, der ruller ud af skærmbilledet.  
> - Hvis du vil tilføje en beskrivelse til forretningsprocessen, skal du vælge **Detaljer** under procesnavnet i venstre hjørne af vinduet med forretningsprocesforløbet. Du kan bruge op til 2.000 tegn.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Redigere et forretningsprocesforløb  
 For at redigere forretningsprocesser skal du åbne løsningsoversigten, vælge **Processer** og derefter vælge **Forretningsprocesforløb** på listen over processer, du vil redigere.  
  
 Når du vælger navnet på forretningsprocesforløbet, som du vil redigere på listen over processer, åbnes det i designeren, hvor du kan foretage opdateringer, du ønsker. Udvid **Detaljer** under navnet på processen for at omdøbe den eller tilføje en beskrivelse og få vist flere oplysninger.  
  
 ![Udvidet sektion med detaljer i et forretningsprocesforløb](media/business-process-flow-details.png "Udvidet sektion med detaljer i et forretningsprocesforløb")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Andre ting, du skal vide om forretningsprocesforløb
 **Redigere faser**  
Forretningsprocesforløb kan indeholde op til 30 faser.    
  
Du kan tilføje eller ændre følgende egenskaber for en fase:  
  
- **Fasenavn**  
  
- **Objekt**. Du kan ændre objektet for alle faser, undtagen den første.  
  
- **Fasekategori**. Med en kategori kan du gruppere faser efter en type handling. Det er nyttigt i forbindelse med rapporter, der grupperer poster efter den fase, de er i. Indstillinger for fasekategorien kommer fra de globale grupperede indstillinger for fasekategorien. Du kan evt. føje yderligere indstillinger til denne globale grupperede indstilling og ændre etiketterne for eksisterende indstillinger. Du kan også slette disse indstillinger, hvis du vil, men vi anbefaler, at du bevarer de eksisterende indstillinger. Du kan ikke tilføje præcist den samme indstilling igen, hvis du sletter den. Hvis du ikke ønsker, at de skal bruges, kan du ændre etiketten til "Brug ikke".  
  
- **Relation**. Angiv en relation, når den foregående fase i processen er baseret på en anden enhed. For den fase, der er under udarbejdelse, skal du vælge **Vælg relationer** for at identificere en relation, der skal bruges, når du flytter mellem de to faser. Det anbefales, at du vælger en relation for følgende fordele:  
  
    -   Relationer har ofte attributtilknytninger defineret, der automatisk overfører data mellem poster, hvilket minimerer dataindtastning.  
  
    -   Når du vælger **Næste fase** på proceslinjen for en post, vises alle de poster, der bruger forholdet i procesforløbet, hvilket fremmer genbrug af poster i processen. Desuden kan du bruge arbejdsprocesser til at automatisere oprettelse af poster, så brugeren blot vælger den i stedet for at oprette en, for yderligere at strømline processen.  
  
**Redigere trin**  
 Hver fase kan have op til 30 trin.    
  
**Tilføj forgrening**  
Du kan få mere for at vide om, hvordan du føjer en forgrening til en fase, under [Forbedre forretningsprocesforløb med forgrening](enhance-business-process-flows-branching.md).  
  
Hvis du vil give andre mulighed for at bruge et forretningsprocesforløb, skal du sortere procesforløbet, aktivere sikkerhedsroller og aktivere det.  
  
**Angiv procesforløbrækkefølge**  
 Når du har mere end ét forretningsprocesforløb for et objekt (posttype), skal du angive, hvilken proces der tildeles automatisk til nye poster. På kommandolinjen vælger du **Ordreprocesforløb**. For nye poster eller poster, der ikke allerede har et tilknyttet procesforløb, er det første forretningsprocesforløb, som en bruger har adgang til, det forløb, der bruges.  
  
**Aktivér sikkerhedsroller**  
Brugerne har adgang til et forretningsprocesforløb, afhængigt af hvilken rettighed, der er defineret i forretningsprocesforløbet i den sikkerhedsrolle, der er tildelt til brugeren. 

Det er som standard kun sikkerhedsrollerne **Systemadministrator** og **Systemtilpasser**, der kan få vist et nyt forretningsprocesforløb. 

Hvis du vil angive rettigheder til et forretningsprocesforløb, skal du åbne forretningsprocesforløbet til redigering og derefter vælge **Rediger sikkerhedsroller** på kommandolinjen i designeren af forretningsprocesforløb. Se trin 13 under [Opret et forretningsprocesforløb](#create-a-business-process-flow), der er vist tidligere i dette emne.
  
**Aktivér**  
Før brugere kan anvende forretningsprocesforløbet, skal du aktivere det. Vælg **Aktivér** på kommandolinjen. Når du har bekræftet aktiveringen, er forretningsprocesforløbet klart til brug. Hvis et forretningsprocesforløb indeholder fejl, kan du ikke aktivere det, før fejlene er rettet.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Tilføjelse af en handling efter behov til et forretningsprocesforløb
Opdateringen Dynamics 365 (online) version 9.0 introducerer en ny funktion til forretningsprocesforløb: automatisering af forretningsprocesforløb med handlingstrin. Du kan føje en knap til et forretningsprocesforløb, der udløser en handling eller en arbejdsproces.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Tilføje anmodede arbejdsprocesser eller handlinger ved hjælp af et handlingstrin
Lad os antage, at virksomheden Contoso som en del af processen til kvalificering af salgsmuligheder kræver, at alle salgsmuligheder skal gennemses af en angivet reviewer. Efterfølgende har Contoso-organisationen oprettet en handling, der: 

- Opretter en opgavepost, der er tilknyttet til revieweren af salgsmuligheden. 
- Føjer "Klar til gennemsyn" til salgsmulighedsemnet. 

Derudover skal Contoso kunne køre disse handlinger efter behov. For at integrere disse opgaver i processen til kvalificering af salgsmuligheden, skal handlingerne vises i forretningsprocesforløbet for salgsmuligheden. Du kan aktivere denne funktion ved at vælge **Som et handlingstrin i et forretningsprocesforløb**.
![Kan køres som et forretningsprocesforløb.](media/action-available-to-run.png)

Derefter føjes handlingstrinnet til Contosos forretningsprocesforløb for salgsmuligheden. Derefter valideres og opdateres procesforløbet.

![Handling, der er føjet til forretningsprocesforløb for salgsmulighed.](media/add-action-to-bpf.png)

Nu kan medlemmer af Contosos salgsafdeling starte handlingen fra forretningsprocestrinnet **Kvalificering af salgsmulighed** efter behov ved at vælge **Udfør**.

![Udfør handling.](media/action-execute.png)

> [!IMPORTANT]
> - Hvis du vil kunne udføre en handling eller en arbejdsproces efter anmodning, skal forretningsprocesforløbet indeholde et handlingstrin. Hvis handlingstrinnet kører en arbejdsproces, skal arbejdsprocessen være konfigureret til at køre efter behov.
> - Det objekt, der er knyttet til handlingen eller arbejdsprocessen, skal være det samme som det objekt, der er knyttet til forretningsprocesforløbet.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Begrænsning af brug af handlingstrin i et forretningsprocesforløb

- Handlinger er ikke tilgængelige som handlingstrin, hvis input- eller outputparametrene er af typen Entity, EntityCollection eller OptionSet (valgliste). Handlinger med mere end én EntityReference-outputparameter eller et hvilket som helst antal EntityReference-inputparametre er ikke tilgængelige som handlingstrin. Handlinger, der ikke er knyttet til et primært objekt (global handling), er ikke tilgængelige som handlingstrin.

## <a name="instant-flows-in-business-process-flows"></a>Øjeblikkelige flow i forretningsprocesforløb

Du kan køre et **øjeblikkeligt flow** for at automatisere gentagne opgaver, oprette dokumenter, spore godkendelser og meget mere fra en fase i en forretningsproces.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Tilføj et øjeblikkeligt forløb som et trin i en forretningsproces

Lad os antage, at du sælger printere og bruger **Kundeemne til salgsproces for salgsmulighed** til at lukke handler. Som en del af denne proces vil du gerne have, at teamlederen til at gennemse og godkende forslag, som salgsteamet sammensætter, i en tidligere fase i forretningsprocesforløbet, før du deler det med kunden.

I den forbindelse skal du gøre to ting:
1. Byg et øjeblikkeligt flow, der anmoder om gennemsyn og godkendelse af forslaget fra teamet.
1. Tilføj det øjeblikkelige flow som et trin i **Kundeemne til salgsproces for salgsmulighed**.

> [!TIP]
> Kun [løsningsorienterede flow](https://docs.microsoft.com/flow/overview-solution-flows) kan tilføjes som et trin i en forretningsproces. 

### <a name="build-an-instant-flow"></a>Opret et øjeblikkeligt flow

1. Vælg **Løsninger** i navigationsmenuen i Power Automate.
1. Vælg **Standardløsning** på listen over de løsninger, der vises. 
1. Vælg menuen **+ Ny**, og vælg derefter **Flow** på den liste, der vises.
1. Søg efter og vælg derefter connectoren for **Common Data Service**.
1. Søg efter, og vælg derefter udløseren **Når der slettes en post** på listen over **Common Data Service**-udløsere.
1. Angiv **Miljø** til **Standard**, og angiv derefter **Enhedsnavn** til **Kundeemne til salgsproces for salgsmulighed**.
1. Tilføj et tekstindtastningsfelt, hvor brugeren kan angive linket til forslaget.

   ![Øjeblikkeligt flow-udløser](media/instant-flow-trigger.png "Øjeblikkeligt flow-udløser")

   Vi skal bruge oplysninger fra forretningsprocesforløb-forekomsten som en konteksthjælp til godkendelsesanmodningen, så du skal følge disse trin for at gøre dette.

1. Tilføj handlingen **Fortolk JSON**. 
1. Angiv **Indhold** til **Enhedsobjekt** ved at vælge den på listen over dynamiske værdier for udløseren **Når en post vælges**.
1. Indsæt følgende indhold i feltet **Skema**.

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   Tingene bør nu se ud på følgende måde:

   ![Fortolk JSON](media/instant-flow-json-date.png "Fortolk JSON")

  1. Tilføj handlingen **Hent post** fra connectoren for **Common Data Service**.
  1. Angiv **Miljø** til **(Aktuelt)**, **Enhedsnavn** til **Kundeemne til salgsproces for salgsmulighed** og **Elementidentifikator** til **BPFFlowStageEntityRecordID**.

     ![Tilføj en post](media/instant-flow-add-record.png)

     Nu, hvor vi har dataene, skal du definere godkendelsesprocessen ved at tilføje handlingen **Start, og vent på en godkendelse (V2)** og derefter udfylde de relevante oplysninger. Få mere at vide om [godkendelser]( sequential-modern-approvals.md), hvis du ikke er bekendt med dem.

     > [!TIP]
     > - Brug den dynamiske indholdsvælger til at tilføje felter fra handlingen **Hent post** for at føje relevante oplysninger til godkendelsesanmodningen, så godkendere nemt kan forstå, hvad anmodningen handler om. 
     > - Hvis du vil angive yderligere kontekst om den aktive fase, som forretningsprocessen befinder sig i, skal du føje feltet **BPFActiveStageLocalizedName** til listen over dynamiske værdier.

     Kortet **Start, og vent på en godkendelse (V2)** kan se ud som dette:

      ![Godkendelseskort](media/instant-flow-add-approval-action.png)

1. Til sidst skal du gemme flowet og derefter aktivere det.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Tilføj dette flow som et trin i Kundeemne til salgsproces for salgsmulighed.

Nu, hvor du har oprettet det øjeblikkelige flow, er det eneste, du skal, at føje den til dit forretningsprocesforløb. 

1. Åbn **Kundeemne til salgsproces for salgsmulighed** i forretningsprocesforløbet. 
1. Træk og slip **Flow-trinnet (prøveversion)** fra listen **komponenter** til fasen **Foreslå**.
1. Derefter skal du vælge søgeikonet i feltet **Vælg et flow** for at få vist alle flows, du kan føje til et forretningsprocesforløb.
1. Vælg et flow på listen, og gem derefter dine ændringer ved at vælge knappen **Anvend** nederst i ruden med egenskaber.
1. Til sidst skal du vælge knappen **Opdater** for at gøre dette forretningsprocesforløb med dets nye øjeblikkeligt flow-trin tilgængelig for dine brugere.


## <a name="the-action-center"></a>Handlingscenteret

Når du har brug for at se en liste over de forretningsprocesforløb, du er involveret i, kan du se det samlede handlingscenter. 

![Visning med forretningsprocesforløb for det samlede handlingscenter](media/approvals-center.png "Visning med forretningsprocesforløb for det samlede handlingscenter")

![Visning med godkendelsesflow for det samlede handlingscenter](media/action-center-bpf.png "Visning med godkendelsesflow for det samlede handlingscenter")

I det samlede handlingscenter kan du se alle forretningsprocesser, hvor du har fået tildelt mindst én Common Data Service-objektpost, som processen bruger. Hvis en forretningsproces f.eks. bruger enhederne **Kundeemne** og **Salgsmulighed** i Common Data Service, kan du se alle forekomster af denne proces, hvor enheden Kundeemne eller enheden Salgsmulighed er tildelt til dig.

Få vist alle forekomster, der aktuelt arbejdes med, under fanen **Aktiv**. Under denne fane kan du få vist følgende oplysninger:

- Navnet på processen.
- Den aktuelle fase for hver proces.
- Ejeren af den Common Data Service-post, der er knyttet til den aktive fase.
- Tidsrum siden forekomsten blev oprettet.

Hvis du vil se

Vælg en forekomst for at åbne den under en ny fane, eller vælg den for at kopiere et link, dele et link via mail, afslutte eller slette forekomsten.
  
## <a name="next-steps"></a>Næste trin

 - [Oversigt over forretningsprocesforløb](business-process-flows-overview.md)  
 - [Forbedre forretningsprocesforløb med forgrening](enhance-business-process-flows-branching.md)
 - [Oversigt over godkendelser](sequential-modern-approvals.md)
 - [Detaljerede trin til tilføjelse af et øjeblikkeligt flow til et forretningsprocesforløb](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


