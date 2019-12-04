---
title: Brug handlingen "Anvend på hver enkelt" til at kan bruge til at gå gennem en matrix af elementer. | Microsoft Docs
description: Brug Power Automate til at gå gennem en matrix af elementer for at kontrollere flere betingelser og udføre handlinger på baggrund af disse betingelser.
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
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3f4ddd361eaad062a7287c1d0b33e00fc320e69e
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74357904"
---
# <a name="use-the-apply-to-each-action-in-power-automate-to-process-a-list-of-items-periodically"></a>Brug handlingen "Anvend på hver enkelt" i Power Automate for at behandle en liste over elementer med jævne mellemrum
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Mange udløsere kan straks begynde et flow på baggrund af en hændelse, f.eks. når du modtager en ny mail i din indbakke. Disse udløsere er gode, men nogle gange du vil køre et flow, der forespørger en datakilde efter et foruddefineret interval og udfører visse handlinger på baggrund af egenskaberne for elementerne i datakilden. For at gøre dette kan du starte dit flow efter en tidsplan (f.eks. én gang pr. dag) og bruge en gennemgangshandling, f.eks **Anvend på hver enkelt** for at behandle en liste over elementer. Du kan f.eks. bruge **Anvend på hver enkelt** til at opdatere poster fra en database eller en liste over elementer fra Microsoft SharePoint.

I denne gennemgang opretter vi et flow, der kører hvert 15. minut, og som gør følgende:

1. Henter de seneste 10 ulæste meddelelser i din Office 365 Outlook-indbakke.
2. Kontrollerer hver af de 10 meddelelser for at bekræfte, om nogen har **møde nu** i emnet.
3. Kontrollerer, om mailen er fra din chef eller blev sendt med høj prioritet.
4. Sender en pushmeddelelse og markerer alle mails som læst, hvis de har **møde nu** i emnet og er enten fra din chef eller blev sendt med høj prioritet.

Dette diagram viser detaljerne for det flow, vi opretter i denne gennemgang:

![oversigt over det flow, der bygges](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Forudsætninger
Her er kravene til vellykket udførelse af trinnene i denne gennemgang:

* En konto, der er registreret til at bruge [Power Automate](https://flow.microsoft.com).
* En Office 365 Outlook-konto.
* Mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).
* Forbindelser til Office 365 Outlook og pushmeddelelsestjenesten.

## <a name="create-a-flow"></a>Opret et flow
1. Log på [Power Automate](https://flow.microsoft.com):
2. Vælg fanen **Mine flows**, og opret derefter et flow fra bunden af:
   
    ![opret fra bunden af](./media/apply-to-each/foreach-1.png)
3. Angiv "planlæg" i søgefeltet for at søge efter alle tjenester og udløsere, der er relateret til planlægning.
4. Vælg udløseren **Tidsplan – Gentagelse** for at angive, at dit flow skal køre efter en tidsplan, som du angiver efterfølgende:
   
    ![Planlæg gentagelse](./media/apply-to-each/foreach-2.png)
5. Angiv, at gentagelsen efter tidsplanen skal køre hvert 15. minut:
   
    ![Planlæg kørsler](./media/apply-to-each/foreach-3.png)
6. Vælg **+ Nyt trin**, **Tilføj en handling**, og skriv derefter **outlook** i søgefeltet for at søge efter alle handlinger, der er relateret til Microsoft Outlook.
7. Vælg handlingen **Office 365 Outlook – Hent mails**:
   
    ![Vælg handlingen Hent mails](./media/apply-to-each/foreach-4.png)
8. Derved åbnes kortet **Hent mails**. Konfigurer kortet **Hent mails** til at vælge de øverste 10 ulæste mails i mappen Indbakke. Medtag ikke vedhæftede filer, da de ikke bruges i flowet:
   
    ![Konfigurer mailkort](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Indtil videre har du oprettet et simpelt flow, der henter nogle mails fra indbakken. Disse mails returneres i en matrix. Handlingen **Anvend på hver enkelt** kræver en matrix, så det er præcis, hvad der skal bruges.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Tilføj handlinger og betingelser
1. Vælg **+ Nyt trin**, **Mere** og derefter handlingen **Anvend på hver enkelt**:
   
    ![Vælg Anvend på hver enkelt](./media/apply-to-each/foreach-6.png)
2. Indsæt tokenet **Tekst** i feltet **Vælg et output fra forrige trin** på kortet **Anvend på hver enkelt**. Dette trækker teksten ind fra de mails, der skal bruges i handlingen **Anvend på hver enkelt**:
   
    ![Tilføj teksttoken](./media/apply-to-each/foreach-7.png)
3. Vælg **Tilføj en betingelse**.
   
    ![Tilføj betingelse](./media/apply-to-each/foreach-8.png)
4. Konfigurer kortet **Betingelse** for at søge efter "møde nu" i emnet for hver mail:
   
   * Indsæt tokenet **Emne** i feltet **Objektnavn**.
   * Vælg **indeholder** på listen **Relation**.
   * Angiv **møde nu** i feltet **Værdi**.
     
     ![Konfigurer betingelse](./media/apply-to-each/foreach-subject-condition.png)
5. Vælg **Flere**, og vælg derefter **Tilføj en betingelse** fra grenen **HVIS JA, GØR INTET**. Dette åbner kortet **Betingelse 2**. Konfigurer kortet som følger:
   
   * Indsæt tokenet **Prioritet** i feltet **Objektnavn**.
   * Vælg **er lig med** på listen **Relation**.
   * Angiv **Høj** i feltet **Værdi**.
     
     ![Tilføj betingelse](./media/apply-to-each/foreach-importance-condition.png)
6. Vælg **Tilføj en handling** under sektionen **HVIS JA, GØR INTET**. Derved åbnes kortet **Vælg en handling**, hvor du kan definere, hvad der skal ske, hvis søgebetingelsen (mailen **møde nu** blev sendt med høj prioritet) er sand:
   
    ![Tilføj handling](./media/apply-to-each/foreach-9.png)
7. Søg efter **meddelelse**, og vælg derefter handlingen **Meddelelser – Send mig en mobilmeddelelse**:
   
    ![Søg, og vælg meddelelse](./media/apply-to-each/foreach-10.png)
8. På kortet **Send mig en mobilmeddelelse** skal du angive oplysningerne for den pushmeddelelse, der sendes, hvis emnet i en mail indeholder "møde nu", og derefter vælge **Tilføj en handling**:
   
    ![Konfigurer meddelelse](./media/apply-to-each/foreach-11.png)
9. Angiv **læse** som søgeord, og vælg derefter handlingen **Office 365 Outlook – Markér som læst**. Dette vil markere hver enkelt mail som læst, når pushmeddelelsen er sendt:
   
    ![Tilføj handlingen Markér som læst](./media/apply-to-each/foreach-12.png)
10. Føj tokenet **Meddelelses-id** til feltet **Meddelelses-id** på kortet **Markér som læst**. Du skal muligvis vælge **Se mere** for at finde tokenet **Meddelelses-id**. Dette angiver id'et for den meddelelse, der markeres som læst:
    
     ![Tilføj meddelelses-id](./media/apply-to-each/foreach-13.png)
11. Gå tilbage til kortet **Betingelse 2** på grenen **HVIS NEJ, GØR INTET**:
    
    * Vælg **Tilføj en handling**, og skriv derefter **Hent leder** i søgefeltet.
    * Vælg handlingen **Office 365-brugere – Hent leder** på listen over søgeresultater.
    * Angiv din *fulde* mailadresse i feltet **Bruger** på kortet **Hent leder**.
      
      ![Tilføj og konfigurer handlingen Hent leder](./media/apply-to-each/foreach-get-manager.png)
12. Vælg **Flere**, og vælg derefter **Tilføj en betingelse** fra grenen **HVIS NEJ**. Dette åbner kortet **Betingelse 3**. Konfigurer kortet for at kontrollere, om mailafsenderens mailadresse (tokenet Fra) er den samme som din chefs mailadresse (tokenet Mail):
    
    * Indsæt tokenet **Fra** i feltet **Objektnavn**.
    * Vælg **indeholder** på listen **Relation**.
    * Angiv tokenet **Mail** i feltet **Værdi**.
      
      ![Konfigurer søgebetingelse](./media/apply-to-each/foreach-condition3-card.png)
13. Vælg **Tilføj en handling** under sektionen **HVIS JA, GØR INTET** på kortet **Betingelse 3**. Derved åbnes kortet **HVIS JA**, hvor du skal definere, hvad der skal ske, hvis søgebetingelsen (mailen blev sendt af din chef) er sand:
    
     ![Konfigurer betingelse](./media/apply-to-each/foreah-condition3-add-action.png)
14. Søg efter **meddelelse**, og vælg derefter handlingen **Meddelelser – Send mig en mobilmeddelelse**:
    
     ![Søg efter handlingen Meddelelse](./media/apply-to-each/foreach-10.png)
15. På kortet **Send mig en mobilmeddelelse 2** skal du angive oplysningerne for den pushmeddelelse, der skal sendes, hvis mailen er fra din chef, og derefter vælge **Tilføj en handling**:
    
     ![Konfigurer kortet Meddelelse](./media/apply-to-each/foreach-boss-notification.png)
16. Tilføj handlingen **Office 365 Outlook – Markér som læst**. Dette vil markere hver enkelt mail som læst, når pushmeddelelsen er sendt:
    
     ![Tilføj handlingen Markér som læst](./media/apply-to-each/foreach-12.png)
17. Føj tokenet **Meddelelses-id** til kortet **Markér som læst 2**. Du skal muligvis vælge **Se mere** for at finde tokenet **Meddelelses-id**. Dette angiver id'et for den meddelelse, der markeres som læst:
    
     ![Konfigurer handlingen Markér som læst](./media/apply-to-each/foreach-mark-as-read2.png)
18. Navngiv dit flow, og opret det derefter:
    
     ![Navngiv dit flow, og gem det](./media/apply-to-each/foreach-14.png)

Hvis du har fulgt med, skal dit flow ligne dette diagram:

![Oversigt over det oprettede flow](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Kør flowet
1. Send dig selv en mail med høj prioritet, der inkluderer **Møde nu** i emnet (eller få nogen i organisationen til at sende dig sådan en mail).
2. Bekræft, at mailen ligger i indbakken og er ulæst.
3. Log på Power Automate, vælg **Mine flow**, og vælg derefter **Kør nu**:
   
    ![Kør nu](./media/apply-to-each/foreach-run-1.png)
4. Vælg **Kør flow** for at bekræfte, at du virkelig vil køre flowet:
   
    ![Bekræft kørsel](./media/apply-to-each/foreach-run-2.png)
5. Efter et øjeblik skal du kunne se resultaterne af den vellykkede kørsel:
   
    ![Kørselsresultater](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Få vist kørselsresultaterne
Nu, hvor du har kørt forløbet korrekt, modtager du pushmeddelelsen på din mobilenhed.

1. Åbn appen Power Automate på din mobilenhed, og vælg derefter fanen **Aktivitet**. Du får vist pushmeddelelsen om mødet:
   
    ![Vælg fanen aktivitet](./media/apply-to-each/foreach-notification-1.png)
2. Hvis du vil se hele indholdet af meddelelsen, skal du muligvis vælge meddelelsen. Du kan se hele meddelelsen, der ser nogenlunde sådan ud:
   
    ![Meddelelsesdetaljer](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Hvis du ikke modtager pushmeddelelsen, skal du kontrollere, at mobilenheden har en aktiv dataforbindelse.
   > 
   > 

