---
title: Lær, hvordan du automatiserer og udfører gentagne opgaver vha. knapflows | Microsoft Docs
description: Introduktion til knapflows.
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
ms.date: 01/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 136bb90c47a1aeea2f11ef45e35a4957506ad488
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74363907"
---
# <a name="introducing-button-flows"></a>Introduktion til knapflows
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>Hvad er knapflows?
Vi har vist alle nogle rutineopgaver, som vi ville ønske, at vi kunne køre med blot et klik på en knap. Det kan f.eks. være, at du skal sende en hurtig mail til dit team for at minde dem om at deltage i dagens teammøde, eller du vil starte et nyt Visual Studio Online-build af koden, efter at du har fået besked om, at der ikke er planlagt flere opdateringer resten af dagen. Med knapflows kan du udføre disse og mange andre typer opgaver ved at trykke på en knap på din mobilenhed.

**Bemærk!** Du kan oprette knapflows enten fra din mobilenhed eller fra Flow-portalen.  
  ![Oversigtsbillede](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Hvorfor oprette knapper?
Du kan oprette knapper for at gøre det nemt at køre gentagne opgaver fra din mobilenhed uanset tid og sted. Når du bruger knapflows, sparer du tid, og da de udfører automatiske opgaver, opstår der færre fejl, end hvis du skulle udføre opgaverne manuelt hver gang.  

## <a name="create-a-button"></a>Opret en knap
### <a name="prerequisites"></a>Forudsætninger
* Adgang til Flow. Hvis du skal have adgang til Flow, skal du kontakte din administrator.
* En konto med tilladelser til at bruge forbindelser, når du opretter din knap. Du skal f.eks. have en Dropbox-konto, hvis du vil oprette en knap, der skal have adgang til Dropbox.

### <a name="from-the-portal"></a>Fra portalen
I denne vejledning opretter vi en knap, der starter et Visual Studio Online (VSO)-build og sender meddelelser for at give dig besked om, når buildet startes:  

1. Vælg rullelisten **Viser**, og vælg kategorien **Knap**. Dette filtrerer listen over skabeloner til dem, der kan bruges i knapflows.  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-1.png)   
2. Vælg skabelonen **Trigger a new build in VSO** (Udløs et nyt build i VSO) på listen over skabeloner.  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-2.png)  
3. Vælg knappen **Brug denne skabelon** på siden **Trigger a new build in VSO**.   
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-3.png)  
4. Hvis du ikke er logget på, bliver du bedt om at gøre det på dette tidspunkt:  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-4.png)  
5. Når du har logget på Flow, bliver du bedt om at logge på de forbindelser, der anvendes i den valgte skabelon. I dette eksempel har vi på trin 2 valgt skabelonen **Trigger a new build in VSO**, så vi skal logge på VSO (og de øvrige forbindelser, du arbejder med), hvis du ikke allerede er logget ind:  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Vælg knappen **Acceptér**, hvis du vil give Flow adgang til din VSO-konto.  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-5.png)   
   **Bemærk!** Du skal godkende hver forbindelse på samme måde. Designeren skal se ud som dette, når du er klar til at gå videre til næste trin. Vælg knappen **Fortsæt** for at gå videre:  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-6.png)   
7. Du er nu klar til at konfigurere egenskaberne for det build, du vil starte:    
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-7.png)  
8. Vælg eller skriv **Kontonavn**, **Projektnavn**, **Builddefinitions-id**, **Kildeforgrening** og eventuelt **Parametre** på kortet **Sæt et nyt build i kø**:    
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-8.png)  
9. Du skal nu konfigurere egenskaberne for pushmeddelelsen på kortet **Send en pushmeddelelse**. Som standard konfigureres denne pushmeddelelse til at sende et HTML-link til en webside, der viser statussen for buildet:  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-9.png)  
10. Vælg knappen **Opret flow** for at gemme dit knapflow: ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-10.png)  
11. Efter et øjeblik skulle du få vist denne bekræftelse på dit flow:  
    ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-11.png)  

Tillykke, du har oprettet et knapflow! Nu kan du køre dette knapflow under fanen **Knapper** i appen Flow, når du vil. Du skal blot trykke på "knappen" for at køre flowet. Mobilappen Power Automate er tilgængelig til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Fra din mobilenhed
**Bemærk!** I denne vejledning vises der skærmbilleder fra en Android-enhed, men skærmbilleder og fremgangsmåderne er det samme på en iOS-enhed.

I appen Flow:

1. Vælg fanen **Gennemse**, og rul til kategorien **Knap**.  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Vælg linket **Se alle**. Dette viser de knapskabeloner, der er klar til brug.     
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Vælg skabelonen **Send an email to remind your team to join a meeting** (Send en mail med en mødepåmindelse til dit team)    
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Vælg linket **BRUG DENNE SKABELON** nederst på siden.    
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Du skal logge på alle de tjenester, som skabelonen bruger:    
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Vælg linket **Næste**, efter at du har logget på alle tjenesterne.      
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Vælg linket **Opret**. Her kan du også gennemse flowet, og du kan ændre ting som eksempelvis at tilpasse mailen.        
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Efter et kort øjeblik oprettes knapflowet. Vælg **Vis mit flow**:   
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Se alle dine flows under fanen **Mine flows**.  
   ![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Tillykke, du har oprettet et knapflow! Nu kan du køre dette knapflow under fanen **Knapper** i appen Flow, når du vil. Du skal blot trykke på "knappen" for at køre flowet. Appen Flow fås i øjeblikket til Android- og iOS-mobilenheder.  

![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Udløs et knapflow
Nu, hvor du har oprettet et knapflow, skal du køre det. Da du kun kan køre knapflows fra appen Flow, skal du have installeret Flow på din Android- eller iOS-mobilenhed.  

1. Start appen Flow, tryk på fanen **Knapper** nederst på siden, og tryk på den *knap*, der repræsenterer det knapflow, du vil udløse:  
   ![Oversigtsbillede](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Se statussen, mens dit flow køres:  
   ![Oversigtsbillede](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Til sidst opdateres siden med en meddelelse om, at knapflowet er fuldført:  
   ![Oversigtsbillede](./media/introduction-to-button-flows/trigger-button-3.png)   

Så nemt er det at køre et flow. 

Du skulle nu modtage en pushmeddelelse om, at mailen er blevet sendt.  

## <a name="monitor-your-button-flow-runs"></a>Overvåg de knapflow, der køres
Du kan overvåge dine knapflows fra fanen **Aktivitet** i appen Flow:   
![Oversigtsbillede](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Bemærk!** Tryk på en aktivitet for at se resultaterne af og detaljerne om kørslen.  

![Oversigtsbillede](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Administrer knapflows
Du har fuld kontrol over dine knapflows, så du kan aktivere eller deaktivere, redigere eller slette en knap, når du vil. I mobilappen eller på flowportalen skal du vælge **Mine flows** for at komme i gang med at administrere dine flows.    

Under fanen **Mine flows** i appen Flow:

1. Vælg det flow, du vil administrere:    
   ![Oversigtsbillede](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Du kan trykke på en af disse indstillinger, afhængigt af hvad du gerne vil opnå:    
   ![Oversigtsbillede](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Tryk på **Slet flow** for at slette et flow.  

**Bemærk!** Hele kørselsoversigten slettes, når du sletter et flow:   
![Oversigtsbillede](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Tryk på **Opdater** for at gemme dine ændringer, når du er færdig med at redigere et knapflow:   
   ![Oversigtsbillede](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Tryk på **Kørselsoversigt** for at se resultaterne af alle kørsler for et knapflow:    
   ![Oversigtsbillede](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Hvis du deaktiverer et flow, vil det ikke længere være tilgængeligt under fanen **Knapper**:    
   ![Oversigtsbillede](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Næste trin
* [Del knapflows](share-buttons.md).
* Lær at bruge [tokens, der udløser knap](introduction-to-button-trigger-tokens.md), til at sende data i realtid, når dine knapflows køres
* Installér mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).

