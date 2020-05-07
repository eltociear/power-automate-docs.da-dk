---
title: Opret et automatiseret flow med Common Data Service-connector (aktuelt miljø) | Microsoft Docs
description: Opret arbejdsprocesser ved hjælp af en Common Data Service-connector og Power Automate
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/26/2020
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 96b97fe3e6090a2810c0fa0e1dfae2d4b890da62
ms.sourcegitcommit: e58c8e6954c8e666497a66dc945fdc16c7c845a9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728533"
---
# <a name="create-an-automated-flow-by-using-common-data-service-current-environment"></a>Opret et automatiseret flow ved hjælp af Common Data Service (aktuelt miljø)

>[!IMPORTANT]
>Der er tre connectors tilgængelige til at oprette forbindelse til Common Data Service. I denne artikel beskrives den anbefalede [Common Data Service-connector (aktuelt miljø)](./connection-cds.md) til oprettelse af forbindelse til Common Data Service. [Common Data Service-connectoren](./connection-cds.md) og [Dynamics 365-connectoren](https://docs.microsoft.com/connectors/dynamicscrmonline/) er også tilgængelige, hvis du ikke kan bruge den anbefalede connector.


Du skal [oprette løsningsorienterede](./overview-solution-flows.md) flow for at bruge Common Data Service-connectoren (aktuelt miljø). 

De flow, du opretter, kan udløses, når en Common Data Service post oprettes, opdateres eller slettes.

Du kan også udføre handlinger for oprettelse, opdatering, hentning og sletning for poster i Common Data Service.

## <a name="initiate-a-flow-with-common-data-service-current-environment"></a>Initier et flow med Common Data Service (aktuelt miljø)

Brug udløseren **Når en post oprettes, opdateres eller slettes** til at initiere dit flow:

   ![Vælg en udløser](./media/cds-connector-native/native-trigger.png)

Når du har valgt en udløser, skal du konfigurere:

- En betingelse for udløseren.
- Navnet på enheden.
- Området for udløseren.

### <a name="trigger-condition"></a>Udløserbetingelsen

Du kan tilføje en af disse betingelser for at bestemme, nøjagtigt hvornår dit flow udløses.

   ![Vælg en udløser](./media/cds-connector-native/trigger-conditions.png)

### <a name="the-entity-name"></a>Enhedens navn

Vælg en af de mange tilgængelige enheder for at angive den enhed, udløseren arbejder med.

   ![Vælg en udløser](./media/cds-connector-native/entity-names.png)

### <a name="scope"></a>Område

Brug områder til at afgøre, om dit flow kører, når du, en person i din afdeling eller en anden bruger i din organisation opretter en post.

![Vælg område](./media/cds-connector-native/scopes.png)

Her er detaljerne for hvert enkelt område.

|Område|Timing af udløser|
| --- | --- |
|Forretningsenhed|Handling, der udføres på en post, der ejes af din forretningsenhed|
|Organisation|Handling, der udføres af en hvilken som helst person i organisationen eller databasen|
|Overordnet: Underordnet afdeling|Handling, der udføres på en post, der ejes af din forretningsenhed eller en underordnet afdeling|
|Bruger|Handling, der udføres på en post, der ejes af dig|


Udløsere, der kører, når en post opdateres, kan også bruges til filtrering af attributter. Dette sikrer, at flowet kun kører, når nogle af de definerede attributter opdateres.

> [!IMPORTANT]
> Brug filterattributter for at undgå, at dit flow kører unødvendigt.

Dette flow udløses, hver gang fornavnet eller efternavnet på en kontakt, som flowbrugeren ejer, opdateres.

![Filterattributter](./media/cds-connector-native/filtering-attributes.png)

## <a name="trigger-privileges"></a>Udløserrettigheder

Hvis du vil oprette et flow, der udløses via oprettelse, opdatering eller sletning af en post, skal brugeren have tilladelser på brugerniveau til at oprette, læse, skrive og slette for posten til **tilbagekald af registreringen**. Derudover skal brugeren, afhængigt af de områder der er defineret, muligvis have mindst samme niveau af læserettigheder for det samme objekt.  [Få mere at vide](https://docs.microsoft.com/power-platform/admin/database-security) om miljøsikkerhed.

## <a name="write-data-into-common-data-service"></a>Skriv data til Common Data Service

Brug en af følgende handlinger til at skrive data til Common Data Service:

![Filterattributter](./media/cds-connector-native/actions.png)

Her er et eksempel på et flow, der sender en meddelelse med navnet og den årlige omsætning, hver gang en **konto** **oprettes** af en person i **området** for afdelingen.

> ![Opfølgningsopgave](./media/cds-connector-native/example-flow.png)

## <a name="advanced-concepts"></a>Avancerede koncepter

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Skriv data til felterne Kunde, Ejer og Angående

Hvis du vil skrive data til felterne Kunde, Ejer og Angående, skal to felter udfyldes.

| Feltkategori | Eksempel på indstillinger |
| --- | --- |
| Angående | Angåede = id for posten (f.eks. konto-id) og typen Angående som valgt på listen. |
| Kunde | Repræsenterer id for posten og typen Kunde som valgt på listen. |
| Ejer | Repræsenterer id for systembrugeren eller teamet og typen Ejer som valgt på listen. |

### <a name="enable-upsert-behavior"></a>Aktivér upsert-funktionsmåde

Du kan udnytte handlingen til **opdatering af en post** til at aktivere upsert-handlinger, som opdaterer posten, hvis den allerede findes, eller opretter en ny post. Du aktiverer upsert ved at angive objektet og en GUID-nøgle. Hvis posten med den angivne type og nøgle findes, foretages en opdatering. I modsat fald oprettes en post med den angivne nøgle.

### <a name="trigger-behavior"></a>Funktionsmåde for udløser

Hvis du har en udløser, der er registreret for opdateringen af en post, kører flowet for hver *bindende* opdatering af den givne post. Tjenesten starter dit flow asynkront og med den nyttelast, som indsamles på det tidspunkt, hvor aktiveringen finder sted.

> [!NOTE]
> Hvis du har to opdateringer, der sker inden for få sekunder efter hinanden, kan flowet blive udløst mere end én gang med det nyeste versionerede indhold.

Flowkørsler kan blive forsinkede, hvis der er en ordrebeholdning af systemjob i miljøet. Hvis denne forsinkelse forekommer, udløses dit flow, når systemjobbet til start af flowet kører.



