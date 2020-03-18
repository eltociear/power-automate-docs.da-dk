---
title: Administrer flows fra din telefon | Microsoft Docs
description: Få vist en liste over dine flows, aktivér eller deaktiver dem, og få vist hændelse(r), handling(er) og kørselsoversigt for hvert enkelt flow
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ce9a943f50ef5c8cc69e5dbf8fde796a75e4cdf9
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195795"
---
# <a name="manage-flows-in-power-automate-from-your-phone"></a>Administrer flow i Power Automate fra din telefon

Få vist en liste over alle de flows, du har oprettet, og få vist hændelser og handlinger for hvert enkelt flow, aktivér eller deaktiver dem, og udforsk kørselsoversigten.

**Forudsætninger**

* Installér mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows) på en [understøttet enhed](getting-started.md#use-the-mobile-app). I grafikken til dette emne er iPhone-versionen af appen anvendt, men grænsefladen på en Android- og Windows Phone-enhed ser ligesådan ud.
* Hvis du ikke allerede har et flow, kan du oprette et på [webstedet for Power Automate](https://flow.microsoft.com/). For lettere at kunne teste dit flow kan du bruge et, du selv kan udløse i stedet for at vente på en ekstern hændelse.

Flowet i dette selvstudium kører, når du modtager en mail fra en bestemt adresse:

![Udløser flow ved modtagelse af mail fra en bestemt adresse](./media/mobile-manage-flows/create-trigger.png)

Du kan konfigurere sådan et flow med din personlige mailadresse til testformål og med en anden adresse (f.eks. din overordnedes), når flowet er parat til reel brug.

Når flowet kører, sender det en brugerdefineret pushmeddelelse med følgende syntaks til din telefon:

![Send meddelelse til slæk](./media/mobile-manage-flows/create-event.png)

**Bemærk!** Du kan også [overvåge flowaktivitet](mobile-monitor-activity.md) fra mobilappen.

## <a name="manage-a-flow"></a>Administrer et flow
1. Åbn mobilappen, og tryk derefter på **Mine flows** i bunden af skærmen for at få vist alle dine flows.
   
    Hver enkelt post viser navnet på flowet, ikonerne for de relaterede hændelser og handlinger, tidspunktet for den seneste kørsel samt et ikon, der angiver, om den seneste kørsel var vellykket.
   
    ![Liste over flows](./media/mobile-manage-flows/flow-list.png)
2. Tryk på et flow for at få vist indstillinger for administration af det.
   
    ![Indstillinger for administration af et flow](./media/mobile-manage-flows/flow-details.png)
3. Tryk på til/fra-knappen **Aktivér flow** for at aktivere eller deaktivere flowet.
4. Tryk på **Se flow** for at vise hændelserne og handlingerne for det pågældende flow, tryk på hver enkelt hændelse eller handling for at udvide den, og tryk derefter på **Tilbage**.
   
    ![Hændelser og handlinger for et flow](./media/mobile-manage-flows/flow-event-action.png)
5. Tryk på **Kørselsoversigt** for at vise flowets succeser, fejl eller begge dele.
   
    ![Liste over kørsler](./media/mobile-manage-flows/history-mixed.png)
6. Tryk på en kørsel for at vise, om hver enkelt hændelse og handling er vellykket, og i så fald hvor lang tid (i sekunder) den har taget.
   
    ![Kørselsdetaljer](./media/mobile-manage-flows/flow-run.png)

