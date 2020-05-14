---
title: Anmodninger i Power Automate om søgning efter dataemner omfattet af GDPR | Microsoft Docs
description: Lær, hvordan du kan bruge Power Automate til at svare på anmodninger om søgning efter dataemner omfattet af GPDR.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 05def202f2a0b0db8a6eebb067406c96221e7d1c
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297159"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-power-automate"></a>Besvarelse af anmodninger i Power Automate om søgning efter dataemner omfattet af GDPR


Det første trin som svar på en DSR-anmodning er at finde de personlige data, som anmodningen gælder. Dette første trin hjælper dig med at afgøre, om en DSR-anmodning opfylder organisationens krav, og om den skal accepteres eller afvises. Når du f.eks. har fundet og gennemset de personlige data, kan det være, at du finder ud af, at anmodningen ikke opfylder organisationens krav, fordi det kan have en negativ indvirkning på andres rettigheder.

Nedenfor vises en oversigt over de typer af Power Automate-ressourcer, der indeholder personlige data for en bestemt bruger.

|**Ressourcer, der indeholder personlige data**|**Formål**|
|-----|-----|
|Systemgenererede logge|Telemetri, der henter systemhændelser og historik.|
|Kørselshistorik|Historikken for hver udførelse af flow de seneste 28 dage. Disse data indeholder starttidspunkt, sluttidspunkt, status og alle input/output-oplysninger for flowet. [Få mere at vide](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Aktivitetsopdatering| Viser en opsummering af flowaktiviteter, herunder kørselsstatus, fejl og beskeder.|
|Brugerjob|Systemjob, der ikke kan ses af brugeren, og som kører på vegne af brugeren, for at flow kan udføres.|
|Flow|Den arbejdsproceslogik, der findes for et flow. [Få mere at vide](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Flowtilladelser|Flow kan deles og tildeles til andre brugere. Der findes en tilladelsesliste for alle flow. [Få mere at vide](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Brugeroplysninger|Oplysninger, som ikke kan ses af brugeren, og som understøtter kørsel af flow.|
|Forbindelser|Bruges af connectors og gør det muligt at oprette forbindelse til API'er, systemer, databaser osv. [Få mere at vide](https://docs.microsoft.com/flow/add-manage-connections)|
|Forbindelsestilladelser|Tilladelser for en bestemt forbindelse. [Få mere at vide](https://docs.microsoft.com/flow/add-manage-connections)|
|Brugerdefinerede connectorer|Brugerdefinerede connectors, som en bruger har oprettet og publiceret for at gøre det muligt at få adgang til brugerdefinerede systemer eller tredjepartssystemer. [Få mere at vide](https://docs.microsoft.com/connectors/custom-connectors/)|
|Tilladelser til brugerdefineret connector|Lister over tilladelser til brugerdefinerede connectors. [Få mere at vide](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Gateways er datatjenester i det lokale miljø, der kan installeres af en bruger til at overføre data hurtigt og sikkert mellem Power Automate og en datakilde, der ikke er i cloudmiljøet. [Få mere at vide](https://docs.microsoft.com/flow/gateway-manage)|
|Gatewaytilladelser|Gateways kan deles med brugere i en organisation. [Få mere at vide](https://go.microsoft.com/fwlink/?linkid=872249)|
