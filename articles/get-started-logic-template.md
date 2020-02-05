---
title: Opret et flow fra en skabelon | Microsoft Docs
description: Opret et flow fra en af de mange indbyggede skabeloner.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2e92d43a33a4a05523ae350a63aa68f9cda2d1f
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74368691"
---
# <a name="create-a-flow-from-a-template-in-power-automate"></a>Opret et flow ud fra en skabelon i Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Opret et flow fra en af de mange indbyggede skabeloner, der f.eks. kan sende dig en Slack-meddelelse, når din chef sender dig en mail i Office 365.

**Bemærk!** [Opret et flow fra bunden](get-started-logic-flow.md), hvis du allerede har en proces i tankerne og kan ikke finde en skabelon til den.

**Forudsætninger**

* En konto på [flow.microsoft.com](https://flow.microsoft.com)
* En Slack-konto
* Office 365-legitimationsoplysninger

## <a name="choose-a-template"></a>Vælg en skabelon
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. På [flow.microsoft.com](https://flow.microsoft.com) skal du vælge **Skabeloner** på den øverste navigationslinje.
2. Skriv **Slack** i søgepanelet, og klik derefter på søgeikonet.
3. Du får kun vist skabeloner, der er relateret til Slack, så du kan nu vælge **Send en meddelelse på Slack, når chefen sender en mail til mig**.
   
    ![Ny indstilling i den venstre navigationslinje](./media/get-started-logic-template/select-template.png)
4. Kontrollér, at du har valgt den korrekte skabelon, og vælg derefter **Brug denne skabelon**.
5. Hvis du ikke er logget på Office eller Slack, kan du vælge **Log på** og derefter følge prompterne.
   
    ![Liste over forbindelser, som kræves af skabelonen](./media/get-started-logic-template/confirm-connections.png)
6. Vælg **Fortsæt**, når du har bekræftet forbindelserne.
   
    Dit flow vises, og hver handling vises med en orange eller titellinje.
   
    ![Standardhændelser og handlinger fra skabelon](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Tilpas dit flow
1. Vælg titellinjen til en begivenhed for at udvide den, og tilpas den derefter (f.eks. ved at angive et filter på mailen, der interesserer dig).
2. Handlinger, der kræver input fra dig, udvides automatisk.
   
    Handlingen **Send meddelelse** er f.eks. udvidet, fordi du skal angive en kanal i stil med dit *\@brugernavn*. Du kan også tilpasse meddelelsesindholdet. Som standard indeholder meddelelsen blot emnet, men du kan medtage andre oplysninger.
   
    ![Angiv kanal til Slack](./media/get-started-logic-template/specify-keyword.png)
3. Angiv et navn til dit flow i den øverste del af skærmen, og vælg derefter **Opret flow**.
4. Hvis du er tilfreds med dit flow, vælger du til sidst **Udført**.
   
    ![Knappen Udført](./media/get-started-logic-template/done.png)

Når din chef nu sender dig en mail, modtager du en Slack-meddelelse, der indeholder de oplysninger, du har angivet.

## <a name="next-steps"></a>Næste trin
* [Se dit flow i aktion](see-a-flow-run.md)
* [Udgiv din egen skabelon](publish-a-template.md)
* [Brug en skabelon til Common Data Service](common-data-model-intro.md)
* [Kom i gang med teamflows](create-team-flows.md), og inviter andre til at samarbejde med dig om at designe flows.

