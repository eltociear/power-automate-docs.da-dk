---
title: Erstat klassiske Common Data Service-arbejdsprocesser med Power Automate | Microsoft Docs
description: Beskriver funktioner i Power Automate og anbefalede mønstre for brug af flow i stedet for en klassisk arbejdsproces.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6e3e6d1ca0a1700bbfaf6d8e8fb76cc888456c2c
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193725"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Erstat klassiske arbejdsprocesser i Common Data Service med flow


I dette emne sammenlignes Power Automate-funktioner med en klassisk arbejdsproces.

Power Automate omfatter betydelige fordele i forhold til den klassiske arbejdsprocesmodel. Du bør overveje at bruge Power Automate til at automatisere processer i stedet for den klassiske arbejdsproces. 

Opret flow i stedet for klassiske Common Data Service-arbejdsprocesser for at bygge nye automatiseringsprocesser. Du bør desuden gennemse dine eksisterende klassiske arbejdsprocesser og overveje at erstatte dem med flow.

## <a name="feature-capability-comparison"></a>Sammenligning af funktionalitet

I denne tabel opsummeres en sammenligning mellem funktioner i Power Automate og i klassiske arbejdsprocesser. 

*Vi føjer løbende nye funktioner til Power Automate, så funktionerne er på højde med og endnu bedre end funktionerne i klassiske arbejdsprocesser. Vi opdaterer oplysningerne i denne tabel efterhånden som Power Automate får flere funktioner. Hold øje med dem! Du kan finde oplysninger om kommende flowfunktioner, der kan hjælpe dig med at udskifte den klassiske arbejdsproces med flow, under [Nyheder og planlagte ændringer i Power Automate](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) i produktbemærkningerne fra april 2019.*

<table>
<tr>
<th colspan="2">Funktion</th>
<th>Power Automate</th>
<th>Klassisk arbejdsproces</th>
</tr>
<tr>
<td rowspan="5">Modellering</td>
<td>Betinget forgrening</td>
<td>Ja</td>
<td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Løkker
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Vent-betingelser i felter
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Parallel forgrening
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Indbyggede forbindelser til eksterne systemer (udløser og udfører handlinger i eksterne tjenester)
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Sammensætning
                    
                </td>
                <td>
                    
   Dynamisk indhold
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Adgang til en foruddefineret afbildning af hændelsesdata
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kørsel af underordnede arbejdsprocesser
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kørsel af Common Data Service-handlinger (herunder brugerdefineret)
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kørsel af brugerdefinerede arbejdsprocesaktiviteter
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Gruppering af trin til kørsel i en transaktion
                    
                </td>
                <td>
                    
   Ja (changesets)
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Godkendelsesarbejdsprocesser
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Udførelse
                    
                </td>
                <td>
                    
   Udløser ved feltændringer
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Udløs betingelse ved feltværdier (f. eks. på en bestemt dato i et datofelt)
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Udløser ved flere Common Data Service-enhedshændelser
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kørsel efter behov
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kørsel som områder    <br/>
   (f. eks. organisation, forretningsenhed, bruger)
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kørsel efter en tidsplan
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Synkron kørsel (realtid)
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Historik
                    
                </td>
                <td>
                    
   Overvågning
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kørsel af analyser
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Oprettelse og mobilitet
                    
                </td>
                <td>
                    
   Løsningssupport
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Moderne designer
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   Nej
                    
                </td>
            </tr>
            <tr>
<td>AI-understøttet oprettelse</td>
<td>Ja</td>
<td>Nej</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Eksempelscenarie: Erstat arbejdsproces med et flow

Forestil dig et salgsscenarie, hvor du har sammensat et tilbud til en kunde og nu har brug for at anmode om godkendelse fra dit administrationsteam, før du sender tilbuddet til kunden. Med klassiske arbejdsprocesser ville dette ikke være nemt at gøre, og de fleste løsninger af dette kræver, at en udvikler skriver brugerdefinerede arbejdsprocesaktiviteter for at hente tilbudslinjeelementer.

Flow gør det nemmere at bygge som vist i gennemgangen senere. Den dækker nogle af de Power Automate-funktioner, der understøtter scenariet. Dette omfatter:

-   Oprettelse af et flow, der kører efter behov

-   Hentning af en liste over poster, der er relateret til en Common Data Service-enhed

-   Løkker i en liste over poster

-   Sender godkendelsesanmodninger

Sådan gør du det muligt for sælgeren at udløse godkendelsesanmodningen efter behov:

1. Log på [Power Automate](https://flow.microsoft.com/), og opret et flow i en løsning. Flere oplysninger: [Opret et flow i en løsning](create-flow-solution.md). 

1. På listen over udløsere skal du vælge **Common Data Service (aktuelt miljø) – Når en post vælges** og vælge **Tilbud** som enheden. Denne udløser gør det muligt at køre et flow på en post eller en liste over poster efter behov.

1. Når udløseren er konfigureret, kan du tilføje handlinger, der skal køres i flowet. Dette giver godkenderen et resume med de oplysninger, de har brug for for at identificere de tilbudte elementer og værdier. Begynd med at tilføje handlingen **Common Data Service (aktuelt miljø) – Listeposter**. Da vi vil hente individuelle linjeelementer fra et tilbud, skal du angive enheden til **Tilbudslinjer**. For at sikre at du kun får vist de tilbudslinjeelementer, der hører til det tilbud, som flowet blev udløst for, skal du angive et filterkriterium for OData-typografien. I feltet **Filterforespørgsel** skal du skrive *\_quoteid_value eq* og derefter vælge *Tilbud* på den liste over dynamiske værdier, der vises.

    ![Definer dit flow](media/define-flow-1.png "Definer dit flow")

1. Da du vil opsummere tilbudslinjeelementer til godkendelsen, skal du tilføje handlingen **Initialiser variabel**. Angiv feltet **Navn** til *Resume af tilbudslinje* og **Type** til Streng (på rullelisten), og lad feltet **Værdi** være tomt.

1. Tilføj handlingen **Tilføj til streng**, og vælg derefter variablen *Resume af tilbudslinje*, som vi oprettede tidligere. I feltet **Værdi** skal du vælge *Antal, Navn, Pris pr. enhed, Udvidet beløb og Manuelt beløb* på listen over dynamiske værdier. Power Automate-designeren identificerer, at disse værdier er fra en liste over tilbudslinjeelementer, og tilføjer denne handling i en **Anvend på alle**-løkke for at sikre, at oplysninger fra hvert linjeelement føjes til dette resume.

    ![Definer dit flow](media/define-flow-2.png "Definer dit flow")

1. Hvis du vil anmode om godkendelse af det tilbudsresume, du har oprettet, skal du tilføje handlingen **Godkendelse – Start, og vent på en godkendelse**. Vælg en godkendelsestype (f. eks. Godkend/Afvis – Første til at svare), giv godkendelsesanmodningen en **Titel** (f. eks. navnet på det tilbud, der anmodes om godkendelse af, og som er angivet på listen over dynamiske værdier), angive mailadressen for den person, der skal gennemse den, og godkend tilbuddet i feltet **Tildelt til** I feltet detaljer skal du tilføje variablen *Resume af tilbudslinje* sammen med eventuelle andre oplysninger, der kan være relevante ved hjælp af den dynamiske værdivælger (f. eks. Samlet beløb).

1. Hvis du vil finde ud af, hvad der sker, når en godkendelse accepteres eller afvises, skal du tilføje handlingen **Betingelse**. Vælg *Resultat* på listen over dynamiske værdier fra det første felt i betingelsen, *Indeholder* på rullelisten i det andet felt, og angiv *Accepter* i det tredje felt i betingelsen. Til sidst kan du tilføje handlinger baseret på resultatet af godkendelsen (f. eks. Send en mail med besked).

    ![Definer dit flow](media/define-flow-3.png "Definer dit flow")

Du har nu oprettet godkendelsesstrukturen, så godkenderen har alle de oplysninger, der kræves for at træffe en beslutning om de næste trin. Her er det fulde eksempel på et behovsbestemt flow for en anmodning om godkendelse:

![Struktur for godkendelsesflow](media/approval-flow-structure.png "Struktur for godkendelsesflow")

Når du kører dette flow i forhold til dit tilbud, opsummeres der tilbudslinjeelementer for det pågældende tilbud, og der sendes en godkendelsesanmodning, som godkenderen kan reagere på, fra Power Automate eller den handlingsrettede mail, de modtager. Nedenfor kan du se et eksempel på visningen:

![Flow i handling](media/flow-in-action.png "Flow i handling")

## <a name="recommended-patterns"></a>Anbefalede mønstre


-   **Arbejdsprocesser med kompleks Ellers Hvis-betingelseslogik**  
    
    I stedet for at bruge betingelser, anbefaler vi, at du bruger [handlingen Skift](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement).

-   **Arbejdsprocesser, der kører fra plug-in/kode**  
    
    Vi anbefaler, at du omdesigner flowet, så det starter med udløsere.

    -   Brug Common Data Service udløsere til at køre flow baseret på hændelser i det.

    -   Hvis du vil køre flow, der er baseret på hændelser i en ekstern tjeneste, kan du udnytte de mere end 260 indbyggede connectorer.

    -   I forbindelse med scenarier, hvor en connector, du har brug for, ikke umiddelbart er tilgængelig, kan du nemt oprette din egen brugerdefinerede connector [Få mere at vide om, hvordan du opretter brugerdefinerede connectorer](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Og endelig gælder det, at hvis der er scenarier, hvor du ikke kan udløse dit flow ved hjælp af en Common Data Service-connector eller en af de indbyggede connectorer eller oprette en brugerdefineret connector, skal du bruge [udløseren Når der modtages en HTTP-anmodning](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) til at kalde flowet

-   **Arbejdsprocesser, der kører rekursivt**  
    
    Brug [Foretag indtil](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop)- eller [Anvend på alle](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop)-løkke i flow i stedet

-   **Arbejdsprocesser, der skal bruge en liste over poster**  
    
    Brug handlingen **Listeposter**. Når du bruger denne handling, skal du definere kriterier for postfiltrering ved hjælp af OData-syntaksen for at optimere handlingen ved at minimere det antal poster, du vil hente.

-   **Arbejdsprocesser, der slumrer, indtil de skal køres efter en tidsplan**  
    
    Brug udløseren **Gentagelse** til at køre forretningslogik med regelmæssige intervaller.

-   **Arbejdsprocesser, hvor kørsler er administreret for at sikre, at aktiviteterne blev udført i en enkelt transaktion**  
    
    [Brug [handlingen changeset](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) til at sikre, at alle handlinger i den udføres som en enkelt atomisk enhed, hvor enten alle lykkes eller mislykkes som en gruppe. Hvis en af handlingerne i et ændringssæt mislykkes, rulles ændringer, der er foretaget af fuldførte handlinger, tilbage.

-   **Overvåg, om der opstår fejl i arbejdsproceskørsler**  
    
    I Power Automate skal du bruge **indstillingen Kør efter** på en handling for at konfigurere den til at køre, når den forrige handling mislykkes. Du kan f. eks. sende en Power Automate-mobilbesked, når handlingen **Opdater en post**, eller der opstår timeout for den.

## <a name="faqs"></a>Ofte stille spørgsmål


-   **Jeg har en Dynamics 365-licens. Kan jeg bruge Power Automate?**

    Alle Dynamics 365-brugere har ret til at bruge Power Automate. Gennemse vores licensoplysninger:<https://flow.microsoft.com/pricing/>

-   **Hvor ofte kan mine flow udløses?**

    -   Dynamics 365-flow (eller Common Data Service) kører næsten i realtid efter udløseren, fordi de bruger webhooks (ingen polling er påkrævet)

    -   Som med direkte API-adgang er der tærskler/begrænsninger i systemet, der er fuldt dokumenteret her: <https://docs.microsoft.com/flow/limits-and-config>

    -   Der er især en grænse på 100.000 handlinger pr. 5 minutter, pr. flow – og en enkelt løkke i et flow kan ikke behandle mere end 100.000 elementer på én gang

    -   Der er et maksimum på 6 GB dataoverførselshastighed pr. 5 minutter

-   **Hvor lang tid kan et enkelt flow køre?**  
    
    Der opstår timeout for kørslen af et enkelt flow efter 30 dage.

-   **Hvordan flytter jeg mine flow mellem miljøer?**  
    
    Lige som ved klassiske arbejdsprocesser kan du oprette flow i løsninger for at understøtte den fulde programlivscyklus for processer.

-   **Spores Power Automate-afhængigheder i Common Data Service?**  
    
    På samme måde som med andre komponenter i en løsning spores alle afhængigheder for flow i løsninger i Common Data Service.

-   **Hvad med synkrone arbejdsprocesser?** 
 
    Du skal evaluere behovet for synkrone arbejdsprocesser igen for at identificere, om målsætningen eller dele af arbejdsprocessen kan oprettes ved hjælp af et flow. Vi kan især ud fra vores telemetri se, at synkrone arbejdsprocesser er en stor bidragyder til den overordnede slutbrugers oplevelse af dårlig ydeevne. Det kan i mange brugssituationer være en fordel at opdele disse handlinger som asynkrone, så brugerne kan fortsætte med deres aktiviteter, mens Power Automate fortsætter med at sikre, at handlingen fuldføres.

-   **Når jeg bruger Power Automate, forbliver mine data så inden for området (dvs. det samme område som mit Dynamics 365- eller Common Data Service-miljø)?**  
    
    Ja, Power Automate bruger altid det samme område som Common Data Service.

-   **Skal jeg foretage ændringer af proxy/firewall?**  
    
    Se [Konfigurationsreference for IP-adresse](limits-and-config.md#ip-address-configuration) for at finde ud af, om du skal foretage ændringer af proxy/firewall.
