---
title: Søgeanmodninger fra registrerede omfattet af Power Automate GDPR for Microsoft-konti (MSA) | Microsoft Docs
description: Få mere at vide om, hvordan du kan bruge Power Automate til at svare på søgeanmodninger fra registrerede omfattet af GPDR for Microsoft-konti.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 5e1dc452bdbe7aa65700d159cf9365812dc50bfb
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194134"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Besvar søgeanmodninger fra fysiske personer omfattet af GDPR 


Det første trin som svar på en DSR-anmodning er at finde de personlige data, som anmodningen gælder.
Nedenfor finder du en oversigt over, hvilke typer af Power Automate-ressourcer der indeholder personlige data for en bruger, som godkendes med sin Microsoft-konto (MSA).

|Ressource|Formål|
|-----|-----|
|Kørselsoversigt|Viser historikken for hver udførelse af flow de seneste 28 dage. Disse data indeholder starttidspunkt, sluttidspunkt, status og alle input/output-oplysninger for hver flowkørsel. Få mere at vide om [kørselsoversigten for flows](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Aktivitetsopdatering| Viser en opsummering af hvert flows aktiviteter, herunder kørselsstatus, fejl og beskeder.|
|Flow|Arbejdsproceslogikken for et [flow](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Forbindelser|Bruges af connectors og gør det muligt at oprette forbindelse til API'er, systemer, databaser og mere. Få mere at vide om [forbindelser](add-manage-connections.md).|

