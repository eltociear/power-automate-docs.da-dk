---
title: Start her | Microsoft Docs
description: Hurtige metoder til at komme i gang med at automatisere dit arbejde og dit liv med Power Automate
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bd7d85dc2ec30147202c2838f00c7de6c7c587ad
ms.sourcegitcommit: 4b9261984a554dfccb0d0d77f3d5fdca60e26433
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340017"
---
# <a name="get-started-with-power-automate"></a>Introduktion til Power Automate 

Velkommen! Power Automate er en tjeneste, der hjælper dig med at oprette automatiserede arbejdsprocesser mellem dine favoritprogrammer og -tjenester, så du kan synkronisere filer, få meddelelser, indsamle data og meget mere.

<br/>

> [!VIDEO https://www.youtube.com/embed/hCuxuUaGC6Y]


## <a name="types-of-flows"></a>Typer af flow

Power Automate er en af pillerne i Power Platform. Den består af en platform med meget lidt kode, som kan bruges til arbejdsprocesser og procesautomatisering. Her er en liste over de forskellige typer flows:

| **Procestype**                                                                       | **Use case**                                                                                  | **Mål**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Automatiserede flow](get-started-logic-flow.md)                 | Opret en proces, der udfører en eller flere opgaver automatisk, når den udløses af en hændelse. | [Connectorer](https://docs.microsoft.com/connectors/) til services i cloudmiljøet og det lokale miljø. |
| [Knapflow](introduction-to-button-flows.md)              | Kør gentagne opgaver fra et hvilket som helst sted, når som helst, via din mobilenhed.                        |                                                                                        |
| [Planlagte flow](run-scheduled-tasks.md)                    | Opret et flow, der udfører en eller flere opgaver efter en tidsplan.             |                                                                                        |
| [Forretningsprocesforløb](business-process-flows-overview.md) | Definer en række trin, der skal følges for at opnå det ønskede resultat.                 | Menneskelige processer                                                                        |
| [Brugergrænsefladeprocesser](ui-flows/overview.md)                                                | Optag og automatiser afspilning af manuelle trin i ældre software.                    | Skrivebords- og webprogrammer, der ikke har API'er tilgængelige til automatisering.    |

Du kan oprette og administrere alle flow via fanen **Mine flows** i Power Automate.

Hvis du bruger Dynamics 365, kender du muligvis også de klassiske Common Data Service-processer, der omfatter [arbejdsprocesser](configure-workflow-steps.md), [handlinger](create-actions.md), [flow for mobilopgaver](create-mobile-task-flow.md) og [dialogbokse](use-cds-for-apps-dialogs.md).

Det første trin er at [tilmelde sig](sign-up-sign-in.md). Hvis du allerede har en konto til Power Automate, kan du [logge på](https://flow.microsoft.com/signin) via din tablet, din stationære computer eller tilmed din telefon.

## <a name="check-out-the-start-page"></a>Tjek startsiden ##

[På startsiden](https://flow.microsoft.com) for Power Automate kan du [se et bredt udvalg af skabeloner](https://flow.microsoft.com/templates) og få mere at vide om nogle af de vigtige funktioner i Power Automate. Du kan få et hurtigt indtryk af, hvad der er muligt, og hvordan Power Automate kan være en hjælp for din virksomhed og dit liv.

Med Power Automate kan du:

- Søg let efter skabeloner og tjenester.

    ![Flow – startside 1](./media/getting-started/flowhome1.png)

- Vælg blandt de mest populære tjenester.

    ![Flow – startside 2](./media/getting-started/flowhome2.png)

- Få vist en oversigt over hvert flow.

    ![Flow – startside 3](./media/getting-started/flowhome3.png)

Hver enkelt skabelon er designet til et specifikt formål. Der er f.eks. skabeloner til at sende en sms til dig, når du får en mail fra din chef, føje Twitter-kundeemner til Dynamics 365 eller sikkerhedskopiere dine filer. Disse skabeloner er bare toppen af isbjerget. De er beregnet til at inspirere dig til at oprette tilpassede flows til lige præcis de processer, du har behov for.

## <a name="create-your-first-flow"></a>Opret dit første flow ##

1. Vælg en skabelon, der er nyttig for dig. En simpel skabelon er [**Få daglige påmindelser pr. mail**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![skabelon til daglig påmindelse](./media/getting-started/template-details.png)

1. Vælg **Fortsæt**.

    ![Oprette forbindelse](./media/getting-started/create-connection.png)

1. Angiv de mailadresser, som den daglige påmindelse skal sendes til. Derefter skal du angive meddelelsen i påmindelsen. Til sidst skal du vælge **Opret flow** og derefter kontrollere, at dit flow kører som forventet.

    ![Angiv legitimationsoplysninger for forbindelsen](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Du kan udforske de betingelser, der udløser flowet, og den handling, der opstår på baggrund af den pågældende hændelse. Leg lidt med indstillingerne for at gøre flowet til dit eget. Du kan endda tilføje eller slette handlinger.

1. Vælg **Udført**.

[Følg dette selvstudium](get-started-logic-template.md) for at få mere at vide om, hvordan du opretter flows på baggrund af skabeloner.

## <a name="get-creative"></a>Vær kreativ ##

Nu da du har oprettet dit første flow på baggrund af en skabelon, skal du bruge en af de mere end [150 datakilder](https://flow.microsoft.com/connectors/), som understøttes af Power Automate, til at [oprette dine egne flows fra bunden](get-started-logic-flow.md).

![Oprette et flow](./media/getting-started/build-a-flow.png)

Når du opretter et flow fra bunden, har du kontrol over hele arbejdsprocessen. Her er nogle idéer, så du kan komme i gang:

- [Flows med mange trin](multi-step-logic-flow.md).
- [Køre opgaver efter en tidsplan](run-scheduled-tasks.md).
- [Oprette et godkendelsesflow](wait-for-approvals.md).
- [Vise et flow i aktion](see-a-flow-run.md).
- [Publicere en skabelon](publish-a-template.md).
- [Opret flows ud fra en Microsoft Teams-skabelon](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Et smugkig på koden

Du behøver ikke at være udvikler for at oprette flows, men Power Automate indeholder funktionen **Smugkig på kode**, som giver alle mulighed for at se nærmere på den kode, der genereres for alle handlinger og udløsere i et flow. Når du smugkigger på koden, vil du få en bedre forståelse af de data, der bruges af udløsere og handlinger. Følg disse trin for at tage et smugkig på den kode, der genereres for dine flows, i Power Automate-designeren: 

1. Vælg menupunktet **...** i øverste højre hjørne af en hvilken som helst **handling** eller **udløser**. 
1. Vælg **Smugkig på kode**.

    ![Smugkig på kode](media/getting-started/peek-code.png)

1. Bemærk den fulde JSON-repræsentation af handlinger og udløsere. Det omfatter alle input, f.eks. den tekst, du angiver direkte, og anvendte udtryk. Du kan vælge udtryk her og derefter indsætte dem i udtrykseditoren **Dynamisk indhold**. Det giver dig også mulighed for at bekræfte de data, du forventer er til stede i flowet.

    ![Smugkig på kode](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Find nemt dine flows

Når kreativiteten *flyder*, opretter du måske mange flows. Bare rolig; det er nemt at finde dine flows – du skal blot bruge søgefeltet på skærmen **Mine flows**, **Teamflows**, **Forbindelser** eller **Løsninger** til kun at få vist de flows, der matcher de angivne søgeord.

![Filtrer eller søg efter flows](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Søgefilteret finder kun de flows, der er indlæst på siden. Hvis du ikke kan finde dit flow, kan du prøve at vælge **Indlæs flere** nederst på siden.

## <a name="get-notifications-when-somethings-wrong"></a>Få meddelelser, når der er noget galt

Brug meddelelsescentret i Power Automate (som findes øverst til højre i designeren) til hurtigt at se en liste over de seneste mislykkede flows. I meddelelsescenteret vises et tal, der angiver antallet af seneste mislykkede flows.

Fra meddelelsescenteret kan du navigere til siden **Aktivitet** i Power Automate for at se de flows, der blev kørt for nylig, sendte meddelelser eller mislykkedes.

![Meddelelsescenter](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Brug mobilappen ##

Download Power Automate-mobilappen til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows). Med denne app kan du [overvåge flowaktivitet](mobile-monitor-activity.md), [administrere dine flows](mobile-manage-flows.md) og [oprette flows på baggrund af skabeloner](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Vi er her for at hjælpe dig ##

Vi er spændte på at se, hvad du vil bruge Power Automate til, og vi vil være sikre på, at du får en god oplevelse. Sørg for at se vores selvstudier med [vejledninger](https://flow.microsoft.com/guided-learning/), og [bliv en del af vores community](https://go.microsoft.com/fwlink/?LinkID=787467), så du kan stille spørgsmål og dele dine idéer. [Kontakt support](https://go.microsoft.com/fwlink/?LinkID=787479), hvis du får problemer.
