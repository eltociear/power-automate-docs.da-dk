---
title: Design flow med Microsoft Visio | Microsoft Docs
description: Gør brug af organisationens Visio-ekspertise til at skabe almindelige modeller som udgangspunkt for at oprette flow.
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
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1df42c58cb02f8d62e016b071b3ce556b06a0efe
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195882"
---
# <a name="design-flows-in-microsoft-visio"></a>Design flow i Microsoft Visio


Power Automate-designeren er et meget omfattende værktøj, hvori du kan konfigurere alle detaljer for din logik. Det kan dog nogle gange være en god idé kun at skitsere din flowlogik, før du begynder at oprette et flow. Det gør du ved at bruge Microsoft Visio direkte fra Power Automate.

>[!TIP]
> Mange processer deler en fælles model blot med mindre variationer på tværs af en organisation. Du kan spare tid i din organisation ved at bruge Visio til at oprette en mastermodel for arbejdsprocessen, som andre derefter kan justere med specialiserede parametre.

## <a name="prerequisites"></a>Forudsætninger

- En Power Automate-konto.
- Microsoft Visio-skrivebordsprogrammet (engelsk version).
- Ekspertise i at bruge Microsoft Visio.

## <a name="design-a-workflow-in-visio"></a>Design en arbejdsproces i Visio

1. Log på [Power Automate](https://flow.microsoft.com).
1. Vælg **Skabeloner** i venstre sidepanel.

     ![Vælg skabeloner i venstre panel](./media/visio-flows/templates-from-left-panel.png)

1. Vælg **Visio** på listen.

     ![Filtrer efter Visio-skabeloner](./media/visio-flows/select-visio.png) 

1. Vælg skabelonen **Grundlæggende BPMN-diagram til flow** på listen over de viste **Visio**-skabeloner.

     ![Vælg en Visio-skabelon](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >Visio advarer dig om, at filer fra internettet kan beskadige din enhed. Hvis du er tryg, skal du vælge **Ja** i advarselsmeddelelsen.

     ![Note med advarsel om filer fra internettet](./media/visio-flows/visio-warning.png)

1. Visio-designer starter.

     ![Visning af Visio designeren](./media/visio-flows/visio-designer.png)


1. Brug grundlæggende BPMN-figurerne til at [designe din arbejdsproces](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a).

   ![Grundlæggende BPMN-figurer](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-power-automate"></a>Forbered eksport af din arbejdsproces til Power Automate

Følg disse trin for at forberede din arbejdsproces, så du kan eksportere den til Power Automate.

1. Vælg fanen **Proces**.
1. Vælg **Forbered til eksport** i gruppen af ikoner til **Power Automate**.

   ![Vælg ikonet Forbered til eksport](./media/visio-flows/prepare-export-icon.png)
   
   Gruppen **Forbered til eksport** åbnes.

   ![Gruppen Forbered til eksport](./media/visio-flows/prepare-export-group.png)

1. På fanen **Flowtilknytning** i gruppen **Forbered til eksport** skal du knytte dit BPMN-diagram til kontrolelementer i Power Automate. 

1. Under fanen **Udløsere og handlinger** i gruppen **Forbered til eksport** skal du knytte dit BPMN-diagram til Power Automate-udløsere og -handlinger ved at vælge hver figur og derefter vælge enten en udløser eller en handling for at repræsentere den pågældende figur i Power Automate.

Din arbejdsproces er klar til at blive eksporteret, når der ikke er flere problemer i kontrolelementet **Forbered til eksport**.

![Ingen problemer](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>Eksportér din arbejdsproces
1. Vælg knappen **Eksporter til Flow** for at eksportere dit arbejdsprocesdiagram til Power Automate.
1. Navngiv dit flow, og vælg derefter knappen **Opret flow**.
   
   ![Opret flowet](./media/visio-flows/export-create-flow.png)

1. Du bør se en rapport for vellykket handling, der ligner denne.

    ![Vellykket](./media/visio-flows/export-create-flow-success.png)

Du kan nu køre eller redigere dit flow fra Power Automate-designeren ligesom med alle andre flow.

>[!TIP]
> Brug egenskaberne for deling og kommentering i Visio til at samarbejde med flere interessenter og hurtigt oprette en komplet arbejdsproces.

## <a name="learn-more"></a>Få mere at vide

- [Introduktion til Power Automate](getting-started.md) 
- [Skab flow med flere trin](multi-step-logic-flow.md)
- [Design et flow med Microsoft Visio](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
