---
title: Introduktion til politikker, der forebygger datatab. | Microsoft Docs
description: Introduktion til politikker til forebyggelse af datatab til Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 63e49b656527f471d7bdd5a5d7a0b02d572c1221
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74374763"
---
# <a name="data-loss-prevention-dlp-policies"></a>Politikker til forebyggelse af datatab
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I dette dokument introduceres du til politikker til forebyggelse af datatab, som kan hjælpe med at beskytte dine organisationsdata imod at blive delt vha. en liste over forbindelse, som du definerer.

## <a name="whats-a-data-loss-prevention-policy"></a>Hvad er en politik til forebyggelse af datatab?

Dataene i en organisation er kritiske for organisationens succes. Dataene skal være tilgængelige, så de nemt kan bruges som grundlag i beslutningsprocesser, men de skal også være beskyttet, så de ikke deles med målgrupper, der ikke skal have adgang til dataene. For at beskytte disse data får du med Power Automate mulighed for at oprette og gennemtvinge politikker, som definerer, hvilke forbrugerconnectors der kan få adgang til og dele forretningsdata. Disse politikker, som definerer, hvordan data kan deles, kaldes politikker til forebyggelse af datatab.

## <a name="why-create-a-dlp-policy"></a>Hvorfor oprette en politik til forebyggelse af datatab?

Du opretter en DLP-politik for tydeligt at definere, hvilke forbrugerforbindelser der må få adgang til og dele dine forretningsdata. Det kan f.eks. være, at en organisation, der bruger Power Automate, måske ikke vil have, at deres forretningsdata på SharePoint automatisk publiceres i deres Twitter-feed. Du kan forhindre dette ved at oprette en politik til forebyggelse af datatab, som blokerer SharePoint-data fra at blive brugt som kilde for tweets.

## <a name="benefits-of-a-dlp-policy"></a>Fordelene ved en politik til forebyggelse af datatab

* Dette sikrer, at data administreres på en ensartet måde på tværs af organisationen.
* Forhindrer, at vigtige forretningsdata ved et uheld publiceres til forbindelser som sociale medier.

## <a name="managing-dlp-policies"></a>Administration af politikker til forebyggelse af datatab

### <a name="prerequisites-for-managing-dlp-policies"></a>Forudsætninger for administration af DLP-politikker

* Tilladelser som enten miljøadministrator eller lejeradministrator.

    Du kan få mere at vide om tilladelser i [artiklen om miljøer](environments-overview-admin.md).
* En [P2-licens til Power Automate](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Opret en politik til forebyggelse af datatab

### <a name="prerequisites-for-creating-dlp-policies"></a>Forudsætninger for oprettelse af DLP-politikker

Hvis du vil oprette en politik til forebyggelse af datatab, skal du have tilladelser til mindst ét miljø.

Følg disse trin for at oprette en politik til forebyggelse af datatab, som forhindrer, at data på virksomhedens SharePoint-websted publiceres på Twitter:

1. Log på [Power Automate Administration](https://admin.flow.microsoft.com) (Administration).

1. Vælg fanen Datapolitikker, og vælg derefter linket **Ny politik**:

    ![Log på](./media/prevent-data-loss/create-policy-1.png)
1. Vælg fanen **Datagrupper**.

1. Skriv navnet på politikken til forebyggelse af datatab som *Sikker dataadgang til Contoso* i feltet **Navn på datapolitik** øverst på siden:

    ![Log på](./media/prevent-data-loss/create-policy-2.png)

1. Vælg [miljøet](environments-overview-admin.md) under fanen **Miljøer**.

    > [!NOTE]
    > Som miljøadministrator kan du oprette politikker, der gælder for et enkelt miljø. Som lejeradministrator kan du oprette politikker, der gælder for enhver kombination af miljøer:
    >
    >

    ![Vælg miljø.](./media/prevent-data-loss/create-policy-3.png)

1. Vælg fanen **Datagrupper**:

    ![Vælg datagrupper](./media/prevent-data-loss/create-policy-4.png)

1. Vælg linket **Tilføj**, som vises i gruppefeltet **Kun forretningsdata**:

    ![Vælg Tilføj](./media/prevent-data-loss/create-policy-5.png)

1. Vælg forbindelserne **SharePoint** og **Salesforce** på siden **Tilføj forbindelser**:

   ![Vælg forbindelser](./media/prevent-data-loss/create-policy-6.png)

1. Vælg knappen **Tilføj forbindelser** for at tilføje forbindelser, der kan dele forretningsdata.

1. Vælg **Gem politik** i øverste højre hjørne af skærmen.

1. Efter et øjeblik vises din nye politik til forebyggelse af datatab på listen over politikker:

    ![DLP-liste](./media/prevent-data-loss/create-policy-9.png)

1. **Valgfri** Send en mail eller anden type kommunikation til dit team for at gøre dem opmærksom på, at der er en ny politik til forebyggelse af datatab tilgængelig.

Du har nu oprettet en politik til forebyggelse af datatab, der giver apps tilladelse til at dele data mellem SharePoint og Salesforce og blokerer delingen af data for alle andre tjenester.

> [!NOTE]
> Når en tjeneste tilføjes til én datagruppe, fjernes den automatisk fra den anden datagruppe. Hvis Twitter f.eks. i øjeblikket er placeret i datagruppen **Kun forretningsdata**, og du ikke vil tillade, at forretningsdata deles på Twitter, skal du blot tilføje tjenesten Twitter til datagruppen **Ingen forretningsdata er tilladt**. Dette vil fjerne Twitter fra datagruppen Kun forretningsdata.
>
>

## <a name="data-sharing-violations"></a>Datadelingsovertrædelser

Under forudsætning af at du har oprettet den DLP-politik, der er beskrevet ovenfor, antages det, at hvis en bruger opretter et flow, der deler data mellem Salesforce (som er i datagruppen **kun forretningsdata**) og Twitter (som er i datagruppen **ingen forretningsdata er tilladt**), informeres brugeren om, at flowet er **midlertidigt afbrudt** på grund af en konflikt med den forebyggelsespolitik, du har oprettet om datatab.

![opret flow](./media/prevent-data-loss/10.png)

Hvis brugerne kontakte dig om midlertidigt afbrudte flows bør du overveje følgende:

1. Hvis der er en gyldig forretningsmæssig årsag til at dele forretningsdata mellem SharePoint og Twitter, kan du redigere politikken til forebyggelse af datatab i dette eksempel.

1. Bed brugeren om at redigere flowet for at overholde politikken til forebyggelse af datatab.

1. Bed brugeren om at lade flowet være midlertidigt afbrudt, indtil der er truffet afgørelse om deling af data mellem disse to enheder.

## <a name="find-a-dlp-policy"></a>Find en politik til forebyggelse af datatab

### <a name="admins"></a>Administratorer

Administratorer kan bruge søgefunktionen i Administratorcenter til at søge efter bestemte politikker til forebyggelse af datatab.

> [!NOTE]
> Administratorer bør publicere alle politikker til forebyggelse af datatab, så brugerne i organisationen er opmærksomme på politikkerne, inden de opretter flows.
>
>

### <a name="makers"></a>Maker

Hvis du ikke har administratortilladelser, og du vil vide mere om politikkerne til forebyggelse af datatab, kan du kontakte administratoren. Du kan også få mere at vide i [artiklen om Maker-miljøer](environments-overview-maker.md)

> [!NOTE]
> Det er kun administratorer, der kan redigere eller slette politikker til forebyggelse af datatab.
>
>

## <a name="edit-a-dlp-policy"></a>Rediger en politik til forebyggelse af datatab

1. Åbn [Administration](https://admin.flow.microsoft.com).

1. Vælg linket **Datapolitikker** i venstre side.

    ![vælg datapolitikker](./media/prevent-data-loss/2.png)

1. Søg på listen over eksisterende politikker til forebyggelse af datatab, og vælg redigeringsknappen ud for den politik, du vil redigere.

1. Foretag de nødvendige ændringer af politikken. Du kan eksempelvis ændre miljøet eller tjenesterne i datagrupperne

1. Vælg **Gem politik** for at gemme ændringerne.

> [!NOTE]
> De politikker til forebyggelse af datatab, der er oprettet af lejeradministratorer, kan ses af miljøadministratorer, men disse kan ikke redigere politikkerne.
>
>

## <a name="delete-a-dlp-policy"></a>Slet en politik til forebyggelse af datatab

1. Åbn [Administration](https://admin.flow.microsoft.com).

1. Vælg fanen **Datapolitikker** i venstre side.

    ![vælg fanen datapolitikker](./media/prevent-data-loss/2.png)

1. Søg på listen over eksisterende politikker til forebyggelse af datatab, og vælg derefter sletteknappen ud for den politik, du vil slette:

    ![Vælg knappen Slet](./media/prevent-data-loss/3-delete.png)

1. Bekræft, at du ønsker at slette politikken ved at vælge knappen **Slet**:

    ![bekræft, at du virkelig vil slette politikken](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Tilladelser til politik til forebyggelse af datatab

Det er kun lejer- og miljøadministratorer, der kan oprette og redigere politikker til forebyggelse af datatab. Du kan få mere at vide om tilladelser i artiklen om [miljøer](environments-overview-admin.md).


## <a name="custom-and-http-connectors"></a>Brugerdefinerede connectors og HTTP-connectors

Brugerdefinerede connectors og HTTP-connectors skal føjes til DLP'er ved hjælp af enten en Power Automate-skabelon eller PowerShell.

> [!TIP]
> Du kan ikke nedgradere fra skemaversion 2018-11-01. HTTP-understøttelse kan ikke fjernes fra en politik. Hvis du forsøger at fjerne HTTP-understøttelse, kan DLP-politikken blive beskadiget. Hvis en DLP-politik opdateres, så den understøtter HTTP-connectors, kan aktuelle flow, der bruger disse HTTP-egenskaber, blive lukket.

Her er de HTTP-connectors, du kan føje til en politik:

- HTTP (og HTTP + Swagger)
- HTTP-webhook
- HTTP-anmodning

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Tilføj brugerdefinerede connectors og HTTP-connectors med skabeloner

Hvis du vil føje en brugerdefineret connector til en politik ved hjælp af en [skabelon](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), skal du angive navnet på politikken, den gruppe, du vil føje connectoren til, og connectorens navn, id og type. Kør flowet én gang for at føje den brugerdefinerede connector til den angivne politik og gruppe.

Hvis du vil føje HTTP-connectors til en eksisterende politik via [skabelonen](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/), skal du angive navnet på den politik, du vil føje dem til, og derefter køre flowet.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Tilføj brugerdefinerede connectors og HTTP-connectors med PowerShell

Hvis du vil føje understøttelse af brugerdefinerede connectors og/eller HTTP-connectors til en politik ved hjælp af PowerShell, skal du [downloade](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) og importere de seneste PowerShell-scripts til Power Apps og derefter bruge disse cmdlet'er: "New-AdminDlpPolicy", "Set-AdminDlpPolicy", "Add-CustomConnectorToPolicy" og "Remove-CustomConnectorFromPolicy" for at redigere politikken. Bruge cmdlet'en "Get-Help -detailed" som reference.


> [!IMPORTANT]
> Brug skemaversion 2018-11-01, når du opretter eller opdaterer en DLP-politik til at inkludere HTTP-connectors. Hvis du tilføjer HTTP-understøttelse ved hjælp af skabelonen eller PowerShell, påvirker det kun den angivne politik. Nye politikker, der oprettes via Administration, indeholder ikke de pågældende HTTP-connectors.



## <a name="next-steps"></a>Næste trin

* [Få mere at vide om miljøer](environments-overview-admin.md)
* [Få mere at vide om Power Automate](getting-started.md)
* [Få mere at vide om administratorcenteret](admin-center-introduction.md)
* [Få mere at vide om dataintegration](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)