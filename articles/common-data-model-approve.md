---
title: Opret en godkendelsesløkke med Common Data Service | Microsoft Docs
description: Opret et objekt, et flow og en app, der arbejder sammen, så validatorer kan godkende eller afvise filer, der er føjet til Dropbox.
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
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6346772d3eba6177577f7c5d7a151174f1a575f9
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193858"
---
# <a name="build-an-approval-loop-by-using-power-automate-and-the-microsoft-common-data-service"></a>Opret en godkendelsesløkke ved hjælp af Power Automate og Microsoft Common Data Service

Med Common Data Service kan du oprette flow på en måde, hvor oplysningerne gemmes i en database, der er uafhængig af et flow. Det bedste eksempel på dette er godkendelser. Hvis du gemmer status for godkendelsen i en enhed, kan dit flow arbejde oven på den.

I dette eksempel skal du oprette en godkendelsesproces, der starter, når en bruger føjer en fil til Dropbox. Når filen er tilføjet, vises oplysninger om det i en app, hvor en validator kan godkende eller afvise ændringen. Hvis validatoren godkender eller afviser ændringen, sendes der en meddelelsesmail, og afviste filer slettes fra Dropbox.

Ved at følge trinnene i dette afsnit opretter du:

* Et **brugerdefineret objekt**, der indeholder oplysninger om hver fil, der er føjet til Dropbox, og hvorvidt filens status er godkendt, afvist eller ventende.
* Et **flow**, der føjer oplysninger til det brugerdefinerede objekt, når en fil føjes til Dropbox, sender mail, når filen er godkendt eller afvist, og sletter afviste filer. Nedenstående trin viser, hvordan du opretter et sådant flow fra bunden, men du kan oprette et lignende flow fra en skabelon.
* En **app**, hvor en validator kan godkende eller afvise filer, der er føjet til Dropbox. Du bruger Power Apps til automatisk at oprette denne app ud fra felterne i det brugerdefinerede objekt.

**Forudsætninger**

* Tilmeld dig [Power Automate](sign-up-sign-in.md) og [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Opret forbindelser til Dropbox og Office 365 Outlook, som beskrevet i [Administrer dine forbindelser](https://powerapps.microsoft.com/tutorials/add-manage-connections/).

## <a name="build-the-entity"></a>Opret objektet
1. Log på [powerapps.com](https://make.powerapps.com).
2. Hvis navigationslinjen til venstre ikke vises som standard, skal du klikke eller trykke på ikonet med tre vandrette streger i øverste venstre hjørne.
   
    ![Åbn venstre navigationslinje](./media/common-data-model-approve/hamburger-icon.png)
3. Klik eller tryk på **Administrer** på den venstre navigationslinje, og klik eller tryk på **Objekter**.
   
    ![Administrer objekter](./media/common-data-model-approve/manage-entities.png)
4. Hvis du bliver bedt om det, skal du klikke eller trykke på **Opret min database**.
   
    ![Opret database](./media/common-data-model-approve/create-database.png)
5. Klik eller tryk på **Nyt objekt** i nærheden af øverste højre hjørne.
   
    ![Opret objekt](./media/common-data-model-approve/new-entity.png)
   
    Hvis dit browservindue ikke er maksimeret, vises denne knap muligvis et andet sted.
6. Under **Objektnavn** skal du angive et navn, der ikke indeholder mellemrum, og som ikke svarer til navnet på et andet objekt i databasen.
   
    For at følge dette eksempel nøjagtigt, skal du angive **ReviewDropboxFiles**.
   
    ![Angiv objektnavnet](./media/common-data-model-approve/entity-name.png)
7. Under **Vist navn** skal du angive et brugervenligt navn.
   
    ![Angiv det viste navn](./media/common-data-model-approve/display-name.png)
8. Klik eller tryk på **Næste**.
   
    ![Knappen Næste](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Føj felter til objektet
1. Klik eller tryk på **Tilføj felt** i nærheden af øverste højre hjørne.
   
    ![Tilføj felt](./media/common-data-model-approve/add-field.png)
2. I den tomme række, der vises nederst på listen over felter, skal du angive egenskaber for et **Godkender**-felt. (I takt med at du angiver disse egenskaber, kan du skifte til den næste kolonne ved at trykke på Tab.)
   
   * I kolonnen **Vist navn** skal du skrive **Godkender**.
   * I kolonnen **Navn** skal du skrive **ApproverEmail**.
   * I kolonnen **Type** skal du klikke eller trykke på indstillingen **Mail**.
   * I kolonnen **Påkrævet** skal du markere afkrydsningsfeltet.
     
     ![Feltet Godkender](./media/common-data-model-approve/approver-field.png)
3. I den næste række skal du angive egenskaberne for et **Status**-felt:
   
   * I kolonnen **Vist navn** skal du skrive **Status**.
   * I kolonnen **Navn** skal du skrive **Status**.
   * I kolonnen **Type** skal du klikke eller trykke på indstillingen **Tekst**.
   * I kolonnen **Egenskaber** beholder du standardværdien.
   * I kolonnen **Påkrævet** skal du markere afkrydsningsfeltet.
     
     ![Statusfelt](./media/common-data-model-approve/status-field.png)
4. I den næste række skal du angive egenskaberne for et **Fil-id**-felt:
   
   * I kolonnen **Vist navn** skal du skrive **Fil-id**.
   * I kolonnen **Navn** skal du skrive **Fil-id**.
   * I kolonnen **Type** skal du klikke eller trykke på indstillingen **Tekst**.
   * I kolonnen **Egenskaber** beholder du standardværdien.
   * I kolonnen **Entydig** skal du markere afkrydsningsfeltet.
   * I kolonnen **Påkrævet** skal du markere afkrydsningsfeltet.
     
     ![Feltet Fil-id](./media/common-data-model-approve/fileid-field.png)
5. I nærheden af højre kant skal du klikke eller trykke på ellipsen (...) til feltet **Fil-id** og derefter klikke eller trykke på **Angiv som titelfelt**.
   
    ![Angiv titelfelt](./media/common-data-model-approve/set-title-field.png)
6. Klik eller tryk på **Opret** i nærheden af nederste venstre hjørne.
   
    ![Opret et objekt](./media/common-data-model-approve/create-button.png)
7. (valgfrit) Når listen over objekter vises igen, skal du maksimere browservinduet, hvis det ikke allerede er maksimeret, og derefter klikke eller trykke på kolonneoverskriften **Type**. Listen sorteres, så de brugerdefinerede objekter, f.eks. det, du lige har oprettet, vises øverst.

## <a name="sign-in-and-create-a-flow"></a>Log på, og opret et flow
1. Åbn [Power Automate-portalen](https://flow.microsoft.com).
2. Maksimer browservinduet, hvis det ikke allerede er maksimeret, og klik eller tryk derefter på **Log på** i nærheden af det øverste højre hjørne.
   
    ![Knappen Log på for Power Automate](./media/common-data-model-approve/signin-flow.png)
3. I menuen øverst til højre skal du vælge det miljø, hvor du oprettede databasen i powerapps.com.
   
    **Bemærk**! Hvis du ikke vælger det samme miljø, får du ikke vist din enhed.
4. Klik eller tryk på **Mine flows** i nærheden af øverste venstre hjørne.
   
    ![Knappen Mine flows](./media/common-data-model-approve/myflows-button.png)
5. Klik eller tryk på **Opret nyt flow** i nærheden af det øverste højre hjørne.
   
    ![Knappen Opret nyt flow](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Start, når en fil tilføjes
1. I feltet, der indeholder **Søg efter flere udløsere**, skal du skrive eller indsætte **Dropbox**, og derefter klikke eller trykke på **Dropbox – når der oprettes en fil**.
   
    ![Opret udløser](./media/common-data-model-approve/create-trigger.png)
2. Klik eller tryk på mappeikonet under **Mappe**, og gå derefter til den mappe, hvor filerne skal tilføjes.
   
    ![Vælg mappe](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Føj data til objektet
1. Klik eller tryk på **Nyt trin**, og klik eller tryk derefter på **Tilføj en handling**.
   
    ![Tilføj en handling](./media/common-data-model-approve/add-action.png)
2. I feltet, der indeholder **Søg efter flere handlinger**, skal du skrive eller indsætte **Common Data Service**, og derefter skal du klikke eller trykke på **Common Data Service – opret objekt**.
   
    ![Opret et objekt i Common Data Model](./media/common-data-model-approve/cdm-create-object.png)
3. Under **objektet** skal du skrive eller indsætte **Gennemse** og derefter klikke eller trykke på **Gennemse Dropbox-filer**.
   
    ![Vælg objektet](./media/common-data-model-approve/choose-entity-flow.png)
4. Klik eller tryk på feltet under **Titel**, og klik eller tryk derefter på **Filnavn** på listen over parametertokens for at føje dette token til feltet.
   
    ![Tilføj tokenet Filnavn](./media/common-data-model-approve/add-filename-token.png)
5. Under **Godkender** skal du skrive eller indsætte mailadressen på den person, der skal gennemse filerne.
   
    **Bemærk!** Angiv din egen adresse, så det er lettere at teste flowet. Du kan ændre den senere, når flowet er klar til faktisk brug.
   
    ![Tilføj godkender](./media/common-data-model-approve/add-approver.png)
6. Under **Status** skal du skrive eller indsætte **Ventende**.
   
    ![Tilføj standardstatus](./media/common-data-model-approve/add-default-status.png)
7. Klik eller tryk på feltet under **Fil-id**, og klik eller tryk derefter på **Fil-id** på listen over parametertokens for at føje dette token til feltet.
   
    ![Tilføj tokenet Fil-id](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Kontrollér, om filen er blevet gennemgået
1. Under handlingen **Opret objekt** skal du klikke eller trykke på **Nye trin**, klikke eller trykke på **Flere** og derefter klikke eller trykke på **Tilføj et foretag indtil**.
   
    ![Tilføj foretag indtil](./media/common-data-model-approve/add-do-until.png)
2. I øverste venstre hjørne af handlingen **Foretag indtil** skal du klikke eller trykke på det felt, der indeholder **Vælg en værdi**.
   
    ![Vælg en værdi](./media/common-data-model-approve/choose-value.png)
   
    **Bemærk!** Hvis browservinduet ikke er maksimeret, skal du klikke eller trykke i det øverste felt, der indeholder **Vælg en værdi**.
3. Under **Output fra Opret objekt** skal du klikke eller trykke på **Status** for at føje dette parametertoken til feltet.
   
    ![Tilføj tokenet Status](./media/common-data-model-approve/add-status.png)
4. Åbn listen tæt på midten af handlingen **Foretag indtil** handling, og klik eller tryk derefter på **er ikke lig med**.
   
    ![Angiv er ikke lig med](./media/common-data-model-approve/is-not-equal.png)
5. I øverste højre hjørne af handlingen **Foretag indtil** skal du klikke på eller indsætte **Ventende** i det felt, der indeholder **Vælg en værdi**.
   
    ![Angiv status til at se](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Bemærk!** Hvis browservinduet ikke er maksimeret, skal du klikke eller trykke i det nederste felt, der indeholder **Vælg en værdi**.
6. Nederst på handlingen **Foretag indtil** skal du klikke eller trykke på **Tilføj en handling**.
   
    ![Tilføj en handling i en foretag indtil](./media/common-data-model-approve/add-action-in-dountil.png)
7. I feltet, der indeholder **Søg efter flere handlinger**, skal du skrive **Fælles**, og derefter skal du klikke eller trykke på **Common Data Service – hent objekt**.
   
    ![Hent et objekt](./media/common-data-model-approve/get-object.png)
8. Under **navneområdet** skal du klikke eller trykke på databasen.
9. Under **objektet** skal du skrive eller indsætte **Gennemse** og derefter klikke eller trykke på **Gennemse Dropbox-filer**.
   
    ![Vælg objekt](./media/common-data-model-approve/choose-entity-flow.png)
10. Klik eller tryk på feltet under **Objekt-id**, og klik eller tryk derefter på parametertokenet **Fil-id** for at føje det til feltet.
    
     ![Tilføj objekt-id](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Kontrollér, om objektet er blevet godkendt
1. Under handlingen **Foretag indtil** skal du klikke eller trykke på **Nyt trin** og derefter klikke eller trykke på **Tilføj en betingelse**.
   
    ![Tilføj betingelse](./media/common-data-model-approve/add-condition.png)
2. I øverste venstre hjørne af betingelsen skal du klikke eller trykke på det felt, der indeholder **Vælg en værdi**.
   
    ![Øverste venstre hjørne af betingelse](./media/common-data-model-approve/condition-upper-left.png)
   
    **Bemærk!** Hvis browservinduet ikke er maksimeret, skal du klikke eller trykke i det øverste felt, der indeholder **Vælg en værdi**.
3. Under **Output fra Hent objekt** skal du klikke eller trykke på parametertokenet **Status** for at føje det til feltet.
   
    ![Tilføj status til betingelse](./media/common-data-model-approve/add-status-to-condition.png)
4. I øverste højre hjørne af betingelsen skal du skrive eller indsætte **Godkendt** i det felt, der indeholder **Vælg en værdi**.
   
    ![Kontroller, om status er angivet til godkendt](./media/common-data-model-approve/status-equals-approved.png)
   
    **Bemærk!** Hvis browservinduet ikke er maksimeret, skal du skrive eller indsætte **Godkendt** i det nederste felt, der indeholder **Vælg en værdi**.

## <a name="send-notification-mail"></a>Send mailmeddelelse
1. Under **Hvis ja, gør ingenting** skal du klikke eller trykke på **Tilføj en handling**.
   
    ![Hvis ja, tilføj en handling](./media/common-data-model-approve/if-yes-action.png)
2. I feltet, der indeholder **Søg efter flere handlinger**, skal du skrive eller indsætte **send mail**, og derefter skal du klikke eller trykke på **Office 365 Outlook – send en mail**.
   
    ![Hvis ja, send mail](./media/common-data-model-approve/if-yes-send-mail.png)
3. Under **Til** skal du skrive eller indsætte adressen på den person, du vil give besked, når et element er accepteret.
   
    **Bemærk!** Angiv din egen adresse, så det er lettere at teste flowet. Du kan ændre den, når flowet er klar til faktisk brug.
   
    ![Godkendelsesmodtager](./media/common-data-model-approve/approval-recipient.png)
4. Klik eller tryk på feltet under **Emne**, og klik eller tryk derefter på parametertokenet **Filnavn** for at føje det til feltet.
   
    ![Angiv filnavnet som mailens emne](./media/common-data-model-approve/subject-is-file-name.png)
5. Under **Meddelelsestekst** skal du skrive eller indsætte **Elementet er blevet godkendt.**
   
    ![Mailteksten i godkendelsesmailen](./media/common-data-model-approve/approval-body.png)
6. Under **Hvis nej, gør ingenting** skal du gentage trinnene 1-5 i denne procedure, men du skal angive meddelelsesteksten i mailen som **Elementet er blevet afvist.**
   
    ![Meddelelsestekst i afvisningsmailen](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Slet afviste filer
1. Klik eller tryk på **Tilføj en handling** under felterne for afvisningsmailen.
   
    ![Tilføj slettehandling](./media/common-data-model-approve/add-delete-action.png)
2. I feltet, der indeholder **Søg efter flere handlinger**, skal du skrive eller indsætte **Dropbox** og derefter klikke eller trykke på **Dropbox – slet fil**.
   
    ![Slet fil fra Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. Klik eller tryk på feltet under **Fil**, og klik eller tryk derefter på tokenparameteren **Fil-id** for at føje den til feltet.
   
    ![Identificer fil, der skal slettes](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Gem flowet
1. Øverst på skærmen skal du skrive eller indsætte et navn til det flow, du opretter, og derefter skal du klikke eller trykke på **Opret flow**.
   
    ![Gem flow](./media/common-data-model-approve/save-flow.png)
2. Klik eller tryk på **Luk**, og klik eller tryk derefter på **Udført**.
3. I Dropbox skal du tilføje mindst to filer til den mappe, du har angivet: en til at teste godkendelse og en til at teste afvisning.

## <a name="build-the-app"></a>Opret appen
1. Log på [powerapps.com](https://make.powerapps.com), og klik eller tryk derefter på **Ny app** nederst i venstre navigationslinje.
   
    ![Opret en app i en browser](./media/common-data-model-approve/new-app-button.png)
2. I den dialogboks, der vises, skal du klikke eller trykke på den indstilling, der åbner enten Power Apps Studio til Windows eller Power Apps Studio til internettet.
3. Hvis du har åbnet Power Apps Studio til Windows, skal du klikke eller trykke på **Ny** på den venstre navigationslinje.
4. Under **Opret en app fra dine data** skal du klikke eller trykke på **Telefonlayout** i feltet **Common Data Service**.
   
    ![Opret app](./media/common-data-model-approve/afd-cdm.png)
5. I feltet **Søg** skal du skrive eller indsætte **Gennemse**.
   
    ![Søg efter et objekt](./media/common-data-model-approve/search-entities.png)
6. Under **Vælg et objekt** skal du klikke eller trykke på **Gennemgå Dropbox-filer**.
   
    ![Vælg et objekt](./media/common-data-model-approve/choose-entity.png)
7. Klik eller tryk på **Opret forbindelse** i nærheden af nederste højre hjørne.
   
    ![Knappen Opret forbindelse](./media/common-data-model-approve/connect-button.png)
8. Hvis åbningsskærmen i introduktionspræsentation vises, kan du se præsentationen for at blive fortrolig med Power Apps (eller du kan klikke eller trykke på **Spring over**).
   
    ![Introduktionspræsentation](./media/common-data-model-approve/quick-tour.png)
   
    Du kan altid gennemgå præsentationen senere ved at klikke eller trykke på spørgsmålstegnsikonet i øverste venstre hjørne og derefter klikke på **Se introduktionspræsentationen**.
9. (valgfrit) Træk i skyderen nederst i skærmbilledet for at forøge zoomniveauet, så appen er nemmere at se.
   
    ![Zoomkontrolelement](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Tilpas appen
1. Klik eller tryk på layoutet, som indeholder en overskrift og en beskrivelse, på den højre navigationslinje.
   
    ![Knappen Opret forbindelse](./media/common-data-model-approve/choose-layout.png)
2. På **BrowseScreen** skal du klikke eller trykke lige under søgepanelet for at vælge kontrolelementet til større tekstfelt.
   
    ![Vælg overskrift](./media/common-data-model-approve/select-header.png)
3. I ruden til højre skal du åbne den nederste liste ved at klikke eller trykke på den nedadgående pil.
   
    ![Åbn rulleliste](./media/common-data-model-approve/open-dropdown.png)
4. På den nederste liste skal du klikke eller trykke på **Titel** for at få vist filnavnet på de tilføjede filer.
   
    ![Angiv overskriftsdata](./media/common-data-model-approve/set-heading.png)
5. I den højre rude skal du åbne den øverste liste og derefter klikke eller trykke på **Status** for at få vist status for hver fil.
   
    ![Angiv data til meddelelsestekst](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Test den overordnede løsning
1. Åbn Vis udskrift i Power Apps ved at klikke eller trykke på afspilningsknappen i øverste venstre hjørne.
   
    ![Åbn Vis udskrift](./media/common-data-model-approve/open-preview.png)
2. Klik på den første fil på listen, og klik eller tryk på pilen for at få vist detaljer om filen.
   
    ![Åbn skærmbilledet Detaljer](./media/common-data-model-approve/open-details.png)
3. Klik eller tryk på blyantsikonet i øverste højre hjørne for at ændre detaljerne om filen.
   
    ![Åbn skærmbilledet Rediger](./media/common-data-model-approve/edit-record.png)
4. Skriv eller Indsæt **Godkendt** i feltet **Status**.
   
    ![Godkend en fil](./media/common-data-model-approve/change-status.png)
5. Klik eller tryk på afkrydsningsikonet i øverste højre hjørne for at gemme ændringerne og vende tilbage til skærmbilledet Detaljer.
   
    ![Gem ændringer](./media/common-data-model-approve/save-record.png)
   
    I løbet af et par minutter vil du modtage en mail, der angiver, at filen blev godkendt.
6. Klik eller tryk på knappen Tilbage i øverste højre hjørne for at gå tilbage til skærmbilledet Gennemse.
   
    ![Tilbage til skærmbilledet Gennemse](./media/common-data-model-approve/back-arrow.png)
7. Klik eller tryk på pilen for at få vist detaljer om den anden fil på listen.
   
    ![Åbn skærmbilledet Detaljer](./media/common-data-model-approve/open-details.png)
8. Klik eller tryk på blyantsikonet i øverste højre hjørne for at ændre detaljerne om filen.
   
    ![Åbn skærmbilledet Rediger](./media/common-data-model-approve/edit-record.png)
9. I feltet **Status** skal du skrive eller indsætte **Afvist** (eller hvad som helst undtagen **Godkendt**, herunder **Godkendt** eller **Godkendt**).
   
    ![Afvis fil](./media/common-data-model-approve/reject-file.png)
10. Klik eller tryk på afkrydsningsikonet i øverste højre hjørne for at gemme ændringerne og vende tilbage til skærmbilledet Detaljer.
    
     ![Gem ændringer](./media/common-data-model-approve/save-record.png)
    
     I løbet af et par minutter vil du modtage en mail, der angiver, at filen blev afvist, og at filen slettes fra Dropbox.

