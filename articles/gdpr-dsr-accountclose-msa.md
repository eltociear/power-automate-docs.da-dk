---
title: Anmodninger om kontolukning fra registrerede omfattet af Power Automate GDPR for Microsoft-konti (MSA) | Microsoft Docs
description: Få mere at vide om, hvordan du kan bruge Power Automate til at svare på anmodninger om kontolukning fra registrerede omfattet af GPDR for Microsoft-konti.
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
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 277765754683a6690b186a5f592517482b32666f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74366368"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-power-automate"></a>Besvar anmodninger om kontolukning fra registrerede omfattet af GDPR for Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

**Retten til sletning** af personlige data er en central sikkerhedsdetalje i persondataforordningen. Denne ret inkluderer fjernelse af alle personlige data, men ikke oplysninger fra overvågningslogge. Når en bruger beslutter at lukke sin Microsoft-konto (MSA), slettes brugerens underliggende data også.

Disse ressourcer indeholder personlige data, der slettes automatisk, når en bruger lukker en MSA:

|Ressourcer, der indeholder personlige data|
|------|
|Produkt- og tjenesteaktivitet|
|Kørselsoversigt|
|Flow|
|Aktivitetsopdatering|
|Brugeroplysninger|
|Forbindelser|

## <a name="account-close-requests"></a>Anmodninger om kontolukning

Disse trin beskriver, hvordan du selv kan lukke din Micorsoft-konto som følge af GDPR.

1. Log på [portalen til lukning af Microsoft-konti](https://go.microsoft.com/fwlink/?LinkId=523898) ved hjælp af din Microsoft-konto, og vælg derefter **Næste**.

    > [!NOTE]
    > Du bliver mindet om at annullere eksisterende abonnementer eller at eksportere data fra eksisterende tjenester, du kan have abonneret på.
    >
    >

    ![Annuller abonnementer](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Bekræft, at du forstår, hvad det medfører at lukke din MSA, og vælg derefter **Markér konto til lukning**.

    Der vises en meddelelse, som angiver, at din konto bliver lukket inden for 30 dage. Du kan åbne kontoen igen inden for denne 30-dages periode.

    ![Konto lukket](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Når de 30 dage er gået, starter den proces, der sletter alle Power Automate-ressourcer for denne MSA.

## <a name="learn-more"></a>Få mere at vide

* Introduktion til [Power Automate](getting-started.md)
* Se [nyhederne](release-notes.md) i Power Automate
