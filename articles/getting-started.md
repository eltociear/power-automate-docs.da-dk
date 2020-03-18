---
title: Introduktion | Microsoft Docs
description: Måder til hurtigt at komme i gang med at automatisere dit arbejde og dit liv med Power Automate
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
ms.openlocfilehash: 7d4cd1523e19811eb4636d0197a347dbc86de9f8
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/13/2020
ms.locfileid: "79224371"
---
# <a name="get-started-with-power-automate"></a>Introduktion til Power Automate 



<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/hCuxuUaGC6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Velkommen! Power Automate er en tjeneste, der hjælper dig med at oprette automatiserede arbejdsprocesser mellem dine favoritprogrammer og -tjenester, så du kan synkronisere filer, få meddelelser, indsamle data og meget mere.

## <a name="types-of-flows"></a>Typer af flow

Power Automate er en af hjørnestenene i Power Platform. Den består af en platform med meget lidt kode, som kan bruges til arbejdsprocesser og procesautomatisering. Her er en liste over de forskellige typer flow:

| **Flowtype**                                                                       | **Use case**                                                                                  | **Destination**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Automatiserede flow](get-started-logic-flow.md)                 | Opret et flow, der udfører en eller flere opgaver automatisk, når det udløses af en hændelse. | [Connectors](https://docs.microsoft.com/connectors/) til tjenester i cloudmiljøet og det lokale miljø. |
| [Flow for knapper](introduction-to-button-flows.md)              | Kør gentagne opgaver fra et hvilket som helst sted, når som helst, via din mobilenhed.                        |                                                                                        |
| [Planlagte flow](run-scheduled-tasks.md)                    | Opret et flow, der udfører en eller flere opgaver efter en tidsplan.             |                                                                                        |
| [Forretningsprocesflow](business-process-flows-overview.md) | Definer en række trin, der skal følges for at opnå det ønskede resultat.                 | Menneskelige processer                                                                        |
| [Flow for brugergrænseflade (prøveversion)](ui-flows/overview.md)                                                | Optag og automatiser afspilning af manuelle trin på ældre software.                    | Skrivebords- og webprogrammer, der ikke har API'er tilgængelige til automatisering.    |

Du kan oprette og administrere alle flow via fanen **Mine flow** i Power Automate.

Hvis du bruger Dynamics 365, kender du muligvis også de klassiske Common Data Service-processer, der omfatter [arbejdsprocesser](configure-workflow-steps.md), [handlinger](create-actions.md), [flow for mobilopgaver](create-mobile-task-flow.md) og [dialogbokse](use-cds-for-apps-dialogs.md).

Det første trin er at [tilmelde sig](sign-up-sign-in.md). Hvis du allerede har en konto til Power Automate, kan du [logge på](https://flow.microsoft.com/signin) via din tablet, din stationære computer eller tilmed din telefon.

## <a name="check-out-the-start-page"></a>Tjek startsiden ##

[På startsiden](https://flow.microsoft.com) for Power Automate kan du [udforske et bredt udvalg af skabeloner](https://flow.microsoft.com/templates) og få mere at vide om de vigtigste funktioner i Power Automate. Du kan få et hurtigt indtryk af, hvad der er muligt, og hvordan Power Automate kan være en hjælp for din virksomhed og dit liv.

Med Power Automate kan du:

- let søge efter skabeloner og tjenester.

    ![Flow – startside 1](./media/getting-started/flowhome1.png)

- vælge blandt de mest populære tjenester.

    ![Flow – startside 2](./media/getting-started/flowhome2.png)

- se en oversigt over hvert flow.

    ![Flow – startside 3](./media/getting-started/flowhome3.png)

Hver enkelt skabelon er designet til et specifikt formål. Der er f.eks. skabeloner til afsendelse af en sms til dig, når du får en mail fra din chef, tilføjelse af Twitter-kundeemner til Dynamics 365 eller sikkerhedskopiering af dine filer. Disse skabeloner er bare toppen af isbjerget. De er beregnet til at inspirere dig til at oprette tilpassede flows til lige præcis de processer, du har behov for.

## <a name="create-your-first-flow"></a>Opret dit første flow ##

1. Vælg en skabelon, der er nyttig for dig. En simpel skabelon er [**Få daglige påmindelser pr. mail**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![skabelon til daglig påmindelse](./media/getting-started/template-details.png)

1. Vælg **Fortsæt**.

    ![Opret forbindelse](./media/getting-started/create-connection.png)

1. Angiv de mailadresser, som den daglige påmindelse skal sendes til. Derefter skal du angive meddelelsen i påmindelsen. Til sidst skal du vælge **Opret flow** og derefter kontrollere, at dit flow kører som forventet.

    ![Angiv legitimationsoplysninger for forbindelsen](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Du kan udforske de betingelser, der udløser flowet, og den handling, der opstår på baggrund af den pågældende hændelse. Leg lidt med indstillingerne for at gøre flowet til dit eget. Du kan endda tilføje eller slette handlinger.

1. Vælg **Udført**.

[Følg dette selvstudium](get-started-logic-template.md) for at få mere at vide om, hvordan du opretter flows på baggrund af skabeloner.

## <a name="get-creative"></a>Vær kreativ ##

Nu, hvor du har oprettet dit første flow ud fra en skabelon, skal du bruge en af de mere end [150 datakilder](https://flow.microsoft.com/connectors/), som understøttes af Power Automate, til at [oprette dine egne flow fra bunden](get-started-logic-flow.md).

![Oprettelse af et flow](./media/getting-started/build-a-flow.png)

Når du opretter et flow fra bunden, har du kontrol over hele arbejdsprocessen. Her er nogle idéer, så du kan komme i gang:

- [Flows med mange trin](multi-step-logic-flow.md).
- [Kørsel af opgaver efter en tidsplan](run-scheduled-tasks.md).
- [Oprettelse af et godkendelsesflow](wait-for-approvals.md).
- [Visning af et flow i aktion](see-a-flow-run.md).
- [Publicering af en skabelon](publish-a-template.md).
- [Opret flow fra en skabelon i Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Et smugkig på koden

Du behøver ikke at være udvikler for at oprette flow, men Power Automate indeholder en funktion til et **smugkig på koden**, der giver alle mulighed for at se nærmere på den kode, der genereres for alle handlinger og udløsere i et flow. Når du smugkigger på koden, vil du få en bedre forståelse af de data, der bruges af udløsere og handlinger. Følg disse trin for at tage et smugkig på den kode, der genereres for dine flow, i Power Automate-designeren: 

1. Vælg menupunktet **...** i øverste højre hjørne af en hvilken som helst **handling** eller **udløser**. 
1. Vælg **Smugkig på kode**.

    ![Smugkig på kode](media/getting-started/peek-code.png)

1. Bemærk den fulde JSON-repræsentation af handlinger og udløsere. Dette omfatter alle input, f.eks. den tekst, du angiver direkte, og anvendte udtryk. Du kan vælge udtryk her og derefter indsætte dem i udtrykseditoren **Dynamisk indhold**. Dette giver dig også mulighed for at bekræfte de data, du forventer er til stede i flowet.

    ![Smugkig på kode](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Find nemt dine flow

Når kreativiteten *flyder*, opretter du måske mange flow. Bare rolig; det er nemt at finde dine flow – du skal blot bruge søgefeltet på skærmen **Mine flow**, **Teamflow**, **Forbindelser** eller **Løsninger** til kun at få vist de flow, der stemmer overens med de angivne søgeord.

![Filtrer eller søg efter flow](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Søgefilteret finder kun de flow, der er indlæst på siden. Hvis du ikke kan finde dit flow, kan du prøve at vælge **Indlæs flere** nederst på siden.

## <a name="get-notifications-when-somethings-wrong"></a>Få meddelelser, når der er noget galt

Brug meddelelsescentret i Power Automate (som findes øverst til højre i designeren) til hurtigt at se en liste over de seneste mislykkede flow. I meddelelsescenteret vises et tal, der angiver antallet af seneste mislykkede flow.

Fra meddelelsescenteret kan du navigere til siden **Aktivitet** i Power Automate for at se alle dine flow, der blev kørt for nylig, der sendte meddelelser eller der mislykkedes.

![Meddelelsescenter](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Brug mobilappen ##

Download Power Automate-mobilappen til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows). Med denne app kan du [overvåge flowaktivitet](mobile-monitor-activity.md), [administrere dine flows](mobile-manage-flows.md) og [oprette flows på baggrund af skabeloner](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Vi er her for at hjælpe ##

Vi er spændte på at se, hvad du vil bruge Power Automate til, og vi vil være sikre på, at du får en god oplevelse. Sørg for at se vores selvstudier med [vejledninger](https://flow.microsoft.com/guided-learning/), og [bliv en del af vores community](https://go.microsoft.com/fwlink/?LinkID=787467), så du kan stille spørgsmål og dele dine idéer. [Kontakt support](https://go.microsoft.com/fwlink/?LinkID=787479), hvis du løber ind i problemer.
