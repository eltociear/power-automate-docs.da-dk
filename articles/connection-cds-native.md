---
title: Opret et automatiseret flow med en connector for Common Data Service (aktuelt miljø) | Microsoft Docs
description: Opret arbejdsprocesser ved hjælp af en connector for Common Data Service (aktuelt miljø) og Power Automate
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
ms.openlocfilehash: 5b144f376640c1de3a1bbd165850555eeb444663
ms.sourcegitcommit: 1ac37360193f30d33c9a689ae6fe9ca7c7d991f2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/09/2020
ms.locfileid: "3789813"
---
# <a name="create-an-automated-flow-by-using-common-data-service-current-environment"></a>Opret et automatiseret flow ved hjælp af Common Data Service (aktuelt miljø)

>[!IMPORTANT]
>Der er tre connectorer tilgængelige til oprettelse af forbindelse til Common Data Service. Denne artikel dækker den anbefalede [Common Data Service-connector (aktuelt miljø)](./connection-cds.md) til oprettelse af forbindelse til Common Data Service. [Common Data Service-connectoren](./connection-cds.md) og [Dynamics 365-connectoren](https://docs.microsoft.com/connectors/dynamicscrmonline/) kan også bruges, hvis du ikke kan bruge den anbefalede connector.


De flows, du opretter, kan blive udløst, når der oprettes, opdateres eller slettes en Common Data Service-post.

Du kan også udføre handlinger for oprettelse, opdatering, hentning og sletning for poster i Common Data Service.

## <a name="initiate-a-flow-with-common-data-service-current-environment"></a>Start et flow med Common Data Service (aktuelt miljø)

Brug udløseren **Når der oprettes, opdateres eller slettes en post** for at starte dit flow:

   ![Vælg en udløser](./media/cds-connector-native/native-trigger.png)

Når du har valgt en udløser, skal du konfigurere følgende:

- Angiv en betingelse for udløseren:
- Navnet på objektet.
- Omfanget af udløseren.

### <a name="trigger-condition"></a>Udløserbetingelse

Du kan tilføje en af disse betingelser for at afgøre præcist, hvornår dit flow skal udløses.

   ![Vælg en udløser](./media/cds-connector-native/trigger-conditions.png)

### <a name="the-entity-name"></a>Objektnavnet

Vælg et af de mange objekter, der er tilgængelige, for at angive det objekt, som udløseren skal køres for.

   ![Vælg en udløser](./media/cds-connector-native/entity-names.png)

### <a name="scope"></a>Scope

Brug omfang til at afgøre, om dit flow skal køres, når du, en person i afdelingen eller en bruger i organisationen opretter en post.

![Vælg omfang](./media/cds-connector-native/scopes.png)

Her er oplysningerne om de enkelte omfang.

|Scope|Timing af udløser|
| --- | --- |
|Afdeling|Handling, der udføres på en post, der ejes af din afdeling|
|Organisation|Handling, der udføres af en hvilken som helst person i organisationen eller databasen|
|Overordnet: Underafdeling|Handling, der udføres på en post, der ejes af din afdeling eller en underafdeling|
|User|Handling, der udføres på en post, der ejes af dig|


Udløsere, der kører, når en post opdateres, kan også bruges til filtrering af attributter. Dette sikrer, at flowet kun kører, når nogle af de definerede attributter opdateres.

> [!IMPORTANT]
> Brug filterattributter for at undgå, at dit flow kører unødvendigt.

Dette flow udløses, hver gang fornavnet eller efternavnet på en kontakt, som flowbrugeren ejer, opdateres.

![Filtrér attributter](./media/cds-connector-native/filtering-attributes.png)

## <a name="trigger-privileges"></a>Udløserrettigheder

Hvis du vil oprette et flow, der udløses ud fra oprettelse, opdatering eller sletning af en post, skal brugeren have tilladelser på brugerniveau til at oprette, læse, skrive og slette for objektet **Registrering af tilbagekald**. Derudover skal brugeren, afhængigt af de områder der er defineret, muligvis have mindst samme niveau af læserettigheder for det samme objekt.  [Få mere at vide](https://docs.microsoft.com/power-platform/admin/database-security) om miljøsikkerhed.

## <a name="write-data-into-common-data-service"></a>Skriv data til Common Data Service

Brug en af følgende handlinger til at skrive data til Common Data Service:

![Filtrér attributter](./media/cds-connector-native/actions.png)

Her er et eksempel på et flow, der sender en notifikation med navnet og den årlige omsætning, hver gang en **konto** **oprettes** af en person inden for afdelingens **omfang**.

> ![Opfølgningsopgave](./media/cds-connector-native/example-flow.png)

## <a name="advanced-concepts"></a>Avancerede koncepter

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Skriv data til felterne Kunde, Ejer og Angående

Hvis du vil skrive data til felterne Kunde, Ejer og Angående, skal to felter udfyldes.

| Feltkategori | Eksempel på indstillinger |
| --- | --- |
| Angående | Angåede = id for posten (f.eks. konto-id) og Angående-type som valgt på listen. |
| Kunde | Repræsenterer id for posten og kundetypen som valgt på listen. |
| Ejer | Repræsenterer id for systembrugeren eller teamet og ejertypen som valgt på listen. |

### <a name="enable-upsert-behavior"></a>Aktivér upsert-funktionsmåde

Du kan udnytte handlingen **opdater en post** til at aktivere upsert-handlinger, som opdaterer posten, hvis den allerede findes, eller opretter en ny post. Du aktiverer upsert ved at angive objektet og en GUID-nøgle. Hvis posten med den angivne type og nøgle findes, foretages en opdatering. I modsat fald oprettes en post med den angivne nøgle.

### <a name="trigger-behavior"></a>Funktionsmåde for udløser

Hvis du har en udløser, der er registreret for opdateringen af en post, kører flowet for hver *bindende* opdatering af den givne post. Tjenesten starter dit flow asynkront og med de nyttedata, som indsamles på det tidspunkt, hvor aktiveringen finder sted.

> [!NOTE]
> Hvis du har to opdateringer, der sker inden for få sekunder efter hinanden, kan flowet derfor blive udløst mere end én gang med det nyeste versionerede indhold.

Flowkørsler kan blive forsinkede, hvis der er en ordrebeholdning af systemjob i miljøet. Hvis denne forsinkelse forekommer, udløses dit flow, når det systemjob, der skal starte flowet, bliver kørt.



