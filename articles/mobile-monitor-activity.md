---
title: Overvåg aktiviteten fra din telefon | Microsoft Docs
description: Se, hvor mange gange hvert flow er lykkedes eller mislykkedes, hvornår hver kørsel er fundet sted, og hvor lang tid det tog
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
ms.openlocfilehash: aa2b5eb13479f50f88ba7f723c5d1649746c74ec
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79196089"
---
# <a name="monitor-activity-in-power-automate-from-your-phone"></a>Overvåg aktiviteten i Power Automate fra din telefon

Få vist en oversigt over, hvor mange gange hvert flow er lykkedes eller mislykkedes i dag, i går og de forrige dage. Udforsk detaljer om hver kørsel, f.eks. hvornår den er kørt, hvor lang tid hvert trin tog og hvorfor den evt. mislykkedes.

**Forudsætninger**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Installér mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows) på en [understøttet enhed](getting-started.md#use-the-mobile-app). I grafikken til dette emne er iPhone-versionen af appen anvendt, men grænsefladen på en Android- og Windows Phone-enhed ser ligesådan ud.
* Hvis du ikke allerede har et flow, kan du oprette et på [webstedet for Power Automate](https://flow.microsoft.com/). For lettere at kunne teste dit flow kan du bruge et, du selv kan udløse i stedet for at vente på en ekstern hændelse.

Flowet i dette selvstudium kører, når du modtager en mail fra en bestemt adresse:

![Udløser flow ved modtagelse af mail fra en bestemt adresse](./media/mobile-monitor-activity/create-trigger.png)

Du kan konfigurere sådan et flow med din personlige mailadresse til testformål og med en anden adresse (f.eks. din overordnedes), når flowet er parat til reel brug.

Når flowet kører, sender det en brugerdefineret pushmeddelelse med følgende syntaks til din telefon:

![Send pushmeddelelse](./media/mobile-monitor-activity/create-event.png)

**Bemærk!** Du kan også [administrere dine flows](mobile-manage-flows.md) fra mobilappen.

## <a name="display-a-summary-of-activity"></a>Få vist en aktivitetsoversigt
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Hvis dit flow ikke har kørt før, skal du udløse en kørsel for at generere data.
   
    Det kan tage lidt tid, før dataene vises i appen.
2. Åbn mobilappen, der som standard viser fanen **Aktivitet**.
   
    Denne fane organiserer dataene efter dag med dags data øverst.
   
    ![Aktivitet, der er organiseret efter dag](./media/mobile-monitor-activity/activity-day2.png)
   
    Hver post viser navnet på et flow vha. ikoner, der svarer til flowets udløsende hændelser og handlinger.
   
    ![Navn og ikoner for hvert flow](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Hvis mindst én kørsel af et flow er lykkedes i løbet af dagen, viser en post antallet af vellykkede kørsler samt det seneste tidspunkt for en vellykket kørsel. En anden post viser lignende oplysninger, hvis et flow er mislykkedes.
   
    ![Oversigt over vellykkede eller mislykkede kørsler](./media/mobile-monitor-activity/activity-summary.png)
   
    Hvis der sendes en pushmeddelelse i et flow, vises teksten i den seneste meddelelse nederst i posten for vellykkede kørsler.
   
    ![Eksempel på pushmeddelelse](./media/mobile-monitor-activity/activity-notification.png)
3. Hvis der sendes flere pushmeddelelser i løbet af en dag, skal du stryge til venstre på meddelelsen for at få vist meddelelser fra op til tre tidligere kørsler. Hvis der blev sendt mere end fire meddelelser i løbet af en dag, skal du stryge til venstre, indtil **Se mere** vises og derefter trykke på den for at få vist en liste over alle meddelelser.
   
    ![Eksempel på pushmeddelelse](./media/mobile-monitor-activity/activity-notification-list.png)
4. Tryk på **Tilbage** for at vende tilbage til aktivitetsoversigt.
5. Hvis du vil filtrere aktivitetsoversigten, skal du trykke på ikonet i øverste højre hjørne.
   
    Du kan få vist alle poster, kun poster over mislykkede kørsler eller kun poster, der inkluderer pushmeddelelser.
   
    ![Vis alle kørsler, kun mislykkede kørsler eller kun meddelelser](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Vis detaljer for en kørsel
1. I aktivitetsoversigten skal du trykke på en post for at få vist detaljer for den seneste kørsel.
   
     Hver enkelt hændelse og handling vises med et ikon, der angiver, om hændelsen eller handlingen er lykkedes eller mislykkedes. Hvis den lykkedes, vises det også, hvor lang tid den tog (i sekunder).
   
    ![Detaljer for en kørsel](./media/mobile-monitor-activity/activity-icons.png)
2. I bunden af skærmen skal du trykke på **Se tidligere kørsler** for at få vist en liste over alle kørsler i flowet, og derefter trykke på en kørsel for at få vist detaljerne for den.
   
    ![Oversigt over vellykkede/mislykkede kørsler](./media/mobile-monitor-activity/history-mixed.png)

