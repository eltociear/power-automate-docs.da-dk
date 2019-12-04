---
title: Bedste praksis for brug af enhedsattributter for forretningsprocesforløb | MicrosoftDocs
description: Få mere at vide om bedste praksis for brug af enhedsattributter for forretningsprocesforløb | MicrosoftDocs
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: ffc9fef64a9eda74d8a834745204fd635125e0c2
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74357260"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Bedste praksis for brug af enhedsattributter for forretningsprocesforløb
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]


Ældre procesrelaterede attributter i enheder frarådes. Her er nogle oplysninger om den bedste praksis for brug af attributten *Aktiv fase* (activestageid) i enheden for forretningsprocesforløb. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Rapportering om den aktive fase i et forretningsprocesforløb

Lad os antage, at du gerne vil have en oversigt over din salgspipeline ved at rapportere om den aktive fase, hvor **Kundeemne til salgsproces for salgsmulighed** befinder sig.

Når du tidligere ville rapportere om forretningsprocesser efter fase, skulle du definere en visning i hver relateret enhed for forretningsprocesforløbet og derefter rapportere i feltet *Aktiv fase* (activestageid).

Nu, hvor feltet *Aktiv fase* (activestageid) frarådes for relaterede enheder, kan der rapporteres om forretningsprocessforløb på to måder.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Mulighed 1: visninger og diagrammer i enhed for forretningsprocesforløb **(anbefales)**

I version 9.0 og nyere opretter hvert forretningsprocesforløb sin egen Common Data Service-enhed, der som regel har det samme navn som forretningsprocesforløbet. Hvis du vil rapportere om forretningsprocesforløbet, skal du vælge enheden for det forretningsprocesforløb, du vil rapportere om, og derefter oprette visninger og diagrammer på samme måde, som du gjorde før.

I vores eksempel skal du følge disse trin for at gå til enheden **Kundeemne til salgsproces for salgsmulighed**:
1. Gå til https://make.powerapps.com
1. Vælg **Data**.
1. Vælg **Enheder**.
1. Angiv filteret til **Alle**.
1. Søg efter, og vælg derefter enheden **Kundeemne til salgsproces for salgsmulighed**.

   ![enheden kundeemne til salgsproces for salgsmuligheder](media/best-practices-entity-attributes/lead-opportunity-process.png)

Her kan du definere visninger og diagrammer på samme måde, som du gør i andre enheder.

![enhedsoplysninger for oversættelsesproces](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

En fordel ved denne fremgangsmåde er, at du kan bruge en enkelt visning eller et enkelt diagram til at rapportere om forretningsprocesforløb, der spænder over flere enheder.

Desuden kan du i takt med, at enheden for forretningsprocesforløbet ikke er forskellig fra andre brugerdefinerede enheder i Common Data Service, kan du føje brugerdefinerede felter til enheden for at spore eventuelle oplysninger, du har brug for.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Mulighed 2: Kopiér aktiv fase til en relateret enhed

Hvis du vil fortsætte med at rapportere om den relaterede enhed, skal du oprette et flow for at kopiere feltet *Aktiv fase* (activestageid) fra enheden for forretningsprocesforløb til et brugerdefineret felt i de relaterede Common Data Service-enheder.

Her er et par ting, du skal være opmærksom på, når du bruger denne fremgangsmåde:

1.  Det er muligt at have mere end ét forretningsprocesforløb til at køre på en enkelt enhed. Med denne fremgangsmåde er det bedst at have ét brugerdefineret felt, hvor det aktive stadie for hvert forretningsprocesforløb, som kører på enheden, gemmes. Denne tilgang garanterer rapporteringens integritet.

1.  Da rapportering er baseret på det relaterede objekt, er det ikke muligt at oprette en enkelt visning, der rapporterer om forretningsprocesforløb, som spænder over flere enheder.

## <a name="using-the-active-stage-to-run-logic"></a>Brug af den aktive fase til kørsel af logik

Her er nogle tilfælde, hvor du måske vil køre logik, der er baseret på den aktive fase:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Brug af den aktive fase til kørsel af logik på klientsiden

Når du bruger forretningsprocessen, er der mange ting, du muligvis vil gøre automatisk. F.eks.:

-   Modificer det aktive forretningsprocesforløb på basis af de nye tilgængelige oplysninger om formularen eller forretningsprocesforløbet.

-   Flytte den aktive fase til næste eller forrige fase på baggrund af værdier, som brugerne har angivet for trin eller formularfelter.

-   Skjule eller vise formularfaner og -felter på basis af den valgte fase.

-   Vise informative meddelelser og køre beregninger på basis af de aktive forretningsprocesforløb, den aktive eller valgte fase eller begivenheder som flytning af den aktive fase.

> [!TIP]
> I forbindelse med scenarier som disse kan du bruge det understøttede sæt [klient-API'er](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) til forretningsprocesforløb.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Brug af den aktive fase til kørsel af logik på serversiden

Der kan være tilfælde, hvor automatisering, der er baseret på forretningsprocesforløbet, skal udføres på serversiden. F.eks.:

-   Send en mail til en bruger, hvis fasen **Kvalificer** i fasen for **Salgsproces for salgsmulighed** er aktiv i mere end 15 dage.

-   Opret automatisk et sæt aktiviteter, der er relevante for den aktive fase for **Salgsproces for salgsmulighed**, hver gang den ændres.

-   Afslut automatisk **Salgsproces for salgsmulighed**, når telefonopkaldsaktiviteten for lukning er fuldført.

> [!TIP]
> Brug klassiske Common Data Service-arbejdsprocesser eller flow, du definerer på enheden for forretningsprocesforløbet.
> 

Hvis du vil oprette en klassisk Common Data Service arbejdsproces, der opretter aktiviteter for interne løsningsgennemgange og følger op på kunden i fasen **Foreslå**  for **Salgsproces for salgsmulighed**:

1. Opret den i enheden **Salgsproces for salgsmulighed**, og indstil den til at køre, hver gang feltet **Aktiv fase** for enheden ændres. 
1. Definer en betingelse for at kontrollere, om feltet **Aktiv fase** er lig med **Foreslå**. 
1. Opret henholdsvis en aftale og en telefonopkaldspost for den interne gennemgang af løsningen og kundeopkaldet for at gennemgå løsningen.

   ![tæt faseopfølgning](media/best-practices-entity-attributes/close-stage-followup.png)
