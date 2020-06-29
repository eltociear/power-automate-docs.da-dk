---
title: Få mere at vide om Power Automate-miljøer | Microsoft Docs
description: Lær, hvordan du bruger miljøer til at isolere dine flow
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/07/2020
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1ad11b90b9682f68c6c8f22d350313f0c2edb75
ms.sourcegitcommit: 7a42629c7bc15208c5a9d692ab89616fc0aa40cb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/08/2020
ms.locfileid: "3352034"
---
# <a name="choosing-an-environment"></a>Vælge et miljø

I denne artikel introduceres du til **miljøer** i Power Automate, hvor du kan oprette og isolere dine flows, gateways, forbindelser og andre ressourcer på en sikker måde.

Du kan få mere at vide om:

* De funktioner, som miljøerne indeholder.
* Hvordan du skifter mellem miljøer.
* Hvordan du opretter et flow i det rette miljø.

## <a name="environments-overview"></a>Oversigt over miljøer

Når du opretter et flow, vælger du, hvilket miljø der skal være vært for flowet, og hvilke ressourcer flowet skal bruge. Du kan bruge separate miljøer til forskellige scenarier.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Her er nogle få scenarier for brug af miljøer

Scenarie|Anbefaling
-----|-----
Du vil gerne oprette et flow, der anvender en forbindelse til Common Data Service.|Anbring dit flow og Common Data Service i det samme miljø. Dette sikrer, at alle dataene er isoleret i det pågældende miljø (isoleringsgrænse).
Du opretter et flow til HR-afdelingen. Du vil sikre, at kun brugere i HR-afdelingen har adgang til flowet.|Opret et miljø, og sørg for kun at føje HR-brugere til miljøet. Placer flowet og andre ressourcer, som flowet bruger, i dette miljø.
Der er brugere i Europa, der benytter et flow til at vise SharePoint-data.|Opret et miljø i Europa, og opret derefter dit flow og SharePoint-forbindelsen til flowet. Dette miljø i Europa giver de europæiske brugere den bedste ydeevne, da alle ressourcer er lokale for Europa (datalokalitet).

En hvilken som helst bruger med korrekt licens kan oprette miljøer i Power Platform Administration som standard, medmindre standardindstillingen for **Hvem kan oprette produktionsmiljøer** er blevet ændret fra **Alle** til **Kun bestemte administratorer**.


Du kan finde oplysninger om, hvordan du kan oprette og administrere miljøer, i emnet [administrere miljøer](environments-overview-admin.md).

## <a name="switching-environments"></a>Skift af miljøer

Power Automate gør det let at skifte mellem miljøer. Når du skifter miljøer, kan du kun se de elementer, der er oprettet i det pågældende miljø. Du kan hverken se eller få adgang til elementer i andre miljøer.

Her er et eksempel.

Du opretter et flow, der hedder *NyMedarbejder* i miljøet *Human Resources*. I [Power Automate](https://flow.microsoft.com) skal du åbne miljøet *Salg*. Flowet *NyMedarbejder* er ikke vist. Hvis du vil have vist flowet *NyMedarbejder*, skal du åbne miljøet *Human Resources*. Husk, at de samme regler gælder for alle elementer, du har oprettet i miljøet, herunder forbindelser, gateways, flows og meget mere.

Følg disse trin for at skifte miljøer:

1. Log på [Power Automate](https://flow.microsoft.com).
1. I øverste højre hjørne kan du se et billede, der repræsenterer din profil.

   ![profilbillede](./media/environments-overview-maker/default-environment.png)

1. Vælg billedet. På rullelisten vises alle de miljøer, der er tilgængelige for dig. Det miljø, du i øjeblikket er logget på, er markeret:

   ![billede af liste over miljøer](./media/environments-overview-maker/all-environments.png)
1. Hvis du vil skifte til et andet miljø, skal du vælge det på listen:

   ![vælg et miljø, du vil skifte til](./media/environments-overview-maker/select-europe.png)
1. Power Automate skifter til det nye miljø.

## <a name="create-flows-in-the-right-environment"></a>Opret flow i det rigtige miljø

Før du opretter et flow, skal du vælge det miljø, hvor flowet og dets ressourcer skal tilføjes.

> [!NOTE]
> Hvis du opretter et flow i det forkerte miljø, skal du slette det og derefter oprette flowet i det korrekte miljø.

Overvej følgende faktorer, når du vælger det miljø, der skal være vært for dine flow:

* Common Data Service er knyttet til et bestemt miljø. Hvis du vil oprette et flow, der bruger Common Data Service, skal du oprette flowet i det miljø, der er vært for databasen.
* Du kan se alle de miljøer, du kan redigere ressourcer i. Du skal dog få en administrator til at tilføje dig som opretter for alle de miljøer, du vil oprette flow i.

> [!NOTE]
> Du kan altid oprette flow i standardmiljøet.

## <a name="next-steps"></a>Næste trin

* [Opret et flow fra en skabelon](get-started-logic-template.md)
* [Opret et forløb](get-started-logic-flow.md)
* [Oversigt over miljøer for administratorer](environments-overview-admin.md)
