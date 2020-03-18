---
title: Søgeanmodninger fra registrerede omfattet af GDPR for Power Automate | Microsoft Docs
description: Få mere at vide om, hvordan du bruger Power Automate til at svare på søgeanmodninger fra registrerede omfattet af GPDR.
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
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195537"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-power-automate"></a>Svar på søgeanmodninger fra registrerede omfattet af GDPR for Power Automate


Det første trin som svar på en DSR-anmodning er at finde de personlige data, som anmodningen gælder. Dette første trin hjælper dig med at afgøre, om en DSR-anmodning opfylder organisationens krav, og om den skal accepteres eller afvises. Når du f.eks. har fundet og gennemset de personlige data, finder du måske ud af, at anmodningen ikke opfylder organisationens krav, fordi det kan have en negativ effekt på andres rettigheder og frihed.

Nedenfor finder du en oversigt over, hvilke typer af Power Automate-ressourcer der indeholder personlige data for en bestemt bruger.

|**Ressourcer, der indeholder personlige data**|**Formål**|
|-----|-----|
|Systemoprettede logge|Telemetri, der henter systemhændelser og historik.|
|Kørselsoversigt|Historikken for hver udførelse af flow de seneste 28 dage. Disse data indeholder starttidspunkt, sluttidspunkt, status og alle input/output-oplysninger for flowet. [Få mere at vide](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Aktivitetsopdatering| Viser en opsummering af flowaktiviteter, herunder kørselsstatus, fejl og beskeder.|
|Brugerjob|Systemjob, der ikke kan ses af brugeren, og som kører på vegne af brugeren, for at flow kan udføres.|
|Flow|Den arbejdsproceslogik, der findes for et flow. [Få mere at vide](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Flowtilladelser|Flow kan deles og tildeles til andre brugere. Der findes en tilladelsesliste for alle flow. [Få mere at vide](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Brugeroplysninger|Oplysninger, som ikke kan ses af brugeren, og som understøtter kørsel af flow.|
|Forbindelser|Bruges af connectors og gør det muligt at oprette forbindelse til API'er, systemer, databaser osv. [Få mere at vide](https://docs.microsoft.com/flow/add-manage-connections)|
|Forbindelsestilladelser|Tilladelser for en bestemt forbindelse. [Få mere at vide](https://docs.microsoft.com/flow/add-manage-connections)|
|Brugerdefinerede forbindelser|Brugerdefinerede connectors, som en bruger har oprettet og publiceret for at gøre det muligt at få adgang til brugerdefinerede systemer eller tredjepartssystemer. [Få mere at vide](https://docs.microsoft.com/connectors/custom-connectors/)|
|Tilladelser til brugerdefineret connector|Lister over tilladelser til brugerdefinerede connectors. [Få mere at vide](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Gateways er datatjenester i det lokale miljø, der kun kan installeres af en bruger, til hurtig og sikker overførsel af data mellem Power Automate og en datakilde, der ikke er i clouden. [Få mere at vide](https://docs.microsoft.com/flow/gateway-manage)|
|Gatewaytilladelser|Gateways kan deles med brugerne i en organisation. [Få mere at vide](https://go.microsoft.com/fwlink/?linkid=872249)|
