---
title: Få mere at vide om, hvordan du eksporterer løsningsorienterede flow | Microsoft Docs
description: Få mere at vide om, hvordan du eksporterer løsningsorienterede flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
ms.service: flow
ms.topic: article
ms.date: 10/06/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d359f1c065db1c089fb367d5b9ba1188da1e47a3
ms.sourcegitcommit: 1ae0dc87353b2ddec8c639d8a3514b7119401977
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/07/2020
ms.locfileid: "3968278"
---
# <a name="export-a-solution"></a>Eksport af en løsning


Følg disse trin for at flytte din løsning og dens afhængigheder til et nyt miljø:

1. Vælg **Løsninger** på navigationslinjen.
1. Vælg den ikke-administrerede løsning, du vil eksportere, og vælg derefter **Eksportér**. Du kan ikke eksportere administrerede løsninger. Flere oplysninger: [Administrerede og ikke-administrerede løsninger](/power-platform/alm/solution-concepts-alm#managed-and-unmanaged-solutions)
1. Ruden **Før du eksporterer** til højre vises. Vælg mellem følgende indstillinger, og vælg derefter **Næste**:  
    - **Publicer alle ændringer**. Bemærk, at det kun er publicerede komponenter, der eksporteres, når du eksporterer en ikke-administreret løsning. Det anbefales, at du vælger **Publicer alle ændringer** for at sikre, at alle komponenter er inkluderet i den eksporterede løsning. 
    - **Søg efter problemer**. Kør løsningskontrol på løsningen for at finde problemer med ydeevnen og stabiliteten.
1. Ruden **Eksportér denne løsning** til højre vises. Angiv eller vælg mellem følgende indstillinger, og vælg derefter **Eksportér**:  
    - **Versionsnummer**: Power Automate øger automatisk din løsningsversion, samtidig med at den aktuelle version vises. Du kan acceptere standardversionen eller angive din egen. 
    - **Eksportér som**: Vælg pakketypen, enten **Administreret** eller **Ikke-administreret**. Flere oplysninger: [Administrerede og ikke-administrerede løsninger](/power-platform/alm/solution-concepts-alm#managed-and-unmanaged-solutions)

 Det kan tage flere minutter at fuldføre eksporten. Når eksporten er afsluttet, er eksport .zip-filen placeret i mappen Overførsel, der er angivet af din webbrowser.

> [!NOTE]
> Hvis du vil implementere en sundt ALM (Application Lifecycle Management) i organisationen, kan du overveje at bruge et kildekontrolsystem til at gemme og samarbejde om dine løsninger og automatisere eksportprocessen til løsningen. Flere oplysninger: [Grundlæggende om ALM](/power-platform/alm/basics-alm) i Power Platform ALM-guiden.

## <a name="learn-more"></a>Flere oplysninger


* [Opret en løsning](./overview-solution-flows.md)
* [Opret et flow i en løsning](./create-flow-solution.md)
* [Importere en løsning](./import-flow-solution.md)
* [Rediger et løsningsorienteret flow](./edit-solution-aware-flow.md)
