---
title: Opret et forretningsprocesforløb i Power Apps | MicrosoftDocs
description: Få mere at vide om, hvordan du opretter et forretningsprocesforløb
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
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
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2c8e512c39805296e5885266750b59b49feca482
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74359192"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Selvstudium: Opret et forretningsprocesflow for at standardisere processer
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I dette selvstudium kan du se, hvordan du opretter et forretningsprocesforløb med Power Apps. Få mere at vide om, hvorfor du bruger forretningsprocesforløb, under [Oversigt over forretningsprocesforløb](business-process-flows-overview.md). Du kan finde oplysninger om, hvordan du opretter et forløb for en mobil opgave under [Opret et forløb for en mobil opgave](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Når en bruger starter et forretningsprocesforløb, vises processens faser og trin i proceslinjen øverst i en formular:  
  
 ![Forretningsproces med faser](media/business-process-stages.png "Forretningsproces med faser")  
  
 > [!TIP]
 >  Når du har oprettet en definition af et forretningsprocesforløb, kan du styre, hvem der kan oprette, læse, opdatere eller slette forekomsten af forretningsprocesforløbet. I forbindelse med servicerelaterede processer kan du f.eks. give kundeservicemedarbejdere fuld adgang til at ændre forekomsten af forretningsprocesforløb, men give sælgere skrivebeskyttet adgang til forekomsten, så de kan overvåge eftersalgsaktiviteter for deres kunder. Hvis du vil angive sikkerhed for en definition af et forretningsprocesforløb, som du opretter, skal du vælge **Aktivér sikkerhedsroller** på handlingslinjen.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Forudsætninger

Du har brug for [Flowplan 2](https://preview.flow.microsoft.com/pricing/) for at kunne oprette forretningsprocesflows. Nogle Dynamics 365-licensplaner inkluderer Flowplan 2.

## <a name="create-a-business-process-flow"></a>Opret et forretningsprocesforløb  
  
1. Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. Vælg **Processer** i venstre navigationsrude. 
  
3.  Vælg **Ny** på værktøjslinjen **Handlinger**.  
  
4.  I dialogboksen **Opret proces** skal du udfylde de obligatoriske felter:  
  
    -   Angiv et navn til processen. Navnet på processen behøver ikke at være entydigt, men det skal give mening for de personer, der skal vælge en proces. Du kan ændre dette senere.  
  
    -   På listen **Kategori** skal du vælge **Forretningsprocesforløb**.  
  
         Du kan ikke ændre kategorien, når du har oprettet processen.  
  
    -   På listen **Enhed** skal du vælge den enhed, du vil basere processen på.  
  
         Den enhed, du vælger, påvirker de felter, der er tilgængelige for trin, som kan føjes til den første fase i procesforløbet. Hvis du ikke kan finde den ønskede enhed, skal du sørge for, at den grupperede indstilling Forretningsprocesforløb er angivet for enheden (der oprettes felter) i definitionen af enheden. Du kan ikke ændre dette, når du har gemt processen.  
  
5. Vælg **OK**.  
  
     Den nye proces oprettes, og designeren til forretningsprocesforløb åbnes med en enkelt fase, der allerede er oprettet for dig.  
  
 ![Vindue med forretningsprocesforløb, hvor hovedelementerne vises](media/business-process-flow-window-showing-main-elements.png "Vindue med forretningsprocesforløb, hvor hovedelementerne vises")  
  
6. **Tilføj faser.** Hvis dine brugere vil gå fra én forretningsfase til en anden i processen:  
  
    1.  Træk en komponent af typen **Fase** fra fanen **Komponenter**, og slip den på et plustegn (+) i designeren.  
  
        ![Træk en forretningsprocesfase](media/drag-business-process-stage.png "Træk en forretningsprocesfase")  
  
    2.  Hvis du vil angive egenskaberne for en fase, skal du vælge fasen og derefter angive egenskaberne under fanen **Egenskaber** i højre side af skærmen:  
  
        -   Angiv det viste navn.  
  
        -   Hvis du ønsker det, kan du vælge en kategori for fasen.  Kategorien (f.eks **Kvalificer** eller **Udvikling**) vises som en dobbeltvinkel på proceslinjen.  
  
            ![Dobbeltvinkel på forretningsproceslinjen](media/business-process-bar-chevron.png "Dobbeltvinkel på forretningsproceslinjen")  
  
        -   Når du er færdig med at ændre egenskaber, skal du vælge knappen **Anvend**.  
  
7. **Føj trin til en fase.** Hvis du vil se trinnene i en fase, skal du vælge **Oplysninger** i nederste højre hjørne af fasen. Sådan tilføjer du flere trin:  
  
    1.  Træk komponenten **Trin** til fasen fra fanen **Komponenter**.  
  
        ![Føj et trin til en fase i en forretningsproces](media/add-step-stage-business-process.png "Føj et trin til en fase i en forretningsproces")  
  
    2.  Vælg trinnet, og angiv derefter egenskaber under fanen **Egenskaber**:  
  
        1.  Angiv trinnets viste navn.  
  
        2.  Hvis du ønsker, at brugerne skal angive data for at fuldføre et trin, skal du vælge det relevante felt på rullelisten.  
  
        3.  Vælg **Påkrævet**, hvis brugerne skal udfylde feltet for at fuldføre trinnet, før de går videre til næste fase i processen.  
  
        4.  Vælg **Anvend**, når du er færdig.  
  
8. **Føj en forgrening (betingelse) til processen.** Sådan tilføjer du en forgreningsbetingelse:  
  
    1.  Træk komponenten **Betingelse** fra fanen **Komponenter** til et plustegn (+) mellem to faser.  
  
        ![Føj en betingelse til et forretningsprocesflow](media/add-condition-business-process-flow.png "Føj en betingelse til et forretningsprocesforløb")  
  
    2.  Vælg betingelsen, og angiv derefter egenskaber under fanen **Egenskaber**. Du kan finde flere oplysninger om forgreningsegenskaber under [Optimer forretningsprocesforløb med forgrening](enhance-business-process-flows-branching.md). Når du er færdig med at angive egenskaber for betingelsen, skal du vælge **Anvend**.  
  
9. **Tilføj en arbejdsproces.** Sådan aktiverer du en arbejdsproces:  
  
    1.  Træk en komponent af typen **Arbejdsproces** fra fanen **Komponenter** til en fase eller til elementet **Global arbejdsproces** i designeren.   Om du føjer den til den ene eller den anden, afhænger af følgende:  
  
       - **Træk den til en fase**, når du vil udløse arbejdsprocessen ved starten eller slutningen af fasen. Arbejdsproceskomponenten skal være baseret på den samme primære enhed som fasen.  
  
       - **Træk den til elementet Global arbejdsproces**, når du vil udløse arbejdsprocessen, når processen aktiveres, eller når processen arkiveres (når status ændres til **Fuldført** eller **Afbrudt**). Arbejdsproceskomponenten skal være baseret på den samme primære enhed som processen.  
  
    2.  Vælg arbejdsprocessen, og angiv derefter egenskaber under fanen **Egenskaber**:  
  
       1.  Angiv det viste navn.  
  
       2.  Vælg, hvornår arbejdsprocessen skal udløses.  
  
       3.  Søg efter en eksisterende aktiv arbejdsproces efter anmodning, der svarer til faseenheden, eller opret en ny arbejdsproces ved at vælge **Ny**.  
  
       4.  Vælg **Anvend**, når du er færdig.  
  
       Du kan finde flere oplysninger om arbejdsprocesser under [Arbejdsprocesser](../common-data-service/workflow-processes.md).  
  
10. Hvis du vil validere forretningsprocesforløbet, skal du vælge **Valider** på handlingslinjen.  
  
11. Hvis du vil gemme processen som et udkast, mens du fortsætter med at arbejde med den, skal du vælge **Gem** på handlingslinjen.  
  
    > [!IMPORTANT]
    >  Så længe en proces er et udkast, kan andre ikke bruge den.  
  
12. Hvis du vil aktivere processen og gøre den tilgængelig for dit team, skal du vælge **Aktivér** på handlingslinjen.  

13. Hvis du vil have kontrol over, hvem der kan oprette, læse, opdatere eller slette forekomsten af forretningsprocesforløbet, skal du vælge **Rediger sikkerhedsroller** på kommandolinjen i designeren. I forbindelse med servicerelaterede processer kan du f.eks. give kundeservicemedarbejdere fuld adgang til at ændre forekomsten af forretningsprocesforløb, men give sælgere skrivebeskyttet adgang til forekomsten, så de kan overvåge eftersalgsaktiviteter for deres kunder.

  På skærmen **Sikkerhedsroller** skal du vælge navnet på en rolle for at åbne siden med oplysninger om sikkerhedsroller. Vælg fanen Forretningsprocesforløb, og tildel derefter relevante rettigheder til forretningsprocesforløbet for en sikkerhedsrolle.

  > [!NOTE]
  > Sikkerhedsrollerne Systemadministrator og Systemtilpasser har som standard adgang til nye forretningsprocesforløb.

   ![Tildel rettigheder til et forretningsprocesforløb](media/bpf-assign-privileges.png)

  Angiv rettigheder ved at vælge de relevante alternativknapper, og klik på Gem. Du kan finde flere oplysninger om rettigheder under [Rettigheder i forretningsprocesforløb](business-process-flows-overview.md#BKMK_MultipleBPF).

  Derefter skal du huske at tildele sikkerhedsrollen til de relevante brugere i din organisation.

> [!TIP] 
>  Her er nogle tip, du kan bruge, når du arbejder med dit opgaveforløb i designervinduet:  
>   
> - Hvis du vil tage et øjebliksbillede af alt i vinduet med forretningsprocesforløbet, skal du vælge **Øjebliksbillede** på handlingslinjen. Dette er nyttigt, hvis du f.eks. vil dele og have kommentarer til processen fra et gruppemedlem.  
> - Brug minioversigten til hurtigt at navigere til forskellige dele af processen. Dette er nyttigt, når du har en kompliceret proces, der ruller ud over skærmen.  
> - Hvis du vil tilføje en beskrivelse af forretningsprocessen, skal du vælge **Oplysninger** under processens navn i venstre hjørne af vinduet med forretningsprocesforløbet. Du kan bruge op til 2000 tegn.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Rediger et forretningsprocesforløb  
 Hvis du vil redigere forretningsprocesforløb, skal du åbne løsningsoversigten, vælge **Processer** og derefter vælge det **forretningsprocesforløb** på listen over processer, du vil redigere.  
  
 Når du vælger navnet på den forretningsproces, du vil redigere, på listen over processer, åbnes den i designeren, hvor du kan foretage de opdateringer, som du ønsker. Udvid **Oplysninger** under navnet på processen for at omdøbe den eller tilføje en beskrivelse og få vist yderligere oplysninger.  
  
 ![Udvidet detaljesektion i et forretningsprocesforløb](media/business-process-flow-details.png "Sektion med udvidede oplysninger i et forretningsprocesforløb")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Andre ting, du skal vide om forretningsprocesforløb
 **Rediger faser**  
Forretningsprocesforløb kan bestå af op til 30 faser.    
  
Du kan tilføje eller ændre følgende egenskaber for en fase:  
  
- **Fasens navn**  
  
- **Enhed**. Du kan ændre enheden for alle faser med undtagelse af den første.  
  
- **Fasekategori**. I en kategori kan du gruppere faser efter typen af handling. Dette er nyttigt for rapporter, der grupperer poster efter den fase, de er i. Indstillingerne for fasekategorien kommer fra den globale grupperede indstilling Fasekategori. Du kan føje yderligere indstillinger til denne globale grupperede indstilling og ændre etiketterne for eksisterende indstillinger, hvis du ønsker det. Du kan også slette disse indstillinger, hvis du ønsker det, men vi anbefaler, at du bevarer de eksisterende indstillinger. Du kan ikke tilføje nøjagtigt den samme indstilling igen, hvis du sletter den. Hvis de ikke skal bruges, kan du ændre etiketten til "Brug ikke".  
  
- **Relation**. Angiv en relation, når den foregående fase i processen er baseret på en anden enhed. For den fase, der i øjeblikket er defineret, skal du vælge **Vælg relationer** for at identificere en relation, der skal bruges, når du flytter mellem de to faser. Det anbefales, at du vælger en relation af følgende årsager:  
  
    -   For relationer er der ofte defineret attributtilknytninger, der automatisk overfører data mellem poster og dermed minimerer indtastning af data.  
  
    -   Når du vælger **Næste fase** på proceslinjen for en post, vises alle poster, der bruger relationen, i procesforløbet, hvilket medfører større genbrug af poster i processen. Du kan desuden bruge arbejdsprocesser til at automatisere oprettelsen af poster, så brugeren blot kan vælge den i stedet for at oprette en, og dermed yderligere strømline processen.  
  
**Rediger trin**  
 De enkelte faser kan bestå af op til 30 trin.    
  
**Tilføj forgrening**  
Du kan få mere at vide om, hvordan du føjer en forgrening til en fase, under [Optimer forretningsprocesforløb med forgrening](enhance-business-process-flows-branching.md).  
  
Hvis du vil gøre et forretningsprocesforløb tilgængeligt, så andre kan bruge det, skal du angive rækkefølgen for procesforløbet, aktivere sikkerhedsroller og aktivere det.  
  
**Angiv rækkefølge for procesforløb**  
 Når du har mere end ét forretningsprocesforløb for en enhed (posttype), skal du angive, hvilken proces der automatisk tildeles til nye poster. På kommandolinjen skal du vælge **Angiv rækkefølge for procesforløb**. For nye poster eller poster, der ikke allerede har tilknyttet et procesforløb, bruges det første forretningsprocesforløb, som en bruger har adgang til.  
  
**Aktivér sikkerhedsroller**  
Brugere har adgang til et forretningsprocesforløb afhængigt af den rettighed, der er defineret for forretningsprocesforløbet i den sikkerhedsrolle, der er tildelt til brugerne. 

Det er kun sikkerhedsrollerne **Systemadministrator** og **Systemtilpasser**, der som standard kan se et nyt forretningsprocesforløb. 

Hvis du vil angive rettigheder til et forretningsprocesforløb, skal du åbne forretningsprocesforløbet til redigering og derefter vælge **Rediger sikkerhedsroller** på kommandolinjen i designeren af forretningsprocesforløb. Se trin 13 under [Opret et forretningsprocesforløb](#create-a-business-process-flow), der er vist tidligere i dette emne.
  
**Aktivér**  
Før andre kan bruge forretningsprocesforløbet, skal du aktivere det. Vælg **Aktivér** på kommandolinjen. Når du har bekræftet aktiveringen, er forretningsprocesforløbet klar til brug. Hvis et forretningsprocesforløb indeholder fejl, kan du ikke aktivere det, før fejlene er rettet.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Føj en handling efter anmodning til et forretningsprocesforløb
I opdateringen Dynamics 365 (online), version 9.0 introduceres der en funktion til forretningsprocesforløb: automatisering af forretningsprocesforløb med handlingstrin. Du kan føje en knap til et forretningsprocesforløb, der udløser en handling eller en arbejdsproces.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Tilføj arbejdsprocesser eller handlinger efter anmodning ved hjælp af et handlingstrin
Lad os antage, at Contoso-organisationen som led i processen til kvalifikation af salgsmuligheder kræver, at alle salgsmuligheder gennemses af en udpeget reviewer. Derfor har Contoso-organisationen oprettet en handling, der: 

- Opretter en opgavepost, som tildeles til revieweren af salgsmuligheder. 
- Vedhæfter "Klar til gennemsyn" til salgsmulighedsemnet. 

Derudover skal Contoso være i stand til at køre disse handlinger efter anmodning. For at disse opgaver skal integreres i processen til kvalifikation af salgsmuligheder, skal handlingerne vises i forretningsprocesforløbet for salgsmuligheder. Hvis du vil aktivere denne funktionalitet, skal du vælge **Som et handlingstrin i et forretningsprocesforløb**.
![Kan køre som et forretningsprocesforløb.](media/action-available-to-run.png)

Som det næste føjes handlingstrinnet til Contosos forretningsprocesforløb for salgsmuligheder. Derefter valideres og opdateres procesforløbet.

![Handling, der føjes til forretningsprocesforløbet for salgsmuligheder.](media/add-action-to-bpf.png)

Nu kan medlemmer af Contosos salgsstyrke starte handlingen fra trinnet **Kvalificer salgsmulighed** i forretningsprocesforløbet ved at vælge **Udfør**.

![Udfør handling.](media/action-execute.png)

> [!IMPORTANT]
> - Forretningsprocesforløbet skal inkludere et handlingstrin for at kunne udføre en handling eller arbejdsproces efter anmodning. Hvis handlingstrinnet kører en arbejdsproces, skal arbejdsprocessen konfigureres til at køre efter anmodning.
> - Den enhed, der er knyttet til handlingen eller arbejdsprocessen, skal være den samme som den enhed, der er knyttet til forretningsprocesforløbet.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Begrænsning af brug af handlingstrin i et forretningsprocesforløb

- Handlinger er ikke tilgængelige som handlingstrin, hvis input- eller outputparametrene er af typen Entity, EntityCollection eller OptionSet (valgliste). Handlinger med mere end én outputparameter af typen EntityReference eller et vilkårligt antal inputparametre af typen EntityReference er ikke tilgængelige som handlingstrin. Handlinger, der ikke er tilknyttet en primær enhed (global handling), er ikke tilgængelige som handlingstrin.

## <a name="instant-flows-in-business-process-flows"></a>Øjeblikkelige flow i forretningsprocesforløb?

Du kan køre et **øjeblikkeligt flow** for at automatisere gentagne opgaver, oprette dokumenter, spore godkendelser og meget mere fra en fase i en forretningsproces.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Tilføj et øjeblikkeligt forløb som et trin i en forretningsproces

Lad os antage, at du sælgere printere og bruger **Kundeemne til salgsproces for salgsmulighed** til at lukke handler. Som en del af denne proces vil du gerne have, at teamlederen til at gennemse og godkende forslag, som salgsteamet sammensætter, i en tidligere fase i forretningsprocesforløbet, før du deler det med kunden.

I den forbindelse skal du gøre to ting:
1. Byg et øjeblikkeligt flow, der anmoder om gennemsyn og godkendelse af forslaget fra teamet.
1. Tilføj det øjeblikkelige flow som et trin i **Kundeemne til salgsproces for salgsmulighed**.

> [!TIP]
> Kun [løsningsorienterede flow](https://docs.microsoft.com/flow/overview-solution-flows) kan tilføjes som et trin i en forretningsproces. 

### <a name="build-an-instant-flow"></a>Opret et øjeblikkeligt flow

1. Vælg **Løsninger** i navigationsmenuen i Power Automate.
1. Vælg **Standardløsning** på listen over de løsninger, der vises. 
1. Vælg menuen **+ Ny**, og vælg derefter **Flow** på den liste, der vises.
1. Søg efter, og vælg derefter connectoren **Common Data Service**.
1. Søg efter, og vælg derefter udløseren **Når en post vælges** på listen over **Common Data Service**-udløsere.
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

  1. Tilføj handlingen **Hent post** fra **Common Data Service**-connectoren.
  1. Angiv **Miljø** til **(Aktuel)** , **Enhedsnavn** til **Kundeemne til salgsproces for salgsmulighed** og **Elementidentifikator** til **BPFFlowStageEntityRecordID**.

     ![Tilføj en post](media/instant-flow-add-record.png)

     Nu, hvor vi har dataene, skal du definere godkendelsesprocessen ved at tilføje handlingen **Start, og vent på en godkendelse (V2)** og derefter udfylde de relevante oplysninger. Få mere at vide om [godkendelser]( sequential-modern-approvals.md) hvis du ikke er bekendt med dem.

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
1. Derefter skal du vælge søgeikonet i feltet **Vælge et flow** for at få vist alle flows, du kan føje til et forretningsprocesforløb.
1. Vælg et flow på listen, og gem derefter dine ændringer ved at vælge knappen **Anvend** nederst i ruden med egenskaber.
1. Til sidst skal du vælge knappen **Opdater** for at gøre dette forretningsprocesforløb med dets nye øjeblikkeligt flow-trin tilgængelig for dine brugere.


## <a name="the-action-center"></a>Handlingscenteret

Når du har brug for at se en liste over de forretningsprocesforløb, du er involveret i, kan du se det samlede handlingscenter. 

![Visning med forretningsprocesforløb for det samlede handlingscenter](media/approvals-center.png "Visning med forretningsprocesforløb for det samlede handlingscenter")

![Visning med godkendelsesflow for det samlede handlingscenter](media/action-center-bpf.png "Visning med godkendelsesflow for det samlede handlingscenter")

I det samlede handlingscenter kan du se alle forretningsprocesser, hvor du har fået tildelt mindst én Common Data Service enhedspost, som processen bruger. Hvis en forretningsproces f. eks. bruger enhederne **Kundeemne** og **Salgsmulighed** i Common Data Service, kan du se alle forekomster af denne proces, hvor enheden Kundeemne eller enheden Salgsmulighed er tildelt til dig.

Få vist alle de instanser, der i øjeblikket arbejdes på, under fanen **Aktiv**. Under denne fane kan du se følgende oplysninger:

- Processens navn.
- Den aktuelle fase for hver proces.
- Ejeren af den Common Data Service-post, der er knyttet til den aktive fase.
- Tidsrum siden forekomsten blev oprettet.

Hvis du vil se

Vælg en forekomst for at åbne den under en ny fane, eller vælg den for at kopiere et link, dele et link via mail, afslutte eller slette forekomsten.
  
## <a name="next-steps"></a>Næste trin

 - [Oversigt over forretningsprocesforløb](business-process-flows-overview.md)  
 - [Optimer forretningsprocesforløb med forgrening ](enhance-business-process-flows-branching.md)
 - [Oversigt over godkendelser](sequential-modern-approvals.md)
 - [Detaljerede trin til tilføjelse af et øjeblikkeligt flow til et forretningsprocesforløb](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


