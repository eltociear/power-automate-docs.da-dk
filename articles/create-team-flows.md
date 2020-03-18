---
title: Få mere at vide om, hvordan du føjer andre ejere til et flow og opretter teamflows | Microsoft Docs
description: Power Automate gør det nemt at automatisere gentagne opgaver. Du kan tilføje brugere eller grupper som ejere og samarbejde med dem om at designe og administrere flows.
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
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 697f41960a62c7da2eee9bc34bb174d39ed2c44b
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195054"
---
# <a name="create-team-flows"></a>Opret teamflows

Opret et teamflow ved at tilføje andre i organisationen som ejere. Alle ejere af et teamflow kan udføre følgende handlinger:

* Få vist historik for flowet (dvs. hver kørsel).
* Administrer egenskaber for flowet (start eller stop f.eks. flowet, tilføj ejere, eller opdater legitimationsoplysningerne for en forbindelse).
* Rediger definitionen af flowet (tilføj eller fjern f.eks. en handling eller betingelse).
* Tilføj og fjern andre medejere (men ikke opretteren af flowet).
* Slet flowet.

Hvis du er opretter eller ejer af et teamflow, vises det under fanen **Teamflow** i [Power Automate](https://flow.microsoft.com).

![fanen Teamflows](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Delte forbindelser kan **kun** bruges i det flow, hvor de blev oprettet.
> 
> 

Ejere kan bruge tjenester i et flow, men de kan ikke ændre legitimationsoplysningerne for en forbindelse, der er oprettet af en anden ejer.

## <a name="prerequisites"></a>Forudsætninger
Hvis du vil oprette et teamflow, skal du have en [betalt Power Automate-plan](https://flow.microsoft.com/pricing/). Du skal desuden være opretter eller ejer for at tilføje eller fjerne ejere fra et teamflow.

## <a name="create-a-team-flow"></a>Opret et teamflow
Følg disse trin for at oprette et teamflow eller føje flere ejere til et teamflow.

1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter **Mine flow**.
2. Markér personikonet for det flow, du vil ændre:
   
    ![teamikon](./media/create-team-flows/addowner1.png)
3. Angiv navn, mailadresse eller gruppenavn på den person eller gruppe, du vil tilføje som ejer:
   
    ![søg efter brugeren](./media/create-team-flows/addowner2.png)
4. Vælg den bruger, du vil gøre til ejer, på den viste liste:
   
    ![vælg brugeren](./media/create-team-flows/addowner3.png)
   
     Den valgte bruger eller gruppe bliver ejer af flowet:
   
    ![ny ejer](./media/create-team-flows/addowner4.png)
   
     Tillykke &mdash; dit teamflow er blevet oprettet!

## <a name="add-a-list-as-a-co-owner"></a>Tilføj en liste som medejer

Du kan tilføje SharePoint-lister som medejere til et flow, så alle, der har redigeringstilladelse til listen automatisk får redigeringstilladelse til flowet. Når flowet er delt, kan du blot distribuere et link til det.

> [!TIP]
> Brug en liste, når flowet er forbundet med SharePoint, og brug en gruppe i andre tilfælde.
>

## <a name="remove-an-owner"></a>Fjern en ejer

> [!IMPORTANT]
> Når du fjerner en ejer, hvis legitimationsoplysninger bruges til at få adgang til Power Automate-tjenester, skal du opdatere legitimationsoplysningerne for disse forbindelser, så flowet fortsat kører korrekt.
> 
> 

1. Markér personikonet for det flow, du vil ændre:
   
    ![vælg ikonet for personer](./media/create-team-flows/removeowner1.png)
2. Markér ikonet **Slet** for den ejer, du vil fjerne:
   
    ![vælg Slet](./media/create-team-flows/removeowner2.png)
3. I bekræftelsesdialogboksen skal du markere **Fjern denne ejer**:
   
    ![bekræft fjernelse](./media/create-team-flows/removeowner3.png)
4. Tillykke &mdash; den bruger eller gruppe, du har fjernet, er ikke længere angivet som ejer af flowet:
   
    ![brugeren er fjernet](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Opdater ejeren af forbindelsen

Du skal muligvis ændre ejeren af en forbindelse i et flow, hvis du fjerner den eksisterende ejer. Følg disse trin for at skifte ejeren af et flow:

1. Vælg **Data** i venstre sidepanel.
1. Vælg **Forbindelser**.
1. Søg efter den forbindelse, du vil opdatere, og vælg den derefter.
1. Vælg **...** (flere kommandoer) for den forbindelse, du har valgt, og vælg derefter **Skift konto**.
1. Følg trinnene for at bruge en anden konto til forbindelsen.

## <a name="embedded-and-other-connections"></a>Integrerede forbindelser og andre forbindelser

Forbindelser, der bruges i et flow, kan deles i to kategorier:

* **Integrerede** &mdash; Disse forbindelser bruges i flowet.
* **Andre** &mdash; Disse forbindelser er defineret for et flow, men anvendes ikke i det.

Hvis du er holdt op med at bruge en forbindelse i et flow, vil den blive vist på listen over **Andre** forbindelser, hvor den forbliver, indtil en ejer inkluderer den i flowet igen.

Følg trinnene for at [opdatere en forbindelsesejer](./create-team-flows.md#update-connection-owner) og foretage ændringer af integrerede forbindelser.

Listen over forbindelser vises under listen over ejere i egenskaberne for et flow:

![integrerede forbindelser](./media/create-team-flows/embeddedconnections.png)

