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
ms.date: 05/06/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fcd99ea786c03eeac6ceabdf9a97886a8bbee022
ms.sourcegitcommit: 8714786a5b632dfd60099871629cf369a31c4125
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895947"
---
# <a name="use-the-apply-to-each-action-in-power-automate-to-process-a-list-of-items-periodically"></a>Brug handlingen "Anvend på hver enkelt" i Power Automate for at behandle en liste over elementer med jævne mellemrum

Mange udløsere kan straks begynde et flow på baggrund af en hændelse, f.eks. når du modtager en ny mail i din indbakke. Disse udløsere er gode, men nogle gange du vil køre et flow, der forespørger en datakilde efter et foruddefineret interval og udfører visse handlinger på baggrund af egenskaberne for elementerne i datakilden. For at gøre dette kan du starte dit flow efter en tidsplan (f.eks. én gang pr. dag) og bruge en gennemgangshandling, f.eks **Anvend på hver enkelt** for at behandle en liste over elementer. Du kan f.eks. bruge **Anvend på hver enkelt** til at opdatere poster fra en database eller en liste over elementer fra Microsoft SharePoint.

I denne gennemgang opretter vi et flow, der kører hvert 15. minut, og som gør følgende:

1. Henter de seneste 10 ulæste meddelelser i din Office 365 Outlook-indbakke.
2. Kontrollerer hver af de 10 meddelelser for at bekræfte, om nogen har **møde nu** i emnet.
3. Kontrollerer, om mailen er fra din chef eller blev sendt med høj prioritet.
4. Sender en pushmeddelelse og markerer alle mails som læst, hvis de har **møde nu** i emnet og er enten fra din chef eller blev sendt med høj prioritet.

Dette diagram viser detaljerne for det flow, vi opretter:

![oversigt over det flow, der bygges](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Forudsætninger
Her er kravene til vellykket udførelse af trinnene i denne gennemgang:

* En konto, der er registreret til at bruge [Power Automate](https://flow.microsoft.com).
* En Office 365 Outlook-konto.
* Mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).
* Forbindelser til Office 365 Outlook og pushmeddelelsestjenesten.

## <a name="create-a-flow"></a>Opret et flow
1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow**> **Nyt**> **Planlagt fra bunden**
1. Angiv et navn til dit flow i **Flownavn** på skærmbilledet **Opret et planlagt flow**. 
1. Angiv, at tidsplanen skal køre hvert 15. minut. 
1. Vælg **Opret** 
   
    ![Planlæg kørsler](./media/apply-to-each/foreach-3.png) 

1. Vælg **+ Nyt trin**, og skriv derefter **outlook** i søgefeltet for at søge efter alle connectors og handlinger, der er relateret til Microsoft Outlook.
1. Vælg handlingen **Hent mails (V3)** :
1. Kortet **Hent mails (V3)** åbnes. Konfigurer kortet **Hent mails (V3)** for at vælge de ti øverste ulæste mails i mappen Indbakke. Medtag ikke vedhæftede filer, da de ikke bruges i flowet:
   
    ![Konfigurer mailkort](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Indtil videre har du oprettet et simpelt flow, der henter nogle mails fra indbakken. Disse mails returneres i en matrix. Handlingen **Anvend på hver enkelt** kræver en matrix, så det er præcis, hvad der skal bruges.

## <a name="add-actions-and-conditions"></a>Tilføj handlinger og betingelser
1. Vælg handlingen **Nyt trin**> **Indbygget**> **Anvend på hver**.
1. Indsæt tokenet **value** i feltet **Vælg et output fra forrige trin** på kortet **Anvend på hver**. Dette trækker teksten ind fra de mails, der skal bruges i handlingen **Anvend på hver enkelt**:
   
    ![Tilføj teksttoken](./media/apply-to-each/foreach-7.png)
1. Vælg **Nyt trin**> **Kontrollér**> **Betingelse**.
1. Konfigurer kortet **Betingelse** for at søge efter "møde nu" i emnet for hver mail:
   
   * Indsæt tokenet **Emne** i det første felt på kortet **Betingelse**.
   * Vælg **indeholder** på listen over operatorer.
   * Angiv **møde nu** i det tredje felt.
     
     ![Konfigurer betingelse](./media/apply-to-each/foreach-subject-condition.png)
1. Vælg **Tilføj en handling**> **Betingelse** fra forgreningen **Hvis ja**. Dette åbner kortet **Betingelse 2**. Konfigurer kortet som følger:
   
   * Indsæt tokenet **Prioritet** i det første felt.
   * Vælg **er lig med** på listen over operatorer.
   * Angiv **høj** i feltet til højre.
     
     ![Tilføj betingelse](./media/apply-to-each/foreach-importance-condition.png)
1. Vælg **Tilføj en handling** i afsnittet **Hvis ja**.     
   Derved åbnes kortet **Vælg en handling**, hvor du kan definere, hvad der sker, hvis søgebetingelsen (mailen **møde nu** blev sendt med høj prioritet) er sand.
1. Søg efter **meddelelse**, og vælg derefter handlingen **Send mig en mobilmeddelelse**:
   
    ![søg efter og vælg meddelelse](./media/apply-to-each/foreach-10.png)
1. På kortet **Send mig en mobilmeddelelse** skal du angive oplysningerne for den pushmeddelelse, der sendes, hvis emnet i en mail indeholder "møde nu", og **Prioritet** er **høj**.
   
    ![Konfigurer meddelelse](./media/apply-to-each/foreach-11.png)

1. Gå tilbage til kortet **Betingelse 2** på forgreningen **Hvis nej**.
    
    * Vælg **Tilføj en handling**, og skriv derefter **Hent leder** i søgefeltet.
    * Vælg handlingen **Hent leder (V2)** på listen over søgeresultater.
    * Angiv tokenet **Til** i feltet **Bruger (UPN)** på kortet **Hent leder (V2)** .
      
      ![Tilføj og konfigurer handlingen Hent leder](./media/apply-to-each/foreach-get-manager.png)
1. Vælg **Tilføj en handling** fra forgreningen **Hvis nej**.
1. Vælg **Betingelse** på kortet **Vælg en handling**. Dette åbner kortet **Betingelse 3**. Konfigurer kortet for at kontrollere, om mailafsenderens mailadresse (tokenet Fra) er den samme som din chefs mailadresse (tokenet Mail):
    
    * Indsæt tokenet **Fra** i det første felt.
    * Vælg **indeholder** på listen over operatorer.
    * Angiv tokenet **mail** i feltet længst til højre.
      
      ![Konfigurer søgebetingelse](./media/apply-to-each/foreach-condition3-card.png)
1. Vælg **Tilføj en handling** under afsnittet **Hvis ja** på kortet **Betingelse 3**.
    
Derefter skal du definere, hvad der skal ske, hvis søgebetingelsen (mailen blev sendt af din chef) er sand:

1. Søg efter **meddelelse**, og vælg derefter handlingen **Send mig en mobilmeddelelse**:
    
     ![Søg efter handlingen Meddelelse](./media/apply-to-each/foreach-10.png)
1. På kortet **Send mig en mobilmeddelelse 2** skal du angive oplysningerne for den pushmeddelelse, der skal sendes, hvis mailen er fra din chef, og derefter vælge **Tilføj en handling**:
    
     ![Konfigurer kortet Meddelelse](./media/apply-to-each/foreach-boss-notification.png)
1. Tilføj handlingen **Markér som læst eller ulæst (V2)** .
1. Føj tokenet **Meddelelses-id** til kortet **Markér som læst eller ulæst (V2)** . Du skal muligvis vælge **Se mere** for at finde tokenet **Meddelelses-id**. **Meddelelses-id** er id'et for den meddelelse, der markeres som læst.
1. Vælg **Læst** på listen **Markér som** på kortet **Markér som læst eller ulæst (V2)** .
    
     ![Konfigurer handlingen Markér som læst](./media/apply-to-each/foreach-mark-as-read2.png)
1. Vælg **Gem** for at gemme dit flow.

## <a name="run-the-flow"></a>Kør flowet
1. Send dig selv en mail med høj prioritet, der inkluderer **Møde nu** i emnet (eller få nogen i organisationen til at sende dig sådan en mail).
1. Bekræft, at mailen ligger i indbakken og er ulæst.
1. Log på Power Automate, og vælg **Mine flow**.
   
    Der vises en liste over dine flow. 
    
1. Vælg det flow, du netop har oprettet, og vælg derefter **Kør**.

   ![Kør nu](./media/apply-to-each/run-flow.png)

1. Vælg **Side til flowkørsel**, og vælg derefter den flowkørsel, du er interesseret i at få vist resultatet for.
   
    ![Kørselsresultater](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Få vist kørselsresultaterne
Nu, hvor du har kørt forløbet korrekt, modtager du pushmeddelelsen på din mobilenhed.
   
> [!NOTE]
> Hvis du ikke modtager pushmeddelelsen, skal du kontrollere, at mobilenheden har en aktiv dataforbindelse.
 

