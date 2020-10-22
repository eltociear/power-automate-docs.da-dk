---
title: Power Automate-ordliste | Microsoft Docs
description: Ordliste med udtryk, der bruges i Power Automate
services: ''
suite: flow
documentationcenter: na
author: nijemcevic
manager: ''
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2020
ms.author: tatn
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ff7585d78a23663516c8d4a3e074493750f703ef
ms.sourcegitcommit: 9f96e86aca714b803d16bebf7957cdf3e1e8c124
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/18/2020
ms.locfileid: "3820661"
---
# <a name="power-automate-glossary"></a>Power Automate-ordliste

Følgende er almindelige udtryk, der anvendes i Power Automate.

## <a name="a"></a>A

**Handling:** En handling er den opgave, der startes, når en udløser aktiveres. Flows kan have en eller mange handlinger, afhængigt af hvad der kræves for at fuldføre et bestemt flow. Handlinger kan f.eks. være **Opret**, **Opdater**, **Slet** eller **Tildel**.

 [Tilføj en handling](multi-step-logic-flow.md)

**Handlingspunkter**: Skærmen **Handlingspunkter** viser status for godkendelser og forretningsprocesforløb. Handlingspunkter findes i navigationsruden i venstre side af Power Automate.

**Godkendelser (godkendelsesanmodninger):** Godkendelse refererer til handlingerne under godkendelse af et flow. Det kan være en basishandling af typen Godkend eller Afvis. Det kan være et brugerdefineret godkendelsesflow, hvor afsenderen kan anmode om at logge af, herunder flere valg. Hvis du vil oprette en arbejdsproces for godkendelser, skal du tilføje en godkendelseshandling. Når du har tilføjet denne handling, kan dit flow administrere godkendelse af dokumenter eller processer

 [Introduktion til det samlede handlingscenter](https://flow.microsoft.com/en-us/blog/introducing-the-unified-action-center/)

**Automatiseret flow:** Automatiske flows udløses af en forudbestemt hændelse. Automatiserede flow køres, når en hændelse udløser flowet til at køre. Eksempel: Når en post oprettes, slettes eller opdateres i Common Data Service, køres flowet, hvis det er den udløser, du vælger.

 [Opret et flow i Power Automate](get-started-logic-flow.md)

## <a name="b"></a>B

**Forretningsprocesforløb**: Et forretningsprocesforløb sikrer, at alle i virksomheden følger samme proces.  Du skal definere et sæt trin, som brugerne skal følge. Du kan f.eks. oprette et forretningsprocesforløb, så alle håndterer kundeserviceanmodninger på samme måde.  Du kan kræve, at brugere får godkendelse af en faktura, før de sender en ordre.

 [Oversigt over forretningsprocesforløb](business-process-flows-overview.md)

## <a name="c"></a>O

**Common Data Service:** En skybaseret database, der bruges til at lagre data til forretningsprogrammer som Power Automate og Power Apps. Det er en abstraktion over de underliggende Azure cloud-dataadministrationstjenester, der gør det nemmere at bygge forretningsprogrammer.

 [Hvad er Common Data Service?](/powerapps/maker/common-data-service/data-platform-intro)

**Common Data Service for Teams**: En fælles skybaseret dataplatform til Microsoft-teams. Common Data Service for Teams gør det muligt for alle hurtigt at opbygge og installere apps og intelligente chatrobotter i Teams med Microsoft Power Apps og Microsoft Power Virtual Agents.

**Betingelser:** Betingelser angiver, at flow skal udføre handlinger, der er baseret på foruddefineret logik angivet i processen. Hvis visse betingelser er sande, fuldføres en eller flere opgaver. Brugerne kan f.eks. oprette betingelser, der angiver, at du får en mail, hvis et tweet, der indeholder et nøgleord, retweetes mindst ti gange.

 [Føj en betingelse til et flow](add-condition.md)

**Connectorer:** Med connectorer kan brugere oprette forbindelse mellem populære tjenester (f.eks. Twitter, Outlook, Gmail og andre) og Microsoft Power Automate, Microsoft Power Apps og Azure Logic Apps. De indeholder et sæt færdige udløsere ("når en ny mail modtages"...) og handlinger ("overfør vedhæftet til i mail til SharePoint og Min app"), der skal bruges i apps og arbejdsprocesser.

 [Dokumentation til connectors](https://docs.microsoft.com/connectors/)

**Brugerdefinerede connectorer:** De brugerdefinerede connectorer giver brugerne mulighed for at oprette forbindelse mellem en webtjeneste og Power Automate. Brugerne lærer Power Automate om karakteristika for webtjenesten, som inkluderer godkendelse, de udløsere og handlinger, der understøttes, samt parametrene og output for hver af disse handlinger. Brugerdefinerede connectorer skal registreres, før de kan deles med din organisation.

[Start opbygning med Power Automate](get-started-flow-dev.md)

## <a name="d"></a>D

**Forebyggelse af datatab**: Med forebyggelse af datatab kan du oprette og gennemtvinge politikker, som definerer, hvilke connectorer der kan få adgang til og dele forretningsdata. Dette er en nøglefunktion, der hjælper dig med at sikre, at forretningsdataene er beskyttet.

 [DLP-politikker (forebyggelse af datatab)](prevent-data-loss.md)

## <a name="f"></a>F

**Flowkontrol:** Flowkontrol er et diagnosticeringsværktøj, der peger på bestemte forekomster i flowet, hvor det kan være nødvendigt at foretage forbedringer for at køre et flow. For hvert identificeret problem vises flowkontrol på designerens kommandolinje. Den viser en rød prik, når den finder en eller flere fejl i flowet.

 [Søg efter og løs fejl med Flowkontrol](error-checker.md)

**Flowtyper:** Automatiseret, øjeblikkelig, planlagt, flow for brugergrænseflade og forretningsprocesforløb.

 [Introduktion til Power Automate](getting-started.md)

**Flowdesigner:** Flowdesigneren er det studie, hvor udviklere opretter flows fra bunden eller starter fra en skabelon (som de kan tilpasse eller føje trin til).

## <a name="i"></a>K

**Øjeblikkeligt flow:** Med øjeblikkeligt flow kan brugerne udløse gentagne opgaver fra mobil- eller skrivebordsappen manuelt. Hvis du f.eks. klikker på en knap på en mobilapp, sendes der en mailpåmindelse til dit team før et møde.

 [Introduktion til øjeblikkeligt flow](introduction-to-button-flows.md)

## <a name="m"></a>M

**Flertrinsflow:** Et flertrinsflow benytter mere end én handling til at udføre en opgave.

## <a name="r"></a>R

**Procesautomatisering med robotteknologi (RPA):** Automatisering med et softwareprogram, der replikerer de handlinger, der udføres af en person, som kommunikerer med brugergrænsefladen i et computersystem.

 [Brug Softomotive's WinAutomation med flows for brugergrænseflade](ui-flows/create-processes.md)

## <a name="s"></a>L

**Planlagte flows:** Planlagte flows kører efter en tidsplan, der er defineret af udvikleren. Planlagte flows kan gentages med følgende mellemrum: hvert sekund, minut, time, dag, uge og/eller måned. Brugere kan f.eks. planlægge en automatisering som daglige dataupload til SharePoint eller en database.

 [Kør flow efter en tidsplan](run-scheduled-tasks.md)

**Trin:** Der findes en knap nederst i hvert trin (handling) med navnet **+Nyt trin** i Flowdesigner, der giver brugeren mulighed for at tilføje endnu en handling.

## <a name="t"></a>T

**Skabeloner:** Skabeloner er et sæt færdige udløsere og handlinger, der er udviklet til at hjælpe brugerne med hurtigt at oprette flows, der opfylder deres specifikke forretningsbehov. Skabeloner kan tilpasses. Der er hundredvis af flow-skabeloner, der passer til mange typer almindelige automatiseringsscenarier.

 [Power Automate-skabeloner](https://flow.microsoft.com/templates/)

**Udløser:** En udløser er en hændelse, der starter et flow.  Hvis du f.eks. opretter et flow: "når der modtages en mail med vedhæftede filer, skal filen automatisk overføres til OneDrive" - modtagelsen af mailen med en vedhæftet fil er udløseren af et sådant flow.

Flows kan have en eller flere udløsere.

## <a name="w"></a>O

**Arbejdsproces:** En række handlinger, der udføres for at føre en opgave fra start til fuldførelse.

## <a name="u"></a>U

**Flows for brugergrænseflade (RPA):** Du kan bruge flows for brugergrænsefladen til at automatisere gentagne opgaver i Windows og webprogrammer. Flows for brugergrænseflade registrerer og afspiller handlinger i brugergrænsefladen (f.eks. klik og tastaturinput) for programmer, hvor der ikke er brugervenlige eller fuldstændige API'er.

[Introduktion til flow for brugergrænseflade](ui-flows/overview.md)

## <a name="learn-more"></a>Flere oplysninger

* Få en [guidet rundvisning](https://docs.microsoft.com/learn/paths/automate-process-using-flow) i Power Automate
* Få et grundlæggende kendskab til Power Automate i [introduktionsvejledningen](getting-started.md)
