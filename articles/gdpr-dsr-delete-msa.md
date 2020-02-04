---
title: Sletteanmodninger fra registrerede omfattet af Power Automate GDPR for Microsoft-konti (MSA) | Microsoft Docs
description: Få mere at vide om, hvordan du kan bruge Power Automate til at svare på sletteanmodninger fra registrerede omfattet af GPDR for Microsoft-konti.
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
ms.openlocfilehash: b9ef70579798b353ddcd8a961604665a287cd63a
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74368139"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Svar på sletteanmodninger fra fysiske personer omfattet af GDPR
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

**Retten til sletning** ved at fjerne personlige data er en central sikkerhedsdetalje i persondataforordningen. Fjernelse af personlige data inkluderer fjernelse af alle personlige data, men ikke oplysninger fra overvågningslogge.

Power Automate giver dig mulighed for at oprette automatiske arbejdsprocesser. Når en bruger har besluttet at slette sine personlige data fra Power Automate, kan brugeren gennemse sine personlige data og beslutte, om vedkommende vil slette nogle eller alle data.

I følgende tabel vises det, hvilke personlige data der slettes automatisk, og hvilke data der kræver, at en Microsoft-kontobruger (MSA) gennemser og sletter dem:

|Kræver, at MSA brugeren gennemser og sletter|Slettes automatisk|
|------|------|
|Produkt- og tjenesteaktivitet|Kørselsoversigt|
|Flow|Aktivitetsopdatering|
|Forbindelser||

Power Automate indeholder følgende funktioner, som hjælper brugerne med at finde, gennemse eller ændre personlige data og ressourcer, som ikke slettes automatisk:

## <a name="manage-delete-requests"></a>Administrer sletteanmodninger

I fremgangsmåden nedenfor beskrives, hvordan man selv kan udføre sletteanmodninger for GDPR.

### <a name="delete-product-and-service-activity"></a>Slet produkt- og tjenesteaktivitet

1. Log på [Microsoft-dashboard til beskyttelse af personlige oplysninger Dashboard](https://account.microsoft.com/privacy/) med din MSA.
1. Vælg linket **Aktivitetsoversigt**.

    ![Aktivitetsoversigt](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Du kan søge efter eller gennemse din aktivitetsoversigt for de forskellige Microsoft-programmer og -tjenester, du bruger, herunder Power Automate. Vælg **Slet** for at fjerne specifikke hændelser for produkt- eller tjenesteaktiviteter.

    ![Slet hændelse](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Elementet slettes og fjernes efter kort tid fra dashboardet til beskyttelse af personlige oplysninger.

### <a name="list-and-delete-flows"></a>Vis og slet flows

En bruger kan få vist og slette sine flow fra [Power Automate](https://flow.microsoft.com) med følgende fremgangsmåde:

1. Log på [Power Automate](https://flow.microsoft.com), og vælg derefter **Mine flow**.

1. Vælg **...**  ud for det flow, du vil slette, og vælg derefter **Slet**.

    ![Slet hændelse](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Slet forbindelser

Connectors bruger forbindelser til at kommunikere med API'er og SaaS-systemer. Forbindelser indeholder referencer til den bruger, der opretter dem. Brugeren kan til enhver tid slette disse referencer med følgende fremgangsmåde:

1. Log på [Power Automate](https://flow.microsoft.com), vælg tandhjulsikonet, og vælg derefter **Forbindelser**.

    ![Slet hændelse](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Vælg den forbindelse, du vil slette, vælg **...** , og vælg derefter **Slet**.

    ![Slet hændelse](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Vælg ikonet **Slet** i bekræftelsesvinduet.

    ![Slet hændelse](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Hvis andre flows bruger den forbindelse, du sletter, får du besked om, at der kræves en ny forbindelse. Ellers skal du vælge **Slet** for at fortsætte.
>
>

## <a name="learn-more"></a>Få mere at vide

* Introduktion til [Power Automate](getting-started.md)
* Se [nyhederne](release-notes.md) i Power Automate
