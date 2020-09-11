---
title: Få mere at vide om, hvordan du deler et flow med andre brugere | Microsoft Docs
description: Power Automate gør det nemt at automatisere gentagne opgaver. Du kan tilføje brugere eller grupper som ejere og arbejde sammen med dem om at designe og administrere flows.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/05/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5b4d97d47b7cd11c4dc42bcdb8b3861ee3c49398
ms.sourcegitcommit: 5c82214daf6aa602732b381c5f411c6a97ac52e9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/19/2020
ms.locfileid: "3705933"
---
# <a name="share-a-flow"></a>Dele et flow 

Del et flow med andre i organisationen, så de kan drage fordel af de automatiseringer, du har oprettet. Der er tre primære måder, du kan dele et flow på i Power Automate:

1. Føj en ejer til et flow.
2. Del et flow med rettigheder udelukkende til kørsel.
3. Del en kopi af et flow.

## <a name="prerequisites"></a>Forudsætninger

- Du skal have en [betalt Power Automate-licens](https://flow.microsoft.com/pricing/) for at dele et flow. 
- Du skal være opretter eller ejer for at tilføje eller fjerne ejere fra et flow.

## <a name="add-an-owner-to-a-flow"></a>Føje en ejer til et flow

Tilføjelse af en ejer til et flow er den mest almindelige måde at dele et flow på. Alle ejere af et flow kan udføre følgende handlinger:

* Få vist kørselsoversigten.
* Administrere egenskaber for flowet (start eller stop f.eks. flowet, tilføje ejere, eller opdatere legitimationsoplysningerne for en forbindelse).
* Redigere definitionen af flowet (f.eks. tilføje eller fjerne en handling eller betingelse).
* Tilføj eller fjern andre medejere (men ikke opretteren af flowet).
* Slette flowet.

Hvis du er opretter eller ejer af et flow, kan du se det angivet på fanen **Gruppeflow** i [Power Automate.](https://flow.microsoft.com)

![fanen gruppeflow](./media/create-team-flows/addowner5.png)

>[!NOTE]
>Delte forbindelser kan **kun** bruges i det flow, hvor de er oprettet.

Ejere kan bruge tjenester i et flow, men de kan ikke ændre legitimationsoplysningerne for en forbindelse, der er oprettet af en anden ejer.


### <a name="steps-to-add-an-owner-to-a-flow"></a>Trin til at føje en ejer til et flow

Udfør disse trin for at føje flere ejere til et flow:

1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter **Mine flows**.
1. Vælg **...** (flere kommandoer), og vælg derefter **Del** for det flow, du vil dele:
   
    ![teamikon](./media/create-team-flows/addowner1.png)

   >[!NOTE]
   >Du kan også dele et flow ved hjælp af indstillingen Del på siden med flowoplysninger. 

1. Angiv navn, mailadresse eller gruppenavn for den person eller gruppe, du vil tilføje som ejer:
   
    ![søge efter brugeren](./media/create-team-flows/addowner2.png)
1. Den valgte bruger eller gruppe bliver ejer af flowet:
     
    ![ny ejer](./media/create-team-flows/addowner4.png)
   
     Tillykke, dit gruppeflow er oprettet!

## <a name="remove-an-owner"></a>Fjerne en ejer

> [!IMPORTANT]
> Når du fjerner en ejer, hvis legitimationsoplysninger bruges til at få adgang til Power Automate-tjenester, skal du opdatere legitimationsoplysningerne for disse forbindelser, så flowet fortsat kører korrekt.

1. På siden med flowoplysninger skal du vælge linket til redigering i ejersektionen ![Redigere ejere](./media/create-team-flows/editowners.png)

   >[!NOTE]
   >Du kan også redigere ejerne af flow ved hjælp af knappen Del på siden med flowoplysninger, der blev nævnt tidligere.

1. Markér ikonet **Slet** for den ejer, du vil fjerne:
   
    ![vælge slet](./media/create-team-flows/removeowner2.png)
1. I bekræftelsesdialogboksen skal du markere **Fjern denne ejer**:
   
    ![bekræfte fjernelse](./media/create-team-flows/removeowner3.png)
1. Tillykke – den bruger eller gruppe, du har fjernet, er ikke længere angivet som ejer af flowet.


### <a name="update-connections"></a>Opdatere forbindelser

Det kan være nødvendigt at ændre ejeren af en forbindelse i et flow, hvis du fjerner den eksisterende ejer, eller hvis du vil bruge en anden konto til at logge på en handling/udløser. Benyt følgende trin for at redigere forbindelserne for en udløser eller handling i forbindelse med et delt flow:

1. Navigere til det flow, du vil ændre
2. Klik på Rediger for at redigere flowet ![Redigere flow](./media/create-team-flows/Edit-flow-details.png)
3. Klik på overløbsmenuen for det trin, du vil redigere forbindelsen for den udløser eller den handling, du vil redigere.
4. Hvis du allerede har en forbindelse, skal du blot vælge denne. Ellers skal du blot klikke på "Tilføj ny forbindelse" for at oprette en ny forbindelse ![Tilføje en ny forbindelse](./media/create-team-flows/edit-connection.png)
5. Klik på Log på for at oprette din nye forbindelse, og du er klar!
![Log på](./media/create-team-flows/sign-in.png)

### <a name="embedded-and-other-connections"></a>Integrerede og andre forbindelser

Forbindelser, der bruges i et flow, kan opdeles i to kategorier:

* **Integrerede** – Disse forbindelser bruges i flowet.
* **Andre** – Disse forbindelser er defineret for et flow, men anvendes ikke i det.

Hvis du er holdt op med at bruge en forbindelse i et flow, vil den blive vist på listen over **Andre** forbindelser, hvor den forbliver, indtil en ejer inkluderer den i flowet igen.

Følg trinnene for at [opdatere en forbindelse](./create-team-flows.md#update-connections) og foretage ændringer af integrerede forbindelser.

Listen over forbindelser vises under listen over ejere i egenskaberne for et flow:

![integrerede forbindelser](./media/create-team-flows/embeddedconnections.png)

## <a name="add-a-list-as-a-co-owner"></a>Tilføje en liste som medejer

Du kan tilføje SharePoint-lister som medejere til et flow, så alle, der har redigeringstilladelse til listen, automatisk får redigeringstilladelse til flowet. Når flowet er delt, kan du blot distribuere et link til det.

> [!TIP]
> Brug en liste, når flowet er forbundet med SharePoint, og brug en gruppe i andre tilfælde.
>

## <a name="share-a-flow-with-run-only-permissions"></a>Dele et flow med rettigheder udelukkende til kørsel

Øjeblikkelige flow (dvs. de flow, der bruger en manuel udløser, f.eks. en knap, for et valgt element osv.) kan deles blot ved hjælp af tilladelser udelukkende til kørsel. Alle brugere, der tilføjes som bruger med tilladelse udelukkende til kørsel, har ikke adgang til at redigere eller ændre flowet på nogen måde. De får kun tilladelser til at udløse flowet. 

### <a name="add-a-run-only-user"></a>Tilføj en bruger med tilladelse udelukkende til kørsel

1. På siden med flowoplysninger skal du vælge linket "Rediger" ud for sektionen for brugere med tilladelse udelukkende til kørsel. 
![dele udelukkende til kørsel](./media/create-team-flows/run-only-share.png)
2. I pop op-vinduet for administration af tilladelser udelukkende til kørsel skal du angive de brugere og grupper, du vil give adgang med tilladelse udelukkende til kørsel ![Tilføje brugere udelukkende med tilladelse til kørsel](./media/create-team-flows/run-only-share2.png)
3. Som ejer kan du vælge, om brugere med tilladelse udelukkende til kørsel, skal angive deres egne forbindelser, når de deler flowet, eller bruge en forbindelse, der allerede er defineret i flowet ![Administrere forbindelser](./media/create-team-flows/manage-run-only-connections.png)
4. Tillykke, brugeren eller gruppen har nu adgang til at køre flowet.

### <a name="remove-a-run-only-user"></a>Fjerne en bruger med tilladelse udelukkende til kørsel

1. På siden med flowoplysninger skal du vælge linket "Rediger" ud for sektionen for brugere med tilladelse udelukkende til kørsel. 
![dele udelukkende til kørsel](./media/create-team-flows/run-only-share.png)
2. I pop op-vinduet for administration af tilladelser udelukkende til kørsel skal du trykke på sletteikonet ud for den bruger, hvorfra du vil fjerne adgangen med tilladelse udelukkende til kørsel, og klikke på gem nederst på siden ![Fjerne en bruger med tilladelse udelukkende til kørsel](./media/create-team-flows/remove-run-only-user.png)
3. Tillykke, brugeren eller gruppen har ikke længere adgang til at køre dette flow.

## <a name="share-a-copy-of-a-flow"></a>Dele en kopi af et flow

Del en kopi giver dig mulighed for at dele definitionen af et flow med en anden bruger som en skabelon. Det giver dig en god måde til at dele den generelle struktur af et flow uden at dele nogen forbindelser, samtidig med at modtageren får mulighed for at ændre deres flow uafhængigt af dit flow, så de kan tilpasse det efter deres behov.

> [!NOTE]
> Del en kopi opretter en uafhængig forekomst af flowet for modtageren. Det er ikke muligt at revoke adgangen til flowet, når først det er delt.

### <a name="send-a-copy-of-a-flow"></a>Sende en kopi af et flow

1. På siden med flowoplysninger skal du vælge muligheden "Send en kopi" på øverste kommandolinje ![Send en kopi](./media/create-team-flows/send-a-copy.png)

   >[!NOTE]
   >Du kan også vælge Send en kopi fra overløbsmenuen for flow

   ![Sende en anden kopi](./media/create-team-flows/send-a-copy2.png)

1. I pop op-vinduet kan du redigere navnet på og beskrivelsen af det flow, du vil dele, og angive de brugere, du vil dele flowet med.
![Oplysninger om at sende kopi](./media/create-team-flows/send-a-copy3.png)
1. Modtageren modtager en mail, der angiver, at du har delt en flowskabelon, og giver pågældende mulighed for at oprette deres egen forekomst af det pågældende flow.

   ![Modtage en kopi](./media/create-team-flows/send-a-copy5.png)
   
   >[!NOTE]
   >Som modtager kan du også få adgang til flowet fra sektionem Delt med mig under skabeloner.

   ![Delt med mig](./media/create-team-flows/send-a-copy6.png)

## <a name="faq"></a>OFTE STILLEDE SPØRGSMÅL

### <a name="what-happens-if-the-user-who-created-a-shared-flow-leaves-the-organization"></a>Hvad sker der, hvis den bruger, der oprettede et delt flow, forlader organisationen?
Så længe det delte flow stadig har en aktiv ejer, vil flowet fortsat køre. 

>[!NOTE]
>Hvis flowet bruger nogen aktive eller integrerede forbindelser, der tilhører den bruger, der har forladt organisationen, kan de specifikke handlinger mislykkes. Du kan løse dette ved at følge de trin, der er nævnt i sektionen [opdatere en forbindelse](./create-team-flows.md#update-connections), for at ændre forbindelsen for en enhver udløser eller handling.

