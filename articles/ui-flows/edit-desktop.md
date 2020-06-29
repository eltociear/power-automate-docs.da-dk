---
title: Få mere at vide om redigering af flow for brugergrænsefladen på skrivebordet | Microsoft Docs
description: Få mere at vide om redigering af flow for brugergrænsefladen på skrivebordet.
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
ms.date: 03/24/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a6b34a58dc028d6d0df9bf03f66a04666998ac69
ms.sourcegitcommit: aefd1ebedfbd8c6cc3d08397ac171cb4ba5b5315
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412976"
---
# <a name="edit-desktop-ui-flows"></a>Redigere flow for brugergrænsefladen på skrivebordet

Windows-skrivebordsprogrammer automatiseres i flow for brugergrænsefladen på skrivebordet. Se [Kendte problemer](create-desktop.md#known-issues-and-solutions) for at få mere at vide om de problemer, der kan opstå, løsninger på disse problemer og scenarier, der ikke understøttes i denne udgivelse.

## <a name="prerequisites"></a>Forudsætninger
Et flow for brugergrænsefladen på skrivebordet. [Opret et flow for brugergrænsefladen på skrivebordet nu](create-desktop.md#create-and-test-desktop-ui-flows), hvis du ikke har et, der skal redigeres.

## <a name="edit-actions"></a>Redigere handlinger

![Redigere handlinger](../media/edit-desktop/edit-actions.png "Redigere handlinger")

Du kan redigere din optagelse for at gøre følgende:

-   Redigere værdien for handlinger, der understøtter den.
-   Slette et trin.
-   Slette optagelsen.
-   Ændre rækkefølgen af handlinger ved hjælp af træk og slip. Vær forsigtig med dette, da det kan ødelægge sammenhængen af optagelsen.

Avancerede parametre giver dig mulighed for at ændre følgende:

-  Forsinkelsen, efter handlingen blev udført. Du kan f.eks. tilføje en forsinkelse på ét sekund ved at ændre PT0S til PT1S. Dette kan være nyttigt, når destinationsprogrammet har en langsom svartid, der ikke fuldføres før næste trin i dit flow for brugergrænsefladen.
-   [Vælgeren](edit-desktop.md#set-the-selector) for elementet i brugergrænsefladen for målbrugeren.


## <a name="add-a-recording"></a>Tilføje en optagelse

Det kan være en god idé at optage dit flow for brugergrænsefladen i flere sessioner. Når du har fuldført din første optagelse, kan du fortsætte på følgende måde:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** > **Flow for brugergrænseflade**.
1. Vælg det flow for brugergrænsefladen, du vil redigere.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Vælg **Rediger**. 
1. Vælg **Nyt trin**.

   ![Nyt trin](../media/edit-desktop/new-step.png "Nyt trin")

1. Vælg **Optagerapp** på listen over handlinger.

   ![Optagerapp](../media/edit-desktop/select-record-ui-actions.png "Optagerapp")

1. Vælg **Start optager**.

   ![Vælg Start optager](../media/create-windows-ui-flow/select-launch-recorder.png "Vælg Start optager")

   Optagerkontrolelementet vises øverst på skærmen.

   ![Optagerkontrolelementet](../media/create-windows-ui-flow/recorder-control.png "Optagerkontrolelementet")

1. Start den app, du vil optage.

     >[!TIP]
     >Når du holder musen over kontrolelementer i appen, kan du se en blå kontur rundt om hvert enkelt kontrolelement. Vent altid på den blå kontur, før du vælger et kontrolelement.
     >
     >Hvis elementet ikke er fremhævet med blåt, optages det muligvis ikke korrekt.

1. Vælg **Optag** i optagerkontrolelementet.

1. Udfør trinnene i brugergrænsefladen for den app, du er ved at optage, og vælg derefter **Udført** i optagerkontrolelementet.
1. Vælg **Gem**, og test derefter dit flow for brugergrænsefladen.

## <a name="add-a-manual-action"></a>Tilføje en manuel handling

Når du har optaget et program med mindst én handling, kan du manuelt tilføje en af følgende handlinger for det pågældende program.

| **Handling**          | **Kommentar**                                                       |
|---------------------|-------------------------------------------------------------------|
| Luk program   |                                                                   |
| Højreklik         |                                                                   |
| Send tastetryk           | Send tastetryk og tastekombinationer, f.eks. CTRL + C.                             |
| Venstreklik          |                                                                   |
| Hent tekst            | Læs teksten fra et element i brugergrænsefladen, og brug det derefter som et output. |
| Angiv tekst          |                                                                   |
| Få element aktiveret | Kontrollér, om et element i brugergrænsefladen er aktiveret eller deaktiveret.         |
| Ryd element       | Ryd værdien i et redigerbart element i brugergrænsefladen.             |
| Vent et par sekunder    | Vent, før du fortsætter til næste trin.                           |

Følg disse trin for at tilføje en manuel handling:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** > **Flow for brugergrænseflade**.
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

Når handlingen er tilføjet, skal du angive **Vælgeren** under avancerede indstillinger for handlingen.

![Avancerede indstillinger for handling](../media/edit-desktop/action-advanced-options.png "Avancerede indstillinger for handling")

### <a name="set-the-selector"></a>Angiv vælgeren

Vælgeren identificerer elementet i brugergrænsefladen, som handlingen udføres på under afspilning. Vi anbefaler, at du kopierer/indsætter disse oplysninger fra et separat trin, der er målrettet det samme element i brugergrænsefladen, hvis det er muligt.

Vælgeren har følgende format:

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

Du skal angive dataene for felterne **elementStack** og **elementXPath** i vælgerelementet.

Her er et eksempel på, hvordan **elementStack** kan se ud.

![ElementStack](../media/edit-desktop/elementstack.png "ElementStack")

Du kan indlæse **elementXPath** ved hjælp af [Optageren for brugergrænsefladen WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![WAD-værktøj](../media/edit-desktop/wad-tool.png "WAD-værktøj")

Fjern det første element (alt før /Window), før du bruger resultatet i **elementXPath** i vælgeren.

Test dit flow for brugergrænsefladen for at bekræfte, at vælgeren fungerer korrekt.

## <a name="use-advanced-controls"></a>Bruge avancerede kontrolelementer

Du kan inkorporere avancerede kontrolelementer, f.eks. handlinger af typen **betingelser**, **skift sager** og **afslut** i dine flow for brugergrænseflade.

Du kan udføre disse avancerede handlinger ved at udføre følgende trin i et eksisterende flow for brugergrænseflade.

1. Vælg det flow for brugergrænseflade, du har oprettet > **Flere kommandoer** (...) > **Rediger**.

1. Vælg **+** > **Tilføj en handling** i rullemenuen i det flow for brugergrænsefladen, som du vil føje logik til.

   ![Tilføj en handling](../media/edit-desktop/add-action.png)

1. Vælg **Indbygget**, og vælg derefter en af de kontrolhandlinger, der er tilgængelige.

   ![Indbygget](../media/edit-desktop/select-built-in.png)

1. Fuldfør det udtryk, der skal evalueres. Du kan bruge dynamisk indhold og udtryk til at evaluere din betingelse og skifte kontrolelementer. Du kan desuden bruge et hvilket som helst output, der er genereret fra de forrige trin i flowet for brugergrænseflade.

   ![Betingelseskort](../media/edit-desktop/condition-card.png)


## <a name="add-a-recording-of-a-remote-computer-using-image-recognition-preview"></a>Tilføje en optagelse af en fjerncomputer ved hjælp af billedgenkendelse (prøveversion)

[!INCLUDE[cc-beta-prerelease-disclaimer](../includes/cc-preview-features-expect-changes.md)]

Billedgenkendelse i flow for brugergrænseflade er en prøveversionsfunktion, der i øjeblikket er tilgængelig, når en fjerncomputer optages via appen Forbindelse til fjernskrivebord (RDC).
 

### <a name="what-is-image-recognition"></a>Hvad er billedgenkendelse?

I øjeblikket optages flow for brugergrænsefladen på skrivebordet primært ved hjælp af API'er for tilgængelighed (UI Automation og WinAppDriver) til registrering af kontrolelementerne i Microsoft Windows-brugergrænsefladetræet. Træet er undertiden ikke tilgængeligt, f.eks. med webbaserede eller Java-apps. Træet kan muligvis være upålideligt, f.eks. når id'erne for et kontrolobjekt ændres ofte eller mellem sessioner. 

Med billedgenkendelse kan du klikke på placeringer og andre detaljer, der afstemmes visuelt under afspilningen, hvilket er en stor udvidelse af det antal programmer, der kan automatiseres. 

### <a name="use-image-recognition-to-record-a-remote-computer"></a>Bruge billedgenkendelse til at registrere en fjerncomputer

 
1. Gå til fanen Input i et nyt eller eksisterende flow for brugergrænseflade, og opret to nye **følsomme tekst**-input, ét til brugernavnet og ét til den adgangskode, der bruges til at logge på fjernenheden. Følsomme tekstinput giver dig mulighed for at overføre værdierne dynamisk, når du tester eller kalder flow for brugergrænseflade fra et andet flow, uden at de gemmes eller logges af selve flowet for brugergrænsefladen.

   ![Følsom tekst ](../media/create-remote-desktop/ir-sensitive-text.png)

1. Følg trinnene i **Tilføje en optagelse** for at starte optagerkontrolelementet for et nyt eller eksisterende flow for brugergrænseflade.

1. Brug appen Fjernskrivebord til at oprette forbindelse til fjerncomputeren.

1. Udvid vinduet Fjernskrivebord til fuld skærm.

1. Vælg **Optag** fra optagerkontrolelementet, og vælg **Forstået** i den viste besked.

   ![Pop op-vindue](../media/create-remote-desktop/popup.png)

1. Udfør trinnene på fjerncomputeren, og vælg derefter **Udført** på optagerkontrolelementet.

1. Find handlingen **Start Fjernskrivebord** i din optagelse, og angiv derefter de følsomme tekstinput for brugernavnet og adgangskoden.

![Brugernavn og adgangskode som følsom tekst](../media/create-remote-desktop/ir-launch-emote_desktop-session.png)

1. Vælg **Gem**, og test derefter dit flow for brugergrænsefladen.

>[!IMPORTANT]
>Når du kalder dette flow for brugergrænseflade fra et automatiseret flow, anbefales du at bruge en nøgleadministrationsløsning, f.eks. en [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), til at hente brugernavnet og adgangskoden og derefter sende dem til de **følsomme tekst**-input i flow for brugergrænseflade dynamisk i stedet for at gemme dem i selve flowet. 

>[!TIP]
> Aktivér **Sikre input** i menuen **Indstillinger** for **Kør et flow for brugergrænsefladen på skrivebordet**-handlingen i det flow, der kalder flow for brugergrænseflade. Derved sikres, at input ikke gemmes i historik over kørsel.

### <a name="use-the-extract-text-from-image-action-while-recording-to-retrieve-an-output-from-a-remote-computer"></a>Brug handlingen Udtræk tekst fra billede under optagelse for at hente et output fra en fjerncomputer.

1. Når du optager dine trin, skal du navigere til placeringen af den tekst, du vil indlæse.

1. Vælg **Output** > **Udtræk tekst fra billede** fra optagerens kontrolelementet.

1. Følg anvisningerne for at vælge et **ankerområde** (en sektion på skærmen, der ikke forventes at blive ændret, f.eks. navnet ud for et felt).

    ![Ankerområde](../media/create-remote-desktop/ir-anchors.png)

1.  Vælg **målområdet** (det område, som tekst skal udtrækkes fra, ved hjælp af optisk tegngenkendelse).

    ![Målområde](../media/create-remote-desktop/ir-targets.png)

1.  Angiv et navn til outputtet.

1.  Vælg **Udført** på optagerens kontrolelementet.

1.  Vælg **Gem**, og test derefter dit flow for brugergrænsefladen.


### <a name="known-issues-for-remote-desktop-recordings"></a>Kendte problemer i forbindelse med optagelser af Fjernskrivebord

1. Kontrollér, at alle krævede input (computernavn, brugernavn og adgangskode) er udfyldt og gemt, før du optager yderligere trin i det samme flow for brugergrænseflade.

1. Hvis du vil knytte til en eksisterende fjernskrivebordssession, skal sessionen være startet tidligere i det samme flow for brugergrænseflade.

1. Den anbefalede måde at starte forbindelse til Fjernskrivebord på (RDC) til optagelse er fra appen Forbindelse til Fjernskrivebord (mstc.exe) fra menuen Start. Hvis sikkerhedshandlinger i Windows optages sammen med handlingen **Start Fjernskrivebord**, skal de fjernes fra designeren, så afspilningen ikke afbrydes (dette kan ske, når fjernskrivebordssessionen startes fra en genvej).

1. Afspilningen kan mislykkes, hvis flow for brugergrænseflade blev optaget på en skærm med skærm skalering (Windows-indstillinger > Skalering af skærm) er indstillet til en anden værdi end 100 %. Du kan løse problemet ved at sikre, at skærmskalering er angivet til 100 % inden optagelsen.


## <a name="handle-error-conditions"></a>Håndtere fejlbetingelser

Der kan opstå uventede tilstande under afspilningen. Disse betingelser kan medføre, at flow for brugergrænseflade ikke fungerer korrekt. Du kan bruge avancerede funktioner til fejlhåndtering for at oprette alternative trin, når der opstår uventede betingelser. 

Det drejer sig om følgende trin.

1. Log på [Power Automate](https://powerautomate.microsoft.com) med din skole- eller arbejdskonto.
1. Vælg **Mine flow** > **Flow for brugergrænseflade**.
1. Vælg **Flere kommandoer** (de tre lodrette prikker for det flow for brugergrænseflade, du vil redigere).
1. Vælg **Rediger**.
1. Vælg pil ned umiddelbart inden det trin i flow for brugergrænseflade, du vil føje fejlhåndtering til, og vælg derefter **+** (Indsæt nyt trin).
   
   I følgende billede indsætter vi det nye trin før trinnet **PostElementText 1**. Det betyder, at hvis **PostElementText 1** mislykkes, køres de alternative trin, som du derefter definerer.

      ![Billede af Indsæt nyt trin](../media/edit-desktop/insert-new-step.png) 

1. Vælg **Tilføj en parallel forgrening**.

    ![Billede, der viser Tilføj en parallel forgrening og andre indstillinger](../media/edit-desktop/add-parallel-branch.png)

1. Vælg den handling, der skal udføres i den parallelle forgrening, hvis der opstår en fejl, når flow for brugergrænseflade køres.

   Du kan vælge **Optagerapp** for at foretage en ny optagelse af den parallelle forgrening eller vælge **Afbryd** via de **indbyggede** handlinger for at afslutte flow for brugergrænseflade på en ordentlig måde, hvis der opstår en fejl.

    ![Billede, der viser indstillingerne for den parallelle forgrening](../media/edit-desktop/add-parallel-branch.png)

   >[!NOTE]
   >Den handling, du tilføjer i den parallelle forgrening, kører som standard kun, hvis det foregående trin mislykkes. Du kan vælge **...** på den parallelle forgrening > **Konfigurer kørsel efter** for at ændre standardfunktionsmåden. 

      ![Billede, der viser indstillingerne, herunder Konfigurer kørsel efter](../media/edit-desktop/configure-run-after.png)

1.  På denne skærm kan du vælge den betingelse, som den parallelle forgrening skal udføres på. Du kan vælge mellem fire tilgængelige indstillinger.

    ![Billede, der viser indstillingerne for kørsel efter](../media/edit-desktop/run-after-options.png)

    Bemærk! Du kan ikke gemme et brugergrænsefladeflow, hvor både hovedforgreningen og den parallelle forgrening er angivet til at køre på samme betingelse.



## <a name="enable-coordinate-based-playback"></a>Aktivere koordinatbaseret afspilning

Koordinatbaseret afspilning bruger relative forskydninger af skærmkoordinater som et fallback, der hjælper flow for brugergrænseflade med at finde destinationsobjekter, som den automatiseringsstruktur, der anvendes som standard af Windows-brugergrænsefladen, ikke kan finde under afspilning. 

Her er nogle af årsagerne til, at den automatiseringsstruktur, der anvendes som standard af Windows-brugergrænsefladen, muligvis ikke kan finde målobjekter under afspilning:

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

- Få mere at vide om, hvordan du [kører det flow for brugergrænsefladen](run-ui-flow.md), du lige har redigeret.

- Hvis du vil foretage dig mere med flow for brugergrænseflade, kan du også afprøve flow for brugergrænseflade med [input- og output](inputs-outputs-web.md)-parametre.

