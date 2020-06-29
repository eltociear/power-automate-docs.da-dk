---
title: Bedste praksis for brug af objektattributter for forretningsprocesforløb | MicrosoftDocs
description: Få mere at vide om bedste praksis for brug af objektattributter for forretningsprocesforløb.
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
ms.openlocfilehash: 10f7e72b931cf9d4dffc51527f1b4ac17bdfbae8
ms.sourcegitcommit: 2284143cf147beb7d6071fd8005a41298e51e493
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/19/2020
ms.locfileid: "3384988"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Bedste praksis for brug af objektattributter for forretningsprocesforløb



Ældre procesrelaterede attributter i objekter er frarådet. Her er nogle oplysninger om den bedste praksis for brug af attributten *Aktiv fase* (activestageid) på objektet for forretningsprocesforløb. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Rapportering om den aktive fase i et forretningsprocesforløb

Lad os antage, at du gerne vil have en oversigt over din salgspipeline ved at rapportere om den aktive fase, hvor **Kundeemne til salgsproces for salgsmulighed** befinder sig.

Når du tidligere ville rapportere om forretningsprocesser efter fase, skulle du definere en visning i hvert relaterede objekt for forretningsprocesforløbet og derefter rapportere i feltet *Aktiv fase* (activestageid).

Nu, hvor feltet *Aktiv fase* (activestageid) frarådes for relaterede objekter, kan der rapporteres om forretningsprocesforløb på to måder.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Mulighed 1: visninger og diagrammer i objekt for forretningsprocesforløb **(anbefales)**

I version 9.0 og nyere opretter hvert forretningsprocesforløb sin egen Common Data Service-enhed, der som regel har det samme navn som forretningsprocesforløbet. Hvis du vil rapportere om forretningsprocesforløbet, skal du vælge objektet for det forretningsprocesforløb, du vil rapportere om, og derefter oprette visninger og diagrammer på samme måde, som du gjorde før.

I vores eksempel skal du følge disse trin for at gå til objektet **Kundeemne til salgsproces for salgsmulighed**:
1. Gå til [https://make.powerapps.com](https://make.powerapps.com).
1. Vælg **Data**.
1. Vælg **Objekter**.
1. Angiv filteret til **Alle**.
1. Søg efter, og vælg derefter objektet **Kundeemne til salgsproces for salgsmulighed**.

   ![objektet kundeemne til salgsproces for salgsmuligheder](media/best-practices-entity-attributes/lead-opportunity-process.png)

Her kan du definere visninger og diagrammer på samme måde, som du gør i andre objekter.

![objektoplysninger til oversættelsesproces](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

En fordel ved denne fremgangsmåde er, at du kan bruge en enkelt visning eller et enkelt diagram til at rapportere om forretningsprocesforløb, der spænder over flere objekter.

Desuden kan du i takt med, at objektet for forretningsprocesforløbet ikke er forskellig fra andre brugerdefinerede objekter i Common Data Service, kan du føje brugerdefinerede felter til enheden for at spore eventuelle oplysninger, du har brug for.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Mulighed 2: Kopiér aktiv fase til et relateret objekt

Hvis du vil fortsætte med at rapportere om det relaterede objekt, skal du oprette et flow for at kopiere feltet *Aktiv fase* (activestageid) fra objektet for forretningsprocesforløbet til et brugerdefineret felt i de relaterede Common Data Service-objekter.

Her er et par ting, du skal være opmærksom på, når du bruger denne fremgangsmåde:

1.  Det er muligt at have mere end ét forretningsprocesforløb til at køre på et enkelt objekt. Med denne fremgangsmåde er det bedst at have ét brugerdefineret felt, hvor den aktive fase for hvert forretningsprocesforløb, som kører på objektet, gemmes. Denne tilgang garanterer rapporteringens integritet.

1.  Da rapportering er baseret på det relaterede objekt, er det ikke muligt at oprette en enkelt visning, der rapporterer om forretningsprocesforløb, som spænder over flere objekter.

## <a name="using-the-active-stage-to-run-logic"></a>Brug af den aktive fase til kørsel af logik

Her er nogle tilfælde, hvor du måske vil køre logik, der er baseret på den aktive fase:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Brug af den aktive fase til kørsel af logik på klientsiden

Når du bruger forretningsprocessen, er der mange ting, du muligvis vil gøre automatisk. For eksempel:

-   Ændre det aktive forretningsprocesforløb på basis af de nye tilgængelige oplysninger om formularen eller forretningsprocesforløbet.

-   Flytte den aktive fase til næste eller forrige fase på baggrund af værdier, som brugerne har angivet for trin eller formularfelter.

-   Skjule eller vise formularfaner og -felter på basis af den valgte fase.

-   Vise informative meddelelser og køre beregninger på basis af de aktive forretningsprocesforløb, den aktive eller valgte fase eller hændelser som flytning af den aktive fase.

> [!TIP]
> I forbindelse med scenarier som disse kan du bruge det understøttede sæt [klient-API'er](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) til forretningsprocesforløb.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Brug af den aktive fase til kørsel af logik på serversiden

Der kan være tilfælde, hvor automatisering, der er baseret på forretningsprocesforløbet, skal udføres på serversiden. For eksempel:

-   Sende en mail til en bruger, hvis fasen **Kvalificer** for **Salgsproces for salgsmulighed** er aktiv i mere end 15 dage.

-   Automatisk oprette et sæt aktiviteter, der er relevante for den aktive fase for **Salgsproces for salgsmulighed**, hver gang den ændres.

-   Automatisk afslutte **Salgsproces for salgsmulighed**, når telefonopkaldsaktiviteten for lukning er fuldført.

> [!TIP]
> Brug klassiske Common Data Service-arbejdsprocesser eller flow, du definerer på objektet for forretningsprocesforløbet.
> 

Hvis du vil oprette en klassisk arbejdsproces for Common Data Service, som opretter aktiviteter for interne løsningsgennemgange og følger op på kunden i fasen **Foreslå** for **Salgsproces for salgsmulighed**:

1. Opret den i objektet **Salgsproces for salgsmulighed**, og indstil den til at køre, hver gang feltet **Aktiv fase** for objektet ændres. 
1. Definer en betingelse for at kontrollere, om feltet **Aktiv fase** er lig med **Foreslå**. 
1. Opret henholdsvis en aftale og en telefonopkaldspost for den interne gennemgang af løsningen og kundeopkaldet for at gennemgå løsningen.

   ![luk faseopfølgning](media/best-practices-entity-attributes/close-stage-followup.png)
