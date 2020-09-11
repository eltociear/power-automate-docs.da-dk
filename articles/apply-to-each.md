---
title: Brug handlingen "Anvend på hver enkelt" gennem en matrix af elementer. | Microsoft Docs
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
ms.openlocfilehash: 670b80583cdf07667675f8538b4114781b7b9ba6
ms.sourcegitcommit: a09a957460f7495c0b103e1d832f65963025fbac
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/15/2020
ms.locfileid: "3696951"
---
# <a name="use-the-apply-to-each-action-in-power-automate-to-process-a-list-of-items-periodically"></a>Brug handlingen "Anvend på hver enkelt" i Power Automate for at behandle en liste over elementer med jævne mellemrum

Mange udløsere kan straks begynde et flow på baggrund af en hændelse, f.eks. når du modtager en ny mail i din indbakke. Disse udløsere er gode, men nogle gange vil du køre et flow, der forespørger på en datakilde efter en foruddefineret tidsplan og udfører visse handlinger på baggrund af egenskaberne for elementerne i datakilden. For at gøre dette kan du starte dit flow efter en tidsplan (f.eks. én gang pr. dag) og bruge en løkkehandling, f.eks **Anvend på hver enkelt** for at behandle en liste over elementer. Du kan f.eks. bruge **Anvend på hver enkelt** til at opdatere poster fra en database eller en liste over elementer fra Microsoft SharePoint.

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
* Power Automate-mobilappen for [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).
* Forbindelser til Office 365 Outlook og pushmeddelelsestjenesten.

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="create-a-flow"></a>Opret et forløb
1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Mine flow** > **Ny** > **Planlagt fra bunden**
1. Angiv et navn til flowet i **Flownavn** på skærmbilledet **Opbyg et planlagt flow**. 
1. Angiv tidsplanen til at køre hvert 15. minut. 
1. Vælg **Opret** 
   
    ![planlægge kørsler](./media/apply-to-each/foreach-3.png) 

1. Vælg **+ Nyt trin**, og skriv derefter **outlook** i søgefeltet for at søge efter alle connectorer og handlinger, der er relateret til Microsoft Outlook.
1. Vælg handlingen **Hent mails (V3)**:
1. Kortet **Hent mails (V3)** vises. Konfigurer kortet **Hent mails (V3)** til at vælge de øverste 10 ulæste mails i mappen Indbakke. Medtag ikke vedhæftede filer, da de ikke bruges i flowet:
   
    ![konfigurere mailkort](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Indtil videre har du oprettet et simpelt flow, der henter nogle mails fra indbakken. Disse mails returneres i en matrix. Handlingen **Anvend på hver enkelt** kræver en matrix, så det er præcis, hvad der skal bruges.

## <a name="add-actions-and-conditions"></a>Tilføj handlinger og betingelser
1. Vælg **Nyt trin** > **Indbygget** > **Anvend for hver enkelt** som handling.
1. Indsæt tokenet **værdi** i feltet **Vælg et output fra forrige trin** på kortet **Anvend på hver enkelt**. Dette trækker teksten ind fra de mails, der skal bruges i handlingen **Anvend på hver enkelt**:
   
    ![tilføje teksttoken](./media/apply-to-each/foreach-7.png)
1. Vælg **Nyt trin** > **Kontrol** > **Betingelse**.
1. Konfigurer kortet **Betingelse** for at søge efter "møde nu" i emnet for hver mail:
   
   * Indsæt **Emne**-tokenet i det første felt på **Betingelse**-kortet.
   * Vælg **indeholder** på listen over operatorer.
   * Angiv **møde nu** i det tredje felt.
     
     ![konfigurere betingelse](./media/apply-to-each/foreach-subject-condition.png)
1. Vælg **Tilføj en handling** > **Betingelse** fra **Hvis ja**-forgreningen. Dette åbner kortet **Betingelse 2**. Konfigurer kortet som følger:
   
   * Indsæt **Vigtighed**-tokenet i det første felt.
   * Vælg **er lig med** på listen over operatorer.
   * Skriv **høj** i feltet i højre side.
     
     ![tilføje betingelse](./media/apply-to-each/foreach-importance-condition.png)
1. Vælg **Tilføj en handling** under sektionen **Hvis ja**.     
   Derved åbnes kortet **Vælg en handling**, hvor du kan definere, hvad der skal ske, hvis søgebetingelsen (mailen **møde nu** blev sendt med høj prioritet) er sand.
1. Søg efter **meddelelse**, og vælg derefter handlingen **Send mig en mobilmeddelelse**:
   
    ![søge efter og vælge meddelelse](./media/apply-to-each/foreach-10.png)
1. På kortet **Send mig en mobilmeddelelse** skal du angive oplysningerne for den pushmeddelelse, der sendes, hvis emnet i en mail indeholder "møde nu", og derefter vælge **Vigtighed** er **høj**.
   
    ![konfigurere meddelelse](./media/apply-to-each/foreach-11.png)

1. Gå tilbage til kortet **Betingelse 2** på forgreningen **Hvis nej**:
    
    * Vælg **Tilføj en handling**, og skriv derefter **Hent leder** i søgefeltet.
    * Vælg handlingen **Hent leder (V2)** på listen over søgeresultater.
    * Angiv **Til**-tokenet i feltet **Bruger (UPN)** i kortet **Hent leder (V2)**.
      
      ![tilføje og konfigurere handlingen Hent leder](./media/apply-to-each/foreach-get-manager.png)
1. Vælg **Tilføj en handling** i forgreningen **Hvis nej**.
1. Vælg **Betingelse** på kortet **Vælg en handling**. Dette åbner kortet **Betingelse 3**. Konfigurer kortet for at kontrollere, om mailafsenderens mailadresse (tokenet Fra) er den samme som din leders mailadresse (tokenet Mail):
    
    * Indsæt **Fra**-tokenet i det første felt.
    * Vælg **indeholder** på listen over operatorer.
    * Angiv **mail**-token i feltet yderst til højre.
      
      ![konfigurere søgebetingelse](./media/apply-to-each/foreach-condition3-card.png)
1. Vælg **Tilføj en handling** under sektionen **Hvis ja** på kortet **Betingelse 3**.
    
Nu skal du definere, hvad der skal ske, hvis søgebetingelsen (mailen blev sendt af din chef) er sand:

1. Søg efter **meddelelse**, og vælg derefter handlingen **Send mig en mobilmeddelelse**:
    
     ![søge efter meddelelseshandling](./media/apply-to-each/foreach-10.png)
1. På kortet **Send mig en mobilmeddelelse 2** skal du angive oplysningerne for den pushmeddelelse, der skal sendes, hvis mailen er fra din chef, og derefter vælge **Tilføj en handling**:
    
     ![konfigurere meddelelseskortet](./media/apply-to-each/foreach-boss-notification.png)
1. Tilføj handlingen **Markér som læst eller ulæst (V2)**.
1. Føj tokenet **Meddelelses-id** til kortet **Markér som læst eller ulæst (V2)**. Du skal muligvis vælge **Se mere** for at finde tokenet **Meddelelses-id**. **Meddelelses-id** er id'et for den meddelelse, der markeres som læst.
1. Vælg **Læst** på listen **Markér som** på kortet **Markér som læst eller ulæst (V2)**.
    
     ![konfigurere handlingen Markér som læst](./media/apply-to-each/foreach-mark-as-read2.png)
1. Vælg **Gem** for at gemme dit flow.

## <a name="run-the-flow"></a>Køre flowet
1. Send dig selv en mail med høj prioritet, der inkluderer **møde nu** i emnet (eller få nogen i organisationen til at sende dig sådan en mail).
1. Bekræft, at mailen ligger i indbakken og er ulæst.
1. Log på Power Automate, og vælg **Mine flows**.
   
    Viser en liste over dine flows. 
    
1. Vælg det flow, du har oprettet, og derefter **Kør**.

   ![køre nu](./media/apply-to-each/run-flow.png)

1. Vælg **siden Flowkørsler**, og vælg derefter den kørsel af flow, hvor du er interesseret i at få vist resultaterne.
   
    ![kørselsresultater](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Få vist kørselsresultaterne
Nu, hvor du har kørt flowet korrekt, skulle du modtage pushmeddelelsen på din mobilenhed.
   
> [!NOTE]
> Hvis du ikke modtager pushmeddelelsen, skal du kontrollere, at mobilenheden har en aktiv dataforbindelse.
 

