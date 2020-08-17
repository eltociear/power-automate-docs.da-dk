---
title: Lære, hvordan du føjer andre ejere til et flow og opretter teamflows | Microsoft Docs
description: Power Automate gør det nemt at automatisere gentagne opgaver. Du kan tilføje brugere eller grupper som ejere og arbejde sammen med dem om at designe og administrere flows.
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
ms.date: 07/05/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7ddcc0303fb2a1a8d3c5a89adb7a7b8d77c3d08b
ms.sourcegitcommit: a1d509e61196054c8272ed96aed9477485d3c71e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/08/2020
ms.locfileid: "3542741"
---
# <a name="share-a-flow"></a>Dele et flow 

Del et flow ved at tilføje andre i organisationen som ejere. Alle ejere af et teamflow kan udføre følgende handlinger:

* Få vist historik for flowet (hver kørsel).
* Administrere egenskaber for flowet (start eller stop f.eks. flowet, tilføje ejere, eller opdatere legitimationsoplysningerne for en forbindelse).
* Redigere definitionen af flowet (f.eks. tilføje eller fjerne en handling eller betingelse).
* Tilføje og fjerne andre medejere (men ikke opretteren af flowet).
* Slette flowet.

Hvis du er opretter eller ejer af et teamflow, bliver det anført på fanen **Teamflows** på [Power Automate](https://flow.microsoft.com).

![fanen teamflows](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Delte forbindelser kan **kun** bruges i det flow, hvor de er oprettet.
> 
> 

Ejere kan bruge tjenester i et flow, men de kan ikke ændre legitimationsoplysningerne for en forbindelse, der er oprettet af en anden ejer.

## <a name="prerequisites"></a>Forudsætninger
Du skal have en [betalt Power Automate-plan](https://flow.microsoft.com/pricing/) for at oprette et teamflow. Du skal desuden være opretter eller ejer for at tilføje eller fjerne ejere fra et teamflow.

## <a name="share-a-flow"></a>Dele et flow
Følg disse trin for at oprette et teamflow eller føje flere ejere til et teamflow.

1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter **Mine flows**.
2. Vælg **...** (flere kommandoer), og vælg derefter **Del** for det flow, du vil dele:
   
    ![teamikon](./media/create-team-flows/addowner1.png)
3. Angiv navn, mailadresse eller gruppenavn for den person eller gruppe, du vil tilføje som ejer:
   
    ![søge efter brugeren](./media/create-team-flows/addowner2.png)
4. Den valgte bruger eller gruppe bliver ejer af flowet:
     
    ![ny ejer](./media/create-team-flows/addowner4.png)
   
     Tillykke, dit teamflow er oprettet!

## <a name="add-a-list-as-a-co-owner"></a>Tilføje en liste som medejer

Du kan tilføje SharePoint-lister som medejere til et flow, så alle, der har redigeringstilladelse til listen, automatisk får redigeringstilladelse til flowet. Når flowet er delt, kan du blot distribuere et link til det.

> [!TIP]
> Brug en liste, når flowet er forbundet med SharePoint, og brug en gruppe i andre tilfælde.
>

## <a name="remove-an-owner"></a>Fjerne en ejer

> [!IMPORTANT]
> Når du fjerner en ejer, hvis legitimationsoplysninger bruges til at få adgang til Power Automate-tjenester, skal du opdatere legitimationsoplysningerne for disse forbindelser, så flowet fortsat kører korrekt.
> 
> 

1. Vælg **...** (flere kommandoer), og vælg derefter **Del** for det flow, du vil dele:
   
    ![vælge ikonet for personer](./media/create-team-flows/addowner1.png)
2. Markér ikonet **Slet** for den ejer, du vil fjerne:
   
    ![vælge slet](./media/create-team-flows/removeowner2.png)
3. I bekræftelsesdialogboksen skal du markere **Fjern denne ejer**:
   
    ![bekræfte fjernelse](./media/create-team-flows/removeowner3.png)
4. Tillykke – den bruger eller gruppe, du har fjernet, er ikke længere angivet som ejer af flowet.


## <a name="update-connection-owner"></a>Opdatere ejer af forbindelse

Du skal muligvis ændre ejeren af en forbindelse i et flow, hvis du fjerner den eksisterende ejer. Følg denne fremgangsmåde for at ændre ejeren af et flow:

1. Vælg **Data** i venstre sidepanel.
1. Vælg **Forbindelser**.
1. Søg efter den forbindelse, du vil opdatere, og vælg den derefter.
1. Vælg **...** (flere kommandoer) for den forbindelse, du har valgt, og vælg derefter **Skift konto**.
1. Følg fremgangsmåden for at bruge en anden konto til forbindelsen.

## <a name="embedded-and-other-connections"></a>Integrerede og andre forbindelser

Forbindelser, der bruges i et flow, kan opdeles i to kategorier:

* **Integrerede** – Disse forbindelser bruges i flowet.
* **Andre** – Disse forbindelser er defineret for et flow, men anvendes ikke i det.

Hvis du er holdt op med at bruge en forbindelse i et flow, vil den blive vist på listen over **Andre** forbindelser, hvor den forbliver, indtil en ejer inkluderer den i flowet igen.

Følg fremgangsmåden for at [opdatere en forbindelsesejer](./create-team-flows.md#update-connection-owner) og foretage ændringer af integrerede forbindelser.

Listen over forbindelser vises under listen over ejere i egenskaberne for et flow:

![integrerede forbindelser](./media/create-team-flows/embeddedconnections.png)

