---
title: Introduktion til knapudløsende tokens | Microsoft Docs
description: Introduktion til tokens, der udløser knap, til Microsoft-knapflows.
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
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b57e9dee27a2d22159a9cd805c65034a5e5bb578
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74363884"
---
# <a name="get-started-with-button-trigger-tokens"></a>Kom godt i gang med tokens, der udløser knap
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-trigger-tokens"></a>Hvad er tokens, der udløser knap?
Tokens, der udløser knap, er datapunkter, der er kendte og tilgængelige for enheden, hvor på der kører et [knapflow](introduction-to-button-flows.md). Disse tokens ændrer sig på baggrund af faktorer, såsom den aktuelle tid eller enhedens geografiske placering et givent øjeblik.  

For eksempel, hvis du kører et knapflow på en smarttelefon, er det sandsynligt, at **telefonen kender tiden** på din aktuelle placering samt datoen og din nuværende adresse. I denne sammenhæng bestemmes tidspunktet, datoen og adressen for telefonens placering på tidspunktet for kørslen af knapflowet. De er automatisk tilgængelige til brug i et hvilket som helst knapflow, der bliver udført på enheden. Du kan bruge disse udløsertokens til at opbygge nyttige flows, der kan minimere gentagne opgaver, såsom at angive din placering eller at spore, hvor meget tid du brugte på en bestemt opgave eller et tjenestekald.

### <a name="list-of-button-trigger-tokens"></a>Liste over tokens, der udløser knap?
Her er listen over tilgængelige tokens, der udløser knap, når du opretter dine knapflows.

| Parameter | Beskrivelse |
| --- | --- |
| By |Byen, som enheden kører flowet i, bliver lokaliseret. |
| Land/område |Landet/området, som enheden kører flowet i, bliver lokaliseret. |
| Komplet adresse |Den komplette adresse, som enheden kører flowet på, bliver lokaliseret. |
| Breddegrad |Breddegraden, hvor enheden kører flowet, bliver lokaliseret. |
| Længdegrad |Længdegraden, hvor enheden kører flowet, bliver lokaliseret. |
| Postnummer |Postnummeret, hvor enheden kører flowet, bliver lokaliseret. |
| Stat |Staten, som enheden kører flowet i, bliver lokaliseret. |
| Gade |Gaden, som enheden kører flowet i, bliver lokaliseret. |
| Tidsstempel |Tidspunktet i området, hvor enheden kører flowet, bliver lokaliseret. |
| Dato |Datoen i området, hvor enheden kører flowet, bliver lokaliseret. |
| Brugernavn |Brugernavnet på personen, der er logget på enheden, som kører flowet. |
| Brugerens e-mail-adresse |E-mail-adressen på den person, der er logget på enheden, som kører flowet. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Opret et knapflow, der bruger udløsertokens
Når du opretter en knap, kan du bruge udløsertokens til at tilføje avanceret funktionalitet til din knap.

I denne gennemgang opretter vi et knapflow på en Android-enhed. Knapflowet vil bruge udløsertokens til at sende datoen og din komplette adresse i en "**arbejder hjemmefra**"-e-mail til din chef.

Under denne gennemgang vises skærmbilleder fra en Android-enhed, men du får dog også samme oplevelse på iOS- og Windows Phone-enheder.

### <a name="prerequisites"></a>Forudsætninger
* En arbejds- eller skolemailadresse eller en [Microsoft-konto](https://account.microsoft.com/about?refd=www.microsoft.com) med adgang til Power Automate.
* Mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).

Lad os komme i gang:

1. Start Flow, og vælg **Gennemse**   
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/1.png)  
2. Vælg **Send en "Arbejder hjemmefra i dag"-e-mail til din leder**-tjeneste under kategorien for **Knap**   
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/2.png)  
3. Vælg **BRUG DENNE SKABELON**  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/3.png)  
4. Vælg **Rediger** på **Send en e-mail**-kortet  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Tryk på tekstboksen for **Emne**, og indtast: " **i dag -** " i tekstboksen efter "AH"-teksten. Bemærk, at når du har trykket på tekstboksen, åbnes der også en liste over parametre/tokens. Vi bruger et af disse tokens i næste trin til at tilføje datoen til e-mailens emne.  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/4.png)  
6. Placer markøren i tekstboksen for emne, rul til den **manuelle** liste over parametre, og tryk på **Dato**. Bemærk, at dato-parameteren nu befinder sig i tekstboksen for **Emne**:  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/6.png)  
7. Rul til tekstboksen for **Meddelelse**, og tryk derefter på standardmeddelelsen, så yderligere tokens kan blive indføjet der.  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/7.png)  
8. Tryk på parameteren for **Komplet adresse**, tryk derefter på **Opret**  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/8.png)  
9. Tryk på **Færdig**. Nu har du oprettet dit knapflow.  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Kør knapflowet
**BEMÆRK!** : Dette knapflow sender din aktuelle placering via e-mail.  

1. Tryk på kategorien for **Knapper** i bunden af skærmen. Her ser du en liste over knapper, som du har tilladelse til at bruge. Tryk på den knap, der repræsenterer det knapflow, du netop har oprettet:  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/10.png)  
2. Tryk på **TILLAD** for at angive, at det er OK, at knapflowet får adgang til oplysninger om enhedens placering:  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/11.png)  
3. Bemærk, at e-mailen blev sendt til din chef i løbet af et øjeblik:  
   ![token, der udløser knap](./media/introduction-to-button-trigger-tokens/12.png)  

Tillykke, du har netop oprettet et knapflow, der bruger udløsertokens til både dato og komplet adresse. 

## <a name="next-steps"></a>Næste trin
* [Del knapflows](share-buttons.md)
* [Få mere at vide om knapflows](introduction-to-button-flows.md)
