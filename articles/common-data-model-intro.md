---
title: Common Data Service | Microsoft Docs
description: Opret et flow fra en skabelon, der bruger Common Data Service.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/17/2020
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 25f719a3a8018a084f059125372a229c00f15190
ms.sourcegitcommit: 89fca599830de21709b47087302a030d91e5fe29
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/10/2020
ms.locfileid: "3549746"
---
# <a name="create-a-flow-that-uses-common-data-service"></a>Opret et flow, der bruger Common Data Service

Du kan forbedre driftseffektiviteten med en samlet visning af virksomhedsdata ved at oprette flows, der bruger [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). 


Du kan f. eks. bruge på Common Data Service fra Power Automate til disse metoder:

* Opret et flow for at importere data, eksportere data eller handle i forhold til data (f.eks. at sende en meddelelse), når data ændres. Du kan finde detaljerede trin under procedurerne, der angives senere under dette emne.
* I stedet for at [oprette en godkendelsesløkke via mail](wait-for-approvals.md) skal du oprette et flow, der gemmer godkendelsestilstanden i en enhed, og derefter oprette en brugerdefineret app, hvor brugerne kan godkende eller afvise elementer. Du kan få vist detaljerede trin under [Opret en godkendelsesløkke med Common Data Service](common-data-model-approve.md).

I denne artikel kan du oprette et flow, der sender en e-mailbesked, når et *kvalificeret kundeemne* opretter en ny *salgsmulighed* i Common Data Service. Beskeden indeholder *noter* fra *kundeemnet*.

## <a name="prerequisites"></a>Forudsætninger

* Tilmeld dig [Power Automate](https://flow.microsoft.com) og [Power Apps](https://make.powerapps.com).
  
    Hvis du har problemer, skal du kontrollere, om [Power Automate](sign-up-sign-in.md) og [Power Apps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) understøtter den kontotype, du har, og at organisationen ikke har blokeret for tilmelding.
* Hvis du ikke har brugt Common Data Service før, skal du åbne fanen **Objekter** i [Power Apps](https://web.powerapps.com/#/entities) og derefter vælge **Opret min database**.

## <a name="sign-in-to-your-environment"></a>Log på dit miljø

1. Find [Power Automate](https://flow.microsoft.com), og vælg derefter **Log ind** i øverste højre hjørne.
   
    ![Log på](./media/common-data-model-intro/signin-flow.png)
1. I menuen øverst til højre skal du vælge det miljø, hvor du oprettede databasen i powerapps.com.
   
    >[!IMPORTANT]
    >Hvis du ikke vælger det samme miljø, kan du ikke se objekterne.
   
    ![Vælg miljø](./media/common-data-model-intro/select-environment.png)

## <a name="use-a-template"></a>Brug en skabelon

1. I boksen **Søg efter en skabelon efter app, opgave eller branche** øverst på skærmen skal du angive **common**, og tryk derefter på **Enter**.

   Der vises en liste over skabeloner med ordet "Common" i navnene, herunder de skabeloner, der bruger Common Data Model.
   
    ![Søg efter skabeloner](./media/common-data-model-intro/template-search.png)

1. Vælg den skabelon, der udfører de opgaver, som skal udføres, på listen over skabeloner.
   
    Du kan f. eks. vælge den skabelon, der kopierer noter fra kundeemne til salgsmulighed i Common Data Service, som vist i de efterfølgende trin.
   
    ![Vælg en skabelon​](./media/common-data-model-intro/select-template.png)
   
1. Hvis du ikke allerede har oprettet en forbindelse, skal du vælge **Log på** og derefter angive dine legitimationsoplysninger efter behov.
   
1. Vælg **Fortsæt**.

   Skabelonen og de tilknyttede forbindelser vises nu. I følgende trin kan du tilpasse denne skabelon.

## <a name="customize-your-flow-template"></a>Tilpas din flow-skabelon

1. På kortet **Når der oprettes en salgsmulighed** skal du vælge det **miljø**, det **objektnavn** og det **omfang**, du vil bruge.
   
    ![Angiv detaljerne om objektet.](./media/common-data-model-intro/specify-instance.png)

1. Fuldfør kortet **Få salgsmulighedspost** i henhold til dine krav.
   
    ![Få Salgsmulighedspost](./media/common-data-model-intro/get-opportunity-record.png)

1. Konfigurer kortet **Stammer fra et kundeemne**. 
   
    ![Stammer fra et kundeemne](./media/common-data-model-intro/originate-from-lead.png)

1. Udfyld kortene **Hent kundeemne** og **Angiv noter for kundeemne** på siden **Hvis ja** i beslutningsforgreningen. 

   ![Fuldfør beslutningsforgrening](./media/common-data-model-intro/get-lead-list-notes.png)

1. Udvid kortet **Anvend på hver enkelt**, og slet derefter kortet **Kopier note til kundeemne til ny note**.

1. Vælg **Tilføj en handling**, søg efter **meddelelse**, og vælg derefter **Send mig en besked via e-mail**.

   ![Mailbesked](./media/common-data-model-intro/apply-to-each.png)

1. Konfigurer meddelelseskortet til at sende dig en e-mailnotifikation med oplysninger om de potentielle kunders noter.

   ![Meddelelseskort](./media/common-data-model-intro/notification-card.png)


>[!TIP]
>Hvis du ikke kan finde en skabelon, der fungerer, som du gerne vil have, kan du [oprette et flow fra bunden](get-started-logic-flow.md), som fungerer oven på Common Data Service.

