---
title: Common Data Service | Microsoft Docs
description: Opret et flow for at importere data, eksportere data eller oprette godkendelser med Common Data Service.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/27/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7138d8f0aefc06799f5023204126e1a95494ba20
ms.sourcegitcommit: e58c8e6954c8e666497a66dc945fdc16c7c845a9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/02/2020
ms.locfileid: "3331053"
---
# <a name="create-a-flow-that-uses-common-data-service"></a>Opret et flow, der bruger Common Data Service

Du kan forbedre driftseffektiviteten med en samlet visning af virksomhedsdata ved at oprette et flow, der bruger [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Udrul denne sikre forretningsdatabase, der omfatter korrekt udformede standardforretningsenheder (f.eks. salg, indkøb, kundeservice og produktivitet) i din organisation. Gem organisationens data i en eller flere [brugerdefinerede objekter](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), som giver adskillige fordele i forhold til eksterne datakilder som f.eks. Microsoft Excel og Salesforce.

Genbrug f.eks. Common Data Service i Power Automate på følgende vigtige måder:

* Opret et flow for at importere data, eksportere data eller handle i forhold til data (f.eks. at sende en meddelelse). Bemærk, at denne metode ikke er en komplet synkroniseringstjeneste; den giver dig ganske enkelt mulighed at flytte data ind eller ud på grundlag af en enkelt enhed.
  
    Du kan finde detaljerede trin under procedurerne, der angives senere under dette emne.
* I stedet for at [oprette en godkendelsesløkke via mail](wait-for-approvals.md) skal du oprette et flow, der gemmer godkendelsestilstanden i en enhed, og oprette en brugerdefineret app, hvor brugerne kan godkende eller afvise elementer.
  
    Du kan få vist detaljerede trin under [Opret en godkendelsesløkke med Common Data Service](common-data-model-approve.md).

**Forudsætninger**

* Tilmeld dig [Power Automate](https://flow.microsoft.com) og [Power Apps](https://make.powerapps.com).
  
    Hvis du har problemer, skal du kontrollere, om [Power Automate](sign-up-sign-in.md) og [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) understøtter den kontotype, du har, og at organisationen ikke har blokeret for tilmelding.
* Hvis du ikke har brugt Common Data Service før, skal du åbne fanen **Objekter** på [powerapps.com](https://web.powerapps.com/#/entities) og derefter klikke eller trykke på **Opret min database**.

## <a name="sign-in-to-your-environment"></a>Log på dit miljø
1. Åbn [Power Automate](https://flow.microsoft.com), og klik eller tryk derefter på **Log på** i øverste højre hjørne.
   
    **Bemærk**! Du skal muligvis åbne menuen øverst til venstre til at få vist knappen **Log på**.
   
    ![Log på](./media/common-data-model-intro/signin-flow.png)
2. I menuen øverst til højre skal du vælge det miljø, hvor du oprettede databasen i powerapps.com.
   
    **Bemærk**! Hvis du ikke vælger det samme miljø, får du ikke vist dine enheder.
   
    ![Vælg miljø](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Åbn en skabelon
1. I feltet **Søg efter skabeloner** øverst i skærmbilledet skal du skrive eller indsætte **fælles**, og derefter trykke på Enter.
   
    ![Søg efter skabeloner](./media/common-data-model-intro/template-search.png)
2. På listen over skabeloner skal du klikke eller trykke på den skabelon, der importerer data fra den ønskede kilde til den ønskede enhed (eller det ønskede *objekt*).
   
    Klik eller tryk f.eks. på den skabelon, der kopierer kontaktoplysninger fra Dynamics 365 til Common Data Service.
   
    ![Vælg en skabelon](./media/common-data-model-intro/choose-template.png)
3. Klik eller tryk på **Anvend denne skabelon**.
   
    ![Brug skabelon](./media/common-data-model-intro/use-template.png)
4. Hvis du ikke allerede har oprettet en forbindelse fra Power Automate til Dynamics 365, skal du klikke eller trykke på **Log på** og derefter angive dine legitimationsoplysninger, hvis du bliver bedt om det.
   
    ![Log på Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Klik eller tryk på **Fortsæt**.
   
    ![Bekræft konti](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Byg dit flow
1. Angiv den hændelse, der udløser flowet, på det første kort.
   
    Du opretter f.eks. et flow, der kopierer nye kontakter fra en forekomst af Dynamics 365 til Common Data Service. Under **Når en post oprettes** skal du antive forekomsten ved at klikke eller trykke på pil ned og derefter klikke eller trykke på en indstilling på den viste liste.
   
    ![Angiv forekomst af Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. (valgfrit) Næsten øverst i skærmbilledet skal du angive et andet navn for det flow, du opretter.
   
    **Bemærk**! Hvis dit browservindue ikke er maksimeret, kan brugergrænsefladen muligvis se lidt anderledes ud.
   
    ![Navngiv flow](./media/common-data-model-intro/name-flow.png)
3. Klik eller tryk på **Opret flow**.
   
    **Bemærk**! Hvis dit browservindue ikke er maksimeret, er det muligvis kun afkrydsningen, der vises.
   
    ![Opret flow](./media/common-data-model-intro/create-flow.png)

Når objektet oprettes i kildesystemet, importeres det nu til Common Data Service. Hvis du ikke kan finde en skabelon, der fungerer, som du gerne vil have, kan du [oprette et flow fra bunden](get-started-logic-flow.md), som fungerer oven på Common Data Service.

Du kan udføre handlinger i forhold til ændringer i databasen. Du kan f.eks. sende en mail med besked, når data ændres.

