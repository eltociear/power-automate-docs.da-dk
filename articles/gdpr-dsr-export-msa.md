---
title: Eksportanmodninger fra registrerede omfattet af Power Automate GDPR for Microsoft-konti (MSA) | Microsoft Docs
description: Få mere at vide om, hvordan du kan bruge Power Automate til at svare på eksportanmodninger fra registrerede omfattet af GPDR for Microsoft-konti.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 05b44b20ec7080eaf603d04627d43b3e73a77a1f
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74354983"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-power-automate"></a>Svar på eksportanmodninger fra registrerede omfattet af GDPR for Power Automate
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Som led i vores bestræbelser på at være med dig gennem hele processen omkring den generelle forordning om databeskyttelse (GDPR) har vi udviklet denne dokumentation. Denne dokumentation beskriver ikke blot, hvad Microsoft gør for at forberede sig på GDPR, men kommer også med eksempler på, hvad du kan gøre i dag med Microsoft for at overholde GDPR, når du bruger Power Automate.

## <a name="manage-export-requests"></a>Administrer eksportanmodninger

*Retten til videregivelse af oplysninger* gør det muligt for registrerede at anmode om en kopi af sine personlige data i elektronisk format, dvs. i et format, der er "struktureret, almindeligt brugt, kan læses af en maskine, og som er kompatibelt", og som kan sendes til en anden datacontroller.

Brug [Microsoft-dashboard til beskyttelse af personlige oplysninger](https://account.microsoft.com/privacy/) eller [Power Automate](https://flow.microsoft.com/) til at finde eller eksportere personlige data for en bestemt bruger.

|Personlige data|Placering|
|-----------------|-------------------|
|Produkt- og tjenesteaktivitet|Microsoft-dashboard til beskyttelse af personlige oplysninger|
|Flow|Power Automate-udviklerportal|
|Kørselsoversigt|Power Automate-udviklerportal|
|Aktivitetsopdatering|Power Automate-udviklerportal|
|Forbindelser|Power Automate-udviklerportal|

## <a name="export-product-and-service-activity"></a>Eksportér produkt- og tjenesteaktivitet

1. Log på [Microsoft-dashboardet til beskyttelse af personlige oplysninger](https://account.microsoft.com/privacy/) med din Microsoft-konto (MSA).
1. Vælg **Aktivitetsoversigt**.

    ![Aktivitetsoversigt](./media/gdpr-dsr-export-msa/activityhistory.png) Du kan søge efter eller gennemse din aktivitetsoversigt for de forskellige Microsoft-programmer og -tjenester, du bruger.
1. Hvis du vil eksportere data fra **produkt- og tjenesteaktivitet**, skal du vælge **Download dine data** og derefter vælge **OPRET NYT ARKIV**.

    ![Download dine data](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Vælg **App- og tjenestebrug**, og vælg derefter **Opret arkiv**.

    ![Download dine data](./media/gdpr-dsr-export-msa/create-archive.png)
1. Der oprettes et nyt arkiv. Vælg **Download** for at hente dine eksporterede data om produkt- og tjenesteaktivitet.

    ![Download](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Eksportér et flow

En slutbruger, der har adgang til et flow, kan eksportere flowet ved at følge disse trin:

1. Log på [Power Automate](https://flow.microsoft.com/).

1. Vælg **Mine flow**, og vælg derefter det flow, der skal eksporteres.

1. Vælg **... Flere**, og vælg derefter **Eksportér**.

    ![Eksportér flow](./media/gdpr-dsr-export/export-flow.png)

1. Vælg **Pakke (.zip)** .

Dit flow er nu tilgængeligt som en zip-komprimeret pakke. Du kan finde flere oplysninger i blogindlægget om, [hvordan du eksporterer og importerer et flow](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Eksportér kørselsoversigt

Kørselsoversigten indeholder en liste over alle kørsler for et flow. Disse data indeholder flowstatus, starttidspunkt, varighed og input/output-data for udløsere og handlinger.

En slutbruger, der har adgang til et flow, kan eksportere data ved at følge disse trin:

1. Log på [Power Automate](https://flow.microsoft.com/).
1. Vælg linket **Mine flow**, og vælg derefter det flow, som du vil eksportere kørselsoversigten for.
1. I ruden **KØRSELSOVERSIGT** skal du vælge **Se alle**.

    ![Kørselsoversigt](./media/gdpr-dsr-export/run-history.png)

1. Vælg **Download CSV**.

    ![Download CSV](./media/gdpr-dsr-export/download-csv.png)

Kørselsoversigten downloades som en .csv-fil, som kan åbnes i Microsoft Excel eller i en teksteditor, hvor du kan analysere resultaterne.

## <a name="export-a-users-activity-feed"></a>Eksportér en brugers aktivitetsopdatering

I [Power Automate](https://flow.microsoft.com/) viser aktivitetsopdateringen en brugers oversigt over aktiviteter, fejl og beskeder. Brugere kan få vist deres aktivitetsopdatering ved at følge disse trin:

1. Log på [Power Automate](https://flow.microsoft.com/), vælg klokkeikonet i nærheden af øverste højre hjørne, og vælg derefter **Vis alle aktiviteter**.

    ![Vis aktivitetsopdatering](./media/gdpr-dsr-export/show-activity-feed.png)

1. På skærmen **Aktivitet** kan du kopiere resultaterne og derefter indsætte dem i en teksteditor, f.eks. Microsoft Word.

    ![Vis aktivitetsopdatering](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Eksportér en brugers forbindelser

Forbindelser gør det muligt for flow at oprette forbindelse til API'er, SaaS-programmer og andre tredjepartssystemer. Udfør disse trin for at få vist dine forbindelser:

1. Log på [Power Automate](https://flow.microsoft.com/), vælg tandhjulsikonet i nærheden af øverste højre hjørne, og vælg derefter **Forbindelser**.

    ![Vis forbindelser](./media/gdpr-dsr-export/show-connections.png)
1. Kopiér resultaterne, og indsæt dem derefter i en teksteditor, f.eks. Microsoft Word.
