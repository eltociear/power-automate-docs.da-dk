---
title: Introduktion til Power Automate-godkendelser. | Microsoft Docs
description: Få mere at vide om tilladelser og generelle detaljer om Power Automate-godkendelser.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/29/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 10cc09d492dc6323c3846ac7911671156f4dba98
ms.sourcegitcommit: bbf1a3bf0d61c856af28f24edad98e56c2fc07df
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/04/2020
ms.locfileid: "3765752"
---
# <a name="get-started-with-approvals"></a>Introduktion til godkendelser

Godkendelsesflows kan hjælpe dig med at automatisere anmodninger om signering og kombinere personers beslutningstagning med baggrundsautomatisering for at hjælpe forretningsbrugere med at fokusere på deres centrale opgaver.

## <a name="prerequisites"></a>Forudsætninger

Her er, hvad du skal bruge for at komme i gang med godkendelser.

- Tilladelser til at oprette en Common Data Service-database.
- En licens til at oprette flows.


## <a name="permissions-to-create-a-common-data-service-database"></a>Tilladelser til at oprette en Common Data Service-database

Når du opretter godkendelsesflows, gemmes de i Common Data Service. Når du i første omgang bruger godkendelses-connectoren i et flow, der er placeret i et ikke-standardmiljø, kan systemet automatisk klargøre en database. For at kunne lykkes skal den bruger, der kører det første godkendelsesflow, have en administratorrolle i miljøet.

Det kan tage et par minutter at fuldføre den databaseklargøring, og du vil bemærke denne forsinkelse, første gang du kører flowet. Andre brugere, der opretter godkendelsesflows, behøver ikke at have udvidede tilladelser i miljøet.

>[!NOTE]
>Hvis du bruger standardmiljøet, behøver du ikke at klargøre Common Data Service-databasen. 

## <a name="license-to-create-flows"></a>Licens til at oprette flows

Da godkendelses-connectoren er en standard-connector, er alle licenser, der giver adgang til Power Automate, og muligheden for at bruge standard-connectorer tilstrækkelige til at oprette godkendelsesflow.

Det kan være en Power Automate-, en Office 365- eller en Dynamics 365-licens med indbyggede Power Automate-funktioner. Du kan finde en liste over disse Office 365-licenser og Dynamics 365-licenser i [Microsoft Power Apps- og Power Automate-licensvejledningen](https://go.microsoft.com/fwlink/?linkid=2085130).


## <a name="assign-approvals-to-any-user-in-your-tenant"></a>Tildel godkendelser til en hvilken som helst bruger i lejeren

Du kan tildele godkendelser til brugere i dit aktuelle Common Data Service-miljø eller din Azure Active Directory-lejer (Azure AD), herunder gæstebrugere. 

Når du tildeler en godkendelse til brugere, der ikke befinder sig i dit-miljø, tilføjes de automatisk, så vi kan behandle deres svar og bevare dem for godkendelsesoversigt. 

Følgende lejerkonfigurationer tillader ikke dette:

- Når indstillingen AllowAdHocSubscriptions i Azure Active Directory (Azure AD) er deaktiveret. I dette tilfælde kan du anmode lejeradministratoren om at aktivere den. Du kan se flere oplysninger om dette i tilmelding via selvbetjening.
- Hvis en sikkerhedsgruppe er blevet brugt til at styre, hvilke brugere der har adgang til Common Data Service-miljøet.
- Power Automate-[planer for offentlige amerikanske myndigheder](https://docs.microsoft.com/power-automate/us-govt).


Når du har tildelt en godkendelsesanmodning til en bruger, kan vedkommende svare direkte fra en Outlook-mail, et Teams-tilpasset kort eller Power Automate Løsningscenter, hvis de har en Power Automate-, eller en Office 365- eller en Dynamics 365-licens med indbyggede Power Automate-funktioner. Du kan finde en liste over disse Office 365-licenser og Dynamics 365-licenser i licensvejledningen til Microsoft Power Apps og Power Automate.

## <a name="next-steps"></a>Næste trin

- Opret [godkendelsesflows](modern-approvals.md)






 
