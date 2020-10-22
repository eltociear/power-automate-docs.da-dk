---
title: Erstat klassiske Common Data Service-arbejdsprocesser med Power Automate | Microsoft Docs
description: Beskriver funktioner i Power Automate og anbefalede mønstre for brug af flow i stedet for en klassisk arbejdsproces.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 09/25/2020
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 72c1296c703070d6fbb9b9a2e7493e507c8bd4b8
ms.sourcegitcommit: 4db6edd51883e28e14a2a7064cf487c167d47649
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/06/2020
ms.locfileid: "3964609"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Erstat klassiske Common Data Service-arbejdsprocesser med flows

I dette emne sammenlignes Power Automate-funktioner med en klassisk arbejdsproces.

Power Automate giver betydelige fordele i forhold til den klassiske baggrundsarbejdsprocesmodel. Du bør overveje at bruge Power Automate til at automatisere processer i stedet for den klassiske arbejdsproces.

Opret flows i stedet for klassiske Common Data Service-arbejdsprocesser for at bygge nye automatiseringsprocesser. Du bør desuden gennemgå dine eksisterende klassiske baggrundsarbejdsprocesser og overveje at erstatte dem med flows.

## <a name="feature-capability-comparison"></a>Sammenligning af funktionalitet

I denne tabel opsummeres en sammenligning mellem funktionerne i Power Automate og i klassiske arbejdsprocesser.

*Vi tilføjer løbende nye funktioner i Power Automate. Vi opdaterer oplysningerne i denne tabel, når Power Automate får nye funktioner. Vend ofte tilbage! Du kan finde oplysninger om de kommende egenskaber, der kan hjælpe dig med at erstatte klassiske baggrundsarbejdsprocesser med flows, under [Nyheder og planlagte funktioner til Power Automate](https://docs.microsoft.com/power-platform-release-plan/2020wave2/power-automate/planned-features)*

<table>
<tr>
<th colspan="2">Egenskab</th>
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
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Vent-betingelser i felter
                    
                </td>
                <td>
                    
   No
                    
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
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Indbyggede forbindelser til eksterne systemer (udløser og udfører handlinger i eksterne services)
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
                <td>
                    
   No
                    
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
                    
   No
                    
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
                    
   Ja
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Kør Common Data Service-handlinger (herunder brugerdefinerede)
                    
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
                    
   Kør brugerdefinerede arbejdsprocesaktiviteter i baggrunden
                    
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
                    
   No
                    
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
                    
   No
                    
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
                    
   Udløs betingelse ved feltværdier (f.eks. på en bestemt dato i et datofelt)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Udløser for flere Common Data Service-objekthændelser
                    
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
   (f.eks. organisation, forretningsenhed, bruger)
                    
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
                    
   No
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Synkron kørsel (realtid)
                    
                </td>
                <td>
                    
   No
                    
                </td>
                <td>
                    
   Ja
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Oversigt
                    
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
                    
   No
                    
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

## <a name="example-scenario-replace-a-background-workflow-with-a-flow"></a>Eksempel på scenarie: Erstat en baggrundsarbejdsproces med et flow

Forestil dig et salgsscenarie, hvor du har sammensat et tilbud til en kunde og nu har brug for at anmode om godkendelse fra dit administrationsteam, før du sender tilbuddet til kunden. Med klassiske arbejdsprocesser er dette ikke nemt at gøre, og de fleste løsninger til dette kræver, at en udvikler skriver brugerdefinerede baggrundsarbejdsprocesaktiviteter for at hente tilbudslinjeelementer.

Flow gør det nemmere at bygge som vist i gennemgangen senere. Den dækker nogle af de Power Automate-funktioner, der understøtter scenariet. Disse funktioner omfatter:

- Oprettelse af et flow, der kører efter behov.
- Visning af en liste over poster, der er relateret til et Common Data Service-objekt.
- Løkker i en liste over poster.
- Afsendelse af godkendelsesanmodninger.

Sådan gør du det muligt for sælgeren at udløse godkendelsesanmodningen efter behov:

1. Log på [Power Automate](https://flow.microsoft.com/), og [opret et flow i en løsning](create-flow-solution.md). 

1. På listen over udløsere skal du vælge **Common Data Service (aktuelt miljø) – Når en post vælges** og vælge **Tilbud** som objektet. 

   Denne udløser gør det muligt at køre et flow på en post eller et sæt af poster efter behov.

1. Når udløseren er konfigureret, kan du tilføje handlinger, der skal køres i flowet. Dette giver godkenderen et resume med de oplysninger, de har brug for til at identificere de tilbudte elementer og værdier. Begynd med at tilføje handlingen **Common Data Service (aktuelt miljø) – Listeposter**. Målet er at hente de enkelte elementer fra et tilbud, så angiv **Objektnavn** til **Tilbudslinjer**. For at sikre, at listen kun viser de tilbudslinjeelementer, der hører til det tilbud, som flowet blev udløst for, skal du angive et filterkriterium for OData-typografien. I feltet **Filterforespørgsel** skal du skrive *\_quoteid_value eq* og derefter vælge *Tilbud* på den liste over dynamiske værdier, der vises.

    ![Tilføj handlinger](media/define-flow-1.png "Fuldfør kortet **Listeposter**")

1. Da du vil opsummere tilbudslinjeelementer til godkendelsen, skal du tilføje handlingen **Initialiser variabel**. Angiv feltet **Navn** til *Resume af tilbudslinje* og **Type** til Streng (på rullelisten), og lad feltet **Værdi** være tomt.

1. Tilføj handlingen **Føj til streng**, og vælg derefter variablen *Resumé af tilbudslinje*, som vi oprettede tidligere. Vælg **Antal, Navn, Pris pr. enhed, Udvidet beløb og Manuelt beløb** på listen over dynamiske værdier i feltet *Værdi*. Power Automate-designeren identificerer, at disse værdier er fra en liste over tilbudslinjeelementer, og tilføjer denne handling i en **Anvend på alle**-løkke for at sikre, at oplysninger fra hvert linjeelement føjes til denne oversigt.

    ![Tilføj variabel](media/define-flow-2.png "Fuldfør kortet **Anvend på hver**")

1. Tilføj handlingen **Godkendelse – Start, og vent på en godkendelse** for at anmode om godkendelse af det tilbudsresumé, du har oprettet. Vælg en godkendelsestype (f.eks. Godkend/Afvis – Første til at svare), giv godkendelsesanmodningen en **Titel** (f.eks. navnet på det tilbud, der anmodes om godkendelse af, og som er angivet på listen over dynamiske værdier), angiv mailadressen for den person, der skal gennemse den, og godkend tilbuddet i feltet *Tildelt til**. Tilføj variablen *Resume af tilbudslinje* i feltet Detaljer sammen med eventuelle andre oplysninger, der kan være relevante ved hjælp af den dynamiske værdivælger (f.eks. Samlet beløb).

1. Tilføj handlingen **Betingelse** for at finde ud af, hvad der sker, når en godkendelse accepteres eller afvises. Vælg *Resultat* på listen over dynamiske værdier fra det første felt i betingelsen, *Indeholder* på rullelisten i det andet felt, og angiv *Accepter* i det tredje felt i betingelsen. Til sidst kan du tilføje handlinger baseret på resultatet af godkendelsen (f.eks. Send en mail med besked).

    ![Tilføj betingelse](media/define-flow-3.png "Indstillinger for tilstanden ja/nej")

Du har nu oprettet godkendelsesstrukturen, så godkenderen har alle de oplysninger, der kræves for at træffe en beslutning om de næste trin. Her er det fuldstændige eksempel 

![Struktur for godkendelsesflow](media/approval-flow-structure.png "Struktur for godkendelsesflow")

Når du kører dette flow i forhold til dit tilbud, opsummeres tilbudslinjeelementer for det pågældende tilbud, og der sendes en godkendelsesanmodning, som godkenderen kan reagere på fra Power Automate eller den handlingsrettede mail, de modtager. Nedenfor vises eksempel på visningen:

![Flow i handling](media/flow-in-action.png "Flow i handling")

## <a name="recommended-patterns"></a>Anbefalede mønstre


- **Arbejdsprocesser med kompleks Ellers Hvis-betingelseslogik**  

  I stedet for at bruge betingelser, anbefaler vi, at du bruger [handlingen Skift](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement).

- **Arbejdsprocesser, der kører fra plug-in/kode**  

  Vi anbefaler, at du omdesigner flowet, så det starter med udløsere.

  - Brug Common Data Service-udløsere til at køre flows baseret på hændelser i den.

  - Hvis du vil køre flows, der er baseret på hændelser i en ekstern tjeneste, kan du udnytte de mere end 260 indbyggede connectorer.

  - I forbindelse med scenarier, hvor en connector, du har brug for, ikke umiddelbart er tilgængelig, kan du nemt oprette din egen brugerdefinerede connector [Få mere at vide om, hvordan du opretter brugerdefinerede connectorer](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

  - Endelig gælder det, at hvis der er scenarier, hvor du ikke kan udløse dit flow ved hjælp af en Common Data Service-connector eller en af de indbyggede connectorer eller oprette en brugerdefineret connector, skal du bruge udløseren [Når der modtages en HTTP-anmodning](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) til at kalde flowet.

- **Arbejdsprocesser, der kører rekursivt**  

  Brug [Foretag indtil](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop)- eller [Anvend på alle](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop)-løkken i Flows i stedet

- **Arbejdsprocesser, der skal bruge en liste over poster**  

  Brug handlingen **Listeposter**. Når du bruger denne handling, skal du definere kriterier for postfiltrering ved hjælp af OData-syntaksen for at optimere handlingen ved at minimere det antal poster, du vil hente.

- **Arbejdsprocesser, der slumrer, indtil de skal køres efter en tidsplan**  

  Brug udløseren **Gentagelse** til at køre forretningslogik med regelmæssige intervaller.

- **Arbejdsprocesser, hvor kørsler er administreret for at sikre, at aktiviteterne blev udført i en enkelt transaktion**  

  Brug handlingen [changeset](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) til at sikre, at alle handlinger i den udføres som en enkelt atomisk enhed, hvor alle lykkes eller mislykkes som en gruppe. Hvis en af handlingerne i et ændringssæt mislykkes, rulles ændringer, der er foretaget af fuldførte handlinger, tilbage.

- **Overvåg, om der opstår fejl i kørsler af baggrundsarbejdsproces**  

  I Power Automate skal du bruge **kør efter-indstillingen** for en handling for at konfigurere den til at køre, når den forrige handling mislykkes. Du kan f.eks. sende en Power Automate-mobilbesked, når handlingen **opdater en post** mislykkedes, eller der opstår timeout for den.

## <a name="faqs"></a>Ofte stillede spørgsmål

- **Jeg har en Dynamics 365-licens. Kan jeg bruge Power Automate?**

  Alle Dynamics 365-brugere har ret til at bruge Power Automate. Gennemse vores licensoplysninger: <https://flow.microsoft.com/pricing/>

- **Hvor ofte kan mine flow udløses?**

   Flows i Dynamics 365 (eller Common Data Service) kører næsten i realtid efter udløseren, fordi de bruger webhooks (ingen polling er påkrævet)

  - Som med direkte API-adgang er der tærskler/begrænsninger i systemet. Se [Grænser og konfiguration i Power Automate](limits-and-config.md)
  - Specifikt er der en begrænsning på 100.000 handlinger pr. 5 minutter pr. flow. En enkelt løkke i et flow kan ikke behandle mere end 100.000 elementer på én gang
  - Der er et maksimum på 6 GB dataoverførselshastighed pr. 5. minut

- **Hvor lang tid kan et enkelt flow køre?**  

  Der opstår timeout for kørslen af et enkelt flow efter 30 dage.

- **Hvordan flytter jeg mine flows mellem miljøer?**  

  Lige som ved klassiske arbejdsprocesser kan du oprette flows i løsninger for at understøtte den fulde programlivscyklus for processer.

- **Spores Power Automate-afhængigheder i Common Data Service?**  

  På samme måde som andre komponenter i en løsning spores alle afhængigheder for flows i løsninger i Common Data Service.

- **Hvad med synkrone arbejdsprocesser?**

  Vi har set feedback om, at synkrone arbejdsprocesser er en væsentlig bidragyder til at løse problemer med brugernes ydeevne. Det anbefales, at du evaluerer, om målsætningen eller dele af baggrundsarbejdsprocessen kan opbygges ved hjælp af et flow. Hvis du kan opdele handlinger som asynkrone, kan brugeren fortsætte aktiviteten, mens Power Automate-handlingen fuldføres.

- **Når jeg bruger Power Automate, forbliver mine data så inden for området (dvs. samme område som mit Dynamics 365- eller Common Data Service-miljø)?**  

  Ja, Power Automate bruger altid det samme område som Common Data Service.

- **Skal jeg foretage ændringer af proxy/firewall?**  

  Se [Konfigurationsreference for IP-adresse](limits-and-config.md#ip-address-configuration) for at finde ud af, om du skal foretage ændringer af proxy/firewall.
