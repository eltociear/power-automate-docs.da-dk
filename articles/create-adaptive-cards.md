---
title: Opret flows, der sender tilpassede kort til Microsoft Teams | Microsoft Docs
description: Lær, hvordan du opretter flows, der sender indhold med omfattende formatering sammen med tilpassede kort til Microsoft Teams.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/04/2020
ms.author: deonhe
ms.openlocfilehash: 186526427d8de7ee05dd6860e302faae5ac1d97f
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297423"
---
# <a name="create-your-first-adaptive-card"></a>Opret dit første adaptive kort

Adaptive kort i Power Automate kan enten dele blokke af oplysninger eller indsamle data via en formular for en given datakilde. 

I begge tilfælde skal du skitsere, hvilke datasæt du vil dele og/eller de data, formularen skal indsamle. 

>[!TIP]
>Brug enkle datablokke i stedet for komplekse tabelmatrixer.

## <a name="prerequisites"></a>Forudsætninger

<!-- Is it still called Flow App? -->
- Microsoft Teams med Flow App installeret.

## <a name="add-an-action"></a>Tilføj en handling

I denne proces skal du tilføje en handling, der skal bruge dataene fra tidligere handlinger i flowet til at poste oplysninger til en Microsoft Teams-kanal.

1. Log på Power Automate.
1. Vælg **Mine flow** på navigationslinjen foroven.
1. Vælg **Ny** > **Øjeblikkeligt fra bunden**.
1. Giv dit flow et navn.
1. Vælg **Udløs et flow manuelt** som udløser.
1. Vælg **Opret**.

    <!-- | [./media/image5.png](./media/image5.png) | [./media/image6.png](./media/image6.png) | -->

1. Vælg **Nyt trin**.
1. Søg efter **Microsoft Teams**, og vælg derefter **Send et adaptivt kort til en Teams-kanal, og vent på svar** som handling.
1. Vælg det **Team** og den **Kanal**, du vil poste kortet til.
1. Indsæt denne JSON i **meddelelsesfeltet**.

    ``` JSON
    {
        "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
        "type": "AdaptiveCard",
        "version": "1.0",
        "body": [
            {
                "type": "TextBlock",
                "text": "Poll Request",
                "id": "Title",
                "spacing": "Medium",
                "horizontalAlignment": "Center",
                "size": "ExtraLarge",
                "weight": "Bolder",
                "color": "Accent"
            },
            {
                "type": "TextBlock",
                "text": "Header Tagline Text",
                "id": "acHeaderTagLine",
                "separator": true
            },
            {
                "type": "TextBlock",
                "text": "Poll Header",
                "weight": "Bolder",
                "size": "ExtraLarge",
                "spacing": "None",
                "id": "acHeader"
            },
            {
                "type": "TextBlock",
                "text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer vestibulum lorem eget neque sollicitudin, quis malesuada felis ultrices. ",
                "id": "acInstructions",
                "wrap": true
            },
            {
                "type": "TextBlock",
                "text": "Poll Question",
                "id": "acPollQuestion"
            },
            {
                "type": "Input.ChoiceSet",
                "placeholder": "Select from these choices",
                "choices": [
                    {
                        "title": "Choice 1",
                        "value": "Choice 1"
                    },
                    {
                        "title": "Choice 2",
                        "value": "Choice 2"
                    },
                    {
                        "title": "Choice 3",
                        "value": "Choice 3"
                    }
                ],
                "id": "acPollChoices",
                "style": "expanded"
            }
        ],
        "actions": [
            {
                "type": "Action.Submit",
                "title": "Submit",
                "id": "btnSubmit"
            }
        ]
    }
    ```

1. Foretag følgende erstatninger i JSON.

    >[!IMPORTANT]
    >Fjern ikke anførselstegn, når du foretager erstatningerne. Du kan ændre bilvalgene, så de passer til dine behov:

    Tekst, der skal ændres | Ny tekst
    ------|------
    Slogantekst for header|Power Automate-afstemning
    Header for afstemning| Foretrukken bilmodel
    | Afstemningsspørgsmål   | Stem på din foretrukne bilmodel på baggrund af de valgmuligheder, der er angivet her. 
    Erstat den latinske tekst med en årsag til eller forretningskontekst for, hvorfor du foretager afstemningen.      |  Vi foretager en afstemning blandt vores medarbejdere for at finde ud af, om vi skal angive personligt tilpassede parkeringspladser, der i størrelse passer til de mest populære biler. 
    | Valgmulighed 1 (erstat begge steder)  | Tesla   |
    | Valgmulighed 2 (erstat begge steder) | Lexus |
    | Valgmulighed 3 (erstat begge steder) | Honda |

1. Vælg **Nyt trin**, og søg derefter efter, og vælg en af handlingerne under **Send en mail**, som du har adgang til. 
1. Angiv mailmodtageren som den person, der har valgt knappen Øjeblikkeligt (brug tagget **Mail** fra det dynamiske indhold fra **udløseren**).
1. Konfigurer **brødteksten** i mailen som følger. Erstat ordene i krøllede parenteser "{}" med dynamiske tokens:  
    **Dit afstemningssvar var {acPollChoices}** (acPollChoices er dynamisk indhold fra handlingen Vent på svar).  **Det blev sendt af {Brugernavn}** (Brugernavn er dynamisk indhold fra udløseren)

## <a name="test-your-adaptive-card"></a>Test dit adaptive kort

Hvis du vil teste dit arbejde, skal du køre det flow, du oprettede tidligere, og bekræfte følgende:

- Der er ingen fejl i flowkørslen, og der ventes på svaret, hvilket vises af ventesymbolet for handlingen for adaptivt kort på kørselsskærmen. 

- Det nye adaptive kort er postet for Teams-kanalen.

- Når du svarer på kortet ved at vælge en bilmodel, skal du vælge knappen **Indsend** nederst på det adaptive kort:

    - Der bør ikke opstå fejl på det adaptive kort.

    - Flowkørslen fuldføres.

- Kortudskiftning er relevant efter indsendelse, hvis du har konfigureret området **Opdater meddelelse** nederst under **Vent på svar**-handlingerne (vises ud for det tilsvarende erstatningskort). Ellers nulstiller alle indsendelser ganske enkelt formularen.

    ![Erstatningskort](./media/adaptive-cards/update-message-2.png)

- Mailmeddelelsen indeholder den brødtekst, der viser, hvem der har indsendt svaret, og hvilken bil der er valgt.

Tillykke! Du har lige oprettet dit første interaktive adaptive kort!

![Første kort er færdigt](media/adaptive-cards/finished-first-card.png) 


## <a name="troubleshooting-tips-for-adaptive-cards"></a>Fejlfindingstip til adaptive kort

De mest almindelige problemer, du vil støde på, når du opretter adaptive kort, er:

-   Flowkørselsfejl skyldes ofte af en af følgende faktorer:

    -  Flow-appen er ikke installeret i Microsoft Teams – [Installér Flow-appen](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams) i Teams. 
    
    I dette tilfælde kan fejled se ud som på dette skærmbillede:  

    ![Fejlmeddelelse](media/adaptive-cards/error-message.png)

    -  Forkert formateret JSON – Dette er normalt ikke så komplekst, som man kan frygte. Det er normalt bare situationer, hvor:

        - Der er krøllede anførselstegn eller mangler anførselstegn omkring værdier i JSON. Kontrollér altid JSON for at sikre, at alle tekstværdier er omfattet af dobbelt anførselstegn, og at tal er omfattet af anførselstegn. Alle anførselstegn bør være lige og ikke krøllede.

        - Du kan validere formatet af din JSON ved at indsætte JSON i [editoren for kortnyttedata](https://adaptivecards.io/designer/).

    - URL-adresser til manglende billeder – alle billedværdier i adaptive kort skal henvise til en gyldig URL-adresse. Komplet billedindhold understøttes ikke direkte i et adaptivt kort. Test dine billedlinks ved at indsætte URL-adressen i browseren for at se, om et billede vises.

- Adaptive kort ser muligvis ikke ud som forventet på grund af stil og skemabegrænsninger:

    - Kontrollér, at pladsholderværdier, teksttypografier og Markup Language er justeret i henhold til skemakravene for adaptive kort (se **Bedste praksis for adaptive kort-skema** [her](https://adaptivecards.io/explorer/))

    - Udnyt valideringen af adaptive kort i **Visual Studio Code**. Hvis du vil installere den fra Visual Studio Code-programmet, skal du åbne markedspladsen for udvidelser og søge efter **Fremviser til adaptive kort**.

      ![Visual Studio Code-filtypenavn](media/adaptive-cards/visual-studio-code-extension.png)
  
Afkortet skærmbillede af udvidelsen Fremviser til adaptive kort, der er installeret i Visual Studio Code (genvej: Ctrl+V+A når aktiveret).

- Fejl efter indsendelsen af adaptivt kort skyldes ofte følgende:

    - Brug af en handling, der ikke omfatter 'Vent på svar' i navnet  
        
        ![Forsøg igen](media/adaptive-cards/try-again.png)

    - Forsøger at indsende kortet mere end én gang. Hvert enkelt tilpasset kort kan kun indsendes én gang, hvorefter alle yderligere indsendelser vil blive ignoreret.
