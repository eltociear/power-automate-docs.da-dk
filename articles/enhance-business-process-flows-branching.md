---
title: Styrk forretningsprocesforløb med forgrening med Power Apps | Microsoft Docs
description: Lære at bruge forgrening i en forretningsprocesforløb
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
ms.openlocfilehash: 821d06ec1fe4efcff4296f9e1bfb63f2b7503790
ms.sourcegitcommit: 9ee79e5b559429dc0e772b6fed763856dc8b51ee
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/30/2020
ms.locfileid: "3518047"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Selvstudium: Optimer forretningsprocesforløb med forgrening


Forretningsprocesforløb fører dig gennem forskellige faser af salgs-, marketing- og serviceprocesser hen mod afslutning. I simple sager er et lineært forretningsprocesforløb en god mulighed. I mere komplekse scenarier kan du forbedre en forretningsprocesforløb med forgrening. Hvis du har tilladelse til oprettelse i forretningsprocesforløb, kan du oprette forretningsprocesforløb med flere grene ved hjælp af `If-Else`-logik. Forgreningsbetingelsen kan være dannet af flere logiske udtryk, der bruger en kombination af `AND`- eller `OR`-operatorer. Forgreningsudvælgelsen foretages automatisk i realtid, baseret på regler, der angives under definitionen af processen. Hvis du f.eks. sælger biler, kan du konfigurere et enkelt forretningsprocesforløb, som efter en fælles kvalifikationsfase opdeles i to adskilte forgreninger på grundlag af en regel (foretrækker kunden en ny bil eller en brugt bil, er budgettet over eller under $20.000 osv. ), én gren for salg af nye biler og en anden for salg af brugte biler. Du kan finde flere oplysninger om forretningsprocesforløb i [Oversigt over forretningsprocesforløb](business-process-flows-overview.md).  
  
 Følgende diagram viser et forretningsprocesforløb med forgreninger.  
  
 ![Rutediagram, der viser trinnene i bilsalgsprocessen](media/example-car-sales-flow-chart.png "Rutediagram, der viser trinnene i bilsalgsprocessen")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Hvad du skal vide, når du udformer forretningsprocesforløb med forgreninger  
 Vær opmærksom på følgende oplysninger, når du designer forretningsprocesforløb med forgreninger:  
  
-   En proces kan strække sig over højst 5 unikke objekter.  
  
-   Du kan bruge op til 30 faser pr. proces og højst 30 trin pr. fase.  
  
-   Hver gren kan have en dybde på højst 5 niveauer.  
  
-   Forgreningsreglen skal være baseret på trinene i fasen umiddelbart foran den.  
  
-   Du kan kombinere flere betingelser i en regel ved hjælp af `AND`-operatoren eller `OR`-operatoren, men ikke begge operatorer.  
  
-   Når du definerer et procesforløb, kan du vælge en objektrelation. Denne relation skal være en 1:N-objektrelation (en-til-mange).  
  
-   Mere end én aktiv proces kan køre samtidigt på den samme datapost.  
  
-   Du kan omarrangere felter (faser, trin, betingelser osv.) i procesforløbet ved hjælp af træk og slip.  
  
-   Når du fletter grene, skal alle tilsvarende peer-grene flettes til en enkelt fase. Peer-grenene skal alle enten flettes til en enkelt fase, eller hver peer-gren skal afslutte processen. En peer-gren kan ikke flettes med andre grene og samtidig afslutte processen.

-   Ændringer af klient-API kan ikke udløse evaluering af forgreningsbetingelse, da en forgrening er afhængig af forretningsregler.
  
> [!NOTE]
> - Du kan vende tilbage til et objekt, der bruges i processen, flere gange (flere lukkede objektløkker).  
> - En proces kan gå tilbage til den forrige fase uanset objekttype. Hvis den aktive fase er for eksempel **Giv et tilbud** på en tilbudspost, kan procesbrugere flytte den aktive fase tilbage til **Afgiv tilbud**-fasen i en salgsmulighedspost.  
>   
>   Antag i et andet eksempel, at en proces i øjeblikket er i fasen **Afgiv tilbud** i arbejdsprocessen: **Kvalificer kundeemne** > **Identificer behov** > **Opret tilbud** > **Præsenter tilbud** > **Luk**. Hvis tilbuddet, som forelægges kunden, kræver yderligere research for at identificere kundens behov, kan brugerne blot vælge **Identificer behov** fasen af processen, og vælg **Angiv aktiv**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Eksempel: procesforløb for bilsalg med to grene
 
Lad os se på eksemplet med forretningsprocesforløbet med to grene for salg af nye og brugte biler.  
  
 Først skal vi oprette en ny proces med navnet **Bilsalgsproces**.  
  
1.  [Åbn løsningsoversigten](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg derefter **Processer** i navigationsruden til venstre.  
  
2.  Hvis du vil oprette en ny proces, skal du vælge **Ny**.  
  
3.  Angiv **Kategori** som **Forretningsprocesforløb**, og som det primære **Objekt** vælg **Kundeemne**.  
  
4.  Føj den første fase til den proces, der hedder **Kvalificer**, og tilføj trin, **Tidsramme for køb** og **Bilpræference**.  
  
5.  Efter den fælles **Kvalificer**-fase opdeler vi processen i to separate grene ved hjælp af feltet **Betingelse**.  
  
    1.  Konfigurer betingelsesfeltet med regler, der opfylder dine forretningsbehov  
  
    2.  Du tilføjer den første gren for en fase ved at tilføje feltet Fase i "Ja"-stien i betingelsesfeltet  
  
    3.  Hvis du vil tilføje endnu en gren, der skal køres, når betingelsen ikke er opfyldt, skal du tilføje endnu et Fase-felt i "Nej"-stien i betingelsesfeltet  
  
> [!TIP]
>  Du kan tilføje en anden betingelse i "Nej"-stien for et eksisterende betingelsesfelt for at oprette mere kompleks forgrening.  
  
 ![Billede af den oprettede Kvalificer-fase](media/example-car-sales-qualify-stage.JPG "Billede af den oprettede Kvalificer-fase")  
  
 Hvis **Bilpræference** = **Ny**, forgrenes processen til fasen **Salg af ny bil** og springer ellers til fasen **Salg af en brugt bil** i den anden gren, som vist nedenfor.  
  
 ![Billede, der viser Salg af ny bil-fasen](media/example-car-sales-new-stage-1.JPG "Billede, der viser Salg af ny bil-fasen")  
  
 ![Fasen Salg af en brugt bil](media/example-car-sales-pre-owned-stage.JPG "Fasen Salg af en brugt bil")  
  
 Når du har gennemført alle trin i fasen **Salg af ny bil** eller **Salg af en brugt bil**, vender processen tilbage til hovedforløbet med fasen **Levering af tilbud**.  
  
 ![Levér tilbud-fase](media/example-car-sales-deliver-quote-stage.JPG "Levér tilbud-fase")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Forhindre offentliggørelse af oplysninger  
 Overvej et forretningsprocesforløb med grene til behandling af en låneanmodning i en bank, som vist nedenfor. De brugerdefinerede objekter, der bruges i faserne, vises i parentes.  
  
 ![Rutediagram, der viser trinnene i en eksempelproces for at forhindre offentliggørelse af oplysninger](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Rutediagram, der viser trinnene i en eksempelproces for at forhindre offentliggørelse af oplysninger")  
  
 I dette scenarie skal den udlånsansvarlige i banken have adgang til anmodningsposten, men vedkommende skal ikke have indsigt i undersøgelsen af anmodningen. Umiddelbart ser det ud til, at vi nemt kan gøre dette ved at tildele lånefunktionæren en sikkerhedsrolle, der ikke giver adgang til undersøgelsesobjektet. Men lad os se på eksemplet i flere detaljer og se, om dette også er sandt.  
  
 Lad os antage, at en kunde anmoder banken om et lån på over $60.000. Bankfunktionæren gennemgår anmodningen i første fase. Hvis forgreningsreglen, der kontrollerer, om det skyldige beløb til banken vil overstige $50.000, er opfyldt, er den næste fase i processen at undersøge, om anmodningen er svigagtig. Hvis det fastslås, at der faktisk er tale om svig, fortsætter processen i retning af at gøre retskrav mod låneanmoderen. Den udlånsansvarlige bør ikke have indblik i de to undersøgelsesfaser, da vedkommende ikke har adgang til undersøgelsesobjektet.  
  
 Men hvis den udlånsansvarlige åbner posten Anmodning, vil alle kunne se hele processen fra start til slut. Ikke blot vil den udlånsansvarlige kunne se fasen med undersøgelse af svindelsagen, men hun kan også identificere resultatet af undersøgelsen, da hun også vil være i stand til at se fasen med sagsanlæg i processen. Vedkommende kan også få vist trinene i undersøgelsesfaserne ved at vælge den pågældende fase. Selvom den udlånsansvarlige ikke kan se dataene eller statussen for fuldførelse af trin, kan hun identificere de potentielle tiltag, der er blevet taget mod indsenderen af anmodningen i undersøgelses- og retsagsfasen.  
  
 I dette procesforløb kan lånefunktionæren se faserne Undersøgelse for svig og Juridisk handling, som udgør en ukorrekt offentliggørelse af oplysninger. Det anbefales at tage særligt hensyn til de oplysninger, der kan blive offentliggjort på grund af forgrening. I eksemplet bør processen opdeles i to separate processer, én for behandlingen af anmodningen og en anden for undersøgelsen af svig, for at forhindre afsløring af oplysninger. Processen for lånfunktionæren ser sådan ud:  
  
 ![Rutediagram, der viser yderligere trin i processen for at forhindre offentliggørelse af oplysninger](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Rutediagram, der viser yderligere trin i processen for at forhindre offentliggørelse af oplysninger")  
  
 Processen i forbindelse med undersøgelsen vil være selvstændig og omfatter følgende faser:  
  
 ![Rutediagram, der viser trin i en undersøgelsesproces i sager om offentliggørelse af oplysninger](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Rutediagram, der viser trin i en undersøgelsesproces i sager om offentliggørelse af oplysninger")  
  
 Du skal angive en arbejdsproces for at synkronisere Godkend/afvis afgørelse fra undersøgelsesposten med anmodningsposten.  
  
### <a name="next-steps"></a>Næste trin  
 [Oprette et forretningsprocesforløb](create-business-process-flow.md)   
 [Oprette brugerdefineret forretningslogik med processer](guide-staff-through-common-tasks-processes.md)   
 
