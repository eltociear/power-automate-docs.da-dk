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
ms.openlocfilehash: ca3271f7c61c6835c856bc363f64882802f1556f
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79195606"
---
# <a name="learn-all-about-data-groups"></a>Få mere at vide om datagrupper

## <a name="what-is-a-data-group"></a>Hvad er en datagruppe?
Datagrupper er en nem måde at kategorisere tjenesteydelser inden for en [DLP-politik (forebyggelse af datatab)](prevent-data-loss.md). Der findes to datagrupper: gruppen **Business data only** (Kun firmadata) og gruppen **No business data allowed** (Firmadata er ikke tilladt). Organisationer kan frit bestemme, hvilke tjenester der er placeret i en bestemt datagruppe. Det er en god ide at kategorisere tjenesterne efter, i hvor høj grad de påvirker organisationen. Alle tjenester er som standard placeret i datagruppen **No business data allowed** (Firmadata er ikke tilladt). Du kan administrere tjenester i en datagruppe, når du opretter eller redigerer egenskaberne for en DLP-politik fra Admin Center.

## <a name="how-data-is-shared-between-data-groups"></a>Sådan deles data mellem datagrupper
Der kan ikke deles data mellem tjenester, der er placeret i forskellige gruppe. Hvis du f.eks. placerer SharePoint og Salesforce i gruppen **Kun forretningsdata**, og du placerer Facebook og Twitter i gruppen **Ingen forretningsdata tilladt**, kan du ikke oprette et flow, der flytter data mellem SharePoint og Facebook. Det er ikke muligt at dele data mellem tjenester i forskellige grupper, men du kan dele data mellem de tjenester, der er placeret i den samme gruppe. Da SharePoint og Salesforce var placeret i den samme datagruppe i det foregående eksempel, kan de flows, som dine slutbrugere opretter, dele data mellem SharePoint og Salesforce. På samme måde kan slutbrugerne oprette flow og Power Apps, der deler data mellem Facebook og Twitter. Det vigtigste er, at tjenester i en bestemt gruppe kan dele data, mens tjenester i forskellige grupper ikke kan dele data.  

Herudover skal en af datagrupperne være angivet som *standardgruppen*. Indledningsvist er gruppen **No business data allowed** (Firmadata er ikke tilladt) *standardgruppen*, og alle tjenester er i datagruppen. En administrator kan vælge **Kun forretningsdata** som standarddatagruppe. **Bemærk!** Enhver ny tjeneste, der føjes til flowet, bliver placeret i den datagruppe, der er valgt som *standardgruppe*. Derfor anbefaler vi, at du bruger **Ingen forretningsdata tilladt** som standardgruppe, og at du manuelt flytter tjenester til gruppen **Kun forretningsdata**, når organisationen har vurderet, om forretningsdata må deles med den nye tjeneste.

## <a name="add-services-to-a-data-group"></a>Føj tjenester til en datagruppe
I denne gennemgang føjer vi SharePoint og Salesforce til datagruppen **Business data only** (Kun firmadata) for en DLP-politik. 

1. Vælg linket **+ Add** (+Tilføj), der er placeret i gruppeboksen **Business data only** (Kun firmadata) for en DLP-politik:    
   ![Billede af Add (Tilføj)](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Vælg SharePoint og Salesforce, og vælg derefter **Add services** (Tilføj tjenester) for at tilføje begge to til gruppen kun med firmadata:    
   ![Billede af Add services (Tilføj tjenester)](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Vælg **Save Policy** (Gem politik) i den øverste menu:  
   ![Gem politik](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Bemærk, at både SharePoint og Salesforce nu er i gruppen, der kun indeholder firmadata:  
   ![Opdateret firmadatagruppe](./media/introduction-to-data-groups/add-to-data-group-3.png)   

I denne gennemgang har du føjet SharePoint og Salesforce til datagruppen **Kun forretningsdata** i en politik til forebyggelse af datatab. Hvis en person, der er del af miljøet for en politik til forebyggelse af datatab, opretter en app, der deler data mellem SharePoint eller Salesforce og en tjeneste i gruppen **Ingen forretningsdata tilladt**, vil appen ikke kunne køres.

## <a name="remove-services-from-a-data-group"></a>Fjern tjenester fra en datagruppe
Eftersom alle tjenester skal være i en af de tilgængelige datagrupper, skal du, hvis du vil fjerne en tjeneste fra en bestemt gruppe, blot føje tjenesten til en anden gruppe og derefter gemme politikken.  

## <a name="change-the-default-data-group"></a>Rediger standarddatagruppen
I denne gennemgang ændrer vi standarddatagruppen fra datagruppen **Ingen forretningsdata tilladt** til datagruppen **Kun forretningsdata**.  

**Vigtigt!** Enhver ny tjeneste, der føjes til flowet, placeres i den valgte *standardgruppe*. Derfor anbefaler vi, at du bevarer **Ingen forretningsdata tilladt** som standardgruppen, og at du manuelt føjer tjenester til datagruppen **Kun forretningsdata**.

1. Vælg **...** øverst til højre i datagruppen, hvis du vil angive den som standarddatagruppen:    
   ![skift standardgruppe](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Vælg **Set as default group** (Angiv som standardgruppe):  
   ![skift standardgruppe](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Vælg **Save Policy** (Gem politik) i den øverste menu:  
   ![Skift standardgruppe](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Bemærk, at datagruppen nu er angivet som standarddatagruppen:  
   ![Skift standardgruppe](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Næste trin
* [Få mere at vide om politikker til forebyggelse af datatab](prevent-data-loss.md)
* [Få mere at vide om miljøer](environments-overview-admin.md)   

