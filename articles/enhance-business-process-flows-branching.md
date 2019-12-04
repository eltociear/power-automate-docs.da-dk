---
title: Optimer forretningsprocesforløb med forgrening med PowerApps | MicrosoftDocs
description: Få mere at vide om, hvordan du bruger forgrening i et forretningsprocesforløb
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 577bad2fa7e0db66c95fae5668c4a576e3c3a2d7
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74365172"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Selvstudium: Optimer forretningsprocesforløb med forgrening
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Forretningsprocesforløb fører dig gennem forskellige faser i salg, marketing eller serviceprocesser, indtil forløbet er fuldført. I simple tilfælde er et lineært forretningsprocesforløb en god mulighed. I mere komplekse scenarier kan du dog forbedre et forretningsprocesforløb med forgreninger. Hvis du har tilladelse til at oprette i forretningsprocesforløb, kan du oprette forretningsprocesforløb med flere forgreninger ved hjælp af logikken `If-Else`. Forgreningsbetingelsen kan være udformet af flere logiske udtryk, der bruger en kombination af operatorerne `AND` eller `OR`. Valg af forgrening sker automatisk, i realtid, baseret på regler, der er defineret i løbet af procesdefinitionen. Når du f.eks. sælger biler, kan du konfigurere et enkelt forretningsprocesforløb, som efter en fælles kvalificeringsfase opdeles i to separate forgreninger på baggrund af en regel (Foretrækker kunden en ny bil eller en brugt bil, er kundens budget over eller under 150.000 osv. ), én forgrening til salg af nye biler og en anden forgrening til salg af brugte biler. Du kan få flere oplysninger om forretningsprocesforløb under [Oversigt over forretningsprocesforløb](business-process-flows-overview.md).  
  
 I følgende diagram vises et forretningsprocesforløb med forgreninger.  
  
 ![Rutediagram, der viser trinnene i bilsalgsprocessen](media/example-car-sales-flow-chart.png "Rutediagram, der viser trinnene i bilsalgsprocessen")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Det har du brug for at vide, når du designer forretningsprocesforløb med forgreninger  
 Vær opmærksom på følgende, når du designer forretningsprocesforløb med forgreningerne:  
  
-   En proces kan maksimalt spænde over fem entydige objekter.  
  
-   Du kan bruge maksimalt 30 faser pr. proces og maksimalt 30 trin pr. fase.  
  
-   Hver forgrening kan bestå af maksimalt fem niveauer.  
  
-   Forgreningsreglen skal være baseret på trinnene i fasen umiddelbart før reglen.  
  
-   Du kan kombinere flere betingelser i en regel ved hjælp af operatoren `AND` eller `OR`, men ikke begge operatorer.  
  
-   Når du definerer et procesforløb, kan du vælge en objektrelation. Denne relation skal være en 1:N-objektrelation (én til mange).  
  
-   Der kan køre mere end én aktiv proces samtidig på den samme datapost.  
  
-   Du kan omarrangere felter (faser, trin, betingelser osv.) i procesforløbet ved at trække og slippe.  
  
-   Når du fletter forgreninger, skal alle peerforgreninger flettes til en enkelt fase. Peerforgreningerne skal enten flettes til en enkelt fase, eller også skal hver peerforgrening afslutte processen. En peerforgrening kan ikke flettes med andre forgreninger og afslutte processen på samme tid.  
  
> [!NOTE]
> - Der kan vendes tilbage til et objekt, der bruges i processen, flere gange (flere lukkede objektløkker).  
> - En proces kan gå tilbage til den forrige fase uanset objekttype. Hvis den aktive fase f.eks. er **Levér tilbud** for en tilbudspost, kan procesbrugere flytte den aktive fase tilbage til fasen **Afgiv tilbud** for en salgsmulighedspost.  
>   
>   Lad os tage et andet eksempel med en proces, der i øjeblikket befinder sig i fasen **Præsenter tilbud** i dit procesforløb: **Kvalificer kundeemne** > **Identificer behov** > **Opret tilbud** > **Præsenter tilbud** > **Afslut**. Hvis det tilbud, der præsenteres for kunden, kræver mere research for at identificere kundens behov, kan brugerne blot vælge fasen **Identificer behov** og vælge **Angiv som aktiv**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Eksempel: Bilsalgsproces med to forgreninger
 
Lad os se nærmere på eksemplet med forretningsprocesforløbet med to forgreninger til salg af nye og brugte biler.  
  
 Først skal vi oprette en ny proces med navnet **Bilsalgsproces**.  
  
1.  [Åbn løsningsoversigten](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg derefter **Processer** i navigationsruden til venstre.  
  
2.  Vælg **Ny** for at oprette en ny proces.  
  
3.  Angiv **kategorien** som **Forretningsprocesforløb**, og vælg **Kundeemne** som det primære **objekt**.  
  
4.  Føj den første fase til den proces, der kaldes **Kvalificer**, og tilføj trinene **Tidsramme for køb** og **Bilpræference**.  
  
5.  Efter den fælles fase **Kvalificer**, opdeles processen i to separate forgreninger ved hjælp af feltet **Betingelse**.  
  
    1.  Konfigurer betingelsesfeltet med regler, der opfylder dine forretningsbehov.  
  
    2.  Du føjer den første forgrening til en fase ved at tilføje et fasefelt på "Ja"-stien i betingelsesfeltet.  
  
    3.  Du tilføjer den anden forgrening, der udføres, når en betingelse ikke opfyldes, ved at tilføje endnu et fasefelt på "Nej"-stien i betingelsesfeltet.  
  
> [!TIP]
>  Du kan tilføje en anden betingelse på "Nej"-stien i et eksisterende betingelsesfelt for at oprette mere komplekse forgreninger.  
  
 ![Billede, der viser den oprettede kvalificeringsfase](media/example-car-sales-qualify-stage.JPG "Billede, der viser den oprettede kvalificeringsfase")  
  
 Hvis **Bilpræference** = **Ny**, forgrenes processen til fasen **Salg af ny bil**, ellers går den til fasen **Salg af brugt bil**  i den anden forgrening, som vist nedenfor.  
  
 ![Billede, der viser fasen Salg af ny bil](media/example-car-sales-new-stage-1.JPG "Billede, der viser fasen Salg af ny bil")  
  
 ![Fasen Salg af brugt bil](media/example-car-sales-pre-owned-stage.JPG "Fasen Salg af brugt bil")  
  
 Når du har fuldført alle trin i fasen **Salg af ny bil** eller **Salg af brugt bil**, vender processen tilbage til det primære forløb med fasen **Levér tilbud**.  
  
 ![Fasen Levér tilbud](media/example-car-sales-deliver-quote-stage.JPG "Fasen Levér tilbud")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Undgå afsløring af oplysninger  
 Forestil dig et forretningsprocesforløb med forgreninger til behandling af en låneanmodning i en bank, som vist nedenfor. De brugerdefinerede objekter, der bruges i faserne, vises i parentes.  
  
 ![Et rutediagram, der viser trinnene i et proceseksempel for at forhindre afsløring af oplysninger](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Et rutediagram, der viser trinnene i et proceseksempel for at forhindre afsløring af oplysninger")  
  
 I dette scenarie skal den udlånsansvarlige i banken have adgang til anmodningsposten, men vedkommende skal ikke have indsigt i undersøgelsen af anmodningen. Ved første øjekast ser det ud til, at vi nemt kan gøre dette ved at tildele den udlånsansvarlige en sikkerhedsrolle, der ikke giver adgang til objektet Undersøgelse. Men lad os se på flere detaljer i eksemplet, og om det virkelig forholder sig sådan.  
  
 Lad os sige, at en kunde anmoder om at låne for over 60.000 USD i banken. Den udlånsansvarlige gennemgår anmodningen i den første fase. Hvis den forgreningsregel, der kontrollerer om det skyldige beløb til banken overstiger $50.000, er opfyldt, er næste trin i processen at undersøge, om anmodningen er falsk. Hvis det bestemmes, at der helt sikkert er tale om en svindelsag, går processen videre til at anlægge sag mod anmoderen. Den udlånsansvarlige bør ikke have indblik i de to undersøgelsesfaser, da vedkommende ikke har adgang til undersøgelsesobjektet.  
  
 Men hvis den udlånsansvarlige åbner posten Anmodning, vil alle kunne se hele processen fra start til slut. Ikke blot vil den udlånsansvarlige kunne se fasen med undersøgelse af svindelsagen, men hun kan også identificere resultatet af undersøgelsen, da hun også vil være i stand til at se fasen med sagsanlæg i processen. Vedkommende kan også få vist trinene i undersøgelsesfaserne ved at vælge den pågældende fase. Selvom den udlånsansvarlige ikke kan se dataene eller statussen for fuldførelse af trin, kan hun identificere de potentielle tiltag, der er blevet taget mod indsenderen af anmodningen i undersøgelses- og retsagsfasen.  
  
 I dette procesforløb kan den udlånsansvarlige se faserne med undersøgelsen af svindelen og anlæggelsen af retssagen, hvilket udgør uretmæssig offentliggørelse af oplysninger. Vi anbefaler, at du er opmærksom på de oplysninger, der kan blive offentliggjort på grund af forgrening. I vores eksempel kan processen opdeles i to separate processer, én for anmodningsbehandlingen og én for undersøgelsen af svindelen, for at forhindre afsløring af oplysninger. Processen for den udlånsansvarlige ser ud på følgende måde:  
  
 ![Et rutediagram, der viser yderligere trin i processen for at forhindre offentliggørelse af oplysninger](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Et rutediagram, der viser yderligere trin i processen for at forhindre offentliggørelse af oplysninger")  
  
 Processen for undersøgelsen foregår separat og indeholder følgende faser:  
  
 ![Et rutediagram, der viser trinnene i en undersøgelsesproces i forbindelse med sager om offentliggørelse af oplysninger](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Et rutediagram, der viser trinnene i en undersøgelsesproces i forbindelse med sager om offentliggørelse af oplysninger")  
  
 Du skal angive en arbejdsproces for at synkronisere godkend/afvis-beslutningen fra posten Undersøgelse til posten Anmodning.  
  
### <a name="next-steps"></a>Næste trin  
 [Opret et forretningsprocesforløb](create-business-process-flow.md)   
 [Opret brugerdefineret forretningslogik via processer](guide-staff-through-common-tasks-processes.md)   
 
