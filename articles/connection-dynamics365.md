---
title: Opret et flow med Dynamics 365 (online) | Microsoft Docs
description: Dynamics 365 Connector er frarådet. Brug Common Data Service-connector (nuværende miljø) eller Common Data Service-connector i stedet.
services: ''
suite: flow
documentationcenter: na
author: JimDaly
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/31/2020
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 59eb50914015ffa76607b377963b616cbcc00ded
ms.sourcegitcommit: b77b16f15bceedc9caa948676bcd641bf0bcaf2c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2020
ms.locfileid: "3413419"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Opret et flow ved hjælp af Dynamics 365 (online)

> [!IMPORTANT]
> Dynamics 365 apps (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing og Dynamics 365 Project Service Automation) bruger [Common Data Service](/powerapps/maker/common-data-service/data-platform-intro) som datakilde.
>
> [Dynamics 365 Connector](/connectors/dynamicscrmonline/) er frarådet, men fortsætter med at fungere, indtil den er fjernet.
> Du kan finde flere oplysninger under [Dynamics 365 Connector er frarådet](/power-platform/important-changes-coming#dynamics-365-connector-is-deprecated).
> 
> Brug ikke Dynamics 365 Connector til nye flows. Brug [Common Data Service-connectoren (aktuelt miljø)](/connectors/commondataserviceforapps/), når du kan.
> Hvis du Common Data Service-connectoren (aktuelt miljø) ikke opfylder dit behov, skal du bruge [Common Data Service-connectoren](/connectors/commondataservice/).
>
> [Common Data Service-connectoren (aktuelt miljø)](/connectors/commondataserviceforapps/) skal være dit førstevalg, da den giver den største kapacitet og bedste ydeevne. Den indeholder dog ikke i øjeblikket visse funktioner, som Dynamics 365 og Common Data Service-connectorer gør, f.eks. muligheden for at oprette forbindelse til flere miljøer. [Common Data Service-connectoren](/connectors/commondataservice/) har samme egenskaber som Dynamics 365 Connector, men giver også større pålidelighed.


Ved hjælp af en Dynamics 365 Connector kan du oprette flows, der starter, når en hændelse indtræffer i Dynamics 365 eller en anden tjeneste, som derefter udfører en handling i Dynamics 365 eller en anden tjeneste. 

I Power Automate kan du installere automatiserede arbejdsprocesser mellem dine yndlingsapps og -tjenester for at synkronisere filer, modtage meddelelser, samle data og meget mere. Du kan finde flere oplysninger under [Introduktion til Power Automate](getting-started.md).

> [!IMPORTANT] 
> Hvis du vil aktivere en Power Automate-udløser, skal **Ændringssporing** være aktiveret for det Common Data Service-objekt, der bruges sammen med flowet. Flere oplysninger: [Aktivere Skift sporing for at styre datasynkronisering](/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Opret et flow fra en skabelon

Du kan oprette et flow ved hjælp af en af de mange tilgængelige skabeloner, såsom disse eksempler:

* Når et objekt er oprettet i Dynamics 365, kan du oprette et listeelement i SharePoint.
* Opret kundeemneposter i Dynamics 365 fra en Excel-tabel.
* Kopier Dynamics 365-konti til kunder i Dynamics 365 for Operations.

Hvis du vil oprette et flow fra en skabelon, skal du følge disse trin.

1. Log på [Power Automate-websitet](https://flow.microsoft.com/).
2. Klik eller tryk på **Tjenester**, og klik eller tryk derefter på **Dynamics 365**.
3. Der er flere tilgængelige skabeloner. Vælg den ønskede skabelon for at komme i gang.

## <a name="create-a-task-from-a-lead"></a>Opret en opgave fra et kundeemne

Hvis en skabelon ikke er tilgængelig i forbindelse med det, du søger, kan du oprette et flow fra bunden. Denne gennemgang viser, hvordan du opretter en opgave i Dynamics 365, hver gang der oprettes et kundeemne i Dynamics 365.

1. Log på [Power Automate-websitet](https://flow.microsoft.com/).
2. Klik eller tryk på **Mine flows**, og klik eller tryk derefter på **Opret fra bunden**.
3. Klik eller tryk på **Dynamics 365 – når en post oprettes** på listen over flowudløsere.
4. Hvis du bliver bedt om det, skal du logge på Dynamics 365.
5. Under **Organisationsnavn** skal du vælge den Dynamics 365-forekomst, hvor du vil have flowet til at lytte.
6. Under **Enhedsnavn** skal du vælge den enhed, du vil lytte til, og som fungerer som en udløser, der starter flowet.
   
     I denne gennemgang skal du vælge **Kundeemner**.
   
    ![Flowdetaljer](./media/connection-dynamics365/flow-details.png)
    > [VIGTIGT!] **Skift sporing** skal være aktiveret for enhedsdefinitionen, for at flowet udløses på Dynamics 365-enheden. Se [Aktivere Skift sporing for at styre datasynkronisering](/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Klik eller tryk på **Nyt trin**, og klik eller tryk derefter på **Tilføj en handling**.
8. Klik eller tryk på **Dynamics 365 – opret en ny post**.
9. Under **Organisationsnavn** skal du vælge den Dynamics 365-forekomst, du vil have flowet til at oprette posten i. Bemærk, at det ikke behøver at være den samme forekomst, hændelsen udløses fra.
10. Vælg under **Objektnavn** det objekt, der opretter en post, når hændelsen forekommer.
    
     I denne gennemgang skal du vælge **Opgaver**.
11. Et **Emne**-felt vises. Når du klikker eller trykker på det, vises en dynamisk indholdsrude, hvor du kan vælge et af disse felter.
    
    * **Efternavn**. Hvis du vælger dette felt, indsættes efternavnet på kundeemnet i opgavens **Emne**-felt, når den oprettes.
    * **Emne**. Hvis du vælger dette felt, indsættes feltet **Emne** for kundeemnet i opgavens **Emne**-felt, når den oprettes.
    
    I denne gennemgang skal du vælge **Emne**.
    
    ![Tilføj emne til flow](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Tip:** Klik på den dynamiske indholdsrude, eller klik eller tryk på **Se mere** for at se flere felter, der er knyttet til objektet. Du kan f.eks. også udfylde opgavens **Emne**-felt med **Firmanavn**, **Kunde**, **Beskrivelse** eller kundeemnets **Mail**-felt.
    > 
    > 
12. Klik eller tryk på **Opret flow**.

## <a name="trigger-based-logic"></a>Udløserbaseret logik

Udløsere som **Når der oprettes en post**, **Når en post opdateres** og **Når en post slettes** starter dit flow inden for nogle få minutter, efter at hændelsen er opstået.  Det kan i sjældne tilfælde tage op til 2 timer, før et flow udløses.

Når udløseren forekommer, modtager flowet en meddelelse, men flowet kører med de data, der findes på det tidspunkt, hvor handlingen køres.  Hvis dit flow f.eks. udløses, når der oprettes en ny post, og du opdaterer posten to gange, inden flowet kører, vil flowet kun blive kørt én gang med de seneste data.

## <a name="specify-advanced-options"></a>Angiv avancerede indstillinger

Når du føjer et trin i et flow, kan du klikke eller trykke på **Vis avancerede indstillinger** for at tilføje et filter eller en order by-forespørgsel, der styrer, hvordan dataene filtreres i flowet.

Du kan f.eks. bruge en filterforespørgsel til at hente udelukkende aktive kontakter, og du kan sortere dem efter efternavn. Det gør du ved at indtaste OData-filterforespørgslens **statuskode lig med 1** og vælge **Efternavn** fra den dynamiske indholdsrude. Du kan finde flere oplysninger om filtrering og Order by-forespørgsler under [Forespørgselsdata > Filtrer resultater](/powerapps/developer/common-data-service/webapi/query-data-web-api#filter-results) og [Forespørgselsdata > Sortér resultater](/powerapps/developer/common-data-service/webapi/query-data-web-api#order-results).

  ![Flow for orderby-forespørgsel](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Bedste fremgangsmåder ved brug af avancerede indstillinger

Når du tilføjer en værdi i et felt, skal du få felttypen til at matche, uanset om du angiver en værdi eller vælger en fra den dynamiske indholdsrude.

| Felttype | Sådan bruges den | Her findes den | Navn | Datatype |
| --- | --- | --- | --- | --- |
| Tekstfelter |Tekstfelter kræver en enkelt tekstlinje eller dynamisk indhold, der er et teksttypefelt. Eksempler indbefatter felterne **Kategori** og **Underkategori**. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Opgave** > **Felter** |**kategori** |**Enkelt tekstlinje** |
| Heltalsfelter |Nogle felter kræver heltal eller dynamisk indhold, der er af typen heltalsfelt. Eksempler indbefatter **Procent fuldført** og **Varighed**. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Opgave** > **Felter** |**percentcomplete** |**Heltal** |
| Datofelter |Nogle felter kræver en angivet dato i formatet dd-mm-åå eller dynamisk indhold, der er af typen datofelt. Eksempler indbefatter **Oprettet den**, **Startdato**, **Faktisk startdato**, **Seneste tid i venteposition**, **Faktisk slutdato** og **Forfaldsdato**. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Opgave** > **Felter** |**createdon** |**Dato og klokkeslæt** |
| Felter, der kræver både et post-id og en opslagstype |Nogle felter, der refererer til en anden objektpost, kræver både post-id'et og opslagstypen. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Konto** > **Felter** |**accountid** |**Primær nøgle** |
|Grupperet indstilling|Felter med grupperede indstillinger kræver en kendt heltalsværdi, for at den videresendes til denne type felt.  I tilpasningsområdet i Dynamics 365 kan du se felterne med grupperede indstillinger, som understøtter feltet med heltalsværdien, sammen med dets respektive navn.|Indstillinger > Tilpasning > Tilpas systemet > Enheder > Konto > Felter | Foretrukken kontaktmetode| Heltal|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Flere eksempler på felter, der kræver både et post-id og en opslagstype

Som en udvidelse af den forrige tabel er her flere eksempler på felter, der ikke virker med værdier, der vælges på listen over dynamisk indhold. I stedet kræver felterne både et post-id og en opslagstype, der angives i felterne i Power Apps.

* **Ejer** og **Ejertype**.
  
  * **Ejer**-feltet skal være en gyldig bruger eller et team-post-id.
  * **Ejertype** skal være enten **systembrugere** eller **teams**.
* **Kunde** og **Kundetype**.
  
  * Feltet **Kunde** skal indeholde en gyldig konto eller et kontaktpost-id.
  * **Kundetype** skal være enten **konti** eller **kontakter**.
* **Angående** og **Angående-type**.
  
  * Feltet **Angående** skal være et gyldigt post-id, såsom en konto eller et kontaktpost-id.
  * **Angående-type** skal være opslagstypen til posten, såsom **konti** eller **kontakter**.

Dette eksempel tilføjer en kontopost, der svarer til post-id'et, og føjer det til opgavens **Angående**-felt.

  ![Flowets recordId og typekonto](./media/connection-dynamics365/flow-recordid-account.png)

Dette eksempel tildeler også opgaven en bestemt bruger på baggrund af brugerens post-id.

  ![Flowets recordId og typebruger](./media/connection-dynamics365/flow-recordid-user.png)

Se [Find post-id](#find-the-records-id) senere i dette emne for at finde en posts id.

> **Vigtigt:** Felter skal ikke indeholde en værdi, hvis de har en beskrivelse, der kun er "til internt brug". Disse felter indbefatter **Gennemløbet sti**, **Flere parametre** og **Versionsnummeret for tidszonereglen.**
> 
> 

## <a name="find-the-records-id"></a>Find postens id

1. Åbn en post i webprogrammet Dynamics 365, f.eks. en kontopost.
2. Klik eller tryk på **Pop-ud** på værktøjslinjen Handlinger
   ![Pop-ud-posten](./media/connection-dynamics365/popout.png) (eller klik eller tryk på **MAIL ET LINK** for at kopiere hele URL-adressen til dit standardmailprogram).
   
    I webbrowserens adresselinje indeholder URL-adressens post-id'et mellem kodningstegnene %7b og %7d.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Relaterede emner

[Fejlfinding i et flow](fix-flow-failures.md)

[Flow i din organisation – ofte stillede spørgsmål](organization-q-and-a.md)

[Ofte stillede spørgsmål](frequently-asked-questions.md)

