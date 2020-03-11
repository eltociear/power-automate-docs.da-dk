---
title: Få mere at vide om redigering af flow for brugergrænsefladen på skrivebordet | Microsoft Docs
description: Få mere at vide om redigering af flow for brugergrænsefladen på skrivebordet
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0be3b3656cf9683b43d4ba22bc23b537ccc4e597
ms.sourcegitcommit: 26cda5060446812f3725ccd4fe435839088f50fa
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/03/2020
ms.locfileid: "78244280"
---
# <a name="edit-desktop-ui-flows"></a>Rediger desktopbrugergrænsefladeflow

[Dette emne er foreløbig dokumentation og kan ændres].

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Windows-skrivebordsprogrammer automatiseres i flow for brugergrænsefladen på skrivebordet. Se [Kendte problemer](create-desktop.md#known-issues-and-solutions) for at få mere at vide om de problemer, der kan opstå, løsninger på disse problemer og scenarier, der ikke understøttes i denne prøveversion.

## <a name="prerequisites"></a>Forudsætninger
Et flow for brugergrænsefladen på skrivebordet. [Opret et flow for brugergrænsefladen på skrivebordet nu](create-desktop.md#create-and-test-desktop-ui-flows), hvis du ikke har et, der skal redigeres.

## <a name="edit-actions"></a>Redigeringshandlinger

![Redigeringshandlinger](../media/edit-desktop/edit-actions.png "Redigeringshandlinger")

Du kan redigere din optagelse for at gøre følgende:

-   Redigere værdien for handlinger, der understøtter den.
-   Slette et trin.
-   Slette hele optagelsen.
-   Ændre rækkefølgen af handlinger ved hjælp af træk og slip. Vær forsigtig med dette, da det kan ødelægge sammenhængen af optagelsen.

Avancerede parametre giver dig mulighed for at ændre følgende:

-  Forsinkelsen, efter handlingen blev udført. Du kan f.eks. tilføje en endnu en forsinkelse ved at ændre PT0S til PT1S. Dette kan være nyttigt, når destinationsprogrammet har en langsom svartid, der ikke fuldføres før næste trin i dit flow for brugergrænsefladen.
-   [Selektoren](edit-desktop.md#set-the-selector) for elementet i brugergrænsefladen for destinationsbrugeren.

## <a name="add-a-recording"></a>Tilføj en optagelse

Det kan være en god idé at optage dit flow for brugergrænsefladen i flere sessioner. Når du har fuldført din første optagelse, kan du fortsætte på følgende måde:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** > **Flow for brugergrænseflade (prøveversion)** .
1. Vælg det flow for brugergrænsefladen, du vil redigere.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Vælg **Rediger**. 
1. Vælg **næste trin**.

   ![Nyt trin](../media/edit-desktop/new-step.png "Nyt trin")

1. Vælg **Optag program** på listen over handlinger.

   ![Optag program](../media/edit-desktop/select-record-ui-actions.png "Optag program")

1. Vælg **Start optager**.

   ![Vælg Start optager](../media/create-windows-ui-flow/select-launch-recorder.png "Vælg Start optager")

   Optagerkontrolelementet vises øverst på skærmen.

   ![Optagerkontrolelementet](../media/create-windows-ui-flow/recorder-control.png "Optagerkontrolelementet")

1. Start det program, du vil optage.

     >[!TIP]
     >Når du holder musen over kontrolelementer i programmet, kan du se en blå kontur rundt om hvert enkelt kontrolelement. Vent altid på den blå markering, før du vælger et kontrolelement.
     >
     >Hvis elementet ikke er fremhævet med blåt, optages det muligvis ikke korrekt.

1. Vælg **Optag** i optagerkontrolelementet.

1. Udfør trinnene i brugergrænsefladen for det program, du er ved at optage, og vælg derefter **Udført** i optagerkontrolelementet.
1. Vælg **Gem**, og test derefter dit flow for brugergrænsefladen.

## <a name="add-a-manual-action"></a>Tilføj en manuel handling

Når du har optaget et program med mindst én handling, kan du manuelt tilføje en af følgende handlinger for det pågældende program.

| **Handling**          | **Kommentar**                                                       |
|---------------------|-------------------------------------------------------------------|
| Luk programmet   |                                                                   |
| Højreklik         |                                                                   |
| Send tastetryk           | Send tastetryk og tastekombinationer, f.eks. CTRL + C.                             |
| Venstreklik          |                                                                   |
| Hent tekst            | Læs teksten fra et element i brugergrænsefladen, og brug det derefter som et output. |
| Angiv tekst          |                                                                   |
| Få element aktiveret | Kontrollér, om et element i brugergrænsefladen er aktiveret eller deaktiveret.         |
| Ryd element       | Ryd værdien i et redigerbart element i brugergrænsefladen.             |
| Vent i sekunder    | Vent, før du fortsætter til næste trin.                           |

Følg disse trin for at tilføje en manuel handling:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** > **Flow for brugergrænseflade (prøveversion)** .
1. Vælg det flow for brugergrænsefladen, du vil redigere.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Vælg **Rediger**. 
1. Vælg det optagekort, der indeholder de trin, som du vil føje et nyt trin til.
   Kortet udvides, og de optagede trin vises.

   ![Vælg optagekort](../media/edit-desktop/manual-select-recording-card.png)

1. Vælg **Tilføj en handling** på optagekortet lige under det seneste optagede trin.
   Du kan se listen over manuelle handlinger, der er angivet tidligere i denne gennemgang. 

1. Vælg den handling, du vil tilføje. Her har jeg valgt **Få element aktiveret**, men du kan vælge en hvilken som helst handling, der giver mening for dit scenarie.

   ![Vælg handling, der skal tilføjes.png](../media/edit-desktop/select-action-to-add.png)

Når handlingen er tilføjet, skal du angive **Selektoren** under avancerede indstillinger for handlingen.

![Avancerede indstillinger for handling](../media/edit-desktop/action-advanced-options.png "Avancerede indstillinger for handling")

### <a name="set-the-selector"></a>Angiv selektor

Selektoren identificerer elementet i brugergrænsefladen, som handlingen udføres på under afspilning. Vi anbefaler, at du kopierer/indsætter disse oplysninger fra et separat trin, der er målrettet det samme element i brugergrænsefladen, hvis det er muligt.

Selektoren har følgende format:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Du skal angive dataene for felterne **elemementStack** og **elementXPath** i selektorelementet.

Her er et eksempel på, hvordan **elemementStack** kan se ud.

![ElementStack](../media/edit-desktop/elementstack.png "ElementStack")

Du kan hente **elementXPath** ved hjælp af [Optageren for brugergrænsefladen WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![WAD-værktøj](../media/edit-desktop/wad-tool.png "WAD-værktøj")

Fjern det første element (alt før /Window), før du bruger resultatet i **elementXPath** i selektoren.

Test dit flow for brugergrænsefladen for at bekræfte, at selektoren fungerer korrekt.


## <a name="enable-coordinate-based-playback"></a>Aktivér koordinatbaseret afspilning

Koordinatbaseret afspilning bruger relative forskydninger af skærmkoordinater som et fallback, der hjælper flow for brugergrænsefladen med at finde destinationsobjekter, som den automatiseringsstruktur, der anvendes som standard af Windows-brugergrænsefladen, ikke kan finde under afspilning. 

Her er nogle af årsagerne til, at den automatiseringsstruktur, der anvendes som standard af Windows-brugergrænsefladen, muligvis ikke kan finde destinationsobjekter under afspilning:

- Det ældre program, som du automatiserer, bruger muligvis ikke programmeringsteknologier, der understøtter automatiseringsstrukturen, der anvendes af Windows-brugergrænsefladen.
- Programmet eller dets kontrolelementer har muligvis ikke en entydig XPath, et entydigt navn eller entydige id'er til brugergrænsefladen i forbindelse med automatisering. 
- Programmet har dynamiske kontrolelementer, hvis navne eller id'er kan ændres. 
- Programmet har kontrolelementer, der ikke har navne, id'er, entydige id'er osv.

>[!TIP]
>Brug den samme skalering og opløsning, og maksimer også destinationsprogrammet under optagelsen for at forbedre nøjagtigheden af koordinatbaseret afspilning.

Følg disse trin, når du har optaget et script til flow for brugergrænsefladen:

1. Udvid det trin, der starter eller tilknytter programmet.
   
   Dette er normalt det første trin i scriptet til optagelse.
1. Vælg **Vis avancerede indstillinger**.
1. Find egenskaben **Brug koordinat for afspilning**.
1. Vælg **Ja** på listen for at aktivere koordinatbaseret afspilning.

>[!TIP]
> Du kan aktivere eller deaktivere **Brug koordinat for afspilning** for hvert program for at anvende indstillingen på alle de trin, der udføres i forbindelse med det pågældende program.  


>[!WARNING]
>Med koordinatbaseret afspilning kan automatiseringen vælge kontrolelementer, der ikke er en del af destinationsprogrammet, af en række årsager, f.eks. når brugergrænsefladen i destinationsprogrammerne ændres drastisk.




## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [kører det flow for brugergrænsefladen](run-ui-flow.md) du lige har redigeret.

- Hvis du vil udføre mere med flow for brugergrænsefladen, kan du også afprøve flow for brugergrænsefladen med [input- og output](inputs-outputs-web.md)parametre.

