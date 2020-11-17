---
title: Køre flows baseret på mailegenskaber | Microsoft Docs
description: Start et flow baseret på egenskaber som emne, afsenderadresse eller modtageradresse i en mail.
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
ms.date: 10/16/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a09209e892fb7f1fe5e9244e90996ef54f44818b
ms.sourcegitcommit: 4f57dea6e1579144353d9e1a3ffba455178c11bc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/20/2020
ms.locfileid: "4042566"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Udløse et flow baseret på mailegenskaber

Brug udløseren **Når en ny mail modtages (V3)** til at oprette et flow, der køres, når en eller flere af følgende mailegenskaber opfylder de kriterier, du har angivet:

| Ejendom | Hvornår bruges  |
| --- | --- |
| Mappe |Udløs et flow, når du modtager mails i en bestemt mappe. Denne egenskab kan være praktisk, hvis du har regler, der sender mails til andre mapper. |
| Til |Udløs et flow baseret på den adresse, som en mail blev sendt til. Denne egenskab kan være praktisk, hvis du modtager mail, der er sendt til forskellige mailadresser, i den samme indbakke. |
|CC|Udløs et flow baseret på den CC-adresse, som en mail blev sendt til. Denne egenskab kan være praktisk, hvis du modtager mail, der er sendt til forskellige mailadresser, i den samme indbakke.
| Fra |Udløs et flow baseret på afsenderens mailadresse. |
| Prioritet |Udløs et flow baseret på den prioritet, som mails blev sendt med. En mail kan sendes med høj, normal eller lav prioritet. |
| Har vedhæftet fil |Udløs et flow baseret på tilstedeværelsen af vedhæftede filer i indgående mails. |
| Emnefilter |Søg efter tilstedeværelsen af bestemte ord i emnet i en mail. Derefter kører dit flow *handlinger*, der er baseret på resultaterne af din søgning. |

> [!IMPORTANT]
> Hver [Power Automate-plan](https://flow.microsoft.com/pricing/) indeholder en kørselskvote. Kontrollér altid egenskaber i flowets udløser, når det er muligt. Hvis du gør det, undgår du at bruge kørselskvoten uden grund. Hvis du kontrollerer en egenskab i en betingelse, tælles de enkelte kørsler med i din plans kørselskvote, også selvom den filterbetingelse, du har angivet, ikke er opfyldt. 

Hvis du f.eks. undersøger *fra*-adressen for en mail i en betingelse, tæller hver kørsel med i din plans kørselskvote, også selvom den ikke er *fra* den adresse, du kontrollerer.
> 
> 

I følgende gennemgange kontrollerer vi alle egenskaberne i udløseren **Når en ny mail modtages (V3)**. Få mere at vide ved at gå til siderne med [ofte stillede spørgsmål om fakturering](billing-questions.md#what-counts-as-a-run) og [prisfastsættelse](https://ms.flow.microsoft.com/pricing/).

## <a name="prerequisites"></a>Forudsætninger
* En konto med adgang til [Power Automate](https://flow.microsoft.com)
* En Microsoft 365 Outlook-konto
* Power Automate-mobilappen for [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows)
* Forbindelser til Office, Outlook og pushmeddelelsestjenesten

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Udløse et flow baseret på emnet i mailen
I denne gennemgang opretter vi et flow, der sender en pushmeddelelse til din mobiltelefon, hvis emnet i en ny mail indeholder ordet "lotteri". Dit flow markerer derefter sådanne mails som *læst*.

>[!NOTE]
>Der sendes en pushmeddelelse under denne gennemgang, men du er velkommen til at bruge andre handlinger, der passer til dine behov i arbejdsprocessen. Du kan f.eks. gemme mailindholdet på et andet lager, f.eks. i Google Sheets eller i en Microsoft Excel-projektmappe, der er gemt i Dropbox.

Lad os komme i gang:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Angiv den tekst, der bruges i dit flow, når du filtrerer indgående mails, i feltet **Emnefilter**.
   
     I dette eksempel er vi interesseret i alle mails, der indeholder ordet "lotteri" i emnet.
   
    ![Avancerede indstillinger](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Angiv detaljerne for den mobilmeddelelse, du vil modtage, når du modtager en mail, der opfylder de kriterier for **Emnefilter**, du har angivet tidligere.
   
    ![Et skærmbillede, der viser oplysningerne om en meddelelse](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Vælg **Gem** øverst på siden.
   
    ![Et skærmbillede, der viser indstillingen Gem flow](./media/email-triggers/email-triggers-subject-notification.png)

Tillykke! Du modtager nu en pushmeddelelse, hver gang du modtager en mail, der indeholder ordet "lotteri" i emnet.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Udløse et flow baseret på afsenderen af mailen
I denne gennemgang opretter vi et flow, der sender en pushmeddelelse til din mobiltelefon, hvis du modtager en mail fra en bestemt afsender (mailadresse). Dit flow markerer også sådanne mails som *læst*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Skriv afsenderens mailadresse i feltet **Fra**. 
   
     Dit flow reagerer, når der modtages mail, som er sendt fra denne adresse.
   
    ![Mailegenskab](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Angiv detaljerne for den mobilmeddelelse, du gerne vil modtage, når du modtager en meddelelse fra den mailadresse, du har angivet tidligere.
   
    ![Meddelelsesdetaljer](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Giv dit flow et navn, og gem det ved at vælge **Opret flow** øverst på siden.
   
    ![Gem flow](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Udløse et flow, når du modtager en mail i en bestemt mappe
Hvis du har regler, der sender mail til forskellige mapper baseret på visse egenskaber, f.eks. adressen, kan du medtage denne type flow.

Lad os komme i gang:

> [!NOTE]
> Hvis du ikke allerede har en regel, der sender mail til en anden mappe end din indbakke, kan du oprette sådan en regel og bekræfte, at den fungerer, ved at sende en testmail.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Vælg den mappe, som du distribuerer bestemte mails til. Hvis du vil have vist alle mailmapper, skal du først vælge ikonet **Vis vælger**, der er placeret til højre for feltet **Mappe** på kortet **Når en ny mail modtages (V3)**.
   
    ![Vælg mappe](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Angiv detaljerne for den mobilmeddelelse, du gerne vil modtage, når du modtager en mail i den mappe, du har valgt tidligere. Hvis du ikke allerede har gjort det, skal du angive legitimationsoplysningerne for meddelelsestjenesten.
   
    ![Meddelelsesdetaljer](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Giv dit flow et navn, og gem det ved at vælge **Opret flow** øverst på siden.
   
    ![Gem flow](./media/email-triggers/email-triggers-7.png)

Test meddelelsesflowet ved at sende en mail, der videresendes til den mappe, du valgte tidligere i denne gennemgang.

