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
ms.date: 09/07/2020
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c4a5ae6a2f5b1bccc81f5e7add3b6380b01b3847
ms.sourcegitcommit: d31569a29a01119c22feaa3012761b24c426f60b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/09/2020
ms.locfileid: "3791305"
---
# <a name="create-a-flow-from-a-template-in-power-automate"></a>Opret et flow ud fra en skabelon i Power Automate

Opret et flow fra en af de mange indbyggede skabeloner, der f.eks. kan sende dig en Slack-meddelelse, når din chef sender dig en mail i Office 365.

>[!TIP]
>[Opret et flow fra bunden](get-started-logic-flow.md), hvis du allerede har en proces i tankerne og ikke kan finde en skabelon til den.

**Forudsætninger**

* En konto på [flow.microsoft.com](https://flow.microsoft.com)
* En Slack-konto
* Office 365-legitimationsoplysninger

## <a name="choose-a-template"></a>Vælg en skabelon

1. I [flow.microsoft.com](https://flow.microsoft.com) skal du markere afkrydsningsfeltet **Søg efter alle skabeloner**, angive **Slack** og derefter trykke på ENTER.
1. Du får kun vist skabeloner, der er relateret til Slack, så du kan nu vælge **Send en meddelelse på Slack, når chefen sender en mail til mig**.
   
    ![Ny indstilling i den venstre navigationslinje](./media/get-started-logic-template/select-template.png)
1. Kontrollér, at du har valgt den korrekte skabelon, og vælg derefter **Brug denne skabelon**.
1. Hvis du ikke er logget på Office eller Slack, kan du vælge **Log på** og derefter følge prompterne.
   
1. Vælg **Fortsæt**, når du har bekræftet forbindelserne.
   
    Dit flow vises, og hver handling vises med en orange titellinje.
   
    ![Standardhændelser og handlinger fra skabelon](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Tilpas dit flow

1. Vælg titellinjen til en hændelse for at udvide den, og tilpas den derefter (f.eks. ved at angive et filter på mailen, der interesserer dig).
1. Handlinger, der kræver input fra dig, udvides automatisk.
   
    Handlingen **Send meddelelse** er f.eks. udvidet, fordi du skal angive en kanal i stil med dit *\@brugernavn*. Du kan også tilpasse meddelelsesindholdet. Som standard indeholder meddelelsen blot emnet, men du kan medtage andre oplysninger.
   
1. Angiv et navn til dit flow i den øverste del af skærmen, og vælg derefter **Opret flow**.
1. Hvis du er tilfreds med dit flow, vælger du til sidst **Udført**.

Når din chef nu sender dig en mail, modtager du en Slack-meddelelse, der indeholder de oplysninger, du har angivet.

## <a name="next-steps"></a>Næste trin

* [Se dit flow i aktion](see-a-flow-run.md)
* [Publicer din egen skabelon](publish-a-template.md)
* [Brug en skabelonen til Common Data Service](common-data-model-intro.md)
* [Kom i gang med teamflows](create-team-flows.md), og inviter andre til at samarbejde med dig om at designe flows.

