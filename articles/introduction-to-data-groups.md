---
title: Datagrupper til Power Automate | Microsoft Docs
description: Introduktion til datagrupper til Microsoft Power Apps og Power Automate.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 205857821402a629bebffe005525536ed42f9669
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74355236"
---
# <a name="learn-all-about-data-groups"></a>Få mere at vide om datagrupper
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>Hvad er en datagruppe?
Datagrupper er en nem måde til at kategorisere tjenester i en [politik til forebyggelse af datatab](prevent-data-loss.md). Der er to tilgængelige datagrupper: **Kun forretningsdata** og **Ingen forretningsdata tilladt**. Organisationer bestemmer selv, hvilke tjenester der placeres i de enkelte datagrupper. En god måde at inddele tjenesterne på, er at placere dem i grupper baseret på deres indflydelse på organisationen. Som standard er alle tjenester placeret i datagruppen **Ingen forretningsdata tilladt**. Du kan administrere tjenesterne i en datagruppe, når du opretter eller ændrer egenskaberne for en politik til forebyggelse af datatab fra administrationscenteret.

## <a name="how-data-is-shared-between-data-groups"></a>Sådan deles data mellem datagrupper
Der kan ikke deles data mellem tjenester, der er placeret i forskellige gruppe. Hvis du f.eks. placerer SharePoint og Salesforce i gruppen **Kun forretningsdata**, og du placerer Facebook og Twitter i gruppen **Ingen forretningsdata tilladt**, kan du ikke oprette et flow, der flytter data mellem SharePoint og Facebook. Det er ikke muligt at dele data mellem tjenester i forskellige grupper, men du kan dele data mellem de tjenester, der er placeret i den samme gruppe. Da SharePoint og Salesforce var placeret i den samme datagruppe i det foregående eksempel, kan de flows, som dine slutbrugere opretter, dele data mellem SharePoint og Salesforce. På samme måde kan slutbrugerne oprette flow og Power Apps, der deler data mellem Facebook og Twitter. Det vigtigste er, at tjenesterne i den samme gruppe kan dele data, mens det ikke er muligt at dele data mellem tjenester i forskellige grupper.  

Desuden skal en af datagrupperne være valgt som *standardgruppe*. Som udgangspunkt er gruppen **Ingen forretningsdata tilladt** anvendt som *standardgruppe*, og alle tjenester placeres i den datagruppe. En administrator kan vælge **Kun forretningsdata** som standarddatagruppe. **Bemærk!** Enhver ny tjeneste, der føjes til flowet, bliver placeret i den datagruppe, der er valgt som *standardgruppe*. Derfor anbefaler vi, at du bruger **Ingen forretningsdata tilladt** som standardgruppe, og at du manuelt flytter tjenester til gruppen **Kun forretningsdata**, når organisationen har vurderet, om forretningsdata må deles med den nye tjeneste.

## <a name="add-services-to-a-data-group"></a>Føj tjenester til en datagruppe
I denne gennemgang føjes SharePoint og Salesforce til datagruppen **Kun forretningsdata** i en politik til forebyggelse af datatab. 

1. Vælg linket **+ Tilføj** i gruppefeltet **Kun forretningsdata** i en politik til forebyggelse af datatab:    
   ![Billede af Tilføj](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Vælg SharePoint og Salesforce, og vælg derefter **Tilføj tjenester** for at føje begge til gruppen Kun forretningsdata:    
   ![Billede af Tilføj tjenester](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Vælg **Gem politik** i menuen øverst:  
   ![Gem politik](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Vær opmærksom på, at både SharePoint og Salesforce nu er i gruppen Kun forretningsdata:  
   ![opdateret forretningsdatagruppe](./media/introduction-to-data-groups/add-to-data-group-3.png)   

I denne gennemgang har du føjet SharePoint og Salesforce til datagruppen **Kun forretningsdata** i en politik til forebyggelse af datatab. Hvis en person, der er del af miljøet for en politik til forebyggelse af datatab, opretter en app, der deler data mellem SharePoint eller Salesforce og en tjeneste i gruppen **Ingen forretningsdata tilladt**, vil appen ikke kunne køres.

## <a name="remove-services-from-a-data-group"></a>Fjern tjenester fra en datagruppe
Da alle tjenester skal være i en af de tilgængelige datagrupper, kan du fjerne en tjeneste fra den ene gruppe ved at flytte den til den anden gruppe og derefter gemme politikken.  

## <a name="change-the-default-data-group"></a>Skift standarddatagruppe
I denne gennemgang ændrer vi standarddatagruppen fra datagruppen **Ingen forretningsdata tilladt** til datagruppen **Kun forretningsdata**.  

**Vigtigt!** Enhver ny tjeneste, der føjes til flowet, placeres i den valgte *standardgruppe*. Derfor anbefaler vi, at du bevarer **Ingen forretningsdata tilladt** som standardgruppen, og at du manuelt føjer tjenester til datagruppen **Kun forretningsdata**.

1. Vælg **...** øverst til højre i den datagruppe, du vil vælge som standarddatagruppe:    
   ![Skift standardgruppe](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Vælg **Angiv som standardgruppe**:  
   ![Skift standardgruppe](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Vælg **Gem politik** i menuen øverst:  
   ![Skift standardgruppe](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Bemærk, at datagruppen nu er valgt som standarddatagruppe:  
   ![Skift standardgruppe](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Næste trin
* [Få mere at vide om politikker til forebyggelse af datatab](prevent-data-loss.md)
* [Få mere at vide om miljøer](environments-overview-admin.md)   

