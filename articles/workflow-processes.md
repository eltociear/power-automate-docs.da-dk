---
title: Klassiske arbejdsprocesser i Common Data Service | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2bb689f9dff55e8313a22d89efd8fa76eca4fb50
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74369703"
---
# <a name="classic-common-data-service-workflows"></a>Klassiske Common Data Service-arbejdsprocesser 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Arbejdsprocesser automatiserer forretningsprocesser uden en brugergrænseflade. Arbejdsprocesser bruges normalt til at starte de automatiseringer, der ikke kræver brugerinput.

> [!IMPORTANT]
> Brug flow i stedet for klassiske arbejdsprocesser til at automatisere dine forretningsprocesser. Flere oplysninger: [Erstat klassiske arbejdsprocesser i Common Data Service med flow](replace-workflows-with-flows.md)  
  
 Hver arbejdsproces er knyttet til et enkelt objekt. Når du konfigurerer arbejdsprocesser, er der fire primære områder, du skal have med i dine overvejelser:  
  
-   Hvornår du skal starte dem?  
  
-   Skal de køre som en realtidsarbejdsproces eller en arbejdsproces i baggrunden?  
  
-   Hvilke handlinger skal de udføre?  
  
-   Under hvilke betingelser skal handlingerne udføres?  
  
 I dette emne introduceres, hvordan du finder arbejdsprocesser, og hvornår du skal starte dem, og om de skal køre i realtid eller som baggrundsjob. Du kan få flere oplysninger om de handlinger, de skal udføre, og betingelserne i [Konfiguration af arbejdsprocesser](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Hvor tilpasses arbejdsprocesser?  
 Du kan få vist arbejdsprocesserne i din organisation ved at få vist noden **Processer** i **standardløsningen** og filtrere på de processer, der har **kategorien** **Arbejdsproces**.  
  
 ![Processer, der er filtreret efter arbejdsproces i Dynamics 365](media/workflow-processes-filtered.PNG "Processer, der er filtreret efter arbejdsproces i Dynamics 365")  
  
 Afhængigt af hvordan appen er bygget, kan brugere oprette eller ændre deres arbejdsprocesser i appen. 
 
Udviklere kan oprette arbejdsprocesser ved hjælp af oplysningerne i [udviklervejledningen til Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions), og de løsninger, som du køber, omfatter muligvis arbejdsprocesser, som du kan ændre.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Egenskaber for arbejdsproces  
 Vælg **Processer** i løsningsoversigten, og klik på **Ny**.  
  
 Når du opretter en arbejdsproces, kræver dialogboksen **Opret proces**, at du angiver tre egenskaber, som alle processerne har:  
  
 ![Oprettelse af en arbejdsproces i Dynamics 365](media/create-workflow.PNG "Oprettelse af en arbejdsproces i Dynamics 365")  
  
 **Procesnavn**  
 Navnet på arbejdsprocessen behøver ikke at være entydigt, men hvis du regner med at have en masse arbejdsprocesser, kan du bruge en navngivningskonvention for at kunne skelne mellem processerne. Du kan anvende standardpræfikser til navnet på arbejdsprocessen. Præfikset kan beskrive funktionen af arbejdsprocessen eller afdelingen i virksomheden. På den måde kan du gruppere lignende elementer på listen over arbejdsprocesser.  
  
 **Kategori**  
 Denne egenskab fastsætter, at dette er en arbejdsproces.  
  
 **Objekt**  
 Hver arbejdsproces skal være angivet til et enkelt objekt. Du kan ikke ændre objektet, når arbejdsprocessen er oprettet.  
  
 **Kør denne arbejdsproces i baggrunden (anbefales)**  
 Denne indstilling vises, når du vælger arbejdsproces som kategori. Indstillingen angiver, om arbejdsprocessen er en i realtid eller kører i baggrunden. Arbejdsprocesser i realtid kører med det samme (synkront), og arbejdsprocesser i baggrunden kører asynkront. De tilgængelige konfigurationsindstillinger afhænger af dit valg til denne indstilling. Arbejdsprocesser i baggrunden tillader vent-betingelser, der ikke er tilgængelige for arbejdsprocesser i realtid. Så længe du ikke bruger disse vent-betingelser, kan du på et senere tidspunkt konvertere arbejdsprocesser i baggrunden til arbejdsprocesser i realtid og arbejdsprocesser i realtid til arbejdsprocesser i baggrunden. Du kan finde flere oplysninger om vent-betingelser i [Angivelse af betingelser for arbejdsproceshandlinger](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Du har også indstillingen **Type** til at angive, om du vil oprette en ny arbejdsproces fra bunden eller vælge at starte fra en eksisterende skabelon. Når du vælger **Ny proces fra en eksisterende skabelon (vælg på listen)** , kan du vælge mellem de tilgængelige arbejdsprocesser, der tidligere er blevet gemt som en processkabelon.  
  
 Når du har oprettet arbejdsprocessen, eller hvis du redigerer en eksisterende, har du følgende yderligere egenskaber:  
  
 ![Fanen Generelt i en arbejdsproces](media/create-workflow-general-tab.PNG "Fanen Generelt i en arbejdsproces")  
  
 **Aktivér som**  
 Du kan vælge **processkabelon** til at oprette et avanceret udgangspunktet for andre skabeloner. Hvis du vælger denne indstilling, når du har aktiveret arbejdsprocessen, anvendes skabelonen ikke, men er i stedet tilgængelig i dialogboksen **Opret proces**, hvis du vælger **Type**: **Ny proces fra en eksisterende skabelon (vælg på liste)**  
  
 Processkabeloner er praktiske, når du har et antal lignende arbejdsprocesser og gerne vil definere dem uden at duplikere den samme logik.  
  
> [!NOTE]
>  Redigering af en processkabelon ændrer ikke funktionsmåderne i andre arbejdsprocesser, der tidligere er oprettet ved hjælp af den pågældende skabelon. En ny arbejdsproces, der er oprettet ved hjælp af en skabelon, er en kopi af indholdet i skabelonen.  
  
 **Tilgængelig til kørsel**  
 Dette afsnit indeholder indstillinger, der beskriver, hvordan arbejdsprocessen er klar til at blive kørt.  
  
 **Kør denne arbejdsproces i baggrunden (anbefales)**  
 Dette afkrydsningsfelt afspejler den indstilling, du valgte, da du oprettede arbejdsprocessen. Indstillingen er deaktiveret, men du kan ændre den i menuen **Handlinger** ved at vælge enten **Konverter til en arbejdsproces i realtid** eller **Konverter til en arbejdsproces i baggrunden**.  
  
 **Som en proces efter behov**  
 Vælg denne indstilling, hvis du vil tillade brugere at køre denne arbejdsproces fra kommandoen **Kør arbejdsproces**.  
  
 **Som en underordnet proces**  
 Vælg denne indstilling, hvis du vil tillade, at arbejdsprocessen skal kunne startes fra en anden arbejdsproces.  
  
 **Opbevaring af arbejdsproces**  
 Dette afsnit indeholder en indstilling til sletning af en arbejdsproces, når udførelsen af arbejdsprocessen er blevet fuldført.  
  
 **Slet automatisk fuldførte arbejdsprocesjob (for at spare plads på harddisken)**  
 Vælg denne indstilling, hvis du vil have, at et fuldført arbejdsprocesjob automatisk slettes.  
  
> [!NOTE]
>  Arbejdsprocesjob slettes ikke umiddelbart efter fuldførelsen, men kort tid efter via en batchproces.  
  
 **Omfang**  
 For objekter, der ejes af brugeren, er indstillingerne **Organisation**, **Overordnet: Underordnede afdelinger**, **Forretningsenhed** eller **Bruger**. For enheder, der ejes af organisationen, er den eneste mulighed **Organisation**.  
  
 Hvis omfanget er **Organisation**, kan arbejdsproceslogikken anvendes for en vilkårlig post i organisationen. I modsat fald kan arbejdsprocessen kun anvendes til et undersæt af poster, der ligger inden for omfanget.  
  
> [!NOTE]
>  Standardværdien for omfang er **Bruger**. Kontrollér, at omfangsværdien er relevant, før du aktiverer arbejdsprocessen.  
  
 **Start, når**  
 Brug indstillingerne i dette afsnit til at angive, hvornår en arbejdsproces skal starte automatisk. Du kan konfigurere en arbejdsproces i realtid til at blive kørt før bestemte hændelser. Dette er en meget effektiv funktion, fordi arbejdsprocessen kan stoppe handlingen, før den finder sted. Flere oplysninger: [Brug af arbejdsprocesser i realtid](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Valgmulighederne er:  
  
- **Post oprettes**  
  
- **Poststatus ændres**  
  
- **Post tildeles**  
  
- **Postfelter ændres**  
  
- **Post slettes**  
  
> [!NOTE]
>  Vær opmærksom på, at de handlinger og betingelser, du definerer for arbejdsprocessen, ikke er klar over, hvornår arbejdsprocessen køres. Hvis du f.eks. definerer en arbejdsproces for at opdatere posten, kan denne handling ikke udføres af en arbejdsproces i realtid, før posten oprettes. En post, der ikke findes, kan ikke opdateres. På samme måde kan en arbejdsproces i baggrunden ikke opdatere en post, der er blevet slettet, selvom du kan definere denne handling for arbejdsprocessen. Det mislykkes, hvis du konfigurerer en arbejdsproces til at udføre en handling, der ikke kan udføres, hvorefter hele arbejdsprocessen mislykkes.  
  
 **Udfør som**  
 Denne indstilling er kun tilgængelig, hvis du har fjernet markeringen af indstillingen **Kør denne arbejdsproces i baggrunden (anbefales)** , da du oprettede arbejdsprocessen, eller hvis du på et senere tidspunkt konverterede en arbejdsproces i baggrunden til en arbejdsproces i realtid.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Sikkerhedskonteksten for arbejdsprocesser  
 Når en arbejdsproces i baggrunden konfigureres som en proces efter behov og startes af en bruger ved hjælp kommandoen **Kør arbejdsproces**, er de handlinger, som arbejdsprocessen kan udføre, begrænset til dem, som brugeren kan udføre på baggrund af de rettigheder og adgangsniveauer, der er defineret af den eller de sikkerhedsroller, der er angivet for brugerens konto.  
  
 Når en arbejdsproces i baggrunden starter på baggrund af en hændelse, fungerer arbejdsprocessen i konteksten af den person, der ejer processen, som regel den person, der oprettede arbejdsprocessen.  
  
 I forbindelse med arbejdsprocesser i realtid har du indstillingen **Udfør som**, og du kan vælge, om arbejdsprocessen skal anvende sikkerhedskonteksten for ejeren af arbejdsprocessen eller den bruger, der har ændret posten. Hvis din arbejdsproces inkluderer handlinger, som alle brugere ikke skal kunne udføre baseret på sikkerhedsbegrænsninger, skal du vælge at få arbejdsprocessen kørt som ejer af arbejdsprocessen.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Aktivér en arbejdsproces  
 Arbejdsprocesser kan kun redigeres, mens de er deaktiveret. Før en arbejdsproces kan bruges manuelt eller anvendes som følge af hændelser, skal den aktiveres. Før en arbejdsproces kan aktiveres, skal den indeholde mindst ét trin. Du kan finde oplysninger om konfiguration af trin i [Konfiguration af arbejdsprocesser](configure-workflow-steps.md)  
  
 En arbejdsproces kan kun aktiveres eller deaktiveres af ejeren af arbejdsprocessen eller af en person, der har rettighed til at **handle på vegne af en anden bruger**, f.eks systemadministratoren.  Årsagen til dette er, at en ondsindet bruger kunne ændre en persons arbejdsproces, uden at vedkommende ville opdage ændringen. Du kan tildele en arbejdsproces, som du ejer, igen ved at ændre ejeren. Dette felt er på fanen **Administration**. Hvis du er ikke systemadministrator, og du har brug for at redigere en arbejdsproces, der ejes af en anden bruger, skal personen deaktivere arbejdsprocessen og tildele den til dig. Når du er færdig med at redigere arbejdsprocessen, kan du tildele arbejdsprocessen tilbage til vedkommende, så den kan blive aktiveret.  
  
 Arbejdsprocesser i realtid kræver, at brugeren har rettigheden **Aktivér processer i realtid**. Da der er større risiko for, at arbejdsprocesser i realtid påvirker systemets ydeevne, bør kun personer, der kan evaluere den potentielle risiko, tildeles denne rettighed.  
  
 Arbejdsprocesser gemmes, når de er aktiveret, så det er ikke nødvendigt at gemme dem, før du aktiverer dem.  
  
## <a name="next-steps"></a>Næste trin  
 [Konfiguration af arbejdsprocesser](configure-workflow-steps.md)  <br/>
[Føj en arbejdsproces efter behov til et forretningsprocesforløb](bpf-add-on-demand-workflow.md) 

