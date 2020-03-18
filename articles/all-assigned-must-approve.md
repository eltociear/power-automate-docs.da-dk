---
title: Opret et godkendelsesflow, som kræver, at alle skal godkende | Microsoft Docs
description: Opret et godkendelsesflow, der kræver, at alle skal godkende, eller én person skal afvise en anmodning.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: abf7be642e1c8e62db54bd7b5472ce29a330ad3a
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193536"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Opret et godkendelsesflow, som kræver, at alle skal godkende


Denne gennemgang viser, hvordan du opretter et godkendelsesforløb, der kræver, at alle (alle tildelte godkendere) skal acceptere, før en ferieanmodning kan godkendes, men enhver godkender kan afvise hele anmodningen.

Denne type godkendelsesforløb er nyttig i en organisation, der kræver, at en persons chef og chefens chef, begge skal acceptere en ferieanmodning, før den kan godkendes. Begge ledere kan imidlertid afvise anmodningen uden input fra den anden person.

> [!NOTE]
> Mens der i denne gennemgang fremhæves et scenarie med en feriegodkendelse, kan du bruge denne type godkendelsesflow i en hvilken som helst situation, hvor der kræves flere godkendere for at godkende en anmodning.
>
>

## <a name="prerequisites"></a>Forudsætninger

* Adgang til [Power Automate](https://flow.microsoft.com), Microsoft Office 365 Outlook og Microsoft Office 365-brugere.
* En SharePoint-[liste](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194).

    I denne gennemgang forudsættes det, at du har oprettet en SharePoint-liste, der bruges til at anmode om ferier. Se gennemgangen af de [parallelle godkendelser](parallel-modern-approvals.md), hvor du kan finde et detaljeret eksempel på, hvordan SharePoint-listen kan se ud.
* Kendskab til de grundlæggende funktioner i oprettelse af flow.

    Du kan gennemse, hvordan du tilføjer [handlinger, udløsere](multi-step-logic-flow.md#add-another-action) og [betingelser](add-condition.md). I de følgende trin forudsættes det, at du ved, hvordan disse handlinger udføres.

> [!NOTE]
> I denne gennemgang bruger vi SharePoint og Office 365 Outlook, men du kan bruge andre tjenester, f.eks. Zendesk, Salesforce, Gmail eller en af de mere end [200 tjenester](https://flow.microsoft.com/connectors/), som Power Automate understøtter.
>
>

## <a name="create-the-flow"></a>Opret flowet

> [!NOTE]
> Hvis du ikke tidligere har oprettet forbindelse til SharePoint eller Office 365, skal du følge vejledningen, når du bliver bedt om at logge på.
>
>

Der bruges tokens i denne gennemgang. Hvis du vi have vist listen over tokens, skal du trykke eller klikke på et vilkårligt inputobjekt og derefter søge efter tokenet på listen **Dynamisk indhold**, der åbnes.

Log på [Power Automate](https://flow.microsoft.com), og udfør derefter følgende trin for at oprette dit flow.

1. Vælg **Mine flows** > **Opret fra bunden af** øverst til højre på skærmen.
1. Tilføj udløseren **SharePoint – Når et element oprettes eller ændres**.
1. Angiv **webstedsadressen** til det SharePoint-websted, der er vært for din liste med ferieanmodninger, og vælg derefter listen **Listenavn**.
1. Tilføj handlingen **Office 365-brugere – Hent chef V2**, markér afkrydsningsfeltet **Bruger (UPN)** , og føj derefter tokenet **Oprettet af mail** til det.

    Tokenet **Oprettet af mail** er placeret i kategorien **Når et element oprettes eller ændres** på listen **Dynamisk indhold**. Dette token giver dynamisk adgang til data om chefen for den person, der oprettede elementet på SharePoint.

1. Tilføj en anden handling af typen **Office 365-brugere – Hent chef V2**, og føj derefter tokenet **Mail** til feltet **Bruger (UPN)** .

    Tokenet **Mail** er placeret i kategorien **Hent chef V2 2** på listen **Dynamisk indhold**. Dette token giver dynamisk adgang til chefens chefs mailadresse.

    Du kan også omdøbe kortet **Hent chef V2 2** til noget, der giver mening, f.eks. "Spring niveauchef over".
1. Tilføj handlingen **Start en godkendelse**, og vælg derefter **Alle fra listen over tildelte** på listen **Godkendelsestype**.

   > [!IMPORTANT]
   > Hvis en af godkenderne afviser, anses godkendelsesanmodningen for at være afvist for alle godkendere.
   >
   >
1. Brug følgende tabel som en vejledning til at fuldføre kortet **Start en godkendelse**.

   | Felt | Beskrivelse |
   | --- | --- |
   |  Godkendelsestype |Brug **Enhver fra listen over tildelte** til at angive, at enhver af godkenderne kan godkende eller afvise anmodningen. </p>Brug **Alle fra listen over tildelte** til at angive, at en anmodning kun er godkendt, hvis alle er enige, og at anmodningen afvises, hvis en enkelt person afviser den. |
   |  Titel |Titlen på godkendelsesanmodningen. |
   |  Tildelt til |Mailadresser til godkenderne. |
   |  Detaljer |Eventuelle yderligere oplysninger, du vil have sendt til de godkendere, der er angivet i feltet **Tildelt til**. |
   |  Elementlink |En URL-adresse til godkendelseselementet. I dette eksempel er dette et link til elementet i SharePoint. |
   |  Beskrivelse af elementlinket |En tekst med beskrivelse til **elementlinket**. |

   > [!TIP]
   > Handlingen **Start en godkendelse** indeholder flere tokens, herunder **Svar** og **Oversigt over svar**. Brug disse tokens i flowet til at levere detaljeret rapportering af resultaterne efter kørsel af et flow til en godkendelsesanmodning .
   >
   >

    Kortet **Start en godkendelse** er en skabelon til godkendelsesanmodning, der sendes til godkendere. Du kan konfigurere det på den måde, der er mest anvendelig i din organisation. Her er et eksempel.

    ![start en godkendelse](media/all-assigned-must-approve/start-an-approval-card.png)

1. Tilføj handlingen **Office 365 Outlook – Send en mail**, og konfigurer den derefter, så du kan sende en mail med resultaterne af anmodningen.

    Her følger et eksempel på, hvordan kortet **Send en mail** kan se ud.

    ![send en mail](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> En vilkårlig handling, der følger kørsler af handlingen **Start en godkendelse** baseret på dit valg på listen **Godkendelsestype** på kortet **Start en godkendelse**. I følgende tabel vises funktionsmåden baseret på det, du har valgt.
>
>

| Godkendelsestype | Adfærd |
| --- | --- |
| Enhver fra listen over tildelte |Handlinger, der følger efter kørsel af handlingen **Start en godkendelse**, efter en af godkenderne har besluttet sig. |
| Alle fra listen over tildelte |Handlinger, der følger efter kørsel af handlingen **Start en godkendelse**, efter en godkender afviser eller alle godkender anmodningen. |

Angiv et navn til dit flow øverst på skærmen i feltet **Flownavn** , og vælg derefter **Opret flow** for at gemme det.

Tillykke, dit flow er fuldført! Hvis du har fulgt gennemgangen, ligner dit flow denne afbildning.

![samlet flowafbildning](media/all-assigned-must-approve/overall-flow.png)

Hver gang et element føjes til din SharePoint-liste, eller et element ændres, udløses dit flow og sender godkendelsesanmodninger til alle godkendere, der er anført i feltet **Tildelt til** på kortet **Start en godkendelse**. Dit flow sender godkendelsesanmodninger via mobilappen Power Automate og via mail. Den person, der opretter elementet i SharePoint, modtager en mail, hvor resultaterne er opsummeret, og som klart angiver, om anmodningen blev godkendt eller afvist.

Her er et eksempel på den godkendelsesanmodning, der sendes til hver godkender.

![anmodning om godkendelse](media/all-assigned-must-approve/approval-request.png)

Her er et eksempel på, hvordan et svar og en svaroversigt kan se ud, når dine flow kører.

![svartokens](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Få mere at vide om godkendelse

* [Enkelt godkenders moderne godkendelse](modern-approvals.md)
* [Sekventielle moderne godkendelser](sequential-modern-approvals.md)
* [Parallelle moderne godkendelser](parallel-modern-approvals.md)
* [Godkendelser og Microsoft Common Data Service](common-data-model-approve.md)
* [Godkend anmodninger, mens du er på farten](mobile-approvals.md)
