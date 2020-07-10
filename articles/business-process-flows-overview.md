---
title: Oversigt over forretningsprocesser | Microsoft Docs
ms.custom: ''
ms.date: 05/06/2019
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0a819c9ccaa3dd3e8ba60088fb8a9c197b74d15b
ms.sourcegitcommit: ab26d3b17cc34c650298ec5ac3b4ea9554e291cf
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/25/2020
ms.locfileid: "3502405"
---
# <a name="business-process-flows-overview"></a>Oversigt over forretningsproces


Du kan hjælpe med til at sikre, at brugerne angiver data konsekvent og følger de samme trin, hver gang de arbejder med en kunde, ved at oprette et forretningsprocesforløb i . F.eks. ønsker du måske at oprette et forretningsprocesforløb for at få alle til at håndtere kundeserviceforespørgsler på samme måde, eller for at kræve, at medarbejdere får godkendelse for en faktura, før de sender en ordre. Forretningsprocesforløb bruger den samme underliggende teknologi som andre processer, men de muligheder, de giver, er meget forskellige fra andre funktioner, der bruger processer. Du kan finde oplysninger om, hvordan du opretter eller redigerer et forretningsprocesforløb, under [Oprette et forretningsprocesforløb](create-business-process-flow.md).  
  
 [Se en kort video (4:49) om forretningsprocesforløb.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Hvorfor bruge forretningsprocesforløb?  
Forretningsprocesforløb giver vejledning til brugere i at få udført deres arbejde. De giver en strømlinet brugeroplevelse, der vejleder brugeren gennem de processer, som organisationen har defineret for interaktioner, der skal ende med en konklusion af en art. Denne brugeroplevelse kan skræddersys, så brugere med forskellige sikkerhedsroller kan få den oplevelse, der er bedst egnet til det arbejde, de udfører.  
  
 Brug forretningsprocesforløb til at definere et sæt af trin, som brugeren skal følge for at opnå det ønskede resultat. Disse trin fungerer som en visuel indikator, der fortæller, hvor i forretningsprocessen man befinder sig. Forretningsprocesforløb reducerer behovet for oplæring, da nye brugere ikke behøver at tænke på, hvilket objekt de skal bruge. De kan lade processen vejlede dem. Du kan konfigurere forretningsprocesforløb til at understøtte almindelige salgsmetoder, der kan hjælpe dine salgsgrupper til at opnå bedre resultater. I forbindelse med servicegrupper kan forretningsprocesforløb hjælpe nye medarbejdere med hurtigere at blive sat ind i sagerne og undgå fejl, som kunne medføre utilfredse kunder.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>Hvad kan forretningsprocesforløb gøre?  
 Med forretningsprocesforløb definerer du en række *faser* og *trin*, som så vises i et kontrolelement øverst i formularen.  
  
 ![Forretningsproces med faser](media/business-process-stages.png "Forretningsproces med faser")  
  
 Hver fase indeholder en gruppe af trin. Hvert trin repræsenterer et felt, hvor der kan angives data. Der skiftes til næste fase vha. knappen **Næste fase**. Du kan oprette et obligatorisk trin, hvor brugeren skal angive data for det tilhørende felt, før de kan gå videre til næste fase. Det kendes også som ”stage-gating”.  
  
 Forretningsprocesforløb virker rimeligt enkelt i sammenligning med andre typer processer, fordi de ikke giver nogen betinget forretningslogik eller automatisering ud over den strømlinede oplevelse med dataindtastning og administration af adgang til faser. Men, når du kombinerer dem med andre processer og tilpasninger, kan de spille en vigtig rolle i forbindelse med at spare folks tid, reducere omkostninger til oplæring samt gøre det nemmere for brugerne at lære programmet at kende.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Forretningsprocesforløb integreret med andre tilpasninger  
 Når du eller en bruger angiver data vha. forretningsprocesforløb, anvendes dataændringerne også i formularfelter, så eventuel automatisering, der udføres af forretningsregler eller formularscripts kan anvendes straks. Der kan tilføjes trin, som angiver værdier for felter, der ikke er til stede i formularen, og disse felter blive føjet til `Xrm.Page`-objektmodellen, som anvendes til formularscripts. Eventuelle arbejdsprocesser, der initieres af ændringer i felter i et forretningsprocesforløb, anvendes, når dataene i formularen gemmes. Hvis automatiseringen anvendes af en realtidsarbejdsproces, bliver de ændringerne straks synlige for brugeren, når dataene i formularen opdateres, når posten er blevet gemt.  
  
 Selvom kontrolelementet for forretningsprocesforløb i formularen ikke indeholder nogen direkte mulighed for programmering på klientsiden, anvendes ændringer, der foretages med forretningsregler eller formularscripts, automatisk på kontrolelementer for forretningsprocesforløb. Hvis du skjuler et felt i en formular, skjules dette felt også kontrolelementet for forretningsprocesforløb. Hvis du angiver en værdi ved hjælp af forretningsregler eller formularscripts, angives denne værdi i forretningsprocesforløbet.  
  
### <a name="concurrent-process-flows"></a>Samtidige procesforløb  
 Med samtidige forretningsprocesforløb kan systemtilpassere konfigurere flere forretningsprocesser og knytte dem til den samme startpost. Brugere kan skifte mellem flere forretningsprocesser, der kører samtidigt, og fortsætte deres arbejde i den procesfase, som de var nået til.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Forretningsprocesforløb i systemet  
 Følgende forretningsprocesforløb er omfattet. Gennemgå systemets forretningsprocesforløb for at forstå, hvordan disse forretningsprocesforløb fungerer:  
  
-   Kundeemne til salgsproces for salgsmulighed  
  
-   Salgsproces for salgsmulighed  
  
-   Telefon til sagsproces  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Flere objekter i forretningsprocesforløb  
 Du kan bruge en forretningsproces for et enkelt objekt, eller den kan omfatte flere objekter. Det kan f.eks være, at du har en proces, der begynder med en salgsmulighed, som derefter bliver til et tilbud, en ordre og derefter en faktura, hvorefter du til sidst kan lukke salgsmuligheden.  
  
 Du kan designe forretningsprocesforløb, som sammenfatter posterne for op til fem forskellige objekter i én samlet proces, således at personer, der bruger appen, kun skal koncentrere sig om forløbet af deres proces og ikke om, hvilket objekt de arbejder i. De kan nemmere navigere mellem de tilknyttede objektposter.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Der er flere tilgængelige forretningsprocesforløb pr. objekt  
 Ikke alle brugere i en organisation følger de samme processer, og forskellige betingelser kan gøre det nødvendigt at anvende en anden proces. Du kan have op til 10 aktive forretningsprocesforløb pr. objekt for at have relevante processer til forskellige situationer.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Bestemme, hvilke forretningsprocesforløb der anvendes  
 Du kan knytte forretningsprocesforløb til sikkerhedsroller, så det kun er personer med de pågældende sikkerhedsroller, der kan se eller bruge dem. Du kan også angive rækkefølgen for forretningsprocesforløb, så du kan styre, hvilke forretningsprocesforløb der angives som standard. Det fungerer på samme måde, som når du definerer flere formularer for et objekt.  
  
 Når en bruger opretter en ny objektpost, filtreres listen over tilgængelige aktive forretningsprocesdefinitioner af brugerens sikkerhedsrolle. Den første aktiverede forretningsprocesdefinition, der er tilgængelig for brugerens sikkerhedsrolle i henhold til listen over procesrækkefølgen, er den værdi, der anvendes som standard. Hvis der findes mere end én tilgængelig aktiv forretningsprocesdefinition, kan brugerne indlæse en anden definition fra dialogen Skift proces. Når du skifter processer, placeres den proces, der i øjeblikket gengives, i baggrunden og erstattes af den valgte proces, men den opretholder sin status og kan flyttes tilbage igen. Hver post kan have flere tilknyttede procesforekomster (hver til en anden forretningsprocesforløbsdefinition, op til 10). Kun ét forretningsprocesforløb gengives ved indlæsning af formularen. Når en bruger anvender en anden proces, indlæses denne proces muligvis kun som standard for den pågældende bruger.  
  
 Hvis du vil sikre, at en forretningsproces indlæses som standard for alle brugere (funktionsmåde svarende til "fastgørelse"-processen), kan et brugerdefineret klient-API-script (webressource) tilføjes ved indlæsning af formularen, som specifikt indlæser en eksisterende forretningsprocesforekomst baseret på forretningsprocessens definitions-id. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Overvejelser i forbindelse med forretningsprocesforløb  
 Du kan kun angive forretningsprocesforløb for de objekter, som understøtter dem. Du skal også være opmærksom på begrænsningerne for antallet af processer, faser og trin, der kan tilføjes.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Forretningsprocesforløb, der kalder en arbejdsproces  
 Du kan kalde anmodede arbejdsprocesser inde i et forretningsprocesforløb. Du kan konfigurere dette fra den ny designfunktion for forretningsprocesforløb ved at trække en arbejdsproceskomponent, til en procesfase eller sektionen Globale arbejdsprocesser. Du kan finde flere oplysninger om brug af arbejdsprocesser i forretningsprocesforløb i [Blog: Automatisering af forretningsprocesforløb i Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Når du inkluderer en arbejdsproces, der skal udløses ved afslutning af en fase i dit forretningsprocesforløb, og den pågældende fase er den sidste fase i forløbet, giver designeren det indtryk, at arbejdsprocessen bliver udløst, når fasen er fuldført. Arbejdsprocessen udløses imidlertid ikke, fordi der ikke finder en faseovergang sted. Du modtager ikke en advarsel eller fejlmeddelelse, der forhindrer, at du inkluderer arbejdsprocessen i fasen. Når en bruger arbejder med forretningsprocesforløbet, resulterer afslutning eller afbrydelse af processen ikke i en faseovergang, og derfor udløses arbejdsprocessen ikke. Overvej følgende eksempler:  
  
-   Når du har oprettet et forretningsprocesforløb med to faser, opretter S1 forbindelse til S2 med en arbejdsproces på fase S2 og angive udløseren til **Faseafslutning**.  
  
-   Når du har oprettet et forretningsprocesforløb med tre faser, opretter S1 forbindelse til S2 og derefter forgrener S2 sig til S3. Det omfatter en arbejdsproces på S2 og angiver udløseren til **Faseafslutning**.  
  
 Arbejdsprocessen udløses ikke i nogen af tilfældene. Hvis du vil løse dette problem, kan du tilføje en global arbejdsproces og tilføje den arbejdsproces, der skal udløses, så den udløses for forretningsprocessen i stedet for et trin i forløbet. Du kan angive en udløser for en Global arbejdsproces til Proces afbrudt eller Proces fuldført for at udløse arbejdsprocessen, når en bruger afbryder eller er fuldfører forretningsprocessen.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Objekter, som kan anvende forretningsprocesforløb  
 Alle brugerdefinerede objekter kan bruge forretningsprocesforløb. Følgende standardobjekter kan også bruge forretningsprocesforløb:  
  
-   Firma  
-   Aftale  
-   Kampagne  
-   Kampagneaktivitet  
-   Kampagnerespons  
-   Konkurrent  
-   Kontaktperson  
-   Mail  
-   Berettigelse  
-   Fax  
-   Sag  
-   Faktura  
-   Potentiel kunde  
-   Brev  
-   Marketingliste  
-   Salgsmulighed  
-   Telefonopkald  
-   Produkt  
-   Prislisteelement  
-   Tilbud  
-   Gentaget aftale  
-   Salgsmateriale  
-   Social aktivitet  
-   Rækkefølge  
-   Bruger  
-   Opgave  
-   Gruppe  
  
 Hvis du vil aktivere et brugerdefineret objekt for forretningsprocesforløb, skal du markere afkrydsningsfeltet **forretningsprocesforløb (felter oprettes)** i objektdefinitionen. Bemærk, at du ikke kan fortryde denne handling.  
  
> [!NOTE]
>  Hvis du navigerer til fasen i forretningsprocesforløbet, der indeholder objektet `Social Activity`, og vælger knappen **Næste fase**, kan du se indstillingen **Opret**. Når du vælger **Opret**, indlæses formularen **Social aktivitet**. Men da `Social Activity` ikke er gyldig for `Create` fra appens brugergrænseflade, kan du ikke gemme formularen, og du får vist fejlmeddelelsen "Uventet fejl".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Maksimalt antal processer, faser og trin  
 Hvis du vil sikre en acceptabel ydeevne samt brugervenligheden af brugergrænsefladen, er der visse begrænsninger, du skal være opmærksom på, når du planlægger at bruge forretningsprocesforløb:  
  
-   Der kan ikke være flere end 10 aktiverede forretningsprocesforløb pr. objekt.  
  
-   Hver proces kan ikke indeholde mere end 30 faser.  
  
-   Processer for flere objekter kan ikke indeholde mere and fem objekter.
  
## <a name="business-process-flow-entity-customization-support"></a>Understøttelse af tilpasning af objekter i forretningsprocesforløb 

Objekter i forretningsprocesforløb, som blev introduceret i Dynamics 365 (online) version 9.0, kan vises i systemet, så objektpostdata kan gøres tilgængelige i gitre, visninger, diagrammer og dashboards. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Bruge objektposter i forretningsprocesforløb med gitre, visninger, diagrammer og dashboards

Med forretningsprocesforløb tilgængelige som et objekt kan du nu bruge avancerede søgninger, visninger, diagrammer og dashboards, hvor kilden er data i forretningsprocesforløb for et bestemt objekt, f.eks. et kundeemne eller en salgsmulighed. Systemadministratorer og systemtilpassere kan oprette brugerdefinerede gitre, visninger, diagrammer og dashboards til forretningsprocesforløb svarende til dem, der oprettes i alle andre objekter.

Forretningsprocesforløb som f.eks. **Kundeemne til salgsproces for salgsmulighed** vises som et objekt, der kan tilpasses, i løsningsoversigten.

![Løsningsoversigt med procesobjektet Kundeemne til salgsmulighed](media/bpf-lead-solution-explorer.png)

Hvis du vil have adgang til en standardvisning af et forretningsprocesforløb, skal du åbne løsningsoversigten, udvide **Objekter** > udvide den ønskede proces, f.eks. **Kundeemne til salgsproces for salgsmulighed**, vælge **Visninger** og derefter vælge den visning, du ønsker.

Der findes flere standardvisninger, som du kan få vist som et diagram, f.eks. visningen **Aktiv salgsproces for salgsmulighed**. 

![Visningen Aktiv salgsproces for salgsmulighed](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagere med et objekt i et forretningsprocesforløb fra en arbejdsproces
Du kan også interagere med et objekt i et forretningsprocesforløb fra en arbejdsproces. Du kan f.eks. oprette en arbejdsproces for objektposten for forretningsprocesforløbet for at ændre den aktive fase, når et felt i objektposten Salgsmulighed bliver opdateret. Du kan finde flere oplysninger om, hvordan du gør dette, under [Automatisere faser i et forretningsprocesforløb ved hjælp af arbejdsprocesser](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).

### <a name="run-business-process-flows-offline"></a>Køre forretningsprocesforløb offline

Du kan anvende forretningsprocesforløb offline, hvis følgende betingelser er opfyldt:

- Forretningsprocesflowet bruges fra en Power Apps-app.
- Power Apps-appen er aktiveret til offline brug.
- Forretningsprocesforløbet har et enkelt objekt.

De tre kommandoer, der specifikt er tilgængelige for et forretningsprocesforløb, når Power Apps-appen er offline, er:

- Næste fase
- Forrige fase
- Angiv aktiv fase

### <a name="limitations-of-using-business-process-flow-entities"></a>Begrænsninger for brug af objekter i et forretningsprocesforløb

- I øjeblikket kan oprette du ikke oprette brugerdefinerede formularer for objekter baseret på et forretningsprocesforløb.
- Hvis en løsning indeholder et objekt i et forretningsprocesforløb, skal dette objekt føjes til løsningen manuelt, før du kan eksportere det. I modsat fald medtages objektet i forretningsprocesforløbet ikke i løsningspakken. Flere oplysninger: [Oprette og redigere objekter](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-entities-solution-explorer).
- Tilføjelse af procesobjektet i en modelbaseret app kan resultere i begrænset funktionalitet. Få mere at vide om [oprettelse og redigering af forretningsprocesforløb](https://docs.microsoft.com/power-automate/create-business-process-flow). 

### <a name="next-steps"></a>Næste trin  
 [Se en kort video (4:49) om forretningsprocesforløb](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Oprette et forretningsprocesforløb](create-business-process-flow.md)   
 [Optimer forretningsprocesforløb med forgrening](enhance-business-process-flows-branching.md) <br/>
 [Hvidbog: Procesgodkendelse med Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
