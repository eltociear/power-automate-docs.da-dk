---
title: Brug IME'er (Input Method Editors) i flow for brugergrænseflader | Microsoft Docs
description: Få mere at vide om at bruge IME'er (Input Method Editors) i flow for brugergrænseflader.
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
ms.date: 02/25/2020
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 167f9321dba853e801102bed2ebe7e8902437d71
ms.sourcegitcommit: 26cda5060446812f3725ccd4fe435839088f50fa
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/03/2020
ms.locfileid: "78253174"
---
# <a name="use-input-method-editors-imes-in-ui-flows"></a>Brug IME'er (Input Method Editors) i flow for brugergrænseflader

Du kan bruge funktionen **Tilføj statisk tekst** til at optage tekstinput på alle sprog ved hjælp af IME'er eller almindelige tastaturer i dine flow for brugergrænsefladen. Brug **Tilføj statisk tekst**, hvis automatiseringen skal indsætte den samme tekst, hver gang dit flow for brugergrænsefladen køres. 

>[!TIP]
>Brug **Tekstinput**, hvis du vil bruge dynamisk tekst, der ændres, hver gang dit flow for brugergrænsefladen køres.

## <a name="invoke-ime"></a>Kald IME

Følg disse trin, når du har startet optagelsen, og du er klar til at indsætte statisk tekstinput:

1. Vælg det kontrolelement, som du vil angive den statiske tekst i.

   ![Vælg kontrolelementet](../media/use-ime/select-control.png)

1. Vælg **Brug input** på optageren, og vælg derefter **Tilføj statisk tekst**.

   ![Vælg Tilføj statisk tekst](../media/use-ime/add-static-text.png)

   Du kan se et inputfelt, som du skal angive den statiske tekst i. Du kan bruge IME, engelsk eller et vilkårligt internationalt tastatur.

   ![Angiv statisk tekst](../media/use-ime/enter-static-text.png)

1. Angiv teksten.

1. Vælg **Føj til app**, og vælg derefter det kontrolelement, du vil indsætte teksten i. Du kan se den tekst, der er indsat i kontrolelementet. 

   Denne tekst angives automatisk på afspilningstidspunktet, selvom afspilningsprogrammerne ikke har samme tastaturlayouts eller IME, som blev brug under optagelsen.

   ![Afspilningstekst](../media/use-ime/playback-text.png)

   >[!TIP]
   >I webdesigneren skal du udvide handlingen **Indsæt tekstinput** for at gennemse eller redigere teksten.

   ![Indsæt tekstinput](../media/use-ime/insert-text-input.png)


## <a name="use-the-replay-keystroke-action"></a>Brug handlingen Afspil tastetryk igen

Hvis du har optaget tekstinput uden at bruge indstillingen **Tilføj statisk tekst**, optages hvert enkelt tastetryk og afspilles kronologisk. Dette inkluderer alle specialtaster, f.eks. CTRL, ALT, Windows osv. på engelske eller internationale tastaturer.

I designeren kan du gennemse og redigere optagelsesoplysningerne i formatet [virtuel-tast](https://docs.microsoft.com/windows/win32/inputdev/virtual-key-codes) under handlingen **Afspil tastetryk igen**. 

![Virtuel tast](../media/use-ime/virtual-key.png)


> [!NOTE]
> En ældre version af optageren af flow for brugergrænsefladen brugte handlingerne **SendTaster** og **PostElement**. Disse handlinger udfases. Vi anbefaler, at du opgraderer til den nyeste version af optageren til flow for brugergrænsefladen og derefter optager dine scripts igen for at anvende de nye funktioner.

## <a name="troubleshooting-tips"></a>Tip til fejlfinding

1. Hvis du optager tastaturhandlinger i tilstanden **Afspil tastetryk igen**, skal du sørge for, at afspilningsprogrammet bruger det samme tastatur som på optagelsestidspunktet, da afspilningssekvenserne for de samme tastetryk kan give andre inputværdier, hvis der anvendes andre tastaturer.

1. Du kan kun anvende **Brug input** for kontrolelementer af typen Tekst. I øjeblikket kan **Brug input** ikke angive tekst for andre typer af kontrolelementer, f.eks. kombinationsfelt, rulleliste, listevisning osv.

## <a name="next-steps"></a>Næste trin

- Få mere at vide om, hvordan du [konfigurerer flow for brugergrænsefladen](setup.md). 
- Få mere at vide om de [forskellige flowtyper](..\getting-started.md#types-of-flows), som du kan bruge til at automatisere dine arbejdsprocesser.


