---
title: Start her | Microsoft Docs
description: Hurtige metoder til at komme i gang med at automatisere dit arbejde og dit liv med Power Automate
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 7/29/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 05f2f6eeca98a23e20abefc24e43302ef300de48
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900210"
---
# <a name="get-started-with-power-automate"></a>Introduktion til Power Automate 

Velkommen! Hvad kan du forvente af Power Automate? Her er nogle eksempler på, hvad du kan foretage dig:

* Automatisere forretningsprocesser
* Sende automatiske påmindelser til forfaldne opgaver
* Flytte forretningsdata mellem systemer efter en tidsplan
* Oprette forbindelse til næsten 300 datakilder eller enhver tilgængelig API
* Du kan endda automatisere opgaver på den lokale computer, f.eks. for beregning af data i Excel. 

Spar tid ved at automatisere gentagne manuelle opgaver blot ved at optage museklik, tastetryk og kopiere trin fra skrivebordet! Power Automate handler udelukkende om automatisering. 

<br/>

> [!VIDEO https://www.youtube.com/embed/H4H_jPJWlxU]

## <a name="who-is-power-automate-for"></a>Hvem er Power Automate beregnet til? 

*Hvilke færdigehder skal du have?* Alle fra en grundlæggende forretningsbruger til it-fagfolk kan oprette automatiserede processer ved hjælp af en Power Automate-platform med intet eller lavt kodningsbehov.

*Hvilke brancher kan drage fordel af Power Automate?* Se, hvordan nogle virksomheder har implementeret Power Platform-løsninger ved hjælp af Power Automate i: 

  * [Bank](https://customers.microsoft.com/en-us/story/821782-illimity-bank-banking-power-automate)
  * [Retail](https://customers.microsoft.com/en-us/story/drivetime-retail-consumer-goods-azure)
  * [Fremstilling](https://customers.microsoft.com/en-us/story/810656-hexion-manufacturing-power-platform)
  * [Forsikring](https://customers.microsoft.com/en-us/story/811345-aioi-nissay-dowa-insurance-microsoft-power-platform)
  * [Sundhedssektor](https://customers.microsoft.com/en-us/story/vnshs-health-provider-microsoft-flow) 

Finde [eksempler fra din branche](https://customers.microsoft.com/en-us/search?sq=%22Power%20Automate%22&ff=story_product_categories%26%3EPower%20Automate&p=0&so=story_publish_date%20desc)


Det første trin til oprettelse af en automatisering er at [tilmelde sig](sign-up-sign-in.md) eller, hvis du allerede har en-konto hos Power Automate, kan du [logge på](https://flow.microsoft.com/signin).

## <a name="types-of-flows"></a>Typer af flow

I tabellen nedenfor kan du få mere at vide om de typer flows, du kan bygge for at håndtere dine brugssager.

| **Procestype**                                                                       | **Use case**                                                                                  | **Automatiseringsmål**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Automatiserede flow](get-started-logic-flow.md)                 | Opret en automatisering, der udløses af en hændelse, f.eks. modtagelsen af en mail fra en bestemt person eller omtale af din virksomhed i sociale medier.| [Connectorer](https://docs.microsoft.com/connectors/) til tjenester i skyen eller i det lokale miljø opretter forbindelse til dine konti og gør det muligt for dem at kommunikere med hinanden. |
| [Øjeblikkelige flows](introduction-to-button-flows.md)              | Start en automatisering med et klik på en knap. Du kan automatisere gentagne opgaver fra skrivebordet eller mobilenheder. Du kan f.eks. sende en påmindelse straks til teamet med et enkelt tryk på en knap fra mobilenheden.                      |     En lang række opgaver, f.eks. anmodning om en godkendelse, en aktion i Teams eller SharePoint.                                                                                |
| [Planlagte flow](run-scheduled-tasks.md)                    | Planlæg en automatisering som f.eks. daglige dataoverførsler til SharePoint eller en database.             |Opgaver, der skal automatiseres i en tidsplan.                                                                            |
| [Forretningsprocesforløb](business-process-flows-overview.md) | Kontrollér, at alle i virksomheden følger samme proces, ved at definere en række trin, som personerne skal følge.                 | Processer, udført af mennesker, f.eks. anmodninger om kundeservice, godkendelser, it-udvikling,...                                                                        |
| [Flow for brugergrænseflade](ui-flows/overview.md)                                                | Optag klik og tastaturtryk fra skrivebordet og webapplikationer, og automatiser afspilningen af manuelle trin i ældre software.                    | Skrivebords- og webprogrammer, der ikke har API'er tilgængelige til automatisering.    |



## <a name="check-out-the-start-page"></a>Tjek startsiden 

[På startsiden](https://flow.microsoft.com) for Power Automate kan du [se et bredt udvalg af skabeloner](https://flow.microsoft.com/templates) og få mere at vide om nogle af de vigtige funktioner i Power Automate. Du kan få et hurtigt indtryk af, hvad der er muligt, og hvordan Power Automate kan være en hjælp for din virksomhed og dit liv.

Hver enkelt skabelon er designet til et specifikt formål. Der er f.eks. skabeloner til at sende en sms til dig, når du får en mail fra din chef, føje Twitter-kundeemner til Dynamics 365 eller sikkerhedskopiere dine filer. Disse skabeloner er bare toppen af isbjerget. De er beregnet til at inspirere dig til at oprette tilpassede flows til lige præcis de processer, du har behov for.

## <a name="create-your-first-flow"></a>Opret dit første flow 

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

## <a name="get-creative"></a>Vær kreativ

Nu da du har oprettet dit første flow på baggrund af en skabelon, skal du bruge en af de mere end [380 datakilder](https://flow.microsoft.com/connectors/), som understøttes af Power Automate, til at [oprette dine egne flows fra bunden](get-started-logic-flow.md).

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

    ![Detaljer om visningskode](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Find nemt dine flows

Når kreativiteten *flyder*, opretter du måske mange flows. Bare rolig; det er nemt at finde dine flows – du skal blot bruge søgefeltet på skærmen **Mine flows**, **Teamflows**, **Forbindelser** eller **Løsninger** til kun at få vist de flows, der matcher de angivne søgeord.

![Filtrer eller søg efter flows](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Søgefilteret finder kun de flows, der er indlæst på siden. Hvis du ikke kan finde dit flow, kan du prøve at vælge **Indlæs flere** nederst på siden.

## <a name="get-notifications-when-somethings-wrong"></a>Få meddelelser, når der er noget galt

Brug meddelelsescentret i Power Automate (som findes øverst til højre i designeren) til hurtigt at se en liste over de seneste mislykkede flows. I meddelelsescenteret vises et tal, der angiver antallet af seneste mislykkede flows.

Fra meddelelsescenteret kan du navigere til siden **Aktivitet** i Power Automate for at se de flows, der blev kørt for nylig, sendte meddelelser eller mislykkedes.

![Meddelelsescenter](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Brug mobilappen 

Download Power Automate-mobilappen til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows). Med denne app kan du [overvåge flowaktivitet](mobile-monitor-activity.md), [administrere dine flows](mobile-manage-flows.md) og [oprette flows på baggrund af skabeloner](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Vi er her for at hjælpe dig 

Vi er spændte på at se, hvad du vil bruge Power Automate til, og vi vil være sikre på, at du får en god oplevelse. Sørg for at se vores selvstudier med [vejledninger](https://flow.microsoft.com/guided-learning/), og [bliv en del af vores community](https://go.microsoft.com/fwlink/?LinkID=787467), så du kan stille spørgsmål og dele dine idéer. [Kontakt support](https://go.microsoft.com/fwlink/?LinkID=787479), hvis du får problemer.
