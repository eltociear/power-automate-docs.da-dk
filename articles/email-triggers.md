---
title: Kør flows baseret på mailegenskaber | Microsoft Docs
description: Start en proces baseret på egenskaber som emne, afsenderadresse eller modtagerafdresse i en mail.
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: fdfa1966c40c3c6db6803a58d9f2df687058b3d6
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74365632"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Udløs et flow baseret på mailegenskaber
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Brug udløseren **Når en ny mail modtages** til at oprette et flow, der køres, når en eller flere af følgende mailegenskaber opfylder de kriterier, du har angivet:

| Egenskab | Hvornår bruger du |
| --- | --- |
| Mappe |Udløs et flow, når du modtager mails i en bestemt mappe. Denne egenskab kan være praktisk, hvis du har regler, der sender mails til andre mapper. |
| Til |Udløs et flow baseret på den adresse, som en mail blev sendt til. Denne egenskab kan være praktisk, hvis du modtager mail, der er sendt til forskellige mailadresser, i den samme indbakke. |
| Fra |Udløs et flow baseret på afsenderens mailadresse. |
| Prioritet |Udløs et flow baseret på den prioritet, som mails blev sendt med. En mail kan sendes med høj, normal eller lav prioritet. |
| Har vedhæftet fil |Udløs et flow baseret på tilstedeværelsen af vedhæftede filer i indgående mails. |
| Emnefilter |Søg efter tilstedeværelsen af bestemte ord i emnet i en mail. Derefter kører dit flow *handlinger*, der er baseret på resultaterne af din søgning. |

> [!IMPORTANT]
> Alle [Power Automate-planer](https://flow.microsoft.com/pricing/) indeholder en kørselskvote. Kontrollér altid egenskaber i flowets udløser, når det er muligt. Hvis du gør det, undgår du at bruge kørselskvoten uden grund. Hvis du kontrollerer en egenskab i en betingelse, tælles de enkelte kørsler med i din plans kørselskvote, også selvom den filterbetingelse, du har angivet, ikke er opfyldt. 

Hvis du f.eks. undersøger *fra*-adressen for en mail i en betingelse, tæller hver kørsel med i din plans kørselskvote, også selvom den ikke er *fra* den adresse, du kontrollerer.
> 
> 

I følgende gennemgange kontrollerer vi alle egenskaberne i udløseren **Når en ny mail modtages**. Få mere at vide ved at gå til siderne med [ofte stillede spørgsmål om fakturering](billing-questions.md#what-counts-as-a-run) og [priser](https://ms.flow.microsoft.com/pricing/).

## <a name="prerequisites"></a>Forudsætninger
* En konto, der har adgang til [Power Automate](https://flow.microsoft.com)
* En Office 365 Outlook-konto
* Mobilappen Power Automate til [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows)
* Forbindelser til Office, Outlook og pushmeddelelsestjenesten

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Udløs et flow baseret på emnet i mailen
I denne gennemgang opretter vi et flow, der sender en pushmeddelelse til din mobiltelefon, hvis emnet i en ny mail indeholder ordet "lotteri". Dit flow markerer derefter sådanne mails som *læst*.

>[!NOTE]
>Der sendes en pushmeddelelse under denne gennemgang, men du er velkommen til at bruge andre handlinger, der passer til dine behov i arbejdsprocessen. Du kan f.eks. gemme mailindholdet på et andet lager, f.eks. i Google Sheets eller i en Microsoft Excel-fil, der er gemt i Dropbox.

Lad os komme i gang:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. I feltet **Emnefilter** skal du skrive den tekst, som dit flow bruger til at filtrere indgående mails.
   
     I dette eksempel er vi interesseret i alle mails, der indeholder ordet "lotteri" i emnet.
   
    ![Avancerede indstillinger](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Angiv detaljerne for den mobilmeddelelse, du vil modtage, når du modtager en mail, der opfylder de kriterier for **Emnefilter**, du har angivet tidligere.
   
    ![Meddelelsesdetaljer](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Navngiv dit flow. Gem det derefter ved at vælge **Opret flow** øverst på siden.
   
    ![Gem flow](./media/email-triggers/email-triggers-subject-notification.png)

Tillykke! Du modtager nu en pushmeddelelse, hver gang du modtager en mail, der indeholder ordet "lotteri" i emnet.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Udløs et flow baseret på afsenderen af mailen
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

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Udløs et flow, når du modtager en mail i en bestemt mappe
Hvis du har regler, der sender mail til forskellige mapper baseret på visse egenskaber, f.eks. adressen, kan du medtage denne type flow.

Lad os komme i gang:

> [!NOTE]
> Hvis du ikke allerede har en regel, der sender mail til en anden mappe end din indbakke, kan du oprette sådan en regel og bekræfte, at den fungerer, ved at sende en testmail.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Vælg den mappe, som du distribuerer bestemte mails til. Hvis du vil have vist alle mailmapper, skal du først vælge ikonet **Vis vælger**, der er placeret til højre for feltet **Mappe** på kortet **Når en ny mail modtages**.
   
    ![Vælg mappe](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Angiv detaljerne for den mobilmeddelelse, du gerne vil modtage, når du modtager en mail i den mappe, du har valgt tidligere. Hvis du ikke allerede har gjort det, skal du angive legitimationsoplysningerne for meddelelsestjenesten.
   
    ![Meddelelsesdetaljer](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Giv dit flow et navn, og gem det ved at vælge **Opret flow** øverst på siden.
   
    ![Gem flow](./media/email-triggers/email-triggers-7.png)

Test meddelelsesflowet ved at sende en mail, der videresendes til den mappe, du valgte tidligere i denne gennemgang.

