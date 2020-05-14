---
title: Klassiske arbejdsprocesser i Common Data Service | Microsoft Docs
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
ms.openlocfilehash: 53bc2b24da55c8700412b527c7f27934e5515bc4
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298325"
---
# <a name="classic-common-data-service-workflows"></a>Klassiske arbejdsprocesser i Common Data Service 


Arbejdsprocesser automatiserer forretningsprocesser uden en brugergrænseflade. Arbejdsprocesser bruges normalt til at starte de automatiseringer, der ikke kræver brugerinput.

> [!IMPORTANT]
> Brug flow i stedet for klassiske arbejdsprocesser til at automatisere dine forretningsprocesser. Flere oplysninger: [Erstat klassiske Common Data Service-arbejdsprocesser med flows](replace-workflows-with-flows.md)  
  
 Hver arbejdsproces er knyttet til et enkelt objekt. Når du konfigurerer arbejdsprocesser, er der fire primære områder, du skal have med i dine overvejelser:  
  
-   Hvornår skal starte dem?  
  
-   Bør de køre som realtidsarbejdsprocesser eller som arbejdsprocesser i baggrunden?  
  
-   Hvilke handlinger skal de udføre?  
  
-   Under hvilke betingelser skal handlinger udføres?  
  
 I emnet forklares det, hvordan du finder processer i arbejdsprocesser, og det beskrives, hvornår du skal starte dem, og om de skal køre i realtid eller i baggrunden. Du kan finde oplysninger om de handlinger, de skal udføre, samt betingelserne, under [Konfigurere arbejdsprocesser](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Hvor skal du tilpasse processer i arbejdsprocessen?  
 Du kan også se arbejdsprocesserne i din organisation ved at få vist noden **Processer** i **Standardløsning** og filtrere på processer, hvor **Arbejdsproces** er angivet til **Kategori**.  
  
 ![Processer, der er filtreret efter arbejdsproces i Dynamics 365](media/workflow-processes-filtered.PNG "Processer, der er filtreret efter arbejdsproces i Dynamics 365")  
  
 Afhængigt af hvordan appen er bygget, kan brugere oprette eller ændre deres arbejdsprocesser i appen. 
 
Udviklere kan oprette arbejdsprocesser ved hjælp af oplysningerne i [Udviklervejledning til Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions), og løsninger, du køber, kan inkludere arbejdsprocesser, du måske kan ændre.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Arbejdsprocesegenskaber  
 I løsningsoversigten skal du vælge **Processer** og klikke på **Ny**.  
  
 Når du opretter en arbejdsproces i dialogboksen **Opret proces** skal du angive tre egenskaber, som alle processer har:  
  
 ![Oprettelse af en arbejdsproces i Dynamics 365](media/create-workflow.PNG "Oprettelse af en arbejdsproces i Dynamics 365")  
  
 **Procesnavn**  
 Navnet på arbejdsprocessen behøver ikke at være entydigt, men hvis du regner med at have en masse arbejdsprocesser, kan du bruge en navngivningskonvention for at kunne skelne mellem processerne. Det kan være en god idé at benytte standardpræfikser til navnet på arbejdsprocessen. Præfikset beskriver måske funktionen for arbejdsprocessen eller afdelingen i virksomheden. Dette vil hjælpe dig med at gruppere lignende elementer på listen over arbejdsprocesser.  
  
 **Kategori**  
 Denne egenskab fastslår, at dette er en arbejdsproces.  
  
 **Enhed**  
 Hver proces i arbejdsprocessen skal angives for et enkelt objekt. Du kan ikke ændre objektet, når processen i arbejdsprocessen er oprettet.  
  
 **Kør denne arbejdsproces i baggrunden (anbefales)**  
 Denne indstilling vises, når du vælger arbejdsproces som kategori. Denne indstilling bestemmer, om arbejdsprocessen er en arbejdsproces i realtid eller i baggrunden. Arbejdsprocesser i realtid køres straks (synkront), og arbejdsprocesser i baggrunden kører asynkront. De tilgængelige konfigurationsindstillinger afhænger af dit valg for denne indstilling. Arbejdsprocesser i baggrunden tillader vent-betingelser, der ikke er tilgængelige for arbejdsprocesser i realtid. Så længe du ikke bruger disse vent-betingelser, kan du senere konvertere arbejdsprocesser i baggrunden til arbejdsprocesser i realtid og arbejdsprocesser i realtid til arbejdsprocesser i baggrunden. Du kan finde flere oplysninger om vent-betingelser i [Angive betingelser for arbejdsproceshandlinger](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Du kan også bruge indstillingen **Type** til at angive, om du vil oprette en ny arbejdsproces fra bunden eller starte fra en eksisterende skabelon. Når du vælger **Ny proces ud fra en eksisterende skabelon (vælg på listen)**, kan du vælge blandt de tilgængelige processer i arbejdsprocessen, der tidligere er gemt som en processkabelon.  
  
 Når du har oprettet arbejdsprocessen, eller hvis du redigerer en eksisterende, har du følgende yderligere egenskaber:  
  
 ![Fanen Generelt i en arbejdsproces](media/create-workflow-general-tab.PNG "Fanen Generelt i en arbejdsproces")  
  
 **Aktivér som**  
 Du kan vælge **Processkabelon** for at oprette et udgangspunkt for andre skabeloner. Hvis du vælger denne indstilling, anvendes arbejdsprocessen ikke, når du har aktiveret den, men i stedet bliver den tilgængelig og kan vælges i dialogboksen **Opret proces**, hvis du vælger **Type**: **Ny proces ud fra en eksisterende skabelon (vælg på listen)**  
  
 Processkabeloner er praktiske, når du har en række lignende processer i arbejdsprocessen, og du vil definere dem uden at kopiere den samme logik.  
  
> [!NOTE]
>  Hvis du redigerer en processkabelon, ændres funktionsmåden ikke for andre processer i arbejdsprocessen, der tidligere er oprettet ved at bruge den som skabelon. En ny arbejdsproces, der oprettes ved hjælp af en skabelon, er en kopi af indholdet i skabelonen.  
  
 **Kan køres**  
 Dette afsnit indeholder indstillinger, der beskriver, hvordan arbejdsprocessen er tilgængelig til kørsel.  
  
 **Kør denne arbejdsproces i baggrunden (anbefales)**  
 Dette afkrydsningsfelt afspejler den indstilling, du valgte, da du oprettede arbejdsprocessen. Denne indstilling er deaktiveret, men du kan ændre den i menuen **Handlinger** ved at vælge enten **Konvertér til en arbejdsproces i realtid** eller **Konvertér til en arbejdsproces i baggrunden**.  
  
 **Som en proces efter behov**  
 Vælg denne indstilling, hvis du vil give brugerne mulighed for at køre denne arbejdsproces fra kommandoen **Kør arbejdsproces**.  
  
 **Som en underordnet proces**  
 Vælg denne indstilling, hvis arbejdsprocessen skal være tilgængelig og kunne startes fra en anden arbejdsproces.  
  
 **Opbevaring af arbejdsprocesjob**  
 Dette afsnit indeholder en indstilling for sletning af en arbejdsproces, når udførelsen af arbejdsprocessen er fuldført.  
  
 **Slet automatisk fuldførte arbejdsprocesjob (for at spare plads på harddisken)**  
 Vælg denne indstilling, hvis du ønsker, at et fuldført arbejdsprocesjob skal slettes automatisk.  
  
> [!NOTE]
>  Arbejdsprocesjobbene slettes ikke umiddelbart efter fuldførelse, men snart efter via en batchproces.  
  
 **Omfang**  
 I forbindelse med brugerejede objekter er indstillinger **Organisation**, **Overordnet: Underafdelinger**, **Afdeling** eller **Bruger**. I forbindelse med organisationsejede objekter er den eneste indstilling **Organisation**.  
  
 Hvis omfang er **Organisation**, kan arbejdsproceslogikken anvendes på alle poster i organisationen. Ellers kan arbejdsprocessen kun anvendes på et delsæt af poster, er inden for omfanget.  
  
> [!NOTE]
>  Standardværdien for omfang er **Bruger**. Husk at kontrollere, at omfangets værdi er relevant, før du aktiverer arbejdsprocessen.  
  
 **Start når**  
 Brug indstillingerne i denne sektion til at angive, hvornår en arbejdsproces skal starte automatisk. Du kan konfigurere en arbejdsproces i realtid til at blive kørt før bestemte hændelser. Dette er en meget effektiv funktion, fordi arbejdsprocessen kan stoppe handlingen, før den finder sted. Flere oplysninger: [Brug af arbejdsprocesser i realtid](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Valgmulighederne er:  
  
- **Posten er oprettet**  
  
- **Ændringer af poststatus**  
  
- **Posten er tildelt**  
  
- **Ændring af postfelter**  
  
- **Posten er slettet**  
  
> [!NOTE]
>  Husk, at de handlinger og betingelser, du definerer for arbejdsprocessen, ikke ved, hvornår arbejdsprocessen køres. Hvis du f.eks. definerer en arbejdsproces, der skal opdatere posten, kan denne handling ikke udføres af en arbejdsproces i realtid, før posten er oprettet. En post, der ikke findes, kan ikke opdateres. På samme måde kan en arbejdsproces i baggrunden ikke opdatere en post, der er blevet slettet, selvom du kan definere denne handling for arbejdsprocessen. Hvis du konfigurerer en arbejdsproces, der skal udføre en handling, der ikke kan udføres, lykkes den ikke, og hele arbejdsprocessen lykkes ikke.  
  
 **Udfør som**  
 Denne indstilling er kun tilgængelig, hvis du fjernede markeringen i indstillingen **Kør denne arbejdsproces i baggrunden (anbefales)**, da du oprettede arbejdsprocessen, eller hvis du senere har konverteret en arbejdsproces i baggrunden til en arbejdsproces i realtid.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Sikkerhed for processer i arbejdsprocessen  
 Når en arbejdsproces i baggrunden er konfigureret som en anmodet arbejdsproces og startes af en bruger ved hjælp af kommandoen **Kør arbejdsproces**, er de handlinger, den pågældende arbejdsproces kan udføre, begrænset til dem, som brugeren kan udføre ud fra de rettigheder og adgangsniveauer, der er defineret af den eller de sikkerhedsroller, der er angivet for brugerkontoen.  
  
 Når en arbejdsproces i baggrunden startes baseret på en hændelse, som arbejdsprocessen fungerer for, er den person, der ejer den, som regel den person, som har oprettet arbejdsprocessen.  
  
 For arbejdsprocesser i realtid har du indstillingen **Udfør som**, og du kan vælge, om arbejdsprocessen skal anvende sikkerhedskonteksten for ejeren af arbejdsprocessen eller den bruger, der har foretaget ændringer af posten. Hvis arbejdsprocessen indeholder handlinger, som alle brugere ikke kan udføre på baggrund af begrænsninger, skal du vælge at køre arbejdsprocessen som ejeren af arbejdsprocessen.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Aktivere en arbejdsproces  
 Arbejdsprocesser kan kun redigeres, hvis de er deaktiverede. Før en arbejdsproces kan bruges manuelt eller anvendes på grund af hændelser, skal den aktiveres. Før en arbejdsproces kan aktiveres, skal den indeholde mindst ét trin. Du kan finde oplysninger om konfigurationstrin i [Konfiguration af arbejdsprocesser](configure-workflow-steps.md)  
  
 En arbejdsproces kan kun aktiveres eller deaktiveres af ejeren af arbejdsprocessen eller af en person med rettigheden **Vær stedfortræder for en anden bruger**, f.eks. systemadministratoren.  Grunden til dette er, at der en ondsindet bruger kunne ændre en anden persons arbejdsproces, uden at denne person er opmærksom på ændringen. Du kan tildele en arbejdsproces, du ejer, ved at ændre ejeren. Dette felt findes under fanen **Administration**. Hvis du ikke er systemadministrator, og du skal redigere en arbejdsproces, der ejes af en anden bruger, skal den anden bruger deaktivere den og tildele den til dig. Når du er færdig med at redigere arbejdsprocessen, kan du tildele den til brugeren igen, så brugeren kan aktivere den.  
  
 Arbejdsprocesser i realtid kræver, at brugeren har rettigheden **Aktivér processer i realtid**. Da der er større risiko for, at arbejdsprocesser i realtid påvirker systemets ydeevne, skal denne rettighed kun tildeles til personer, der kan evaluere den potentielle risiko.  
  
 Arbejdsprocesser gemmes, når de er aktiveret, så det er ikke nødvendigt at gemme dem, før du aktiverer dem.  
  
## <a name="next-steps"></a>Næste trin  
 [Konfiguration af arbejdsprocesser](configure-workflow-steps.md)  <br/>
[Føj en arbejdsproces efter behov til et forretningsprocesforløb](bpf-add-on-demand-workflow.md) 

