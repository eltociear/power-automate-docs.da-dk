---
title: Anmodninger i Power Automate om kontolukning for dataemner omfattet af GDPR for Microsoft-konti (MSA) | Microsoft Docs
description: Lær at bruge Power Automate til at svare på anmodninger om kontolukning for dataemner omfattet af GPDR for Microsoft-konti.
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
ms.openlocfilehash: 10f232e45a53cea30892f512b626246fec16deed
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297819"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-power-automate"></a>Besvarelse af anmodninger i Power Automate om kontolukning for dataemner omfattet af GDPR


**Retten til sletning** af personlige data er en central sikkerhedsdetalje i persondataforordningen. Denne ret inkluderer fjernelse af alle personlige data, men ikke oplysninger fra overvågningslogge. Når en bruger beslutter at lukke sin Microsoft-konto (MSA), slettes brugerens underliggende data også.

Disse ressourcer indeholder personlige data, der slettes automatisk, når en bruger lukker en MSA:

|Ressourcer, der indeholder personlige data|
|------|
|Produkt- og tjenesteaktivitet|
|Kørselshistorik|
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
* Lær [nyheder i](release-notes.md) med Power Automate
