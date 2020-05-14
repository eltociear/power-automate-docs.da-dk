---
title: Anvend brugerdefinerede kontrolelementer i forretningsprocesflow | Microsoft Docs
description: Få mere at vide om, hvordan du anvender brugerdefinerede kontrolelementer i trinnene i et forretningsprocesflow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cd312fea655dfc652cf92a440801da2fdb17ebe4
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297027"
---
# <a name="use-custom-controls-in-business-process-flows"></a>Anvend brugerdefinerede kontrolelementer i forretningsprocesflow

Med forretningsprocesflow får du hjælp til at få arbejdet udført i form af faser og trin. Faserne fortæller dig, hvor du befinder dig i processen, mens trinnene er handlingselementer, der fører til et ønsket resultat. Trin i en forretningsproces er bundet til felter i Common Data Service. Ud over standardvisualiseringerne for felttypen (tekstfelter, rullemenuer osv.) kan du anvende brugerdefinerede kontrolelementer til at føje omfattende visualiseringer (f.eks. skydere, radiale knapper, LinkedIn-kontrolelement og meget mere) til trinnene i forretningsprocesflowet og give brugerne af din forretningsproces engagerende oplevelser.

## <a name="adding-custom-controls-to-a-business-process"></a>Tilføjelse af brugerdefinerede kontrolelementer til et forretningsprocesflow

Lad os sige, at du vil føje en radial knap til trinnet **Estimeret budget** og en flipswitch til trinnet **Identificer beslutningstager** i Kundeemne til salgsproces for salgsmulighed. 

![Oversigt](./media/custom-controls/overview.png)

Her er de trin, du skal følge for at føje brugerdefinerede kontrolelementer til et forretningsprocesflow:

1. Konfigurer brugerdefinerede kontrolelementer i en relateret enhedsformular.
1. Generering og eksport af formularen til forretningsprocesflow.
1. Kopiér brugerdefinerede kontrolelementkonfigurationer til forretningsprocesflowformularen fra den relaterede enhedsformular.
1. Importer tilpasningerne tilbage til Common Data Service.

Følg disse trin for at få en [detaljeret gennemgang af tilføjelsen af brugerdefinerede kontrolelementer](https://powerusers.microsoft.com/t5/Power-Automate-Community-Blog/Preview-Custom-Controls-in-Business-Process-Flows/ba-p/263237) til trinnene i forretningsprocesflow.






