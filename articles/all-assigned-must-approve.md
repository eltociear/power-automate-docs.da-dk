---
title: Opret et godkendelsesflow, som kræver, at alle skal godkende | Microsoft Docs
description: Opret et godkendelsesflow, der kræver, at alle skal godkende, eller én person skal afvise en anmodning.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3f668d4462c06e061efe2a03b4e5e842364c4b6e
ms.sourcegitcommit: 5b1965a0c319c4294b7dc0c829120ed1f4f90444
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/25/2020
ms.locfileid: "3299293"
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
* En SharePoint[-liste](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194).

    I denne gennemgang forudsættes det, at du har oprettet en SharePoint-liste, der bruges til at anmode om ferier. Se gennemgangen af de [parallelle godkendelser](parallel-modern-approvals.md), hvor du kan finde et detaljeret eksempel på, hvordan SharePoint-listen kan se ud.
* Kendskab til grundlæggende oplysninger om oprettelse af flow.

    Du kan gennemse, hvordan du tilføjer [handlinger, udløsere](multi-step-logic-flow.md#add-another-action) og [betingelser](add-condition.md). I de følgende trin forudsættes det, at du ved, hvordan disse handlinger udføres.

> [!NOTE]
> Selv om vi bruger SharePoint og Office 365 Outlook i denne gennemgang, kan du bruge andre tjenester, f.eks. Zendesk, Salesforce, Gmail eller en af de mere end [200 tjenester](https://flow.microsoft.com/connectors/), som Power Automate understøtter.
>
>

## <a name="create-the-flow"></a>Opret flowet

> [!NOTE]
> Hvis du ikke tidligere har oprettet forbindelse til SharePoint eller Office 365, skal du følge vejledningen, når du bliver bedt om at logge på.
>
>

Der bruges tokens i denne gennemgang. Hvis du vi have vist listen over tokens, skal du trykke eller klikke på et vilkårligt inputobjekt og derefter søge efter tokenet på listen **Dynamisk indhold**, der åbnes.

Log på [Power Automate](https://flow.microsoft.com), og udfør derefter følgende trin for at oprette dit flow.

1. Vælg **Mine flows** > **Ny** > **Automatiseret – fra bunden** øverst til højre på skærmen.
1. Giv dit flow et navn, og tilføj derefter udløseren for **SharePoint – Når et element oprettes eller redigeres**.
1. Angiv **Webstedsadresse** til det SharePoint-websted, der er vært for din liste med ferieanmodninger, og vælg derefter en liste fra **Listenavn**.
1. Vælg **Nyt trin**, tilføj handlingen **Hent chef (V2)** for Office 365, markér afkrydsningsfeltet **Bruger (UPN)**, og føj derefter tokenet **Oprettet af mail** til det.

    Tokenet **Oprettet af mail** er placeret i kategorien **Når et element oprettes eller ændres** på listen **Dynamisk indhold**. Dette token giver dynamisk adgang til data om chefen for den person, der oprettede elementet på SharePoint.

1. Vælg **Nyt trin**, tilføj en anden handling af **Hent chef (V2)** for Office 365, og føj derefter tokenet **Mail** til feltet **Bruger (UPN)**.

    Tokenet **Mail** er placeret i kategorien **Hent chef (V2)** på listen **Dynamisk indhold**. Dette token giver dynamisk adgang til chefens chefs mailadresse.

    Du kan også omdøbe kortet **Hent chef (V2) 2** til noget, der giver mening, f.eks. "Spring niveauchef over".
1. Vælg **Nyt trin**, tilføj handlingen **Start og vent for en godkendelse**, og vælg derefter **Godkend/afvis – Alle skal godkende** på listen **Godkendelsestype**.

   > [!IMPORTANT]
   > Hvis en af godkenderne afviser, anses godkendelsesanmodningen for at være afvist for alle godkendere.
   >
   >
1. Brug følgende tabel som en vejledning til at fuldføre kortet **Start og vent på en godkendelse**.

   | Felt | Beskrivelse |
   | --- | --- |
   | Godkendelsestype |Se [godkendelsestyperne](#approval-types-and-their-behaviors). |
   |  Titel |Titlen på godkendelsesanmodningen. |
   |  Tildelt til |Mailadresser til godkenderne. |
   |  Detaljer |Eventuelle yderligere oplysninger, du vil have sendt til de godkendere, der er angivet i feltet **Tildelt til**. |
   |  Elementlink |En URL-adresse til godkendelseselementet. I dette eksempel er dette et link til elementet i SharePoint. |
   |  Beskrivelse af elementlinket |En tekst med beskrivelse til **elementlinket**. |

   > [!TIP]
   > Handlingen **Start og vent på en godkendelse** indeholder flere tokens, herunder **Svar** og **Resultat**. Brug disse tokens i flowet til at levere detaljeret rapportering af resultaterne efter kørsel af et flow til en godkendelsesanmodning .
   >
   >

    Kortet **Start og vent på en godkendelse** er en skabelon til godkendelsesanmodning, der sendes til godkendere. Du kan konfigurere det på den måde, der er mest anvendelig i din organisation. Her er et eksempel.

    ![Start og vent på en godkendelse](media/all-assigned-must-approve/start-an-approval-card.png)

    Når der er konfigureret et flow med handlingen **Start og vent på en godkendelse** med **Godkend/afvis – Alle skal godkende**, venter den, indtil alle **Tildelt til** har godkendt eller mindst en **Tildelt til** har afvist godkendelsesanmodningen.

    >[!TIP]
    >Tilføj trinnet **Betingelse**, hvis du vil have flowet til at kontrollere svaret på godkendelsesanmodningen og udføre forskellige handlinger på baggrund af **Resultat**. **Resultat** kan være **Godkend** eller **Afvis**. 

    Lad os fortsætte flowet og sende en mail, når der træffes beslutning om godkendelsesanmodningen.

1. Vælg **Nyt trin**, søg efter "Send en e-mail", tilføj handlingen **Send en e-mail (V2)** for Office 365 Outlook, og konfigurer derefter handlingen til at sende en e-mail med resultaterne fra anmodningen til den person, der vil have ferie.

    Her er et eksempel på, hvordan kortet **Send en mail (V2)** kan se ud.

    ![send en mail](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> En vilkårlig handling, der følger efter kørsler af handlingen **Start og vent på en godkendelse** ud fra dit valg på listen **Godkendelsestype** på kortet **Start og vent på en godkendelse**. I følgende tabel vises funktionsmåden baseret på det, du har valgt.
>
>

### <a name="approval-types-and-their-behaviors"></a>Godkendelsestyper og deres funktionsmåder

| Godkendelsestype | Funktionsmåde |
| --- | --- |
| Godkend/afvis – Alle skal godkende | Godkendelse eller afvisning er nødvendig, for at **alle** godkendere kan fuldføre anmodningen. </p> De handlinger, der følger efter kørsler af handlingen **Start og vent på en godkendelse**, efter at **alle** godkenderne har godkendt, eller når en enkelt afvisning er udført.|
| Godkend/afvis – Første til at svare | Godkendelse eller afvisning af enhver godkender, fuldfører anmodningen.  </p> De handlinger, der følger efter kørsel af handlingen **Start og vent på en godkendelse**, efter en af godkenderne har besluttet sig.|
| Brugerdefinerede svar – Vent på alle svar | Alle godkendere skal reagere for at fuldføre processen. |
| Brugerdefinerede svar – Vent på ét svar | Et svar fra enhver godkender fuldfører processen. |

Vælg **Gem** øverst på skærmen for at gemme dit flow.

Tillykke, dit flow er fuldført! Hvis du har fulgt gennemgangen, ligner dit flow denne afbildning.

![samlet flowafbildning](media/all-assigned-must-approve/overall-flow.png)

Hver gang et element føjes til din SharePoint-liste, eller et element ændres, udløses dit flow og sender godkendelsesanmodninger til alle godkendere, der er anført i feltet **Tildelt til** på kortet **Start og vent på en godkendelse**. Dit flow sender godkendelsesanmodninger via mobilappen Power Automate og via mail. Den person, der opretter elementet i SharePoint, modtager en mail, hvor resultaterne er opsummeret, og som klart angiver, om anmodningen blev godkendt eller afvist.

Her er et eksempel på den godkendelsesanmodning, der sendes til hver godkender.

![anmodning om godkendelse](media/all-assigned-must-approve/approval-request.png)

Her er et eksempel på, hvordan et svar og en svaroversigt kan se ud, når dine flow kører.

![svartokens](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Få mere at vide om godkendelse

* [Enkelt godkenders moderne godkendelse](modern-approvals.md)
* [Sekventielle moderne godkendelser](sequential-modern-approvals.md)
* [Parallelle moderne godkendelser](parallel-modern-approvals.md)
* [Godkendelser og Common Data Service](common-data-model-approve.md)
* [Godkend anmodninger, mens du er på farten](mobile-approvals.md)
