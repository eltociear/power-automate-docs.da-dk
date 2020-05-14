---
title: Opret et automatiseret flow med Common Data Service | Microsoft Docs
description: Opret arbejdsprocesser ved hjælp af en Common Data Service-forbindelse og Power Automate
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
ms.openlocfilehash: 18719ac34d84298dd813b0241d00b652ae172ef6
ms.sourcegitcommit: e58c8e6954c8e666497a66dc945fdc16c7c845a9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/02/2020
ms.locfileid: "3331077"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Opret et automatiseret flow ved hjælp af Common Data Service

>[!IMPORTANT]
>Der er tre connectorer tilgængelige til oprettelse af forbindelse til Common Data Service. Brug den anbefalede connector for [Common Data Service (aktuelt miljø)](./connection-cds-native.md). **Common Data Service-connectoren**, som beskrives i denne artikel, og [Dynamics 365-connectoren](https://docs.microsoft.com/connectors/dynamicscrmonline/) kan også bruges, hvis du ikke kan bruge den anbefalede connector.


Med Common Data Service-connectoren kan du oprette flows, der startes ved at oprette og opdatere hændelser i Common Data Service. Du kan også udføre handlinger for oprettelse, opdatering, hentning og sletning for poster i Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Start et flow fra Common Data Service

Du kan bruge en af følgende udløsere til at starte dit flow:

- Når en post vælges
- Når en post oprettes
- Når en post slettes
- Når en post opdateres


> [!div class="mx-imgBorder"]
> ![Vælg en udløser](./media/cds-connector/Triggers.png)

Hvis den valgte udløser kræver, at der vælges et miljø, kan du vælge `(Current)`, som altid vil bruge databasen i det miljø, som Power Automate kører i. Hvis du vil have dit flow til altid at blive udløst af en hændelse i et bestemt miljø, skal du vælge det pågældende miljø.

> [!div class="mx-imgBorder"]
> ![Vælg miljø](./media/cds-connector/Environments.png)

Du kan bruge områder til at bestemme, om dit flow kører, hvis du opretter en ny post, hvis en ny post oprettes af en bruger i din forretningsenhed, eller hvis der oprettes en ny post af brugere i din organisation.

> [!div class="mx-imgBorder"]
> ![Vælg omfang](./media/cds-connector/Scopes.png)

|Scope|Timing af udløser|
| --- | --- |
|Afdeling|Handling, der udføres på en post, der ejes af din forretningsenhed|
|Organisation|Handling, der udføres af en hvilken som helst person i organisationen eller databasen|
|Overordnet: Underordnet afdeling|Handling, der udføres på en post, der ejes af din forretningsenhed eller en underordnet afdeling|
|Bruger|Handling, der udføres på en post, der ejes af dig|

Udløsere, der kører, når en post opdateres, kan også bruges til filtrering af attributter. Dette sikrer, at flowet kun kører, når nogle af de definerede attributter opdateres.

> [!IMPORTANT]
> Brug filterattributter for at undgå, at dit flow kører unødvendigt.

Dette flow udløses, hver gang fornavnet eller efternavnet på en kontakt, som flowbrugeren ejer, opdateres.

> [!div class="mx-imgBorder"]
> ![Filtrér attributter](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Udløserrettigheder

Hvis du vil oprette et flow, der udløses via oprettelse, opdatering eller sletning af en post, skal brugeren have tilladelser på brugerniveau til at oprette, læse, skrive og slette for posten til tilbagekald af registreringen. Derudover skal brugeren, afhængigt af de områder der er defineret, muligvis have mindst samme niveau af læserettigheder for det samme objekt.  [Få mere at vide](https://docs.microsoft.com/power-platform/admin/database-security) om miljøsikkerhed.

## <a name="write-data-into-common-data-service"></a>Skriv data til Common Data Service

Brug en af følgende handlinger til at skrive data til Common Data Service:

- Opret en ny post
- Opdatering af en post

Her er et eksempel på oprettelse af en opfølgningsopgave, når den angivne bruger opretter en ny kontopost.  

> [!div class="mx-imgBorder"]
> ![Opfølgningsopgave](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Avancerede koncepter

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Skriv data til felterne Kunde, Ejer og Angående

Hvis du vil skrive data til felterne Kunde, Ejer og Angående, skal to felter udfyldes.

| Feltkategori | Eksempel på indstillinger |
| --- | --- |
| Angående | Angåede = id for posten (f.eks. konto-id) og typen Angående som valgt på listen. |
| Kunde | Repræsenterer id for posten og typen Kunde som valgt på listen. |
| Ejer | Repræsenterer id for systembrugeren eller teamet og typen Ejer som valgt på listen. |

### <a name="enable-upsert-behavior"></a>Aktivér upsert-funktionsmåde

Du kan udnytte kommandoen til **opdatering af en post** til at aktivere upsert-handlinger, som opdaterer posten, hvis den allerede findes, eller opretter en ny post. Du aktiverer upsert ved at angive objektet og en GUID-nøgle. Hvis posten med den angivne type og nøgle findes, foretages en opdatering. I modsat fald oprettes en post med den angivne nøgle.

### <a name="trigger-behavior"></a>Funktionsmåde for udløser

Hvis du har en udløser, der er registreret for opdateringen af en post, kører flowet for hver *bindende* opdatering af den givne post. Tjenesten starter dit flow asynkront og med den nyttelast, som indsamles på det tidspunkt, hvor aktiveringen finder sted.

> [!NOTE]
> Hvis du har to opdateringer, der sker inden for få sekunder efter hinanden, kan flowet derfor blive udløst mere end én gang med det nyeste versionerede indhold.

Flowkørsler kan blive forsinkede, hvis der er en ordrebeholdning af systemjob i miljøet.  Hvis denne forsinkelse forekommer, udløses dit flow, når systemjobbet til aktivering af flowet kører.

