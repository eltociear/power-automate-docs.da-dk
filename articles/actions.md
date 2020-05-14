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
ms.openlocfilehash: c165213949d72fa9e7aacbc28d076969677a8802
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296653"
---
# <a name="use-actions"></a>Brug af handlinger


Handlinger åbner op for en lang række muligheder for oprettelse af forretningslogik. I forbindelse med handlinger kan du oprette, opdatere, slette, tildele eller udføre handlingen. Internt opretter en handling en brugerdefineret meddelelse. Udviklere refererer til disse handlinger som "meddelelser". Hver af disse meddelelser er baseret på handlinger, der udføres på en forekomst af et objekt. Hvis målet med en proces er at oprette en post, opdatere den og derefter tildele den, er der tre separate trin. Hvert trin defineres af funktionerne for objektet – ikke nødvendigvis af din forretningsproces.  
  
Handlinger gør det muligt at definere et enkelt verbum (eller en enkelt meddelelse), der stemmer overens med en handling, du skal udføre for virksomheden. Disse nye meddelelser styres af en proces eller funktionsmåde i stedet for det, der kan udføres med et objekt. Disse meddelelser kan svare til verber som Escalate, Convert, Schedule, Route eller Approve – alt det, du har brug for. Tilføjelsen af disse verber er med til at give dig et større ordforråd, så du kan definere dine forretningsprocesser på en mere flydende måde. Du kan bruge dette større ordforråd fra klienter eller integrationer i stedet for at skulle skrive handlingen i klienter. Det gør det også lettere, da du kan administrere og logføre succes eller fejl for hele handlingen som en enkelt enhed.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Konfigurerbare meddelelser  
 Når en handling er defineret og aktiveret, kan en udvikler bruge denne meddelelse som en hvilken som helst anden meddelelse, der leveres af platformen. Men en vigtig forskel er, at nu kan en bruger, der ikke er udvikler, anvende ændringer på det, der skal udføres, når meddelelsen bruges. Du kan konfigurere handlingen til at ændre trin, efterhånden som forretningsprocesserne ændres. En brugerdefineret kode, der bruger meddelelsen, behøver ikke at blive ændret, så længe processens argumenter ikke ændres.  
  
 Processer i arbejdsprocessen og plug-ins indeholder samme funktioner for definition af automatisering. Processer i arbejdsprocessen gør det stadig muligt for en bruger, der ikke er udvikler, at anvende ændringer. Men forskellen er den måde, forretningsprocesserne er udviklet på, og den måde, en udvikler kan skrive kode på. En handling er en meddelelse, der fungerer på samme niveau som alle meddelelser, der leveres af platformen. Udviklere kan registrere plug-ins til handlinger.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Globale meddelelser 
 
 I modsætning til Common Data Service-arbejdsprocesser eller -[plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in) behøver en handling ikke at blive knyttet til et bestemt objekt. Du kan definere "globale" handlinger, der kan kaldes separat.

## <a name="next-steps"></a>Næste trin

[Opret en brugerdefineret handling](create-actions.md)  
  

