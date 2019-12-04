---
title: Få mere at vide om Power Automate-miljøer| Microsoft Docs
description: Lær, hvordan du bruger miljøer til at isolere dine flow
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 263ebf710d280ebd7c4a6d2846fa859693561476
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74355466"
---
# <a name="choosing-an-environment"></a>Valg af et miljø
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I denne artikel introduceres du til **miljøer** i Power Automate, hvor du kan oprette og isolere dine flow, gateways, forbindelser og andre ressourcer på en sikker måde.

Du kan få mere at vide om:

* De funktioner, som miljøerne indeholder.
* Hvordan du skifter mellem miljøer.
* Hvordan du opretter et flow i det rette miljø.

## <a name="environments-overview"></a>Oversigt over miljøer

Når du opretter et flow, vælger du, hvilket miljø der skal hoste flowet, og hvilke ressourcer flowet skal bruge. Du kan bruge separate miljøer til forskellige scenarier.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Her er nogle få scenarier i forbindelse med brug af miljøer

Scenarie|Anbefaling
-----|-----
Du vil gerne oprette et flow, der anvender en forbindelse til Microsoft Common Data Service.|Placer flowet og Common Data Service i det samme miljø. Dette sikrer, at alle dataene er isoleret i det pågældende miljø (isoleringsgrænse).
Du opretter et flow til HR-afdelingen. Du vil sikre, at kun brugere i HR-afdelingen har adgang til flowet.|Opret et miljø, og sørg for kun at føje HR-brugere til miljøet. Placer flowet og andre ressourcer, som flowet bruger, i dette miljø.
Der er brugere i Europa, der benytter et flow til at vise data i SharePoint.|Opret et miljø i Europa, og opret derefter dit flow og SharePoint-forbindelsen til flowet. Dette miljø i Europa giver de europæiske brugere den bedste ydeevne, da alle ressourcer er lokale for Europa (datalokalitet).

Du skal være Power Automate-administrator for at oprette miljøer. Administratorer styrer, hvem der har adgang til miljøer. Du kan finde oplysninger om, hvordan du kan oprette og administrere miljøer, i emnet [Administration af miljøer](environments-overview-admin.md).

## <a name="switching-environments"></a>Skift af miljøer

Med Power Automate er det nemt at skifte mellem miljøer. Når du skifter miljøer, kan du kun se de elementer, der er oprettet i det pågældende miljø. Du kan hverken se eller har adgang til elementer i andre miljøer.

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

* Du kan kun oprette gateways i standardmiljøet. Hvis du vil bruge en gateway til at oprette forbindelse mellem dit flow og data i det lokale miljø, skal du derfor bruge standardmiljøet.
* Microsoft Common Data Service-databaser er knyttet til et bestemt miljø. Hvis du vil oprette en proces, der bruger Common Data Server, skal du derfor oprette flowet i det miljø, der er vært for databasen.
* Du kan se alle de miljøer, du kan redigere ressourcer i. Du skal dog få en administrator til at tilføje dig som opretter for alle de miljøer, du vil oprette flow i.

> [!NOTE]
> Du kan altid oprette flow i standardmiljøet.

## <a name="next-steps"></a>Næste trin

* [Opret et flow fra en skabelon](get-started-logic-template.md)
* [Opret et flow](get-started-logic-flow.md)
* [Oversigt over miljøer for administratorer](environments-overview-admin.md)
