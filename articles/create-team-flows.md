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
ms.date: 08/25/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2f0187c7c2acea8cc825fdebb98b3e412b2e298
ms.sourcegitcommit: 4db6edd51883e28e14a2a7064cf487c167d47649
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/06/2020
ms.locfileid: "3964644"
---
# <a name="share-a-flow"></a>Dele et flow

Del et flow med andre i organisationen, så de kan drage fordel af de automatiseringer, du har oprettet. Der er tre primære måder, du kan dele et flow på i Power Automate:

- Føj en ejer til et flow.
- Del et flow med rettigheder udelukkende til kørsel.
- Del en kopi af et flow.

## <a name="prerequisites"></a>Forudsætninger

- Du skal have en [betalt Power Automate-licens](https://flow.microsoft.com/pricing/) for at dele et flow.
- Du skal være opretter eller ejer for at tilføje eller fjerne ejere fra et flow.

### <a name="about-embedded-and-other-connections"></a>Om integrerede forbindelser og andre forbindelser

Forbindelser, der bruges i et flow, kan opdeles i to kategorier:

- **Integrerede**: Disse forbindelser bruges i flowet.
- **Andre**: Disse forbindelser er defineret for et flow, men anvendes ikke i det.

Hvis du er holdt op med at bruge en forbindelse i et flow, vil den blive vist på listen over **Andre forbindelser**, hvor den forbliver, indtil en ejer inkluderer den i flowet igen. Følg trinnene under [Rediger en forbindelse](#modify-a-connection) senere i denne artikel for at foretage ændringer af integrerede forbindelser.<!--What is the significance of this? Embedded versus other?  DH: Its described in this section-->

Listen over forbindelser vises under listen over ejere i flowets egenskaber som vist i følgende billede.

![Integrerede forbindelser](./media/create-team-flows/embeddedconnections.png "Integrerede forbindelser")

## <a name="add-an-owner-to-a-flow"></a>Føje en ejer til et flow

Tilføjelse af en ejer i et flow er den mest almindelige måde at dele et flow på. Alle ejere af et flow kan udføre følgende handlinger:

- Få vist kørselsoversigten.
- Administrere egenskaber for flowet (start eller stop f.eks. flowet, tilføj ejere, eller opdater legitimationsoplysningerne for en forbindelse).
- Redigere definitionen af flowet (f.eks. tilføje eller fjerne en handling eller betingelse).
- Tilføj eller fjern andre medejere (men ikke opretteren af flowet).
- Slette flowet.

Hvis du er opretter eller ejer af et flow, kan du se det angivet under fanen **Gruppeflow** i Power Automate.

![Fanen Gruppeflow](./media/create-team-flows/addowner5.png "Fanen Gruppeflow")

>[!NOTE]
>Delte forbindelser kan *kun* bruges i det flow, hvor de er oprettet.

Ejere kan bruge tjenester i et flow, men de kan ikke ændre legitimationsoplysningerne for en forbindelse, der er oprettet af en anden ejer.<!--I'm confused by this. In line 42, you say that "any owner of a flow can...update credentials for a connection." It seems that there's a difference between being added as an owner of a flow and owning a connection within a flow - will this be obvious to the reader? -->

<!--markdownlint-disable MD036-->
**Sådan tilføjer du flere ejere i et flow**

1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter fanen **Mine flow**.
1. Vælg det flow, du vil dele, vælg **Flere kommandoer** ![Flere kommandoer](./media/create-team-flows/more-commands.png), og vælg derefter **Del**.
  
    ![Vælg Del fra Flere kommandoer](./media/create-team-flows/addowner1.png "Vælg Del fra Flere kommandoer")

1. Angiv navn, mailadresse eller gruppenavn for den person eller gruppe, du vil tilføje som ejer.

    ![Søge efter en bruger eller gruppe](./media/create-team-flows/addowner2.png "Søge efter en bruger eller gruppe")

    Den valgte bruger eller gruppe bliver ejer af flowet.

    ![Ny ejer](./media/create-team-flows/addowner4.png "Ny ejer")

Tillykke, du har oprettet dit gruppeflow!

## <a name="add-a-list-as-a-co-owner"></a>Tilføje en liste som medejer

Du kan tilføje SharePoint-lister som medejere af et flow, så alle, der har redigeringstilladelse til listen automatisk får redigeringstilladelse til flowet. Når flowet er delt, kan du blot distribuere et link til det. Flere oplysninger: [Træning: Opret og konfigurer en SharePoint-liste](https://support.microsoft.com/office/training-create-and-set-up-a-list-1ddc1f5a-a908-478b-bb6d-608f34b71f94)

> [!TIP]
> Brug en liste, når flowet er forbundet med SharePoint, og brug en gruppe i alle andre tilfælde.

>[!IMPORTANT]
>SharePoint-brugere skal have tilladelsen **Rediger** eller være medlem af gruppen **Medlemmer** eller **Ejere** for at køre flows i SharePoint.

## <a name="remove-an-owner"></a>Fjerne en ejer

> [!IMPORTANT]
> Når du fjerner en ejer, hvis legitimationsoplysninger bruges til at få adgang til Power Automate-tjenester, skal du opdatere legitimationsoplysningerne for disse forbindelser, så flowet fortsat kører korrekt. Flere oplysninger: [Rediger en forbindelse](#modify-a-connection)

1. Vælg **Rediger** i sektionen **Ejere** på siden med flowdetaljer.

   ![Rediger ejere](./media/create-team-flows/editowners.png "Rediger ejere")

1. Vælg **Slet** ![knappen Slet](./media/create-team-flows/delete.png) for den ejer, du vil fjerne.

    ![Slet en ejer](./media/create-team-flows/removeowner2.png "Slet en ejer")

1. Vælg **Fjern** i bekræftelsesdialogboksen.

Tillykke – den bruger eller gruppe, du har fjernet, er ikke længere angivet som ejer af flowet.

## <a name="modify-a-connection"></a>Rediger en forbindelse

Det kan være nødvendigt at ændre ejeren af en forbindelse i et flow, hvis du fjerner den eksisterende ejer, eller hvis du vil bruge en anden konto til at logge på en handling eller udløser.

1. Gå til det flow, du vil ændre.

1. Vælg **Rediger**.

   ![Redigere et flow](./media/create-team-flows/Edit-flow-details.png "Redigere et flow")

1. Vælg **Flere kommandoer** (...) i det trin, hvor du vil redigere forbindelsen.

1. Hvis der allerede findes en forbindelse, skal du vælge den. Hvis ikke, skal du vælge **Tilføj ny forbindelse** for at oprette en ny forbindelse og derefter vælge **Log på** for at oprette den nye forbindelse.

   ![Tilføj en ny forbindelse](./media/create-team-flows/edit-connection.png "Tilføj en ny forbindelse")

## <a name="share-a-flow-with-run-only-permissions"></a>Dele et flow med rettigheder udelukkende til kørsel

Øjeblikkelige flow (som er flow, der bruger en manuel udløser som en knap eller et valgt element) kan deles ved hjælp af tilladelser udelukkende til kørsel. En bruger, der er tilføjet som en bruger, der kun er til kørsel, har ikke adgang til at redigere eller ændre flowet på nogen måde, men har kun tilladelse til at udløse flowet.

**Sådan tilføjer du en kørselsbruger**

1. Vælg **Rediger** i sektionen **Kør kun brugere** på siden med flowdetaljer. 

   ![Rediger sektionen Kør kun brugere](./media/create-team-flows/run-only-share.png "Rediger sektionen Kør kun brugere")

1. I panelet **Administrer run-only-tilladelser** skal du angive de brugere og grupper, du vil give kørselsadgang.

   ![Tilføj kørselsbrugere](./media/create-team-flows/run-only-share2.png "Tilføj kørselsbrugere")

1. Som ejer kan du vælge, om kørselsbrugere skal angive deres egne forbindelser eller bruge en forbindelse, der allerede er defineret i flowet.

   ![Administrer forbindelser](./media/create-team-flows/manage-run-only-connections.png "Administrer forbindelser")

Tillykke, brugeren eller gruppen har nu adgang til at køre flowet.

**Sådan fjerner du en kørselsbruger**

1. Vælg **Rediger** i sektionen **Kør kun brugere** på siden med flowdetaljer. 
1. I panelet **Administrer run-only-tilladelser** skal du vælge **Slet** ![knappen Slet](./media/create-team-flows/delete.png) ud for den bruger, hvis adgang du vil fjerne, og vælg derefter **Gem**.

    ![Fjerne en bruger med tilladelse udelukkende til kørsel](./media/create-team-flows/remove-run-only-user.png "Fjerne en bruger med tilladelse udelukkende til kørsel")

Tillykke, brugeren eller gruppen har ikke længere adgang til at køre dette flow.

## <a name="share-a-copy-of-a-flow"></a>Dele en kopi af et flow

Du kan dele en kopi med en anden bruger, som derefter kan bruge definitionen af et flow som en skabelon. Det giver dig en god måde til at dele den generelle struktur af et flow uden at dele nogen forbindelser, samtidig med at modtagerne kan ændre deres flow uafhængigt af dit flow, så de kan tilpasse det efter behov.

> [!NOTE]
> Deling af en kopi opretter en uafhængig forekomst af flowet for modtageren. Du kan ikke tilbagekalde adgang til flowet, når du deler det.

**Sådan sender du en kopi af et flow**

1. Vælg **Send en kopi** på kommandolinjen på flowdetaljesiden.

   ![Send en kopi fra kommandolinjen](./media/create-team-flows/send-a-copy.png "Send en kopi fra kommandolinjen")

1. I panelet **Send en kopi** kan du redigere navnet på og beskrivelsen af det flow, du vil dele, og angive de brugere, du vil dele det med.

   ![Oplysninger om at sende kopi](./media/create-team-flows/send-a-copy3.png "Oplysninger om at sende kopi")

1. Modtageren får en mail, der angiver, at du har delt en flowskabelon med dem, og det giver den pågældende mulighed for at oprette sin egen forekomst af dette flow.

   ![Modtage en kopi](./media/create-team-flows/send-a-copy5.png "Modtage en kopi")

   >[!NOTE]
   >Som modtager kan du også få adgang til flowet ved at vælge **Skabeloner** i venstre rude og derefter vælge fanen **Delt med mig**.

   ![Delt med mig](./media/create-team-flows/send-a-copy6.png "Delt med mig")

## <a name="faq"></a>OFTE STILLEDE SPØRGSMÅL

### <a name="what-happens-if-the-user-who-created-a-shared-flow-leaves-the-organization"></a>Hvad sker der, hvis den bruger, der oprettede et delt flow, forlader organisationen?

Hvis det delte flow stadig har en aktiv ejer, vil flowet fortsat køre. 

>[!NOTE]
>Hvis flowet bruger nogen aktive eller integrerede forbindelser, der tilhører den bruger, der har forladt organisationen, kan de specifikke handlinger mislykkes. Du kan løse problemet ved at udføre trinnene i [Rediger en forbindelse](#modify-a-connection) tidligere i denne artikel for at opdatere legitimationsoplysningerne.
<!--markdownlint-enable MD036-->
