---
title: Fejlfinding i forbindelse med et flow | Microsoft Docs
description: Løs nogle af de mest almindelige årsager til, hvorfor flows ikke fungerer
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: faa0b50a9a525d5abaa818d05be8a97e6ad6663b
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297313"
---
# <a name="troubleshooting-a-flow"></a>Fejlfinding af et flow


## <a name="repair-tips-in-email"></a>Mail med reparationstip

Reparationstip sendes til ejerne af flowene via mail, når et flow mislykkes. Disse reparationstip i mails indeholder specifik feedback om bestemte fejl, der kan handles på. En almindelig fejl er f.eks. konfiguration af et flow, der forsøger at hente en persons leder i Office 365, men der er ikke konfigureret nogen leder i Azure Active Directory (Azure AD). Hvis dette eller flere andre betingelser forårsager fejl i dit flow, får du en mail med reparationstip som denne:

![Reparationstip](media/fix-flow-failures/repair-tips-email.png)

Mailen med reparationstip indeholder følgende afsnit:

Navn|Beskrivelse
---|---
Periode|Viser det klokkeslæt, hvor flowet først mislykkedes.
Hvad skete der?|Indeholder en beskrivelse af det problem, der forårsagede fejlen i flowet.
Hvordan løser jeg problemet?|Indeholder tip til løsning af det problem, der forårsager fejlen i flowet.
Tip til fejlfinding|Indeholder oplysninger om, hvor mange gange flowet mislykkedes, og et link til at prøve flowet igen med de samme inputdata.

Hvis du vil løse de rapporterede fejl, skal du vælge **Ret mit flow** og følge trinnene i mailen med reparationstip.

Mails med reparationstip er valgfri. Hvis du ikke vil modtage dem, skal du blot slå dem fra i menuen med egenskaber for det specifikke flow.

Hvis dit flow mislykkes, kan du også foretage fejlfinding af det direkte i Power Automate.  Her er nogle almindelige fejlscenarier og tip til, hvordan du løser dem.

## <a name="identify-the-error"></a>Identificer fejlen
Før du kan udbedre et flow, skal du identificere, hvorfor det ikke fungerer. Klik eller tryk på ikonet for meddelelser øverst på webportalen (eller åbn fanen **Aktivitet** i mobilappen), og klik eller tryk derefter på dit flow på den viste liste.

![Beskeder](./media/fix-flow-failures/notifications-toolbar.png)

Der vises detaljer om flowet, og for mindst ét trin vises et ikon med et rødt udråbstegn. Åbn dette trin, og gennemse fejlmeddelelsen.

![Fejlmeddelelse](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Godkendelsesfejl
I mange tilfælde fungerer flowet ikke på grund af en godkendelsesfejl. Hvis du har denne type fejl, indeholder fejlmeddelelsen **Uautoriseret** eller fejlkoden **401** eller **403** vises. Du kan normalt løse en godkendelsesfejl ved at opdatere forbindelsen:

1. Øverst på webportalen skal du klikke eller trykke på tandhjulsikonet for at åbne menuen **Indstillinger** og derefter klikke eller trykke på **Forbindelser**.
2. Rul til den forbindelse, som du så fejlmeddelelsen **Uautoriseret** for.
3. Ud for forbindelsen skal du klikke eller trykke på linket **Bekræft adgangskode** i meddelelsen om den forbindelse, der ikke er godkendt.
4. Kontrollér dine legitimationsoplysninger ved at følge de anvisninger, der vises. Vend tilbage til det fejlbehæftede flow, og klik eller tryk derefter på **Send igen**.
   
    Flowet bør nu køre som forventet.

## <a name="action-configuration"></a>Konfiguration af handling
Der kan også opstå fejl i et flow, hvis en indstilling under kørslen ikke fungerer som forventet. I dette tilfælde indeholder fejlmeddelelsen **Forkert anmodning** eller **Blev ikke fundet**, eller fejlkoden **400** eller **404** vises.

Fejlmeddelelsen skal angive, hvordan du retter fejlen. Du skal klikke eller trykke på knappen **Rediger** og derefter løse problemet i flowdefinitionen. Gem det opdaterede flow, og klik eller tryk på **Send igen** for at forsøge at køre det igen med den opdaterede konfiguration.

## <a name="other-failures"></a>Andre fejl
Hvis fejlkoden **500** eller **502** vises, er der tale om en midlertidig eller forbigående fejl. Klik eller tryk på **Send igen** for at afprøve flowet igen.

## <a name="getting-help-from-support-or-the-community"></a>Få hjælp fra support eller community'et

Når du har brug for hjælp, kan du bruge vores muligheder for **Selvhjælp**, eller du kan **bede om hjælp** fra andre.

### <a name="self-help"></a>Selvhjælp 

1. Gå til [supportwebstedet](https://flow.microsoft.com/support/).
1. Gå til kategorien **Selvhjælp**, og vælg en af mulighederne for selvhjælp.

    ![Afsnittet Bed om hjælp. Kontakt support.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Bed andre om hjælp

1. Gå til [supportwebstedet](https://flow.microsoft.com/support/).
1. Vælg **Kontakt support** i afsnittet **Bed om hjælp**.
    
    ![Afsnittet Bed om hjælp. Kontakt support.](media/fix-flow-failures/ask-for-help.png)

1. Udfyld felterne **Problemtype**, **Kategori** og **Fortæl os, hvad du har brug for hjælp til**, og vælg derefter **Se løsninger**. 

1. Bemærk, at afsnittet **Løsninger** vises, efter du har valgt **Se løsninger**. Det indeholder en liste over resultater, som du kan bruge til at løse det problem, du står overfor. 

    ![Integrerede hjælpoplysninger](media/fix-flow-failures/integrated-helper-details.png)

Hvis du har brug for hjælp med et problem, kan du få hjælp via vores [community](https://go.microsoft.com/fwlink/?LinkID=787467) og Microsoft. 

