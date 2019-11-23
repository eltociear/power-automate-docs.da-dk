---
title: Brug af handlinger | MicrosoftDocs
description: I forbindelse med handlinger kan du oprette, opdatere, slette, tildele eller udføre handlingen. En handling opretter en brugerdefineret meddelelse internt
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e3b5d53e72cff93f853bafd89f8a51200a7e735f
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74354592"
---
# <a name="use-actions"></a>Brug af handlinger
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Handlinger åbner op for en lang række muligheder for oprettelse af forretningslogik. I forbindelse med handlinger kan du oprette, opdatere, slette, tildele eller udføre handlingen. En handling opretter en brugerdefineret meddelelse internt. Udviklere kalder disse handlinger "meddelelser". Hver af disse meddelelser er baseret på de handlinger, der udføres på en objektpost. Hvis målet for en proces er at oprette en post, derefter opdatere den og derefter tildele den, er der tre separate trin. Hvert trin er defineret af funktionaliteten i objektet – ikke nødvendigvis dine forretningsprocesser.  
  
Handlinger gør det muligt at definere et enkelt verbum (eller en meddelelse), der svarer til en handling, du har brug for at udføre for din virksomhed. Disse nye meddelelser drives af en proces eller funktionsmåde, i stedet for hvad der kan foretages med et objekt. Disse meddelelser kan svare til verber som Eskaler, Konverter, Planlæg, Diriger eller Godkend, afhængigt af hvad du har brug for. Tilføjelsen af disse verber er med til at levere en mere omfattende ordliste, så du nemt kan definere dine forretningsprocesser. Du kan anvende denne mere omfattende ordliste fra klienter eller integrationer i stedet for at skulle skrive handlingen i klienter. Det gør det også lettere, fordi du kan administrere og logge gennemførelsen eller den manglende gennemførelse af hele handlingen som en enkelt enhed.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Meddelelser, der kan konfigureres  
 Når en handling er defineret og aktiveret, kan en udvikler bruge denne meddelelse som alle andre meddelelser, der leveres af platformen. En væsentlig forskel er dog, at en person, der ikke er udvikler, kan ændre, hvad der skal ske, når denne meddelelse bruges. Du kan konfigurere handlingen for at redigere trin, efterhånden som dine virksomhedsprocesser ændres. Brugerdefineret kode, der bruger denne meddelelse, behøver ikke at blive ændret, så længe procesargumenterne ikke ændres.  
  
 Arbejdsprocesser og plug-ins leverer fortsat lignende funktionalitet til definition af automatisering. Arbejdsprocesser gør det stadig muligt for en person, der ikke er udvikler, at anvende ændringer. Men forskellen er, hvordan forretningsprocesserne er sammensat, og hvordan en udvikler kan skrive kode. En handling er en meddelelse, der fungerer på samme niveau som en af de meddelelser, der leveres af platformen. Udviklere kan registrere plug-ins til handlinger.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Globale meddelelser 
 
 I modsætning til arbejdsprocesser eller [plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in) i Common Data Service, behøver en handling ikke at være knyttet til et bestemt objekt. Du kan definere "globale" handlinger, der kan kaldes separat.

## <a name="next-steps"></a>Næste trin

[Opret en brugerdefineret handling](create-actions.md)  
  

