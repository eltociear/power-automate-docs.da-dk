---
title: Fejlfinding af et flow | Microsoft Docs
description: Løs nogle af de mest almindelige årsager til, at flows ikke fungerer
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
ms.date: 07/16/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8e0344411dbda57009822376cc3c980f599b1877
ms.sourcegitcommit: d4857e5ce087f9a72469ff08a1a91349a0a94505
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/16/2020
ms.locfileid: "3598026"
---
# <a name="troubleshooting-a-flow"></a>Fejlfinding i et flow


## <a name="repair-tips-in-email"></a>Mail med reparationstip

Reparationstip sendes til ejerne af flows via mail, når et flow mislykkes. Disse reparationstip i mails indeholder specifik feedback om bestemte fejl, der kan handles på. En almindelig fejl er f.eks. konfiguration af et flow, der forsøger at hente en persons leder i Office 365, men der er ikke konfigureret nogen leder i Azure Active Directory (Azure AD). Hvis dette eller flere andre betingelser forårsager fejl i dit flow, får du en mail med reparationstip som denne:

![Reparationstip](media/fix-flow-failures/repair-tips-email-2.png)

Mailen med reparationstip indeholder følgende afsnit:

Navn|Beskrivelse
---|---
Time|Viser det klokkeslæt, hvor flowet først mislykkedes.
Hvad skete der?|Indeholder en beskrivelse af det problem, der forårsagede fejlen i flowet.
Hvordan løser jeg problemet?|Indeholder tip til løsning af det problem, der forårsager fejlen i flowet.
Tip til fejlfinding|Indeholder oplysninger om, hvor mange gange flowet mislykkedes, og et link til at prøve flowet igen med de samme inputdata.

Hvis du vil løse de rapporterede fejl, skal du vælge **Ret mit flow** og følge fremgangsmåden i mailen med reparationstip.

Mails med reparationstip er valgfri. Hvis du ikke vil modtage dem, skal du blot slå dem fra i menuen for det specifikke flows egenskaber.

Hvis dit flow mislykkes, kan du også foretage fejlfinding af det direkte i Power Automate.  Her er nogle almindelige fejlscenarier og tip til, hvordan du løser dem.

## <a name="identify-the-error"></a>Identificere fejlen

1. Vælg **Mine flows**.
1. Vælg det flow, der mislykkedes.
1. I sektionen **Kørselshistorik for 28 dage** skal du vælge **datoen** for den mislykkede kørsel.
   
   Der vises detaljer om flowet, og for mindst ét trin vises et ikon med et rødt udråbstegn.
1. Åbn dette mislykkede trin, og gennemse derefter fejlmeddelelsen.

   I højre rude kan du se **detaljerne** om fejlen og **Sådan løses problemet** 

   ![Fejlmeddelelse](./media/fix-flow-failures/identify-error.png)


## <a name="authentication-failures"></a>Godkendelsesfejl
I mange tilfælde fungerer flowet ikke, fordi der er en godkendelsesfejl. Hvis du har denne type fejl, indeholder fejlmeddelelsen **Uautoriseret**, eller fejlkoden **401** eller **403** vises. Du kan normalt løse en godkendelsesfejl ved at opdatere forbindelsen:

1. I højre rude skal du klikke på **Vis forbindelser** under **Sådan løses problemet**.
1. Rul til den forbindelse, hvor fejlmeddelelsen **Uautoriseret** vises.
1. Ud for forbindelsen skal du klikke eller trykke på linket **Ret forbindelse** i meddelelsen om den forbindelse, der ikke er godkendt.
1. Kontrollér dine legitimationsoplysninger ved at følge de anvisninger, der vises. Gå tilbage til det flow, der ikke kunne køres, og klik eller tryk derefter på **Send igen**.

   ![Fejlmeddelelse](./media/fix-flow-failures/resubmit.png)
   
 Flowet bør nu køre som forventet.

## <a name="action-configuration"></a>Konfiguration af handling
Flows mislykkes også, hvis en indstilling i en handling i flowet ikke fungerer som forventet. I dette tilfælde indeholder fejlmeddelelsen **Forkert anmodning** eller **Ikke fundet**, eller fejlkoden **400** eller **404** vises.

Fejloplysningerne skal angive, hvordan du retter fejlen. Du skal klikke eller trykke på knappen **Rediger** og derefter løse problemet i flowdefinitionen. Gem det opdaterede flow, og klik eller tryk derefter på **Send igen** for at forsøge at køre det igen med den opdaterede konfiguration.

## <a name="other-failures"></a>Andre fejl
Hvis fejlkoden **500** eller **502** vises, er der tale om en midlertidig eller forbigående fejl. Klik eller tryk på **Send igen** for at afprøve flowet igen.

## <a name="getting-help-from-support-or-the-community"></a>Få hjælp fra support eller community'et

Når du har brug for hjælp, kan du bruge funktionerne **Selvhjælp** eller **Bed om hjælp**.

### <a name="self-help"></a>Selvhjælp 

1. Gå til [supportwebstedet](https://flow.microsoft.com/support/).
1. Gå til kategorien **Selvhjælp**, og vælg en af mulighederne for selvhjælp.

    ![Sektionen Bed om hjælp. Kontakt Support.](media/fix-flow-failures/self-help-section.png)

### <a name="ask-for-help-from-others"></a>Bede andre om hjælp

1. Gå til [supportwebstedet](https://flow.microsoft.com/support/).
1. Vælg **Kontakt support** i sektionen **Bed om hjælp**.
    
    ![Sektionen Bed om hjælp. Kontakt Support.](media/fix-flow-failures/ask-for-help.png)

1. Udfyld felterne **Problemtype**, **Kategori** og **Fortæl os, hvad du har brug for hjælp til**, og vælg derefter **Se løsninger**. 

1. Bemærk, at afsnittet **Løsninger** vises, efter du har valgt **Se løsninger**. Det indeholder en liste over resultater, som du kan bruge til at løse det problem, du står overfor. 

    ![Oplysninger om integreret hjælpefunktion](media/fix-flow-failures/support-request.png)

Hvis du har brug for hjælp med et problem, kan du få den via vores [community](https://go.microsoft.com/fwlink/?LinkID=787467) og Microsoft. 

