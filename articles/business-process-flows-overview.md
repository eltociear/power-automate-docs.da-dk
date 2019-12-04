---
title: Oversigt over forretningsprocesforløb | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
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
ms.openlocfilehash: 5ca4e1698ec3196f90d6765fc52d26ddbb1eb591
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74356616"
---
# <a name="business-process-flows-overview"></a>Oversigt over forretningsprocesforløb
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Du kan hjælpe med at sikre, at personer angiver data på en ensartet måde og følger de samme trin, hver gang de arbejder med en kunde, ved at oprette et forretningsprocesforløb. Du kan f.eks. oprette et forretningsprocesforløb, hvis du vil have alle til at håndtere anmodninger om kundeservice på samme måde, eller hvis medarbejderne skal have godkendt en faktura, før de afgiver en ordre. Forretningsprocesforløb bruger den samme underliggende teknologi som andre processer, men de funktioner, de indeholder, er meget forskellige fra andre funktioner, der bruger processer. Du kan få mere at vide om, hvordan du opretter eller redigerer en forretningsproces, under [Opret et forretningsprocesforløb](create-business-process-flow.md).  
  
 [Se en kort video (4:49) om forretningsprocesforløb.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Hvorfor bruge forretningsprocesforløb?  
Forretningsprocesforløb indeholder en vejledning i, hvordan man får arbejdet fra hånden. De leverer en strømlinet brugeroplevelse, der fører personer gennem de processer, deres organisation har defineret for interaktioner, der skal føre til en konklusion af en slags. Denne brugeroplevelse kan tilpasses, så personer med forskellige sikkerhedsroller kan have en oplevelse, der er bedst egnet til det arbejde, de laver.  
  
 Brug forretningsprocesforløb til at definere et sæt trin, der skal følges for at opnå det ønskede resultat. Disse trin indeholder en visuel indikator, der fortæller personer, hvor de befinder sig i forretningsprocessen. Forretningsprocesforløb reducerer behovet for uddannelse, fordi nye brugere ikke behøver at fokusere på, hvilket objekt de skal bruge. De kan lade processen vejlede dem. Du kan konfigurere forretningsprocesforløb for at understøtte fælles salgsmetoder, der kan hjælpe dine salgsgrupper med at opnå bedre resultater. Forretningsprocesforløb til servicegrupper kan hjælpe nye medarbejdere med at komme i gang hurtigere og undgå fejl, der kan resultere i utilfredse kunder.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>Hvad kan forretningsprocesforløb?  
 Med forretningsprocesforløb kan du definere et sæt af *faser* og *trin*, som derefter vises i et kontrolelement øverst i formularen.  
  
 ![Forretningsproces med faser](media/business-process-stages.png "Forretningsproces med faser")  
  
 Hver fase indeholder en gruppe trin. Hvert trin repræsenterer et felt, hvor data kan angives. Personer går videre til den næste fase ved hjælp af knappen **Næste fase**. Du kan gøre et trin obligatorisk, så brugerne skal indtaste data i det tilsvarende felt, før de kan fortsætte til næste fase. Dette kaldes ofte fasestyret.  
  
 Forretningsprocesforløb synes relativt simple sammenlignet med andre typer processer, fordi de ikke indeholder nogen betinget forretningslogik eller automatisering ud over at levere en strømlinet oplevelse til dataindtastning og styring af registrering af faser. Når du kombinerer dem med andre processer og tilpasninger, kan de dog spille en vigtig rolle og f.eks. spare tid, reducere omkostningerne til oplæring og øge forankringen hos brugerne.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Forretningsprocesforløb integreret med andre tilpasninger  
 Når du eller dine brugere indtaster data ved hjælp af forretningsprocesforløb, anvendes dataændringerne også til formularfelter, så en eventuel automatisering, der leveres af forretningsregler eller formularscripts, kan anvendes med det samme. Trin kan tilføjes, der angiver værdier for felter, der er ikke til stede i formularen, og disse felter vil blive føjet til objektmodellen `Xrm.Page`, der bruges til formularscripts. Alle arbejdsprocesser, der er igangsat af ændringer af felter, der er inkluderet i et forretningsprocesforløb, anvendes, når dataene i formularen gemmes. Hvis automatiseringen anvendes af en arbejdsproces i realtid, bliver ændringerne med det samme synlige for brugeren, når dataene i formularen opdateres, når posten er blevet gemt.  
  
 Selvom kontrolelementet for forretningsprocesforløbet i formularen ikke giver nogen direkte programmeringsmuligheder på klientsiden, anvendes ændringerne af forretningsregler eller formularscripts automatisk for kontrolelementer for forretningsprocesforløb. Hvis du skjuler et felt i en formular, skjules feltet også i kontrolelementet for forretningsprocesforløbet. Hvis du angiver en værdi ved hjælp af forretningsregler eller formularscripts, angives denne værdi i forretningsprocesforløbet.  
  
### <a name="concurrent-process-flows"></a>Samtidige procesforløb  
 Samtidige forretningsprocesforløb gør det muligt at konfigurere flere forretningsprocesser og knytte dem til den samme startpost. Brugerne kan skifte mellem flere forretningsprocesser, der kører samtidigt, og genoptage deres arbejde i den fase af processen, som de var i gang med.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Forretningsprocesforløb for systemer  
 Følgende forretningsprocesforløb er inkluderet. Gennemse disse forretningsprocesforløb for systemer for at forstå, hvordan forretningsprocesforløb fungerer:  
  
-   Kundeemne til salgsproces for salgsmulighed  
  
-   Salgsproces for salgsmulighed  
  
-   Proces for opkald til kundeemne  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Flere objekter i forretningsprocesforløb  
 Du kan bruge et forretningsprocesforløb for et enkelt objekt eller over flere objekter. Du kan f.eks. have en proces, der begynder med en salgsmulighed, og derefter fortsætter med et tilbud, en ordre og derefter en faktura, før der til sidst returneres for at lukke salgsmuligheden.  
  
 Du kan designe forretningsprocesforløb, der sammenknytter poster for op til fem forskellige objekter i en enkelt proces, så de personer, der benytter appen, kan fokusere på flowet af deres proces, i stedet for på hvilket objekt de arbejder på. De kan nemmere navigere mellem relaterede objektposter.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Der findes flere forretningsprocesforløb pr. objekt  
 Ikke alle brugere i en organisation kan følge den samme proces, og forskellige betingelser kan kræve, at der anvendes en anden proces. Du kan have op til 10 aktive forretningsprocesforløb pr. objekt for at have relevante processer til forskellige situationer.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Kontrollér, hvilke forretningsprocesforløb der anvendes  
 Du kan knytte forretningsprocesforløb til sikkerhedsroller, så kun personer med disse sikkerhedsroller kan få vist eller bruge dem. Du kan også angive rækkefølgen af forretningsprocesforløb, så du kan styre, hvilke forretningsprocesforløb der angives som standard. Dette fungerer på samme måde, som flere formularer for et objekt defineres.  
  
 Når en medarbejder opretter en ny objektpost, filtreres listen over tilgængelige aktive forretningsprocesdefinitioner af brugerens sikkerhedsrolle. Den første aktiverede forretningsprocesdefinition, der er tilgængelig for brugerens sikkerhedsrolle i henhold til proceslisten, anvendes som standard. Hvis mere end én aktiv forretningsprocesdefinition er tilgængelig, kan brugerne indlæse en anden fra dialogboksen Skift proces. Når der skiftes processer, går den, der gengives i øjeblikket, i baggrunden og erstattes af den valgte, men processen beholder sin tilstand, og der kan skiftes til den igen. Hver post kan have flere procesforekomster tilknyttet (for forskellige forretningsprocesforløbsdefinitioner, op til 10 alt). Kun ét forretningsprocesforløb gengives ved indlæsning af formularen. Når en bruger anvender en anden proces, indlæses denne proces muligvis kun som standard for den pågældende bruger.  
  
 Hvis du vil sikre, at en forretningsproces som standard indlæses for alle brugere (funktionsmåden svarer til at "fastgøre" processen), kan et brugerdefineret API-klient-script (webressource) føjes til indlæsningen af formularen, som specifikt indlæser en eksisterende forekomst af en forretningsproces, der er baseret på id'et for forretningsprocesdefinitionen. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Overvejelser i forbindelse med forretningsprocesforløb  
 Du kan kun definere forretningsprocesforløb for de objekter, der understøtter dem. Du skal også være opmærksom på grænserne for antallet af processer, faser og trin, der kan tilføjes.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Forretningsprocesforløb, der kalder en arbejdsproces  
 Du kan kalde arbejdsprocesser efter behov inde i et forretningsprocesforløb. Du konfigurerer dette fra det nye forretningsprocesforløb ved at trække en arbejdsproceskomponent til en fase i processen eller til afsnittet med globale arbejdsprocesser. Du kan finde flere oplysninger om brug af arbejdsprocesser i forretningsprocesforløb i [Blog: Automatisering af forretningsprocesforløb i Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Når du medtager en arbejdsproces, som du vil udløse ved registrering af en fase i forretningsprocesforløbet, og denne fase er det sidste trin i forløbet, giver designeren det indtryk, at arbejdsprocessen udløses, når den pågældende fase er afsluttet. Arbejdsprocessen udløses dog ikke, fordi en faseovergang ikke finder sted. Du modtager ikke en advarsel eller fejl, der forhindrer dig i at inkludere arbejdsprocessen i fasen. Når en bruger interagerer med forretningsprocesforløbet, resulterer afslutning eller annullering af processen ikke i en faseovergang, og arbejdsprocessen udløses derfor ikke. Overvej følgende eksempler:  
  
-   Du opretter en forretningsproces med to faser, F1 er forbundet med F2 med en arbejdsproces i F2, og angiver udløseren til **Faseafslutning**.  
  
-   Du opretter en forretningsproces med tre faser, F1 er forbundet med F2, hvorefter F2 forgrenes til F3. Du inkluderer en arbejdsproces i F2 og angiver udløseren til **Faseafslutning**.  
  
 Arbejdsprocessen udløses ikke i nogen af tilfældene. Du kan løse dette problem ved at tilføje en global arbejdsproces og føje den arbejdsproces, du vil have udløst til den globale arbejdsproces, så arbejdsprocessen udløses for forretningsprocessen frem for en fase i processen. Du kan angive udløseren for en global arbejdsproces til Proces afbrudt eller Proces fuldført for at udløse arbejdsprocessen, når en bruger afbryder eller fuldfører forretningsprocessen.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Objekter, der kan bruge forretningsprocesforløb  
 Alle brugerdefinerede objekter kan bruge forretningsprocesforløb. Følgende standardobjekter kan også bruge forretningsprocesforløb:  
  
-   Konto  
-   Aftale  
-   Kampagne  
-   Kampagneaktivitet  
-   Kampagnerespons  
-   Konkurrent  
-   Kontakt  
-   Mail  
-   Berettigelse  
-   Fax  
-   Case  
-   Faktura  
-   Kundeemne  
-   Brev  
-   Marketingliste  
-   Salgsmulighed  
-   Telefonopkald  
-   Produkt  
-   Prislisteelement  
-   Tilbud  
-   Tilbagevendende aftale  
-   Salgsmateriale  
-   Social aktivitet  
-   Ordre  
-   Bruger  
-   Opgave  
-   Team  
  
 Du aktiverer et brugerdefineret objekt for et forretningsprocesforløb ved at markere afkrydsningsfeltet **Forretningsprocesforløb (felter oprettes)** i definitionen af objektet. Bemærk, at denne handling ikke kan fortrydes.  
  
> [!NOTE]
>  Hvis du navigerer til den fase i forretningsprocesforløbet, der indeholder objektet `Social Activity` og vælger knappen **Næste fase**, får du vist indstillingen **Opret**. Når du vælger **Opret**, indlæses formularen **Social aktivitet**. Men eftersom `Social Activity` ikke er gyldig for `Create` fra appens brugergrænseflade, kan du ikke gemme formularen, og du får vist fejlmeddelelsen: "Uventet fejl".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Det maksimale antal processer, faser og trin  
 Der er nogle begrænsninger, du skal være opmærksom på, når du planlægger at bruge forretningsprocesforløb, for at sikre en acceptabel ydeevne og anvendelighed af brugergrænsefladen:  
  
-   Der kan ikke være mere end 10 aktiverede forretningsprocesforløb pr. objekt.  
  
-   Hver proces kan ikke indeholde mere end 30 faser.  
  
-   Processer med flere objekter kan ikke indeholde mere end fem objekter.
  
## <a name="business-process-flow-entity-customization-support"></a>Understøttelse af objekttilpasning i forretningsprocesforløb 

Objekter i forretningsprocesforløb blev introduceret i Dynamics 365 (online), version 9.0-opdateringen og kan blive vist i systemet, så objektpostdata kan blive gjort tilgængelige i gitre, visninger, diagrammer og dashboards. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Brug af objektposter i forretningsprocesforløb sammen med gitre, visninger, diagrammer og dashboards

Det faktum, at forretningsprocesforløb er tilgængelige som et objekt, betyder, at du kan bruge avancerede søgninger, visninger, diagrammer og dashboards fra forretningsprocesfoløbsdataene for et givet objekt, f.eks. et kundeemne eller en salgsmulighed. Systemadministratorer og -tilpassere kan oprette brugerdefinerede procesforløbsgitre, visninger, diagrammer og dashboards, der svarer til dem, der er oprettet med et hvilken som helst anden objekt.

Forretningsprocesforløb, f.eks **Kundeemne til salgsproces for salgsmulighed**, vises som et objekt, der kan tilpasses i løsningsoversigten.

![Løsningsoversigt med processen fra kundeemne til salgsmulighed](media/bpf-lead-solution-explorer.png)

Du kan få adgang til en standardvisning af et forretningsprocesforløb ved at åbne løsningsoversigten, udvide **Objekter** > udvide den relevante proces, f.eks. **Kundeemne til salgsproces for salgsmulighed**, og derefter vælge **Visninger**  og den relevante visning.

Flere standardvisninger er tilgængelige, som du kan få vist som et diagram, f.eks **salgsprocessen for aktive salgsmuligheder**. 

![Visning af salgsprocessen for aktive salgsmuligheder](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interager med et objekt i et forretningsprocesforløb fra en arbejdsproces
Du kan også interagere med et objekti et forretningsprocesforløb fra en arbejdsproces. Du kan f.eks. oprette en arbejdsproces for objektposten for forretningsprocesforløbet for at ændre den aktive fase, når et felt i objektposten Salgsmulighed bliver opdateret. Du kan finde flere oplysninger om, hvordan du gør dette, under [Automatiser faser i et forretningsprocesforløb ved hjælp af arbejdsprocesser](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Begrænsninger ved brug af objekter i forretningsprocesforløb

- Du kan i øjeblikket ikke oprette brugerdefinerede formularer for objekter, der er baseret på et forretningsprocesforløb.
- Hvis en løsning indeholder et objekt i et forretningsprocesforløb, skal dette objekt føjes til løsningen manuelt, før du kan eksportere det. I modsat fald medtages objektet i forretningsprocesforløbet ikke i løsningspakken. Flere oplysninger: [Tilføj løsningskomponenter](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Næste trin  
 [Se en kort video (4:49) om forretningsprocesforløb.](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Opret et forretningsprocesforløb](create-business-process-flow.md)   
 [Optimer forretningsprocesforløb med forgrening](enhance-business-process-flows-branching.md) <br/>
 [Whitepaper: Aktivering af processen med Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
