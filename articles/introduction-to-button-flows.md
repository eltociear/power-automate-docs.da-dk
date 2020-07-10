---
title: Få mere at vide om, hvordan du automatiserer og udfører gentagne opgaver vha. øjeblikkeligt flow | Microsoft Docs
description: Introduktion til øjeblikkeligt flow.
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
ms.date: 03/17/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b16e07cf5d6f4cc5a711646b30b7b0780916d281
ms.sourcegitcommit: a51ebdce86c0c2399afa4ba36591fb3230eb82d9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527311"
---
# <a name="introducing-instant-flows"></a>Introduktion til øjeblikkeligt flow

## <a name="what-are-instant-flows"></a>Hvad er øjeblikkeligt flow?
Der er mange gentagne opgaver, som vi ønsker, vi kan køre med blot et enkelt tryk på en knap. Du har f.eks. brug for hurtigt at sende en mail til teamet for at minde dem om at deltage i den daglige teamsynkronisering, eller du vil starte et nyt Visual Studio Online-build af din kodebase, når du har fået besked om, at der ikke er planlagt flere indtjekninger i løbet af dagen. Med øjeblikkeligt flow kan du udføre disse og mange andre typer opgaver ved at trykke på en knap på din mobilenhed.

**Bemærk!** Du kan oprette øjeblikkelige flow enten fra din mobilenhed eller i Power Automate.  
  ![Oversigtsbillede](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Hvorfor oprette knapper?
Du kan oprette knapper for at gøre det nemt at køre gentagne opgaver fra din mobilenhed uanset tid og sted. Når du kører knapper, sparer du tid, og da de udfører automatiske opgaver, opstår der færre fejl, end hvis du skulle udføre opgaverne manuelt hver gang.  

## <a name="create-a-button"></a>Opret en knap
### <a name="prerequisites"></a>Forudsætninger
* Adgang til [Power Automate](https://flow.microsoft.com).
* En konto med tilladelser til at bruge forbindelser, når du opretter din knap. Du skal f.eks. have en Dropbox-konto, hvis du vil oprette en knap, der skal have adgang til Dropbox.

### <a name="from-the-portal"></a>Fra portalen
I denne vejledning opretter vi en knap, der starter et Visual Studio Online (VSO)-build og sender meddelelser for at give dig besked om, når buildet startes:

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Opret** i den venstre side af skærmen.
1. Vælg **Øjeblikkeligt flow**.
1. Giv dit flow et navn i **Flownavn** > **Udløs et flow manuelt** > **Opret**. 
 
2. Vælg skabelonen **Trigger a new build in VSO** (Udløs et nyt build i VSO) på listen over skabeloner.  
   ![Billede, der viser skabeloner](./media/introduction-to-button-flows/create-button-2.png)  
3. Vælg knappen **Brug denne skabelon** på siden **Trigger a new build in VSO** (Udløs et nyt build i VSO).   
   ![Billede, der viser den skabelon, som skal bruges](./media/introduction-to-button-flows/create-button-3.png)  
4. Hvis du ikke er logget på, bliver du bedt om at gøre det på dette tidspunkt:  
   ![Billede, der viser logonindstillinger](./media/introduction-to-button-flows/create-button-4.png)  
5. Når du har logget på Flow, bliver du bedt om at logge på de forbindelser, der anvendes i den valgte skabelon. I dette eksempel har vi på trin 2 valgt skabelonen **Trigger a new build in VSO** (Udløs et nyt build i VSO), så vi skal logge på VSO (og de øvrige forbindelser, du arbejder med), hvis du ikke allerede er logget ind:  
   ![Billede, der viser logonknappen](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Vælg knappen **Acceptér**, hvis du vil give Power Automate adgang til din VSO-konto.  
   ![Billede, der viser muligheder for at give adgang til din Visual Studio-konto](./media/introduction-to-button-flows/create-button-5.png)   
   **Bemærk!** Du skal godkende hver forbindelse på samme måde. Designeren skal se ud som dette, når du er klar til at gå videre til næste trin. Vælg knappen **Fortsæt** for at gå videre:  
   ![Knappen Fortsæt](./media/introduction-to-button-flows/create-button-6.png)   
7. Du er nu klar til at konfigurere egenskaberne for det build, du vil starte:    
   ![Skærmbilledet Egenskaber](./media/introduction-to-button-flows/create-button-7.png)  
8. Vælg eller skriv **Kontonavn**, **Projektnavn**, **Builddefinitions-id**, **Kildeforgrening** og eventuelt **Parametre** på kortet **Sæt et nyt build i kø**:    
   ![Skærmbilledet Nyt build](./media/introduction-to-button-flows/create-button-8.png)  
9. Du skal nu konfigurere egenskaberne for pushmeddelelsen på kortet **Send en pushmeddelelse**. Som standard konfigureres denne pushmeddelelse til at sende et HTML-link til en webside, der viser statussen for buildet:  
   ![Skærmbilledet Pushmeddelelser](./media/introduction-to-button-flows/create-button-9.png)  
10. Vælg knappen **Opret flow** for at gemme dit øjeblikkelige flow: ![Opret flow-knap](./media/introduction-to-button-flows/create-button-10.png)  
11. Efter et øjeblik skulle du få vist denne bekræftelse på dit flow:  
    ![Udført-meddelelse](./media/introduction-to-button-flows/create-button-11.png)  

Tillykke, du har oprettet et øjeblikkeligt flow! Nu kan du køre dette øjeblikkelige flow under fanen **Knapper** i appen Flow, når du vil. Du skal blot trykke på "knappen" for at køre flowet. Power Automate-mobilappen er tilgængelig for [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Fra din mobilenhed

>[!NOTE]
>I denne vejledning vises der skærmbilleder fra en Android-enhed, men skærmbilleder og fremgangsmåderne er det samme på en iOS-enhed.

I appen:

1. Vælg fanen **Gennemse**, og rul til kategorien **Knap**.  
   ![Skærmbilledet Landingsside](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Vælg linket **Se alle**. Det viser de knapskabeloner, der er klar til brug.     
   ![Linket Se alle](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Vælg skabelonen **Send an email to remind your team to join a meeting** (Send en mail med en mødepåmindelse til dit team)    
   ![Billede af Send en mail som påmindelse til teamet om at deltage i et møde](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Vælg linket **BRUG DENNE SKABELON** nederst på siden.    
   ![Billede af BRUG DENNE SKABELON](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Du skal logge på alle de tjenester, som skabelonen bruger:    
   ![Billede af Log på tjenester eller opdater tjenester](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Vælg linket **Næste**, efter at du har logget på alle tjenesterne.      
   ![Næste link](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Vælg linket **Opret**. Her kan du også gennemse flowet, og du kan ændre ting som eksempelvis at tilpasse mailen.        
   ![Opret link](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Efter et kort øjeblik oprettes det øjeblikkelige flow. Vælg **VIS MIT FLOW**:   
   ![Billede af VIS MIT FLOW](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Vis alle dine flows på fanen **Mine flows**  
   ![Billede af Vis alle flow](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Tillykke, du har oprettet et øjeblikkeligt flow! Nu kan du køre dette øjeblikkelige flow under fanen **Knapper** i appen Flow, når du vil. Du skal blot trykke på "knappen" for at køre flowet. Flow-appen fås i øjeblikket til Android- og iOS-mobilenheder.  

![Billede af Nyt øjeblikkeligt flow](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-an-instant-flow"></a>Udløs et øjeblikkeligt flow
Nu, hvor du har oprettet et øjeblikkeligt flow, skal du køre det. Da du kun kan køre øjeblikkelige flow fra Flow-appen, skal du have installeret Flow på din Android- eller iOS-mobilenhed.  

1. Start appen Flow, tryk på fanen **Knapper** nederst på siden, og tryk på den *knap*, der repræsenterer det øjeblikkelige flow, du vil udløse:  
   ![Udløs flowet](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Se statussen, mens dit flow køres:  
   ![Billede af det kørende flow](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Til sidst opdateres siden med en meddelelse om, at det øjeblikkelige flow er fuldført:  
   ![Billede af Fuldført flow](./media/introduction-to-button-flows/trigger-button-3.png)   

Så nemt er det at køre et flow. 

Du skulle nu modtage en pushmeddelelse om, at mailen er blevet sendt.  

## <a name="monitor-your-instant-flow-runs"></a>Overvåg kørslen af dine øjeblikkelige flow
Du kan overvåge dine øjeblikkelige flow via fanen **Aktivitet** i appen Flow:   
![Billede af fanen Aktivitet](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

>[!TIP ]Tryk på en aktivitet for at få vist resultaterne af og detaljerne om kørslen.  

![Billede af aktivitetsdetaljer](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-instant-flows"></a>Administrer øjeblikkeligt flow
Du har fuld kontrol over dine øjeblikkelige flow, så du kan aktivere eller deaktivere, redigere eller slette en knap, når du vil. Vælg **Mine flows** i mobilappen eller på flowportalen for at komme i gang med at administrere dine flows.    

Under fanen **Mine flows** i appen Flow:

1. Vælg det flow, du vil administrere:    
   ![Billede af alle flow](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Du kan trykke på en af disse indstillinger, afhængigt af hvad du gerne vil opnå:    
   ![Indstillinger for administration af flow](./media/introduction-to-button-flows/manage-flow-1.png)  

   Tryk på **Slet flow** for at slette et flow.  

      >[!WARNING]
      >Hele kørselsoversigten slettes, når du sletter et flow.

      ![Advarselsbillede af Slet flow](./media/introduction-to-button-flows/manage-flow-2.png)   

   Tryk på **Opdater** for at gemme dine ændringer, når du er færdig med at redigere et øjeblikkeligt flow:   
   ![Billede af Opdater flow](./media/introduction-to-button-flows/manage-flow-3.png)   

   Tryk på **Kørselsoversigt** for at se resultaterne af alle kørsler for et øjeblikkeligt flow:    
   ![Vis historik over kørsel](./media/introduction-to-button-flows/manage-flow-4.png)  

   Hvis du deaktiverer et flow, vil det ikke længere være tilgængeligt under fanen **Knapper**:    
   ![Deaktiverede flows er ikke under fanen Knapper](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Næste trin
* [Del øjeblikkeligt flow](share-buttons.md).
* Lær at bruge [tokens, der udløser knap](introduction-to-button-trigger-tokens.md), til at sende data i realtid, når dine øjeblikkelige flows køres.
* Installer Power Automate-mobilappen for [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).

