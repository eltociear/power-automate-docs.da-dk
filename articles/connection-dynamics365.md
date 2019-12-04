---
title: Opret et flow med Dynamics 365 (online) | Microsoft Docs
description: Opret nyttige arbejdsprocesser ved hjælp af en Dynamics 365-forbindelse og Power Automate
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 84b3a8956008149f80f1790a20c1388dde8737ac
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74360227"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Opret et flow ved hjælp af Dynamics 365 (online)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Ved hjælp af en Dynamics 365-forbindelse kan du oprette flows, der starter, når en hændelse indtræffer i Dynamics 365 eller en anden tjeneste, som derefter udfører en handling i Dynamics 365 eller en anden tjeneste. 

Du kan konfigurere automatiserede flow i Power Automate mellem dine yndlingsprogrammer og -tjenester for at synkronisere filer, modtage meddelelser, indsamle data og meget mere. Du finder flere oplysninger under [Kom i gang med Power Automate](getting-started.md).

> [!IMPORTANT] 
> Hvis du vil aktivere en flowudløser, skal **Ændringssporing** være aktiveret for den Common Data Service-enhed, der bruges sammen med flowet. Flere oplysninger: [Aktivér ændringssporing for at kontrollere datasynkronisering](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Opret et flow fra en skabelon
Du kan oprette et flow ved hjælp af en af de mange tilgængelige skabeloner, såsom disse eksempler:

* Når et objekt er oprettet i Dynamics 365, kan du oprette et listeelement i SharePoint.
* Opret poster for potentielle kunder i Dynamics 365 fra en Excel-tabel.
* Kopiér konti i Dynamics 365 til kunder i Dynamics 365 til handlinger.

Hvis du vil oprette et flow fra en skabelon, skal du følge disse trin.

1. Log på [Power Automate-webstedet](https://flow.microsoft.com/).
2. Klik eller tryk på **Tjenester**, og klik eller tryk derefter på **Dynamics 365**.
3. Der er adskillige tilgængelige skabeloner. Vælg den ønskede skabelon for at komme i gang.

## <a name="create-a-task-from-a-lead"></a>Opret en opgave fra en potentiel kunde
Hvis en skabelon ikke er tilgængelig i forbindelse med det, du søger, kan du oprette et flow fra bunden. Denne gennemgang viser, hvordan du opretter en opgave i Dynamics 365, hver gang der oprettes en potentiel kunde i Dynamics 365.

1. Log på [Power Automate-webstedet](https://flow.microsoft.com/).
2. Klik eller tryk på **Mine flows**, og klik eller tryk derefter på **Opret fra bunden**.
3. Klik eller tryk på **Dynamics 365 – når en post oprettes** på listen over flowudløsere.
4. Hvis du bliver bedt om det, skal du logge på Dynamics 365.
5. Under **Organisationsnavn** skal du vælge den Dynamics 365-instans, hvor du vil have flowet til at lytte.
6. Under **Enhedsnavn** skal du vælge den enhed, du vil lytte til, og som fungerer som en udløser, der starter flowet.
   
     I denne gennemgang skal du vælge **Potentielle kunder**.
   
    ![Flowdetaljer](./media/connection-dynamics365/flow-details.png)
    > [VIGTIGT!] **Skift sporing** skal være aktiveret for enhedsdefinitionen, for at flowet udløses på Dynamics 365-enheden. Se under [Aktivér ændringssporing for at kontrollere datasynkronisering](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Klik eller tryk på **Nyt trin**, og klik eller tryk derefter på **Tilføj en handling**.
8. Klik eller tryk på **Dynamics 365 – opret en ny post**.
9. Under **Organisationsnavn** skal du vælge den Dynamics 365-instans, du vil have flowet til at oprette posten i. Bemærk, at det ikke behøver at være den samme instans, hændelsen udløses fra.
10. Vælg under **Enhedsnavn** den enhed, der opretter en post, når hændelsen forekommer.
    
     I denne gennemgang skal du vælge **Opgaver**.
11. Et **emne**-felt vises. Når du klikker eller trykker på det, vises en dynamisk indholdsrude, hvor du kan vælge et af disse felter.
    
    * **Efternavn**. Hvis du vælger dette felt, indsættes efternavnet på den potentielle kunde i opgavens **emne**felt, når den oprettes.
    * **Emne**. Hvis du vælger dette felt, indsættes feltet **Emne** for den potentielle kunde i opgavens **emnefelt**, når den oprettes.
    
    I denne gennemgang skal du vælge **Emne**.
    
    ![Tilføj emne til flow](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Tip!** Klik på den dynamiske indholdsrude, eller klik eller tryk på **Se mere** for at se flere felter, der er knyttet til enheden. Du kan f.eks. også udfylde opgavens **emnefelt** med **firmanavnet**, **kunden**, **beskrivelsen**, eller den potentielle kundes **mailfelt**.
    > 
    > 
12. Klik eller tryk på **Opret flow**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Opret en Wunderlist-opgave fra en Dynamics 365-opgave
Denne gennemgang viser, hvordan du opretter en opgave i [Wunderlist](https://www.wunderlist.com), hver gang der oprettes en opgave i Dynamics 365. Wunderlist er en internetbaseret tjeneste, som du kan bruge til at oprette opgavelister, tilføje påmindelser eller spore ærinder.

1. Log på [Power Automate-webstedet](https://flow.microsoft.com/).
2. Klik eller tryk på **Mine flows**, og klik eller tryk derefter på **Opret fra bunden**.
3. Klik eller tryk på **Dynamics 365 – når en post oprettes** på listen over flowudløsere.
4. Under **Organisationsnavn** skal du vælge den Dynamics 365-instans, hvor du vil have flowet til at lytte.
5. Vælg under **Enhedsnavn** den enhed, du vil lytte til, og som fungerer som en udløser, der starter flowet.
   
    I denne gennemgang skal du vælge **Opgaver**.
6. Klik eller tryk på **Nyt trin**, og klik eller tryk derefter på **Tilføj en handling**.
7. Indtast *Opret en opgave*, og klik eller tryk derefter på **Wunderlist – opret en opgave**.
8. Under **liste-id'et** skal du vælge **Indbakke**.
9. Under **titel** skal du vælge **Emne** i den dynamiske indholdsrude.
10. Klik eller tryk på **Opret flow**.  

## <a name="trigger-based-logic"></a>Udløserbaseret logik
Udløsere som **Når der oprettes en post**, **Når en post opdateres** og **Når en post, slettes** starter dit flow inden for nogle få minutter, efter at hændelsen er opstået.  Det kan i sjældne tilfælde tage op til 2 timer, før et flow udløses.

Når udløseren udløses, modtager flowet en meddelelse, men flowet kører med de data, der findes på det tidspunkt, hvor handlingen køres.  Hvis dit flow f.eks. udløses, når der oprettes en ny post, og du opdaterer posten to gange, inden flowet kører, vil flowet kun blive kørt én gang med de seneste data.

## <a name="specify-advanced-options"></a>Angiv avancerede indstillinger
Når du føjer et trin til et flow, du kan klikke eller trykke på **Vis avancerede indstillinger** for at tilføje et filter eller en ordre fra forespørgsel, der styrer, hvordan dataene filtreres i flowet.

Du kan f.eks. bruge en filterforespørgsel til at hente udelukkende aktive kontakter, og du kan sortere dem efter efternavn. Det gør du ved at indtaste OData-filterforespørgslens **statuskode lig med 1** og vælge **Efternavn** fra den dynamiske indholdsrude. Find flere oplysninger om filter og rækkefølge af forespørgsler på [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) og [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Flowrækkefølge efter forespørgsel](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Bedste fremgangsmåder ved brug af avancerede indstillinger
Når du tilføjer en værdi til et felt, skal du få felttypen til at passe, uanset om du angiver en værdi eller vælger en fra den dynamiske indholdsrude.

| Felttype | Sådan bruger du | Her finder du | Navn | Datatype |
| --- | --- | --- | --- | --- |
| Tekstfelter |Tekstfelter kræver en enkelt tekstlinje eller dynamisk indhold, der er et teksttypefelt. Eksempler indbefatter felterne **Kategori** og **Underkategori**. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Opgave** > **Felter** |**kategori** |**Enkelt tekstlinje** |
| Heltalsfelter |Nogle felter kræver heltal eller dynamisk indhold, der er af typen heltalsfelt. Eksempler indbefatter **Procent fuldført** og **Varighed**. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Opgave** > **Felter** |**procentfuldført** |**Helt tal** |
| Datofelter |Nogle felter kræver en angivet dato i formatet dd-mm-åå eller dynamisk indhold, der er af typen datofelt. Eksempler indbefatter **Oprettet den**, **Startdato**, **Faktisk startdato**, **Seneste tid for i venteposition**, **Faktisk slutdato**, og **Forfaldsdato**. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Opgave** > **Felter** |**oprettetden** |**Dato og klokkeslæt** |
| Felter, der kræver både et post-id og en opslagstype |Nogle felter, der refererer til en anden objektpost, kræver både post-id'et og opslagstypen. |**Indstillinger** > **Tilpasninger** > **Tilpas systemet** > **Enheder** > **Konto** > **Felter** |**kontoid** |**Primær nøgle** |
|Grupperet indstilling|Felter med grupperede indstillinger kræver en kendt heltalsværdi, for at den videresendes til denne type felt.  I tilpasningsområdet i Dynamics 365 kan du få vist felterne med grupperede indstillinger, som understøtter feltet med heltalsværdien, sammen med dets respektive mærkat.|Indstillinger > Tilpasning > Tilpas systemet > Enheder > Konto > Felter | Foretrukket kontaktmetode| Helt tal|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Flere eksempler på felter, der kræver både et post-id og en opslagstype
Som en udvidelse af den forrige tabel, er her flere eksempler på felter, der ikke virker med værdier, der vælges i listen over dynamisk indhold. I stedet kræver felterne, at der både angives et post-id og en opslagstype i felterne i Power Apps.

* **Ejer** og **Ejertype**.
  
  * **Ejer**-feltet skal være en gyldig bruger eller et team-post-id.
  * **Ejertypen** skal være enten **systembrugere** eller **teams**.
* **Kunde** og **kundetype**.
  
  * Feltet **Kunde** skal indeholde en gyldig konto eller et kontaktpost-id.
  * **Kundetypen** skal være enten **konti** eller **kontakter**.
* **Angående** og **Angående type**.
  
  * Feltet **Angående** skal være et gyldigt post-id, såsom en konto eller et kontaktpost-id.
  * **Angående type** skal være opslagstypen til posten, såsom **konti** eller **kontakter**.

Dette eksempel tilføjer en kontopost, der svarer til post-id'et, og føjer det til opgavens **Angående**-felt.

  ![Flowets post-id og typekonto](./media/connection-dynamics365/flow-recordid-account.png)

Dette eksempel tildeler også opgaven til en bestemt bruger på baggrund af brugerens post-id.

  ![Flowets post-id og brugertype](./media/connection-dynamics365/flow-recordid-user.png)

Se [Find post-id](#find-the-records-id) for at finde en posts id senere under dette emne.

> **Vigtigt!** Felter skal ikke indeholde en værdi, hvis de har en beskrivelse, der kun er "til internt brug". Disse felter indbefatter **Gennemløbet sti**, **Flere parametre** og **Versionsnummeret for tidszonereglen.**
> 
> 

## <a name="find-the-records-id"></a>Find postens id
1. Åbn en post i webprogrammet til Dynamics 365, såsom en kontopost.
2. Klik eller tryk på værktøjslinjen Handlinger, eller klik eller tryk på **Pop-ud**
   ![Pop-udposten](./media/connection-dynamics365/popout.png) (eller klik eller tryk på **MAIL ET LINK** for at kopiere hele URL-adressen til dit standard mailprogram).
   
    I webbrowserens adresselinje indeholder URL-adressens post-id mellem % 7b og % 7d kodningstegn.
   
   ![Post-id](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Relaterede emner
[Fejlfinding i et flow](fix-flow-failures.md)

[Flow i din organisation – ofte stillede spørgsmål](organization-q-and-a.md)

[Ofte stillede spørgsmål](frequently-asked-questions.md)

