---
title: Datagrupper for Power Automate | Microsoft Docs
description: Introduktion til datagrupper for Microsoft Power Apps og Power Automate.
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
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298171"
---
# <a name="learn-all-about-data-groups"></a>Få mere at vide om datagrupper

## <a name="what-is-a-data-group"></a>Hvad er en datagruppe?
Datagrupper er en enkel måde at kategorisere tjenester på i en [DLP-politik (forhindring af datatab)](prevent-data-loss.md). De to tilgængelige datagrupper er gruppen **Kun forretningsdata** og gruppen **Ingen tilladte forretningsdata**. Organisationer kan frit afgøre, hvilke tjenester der skal placeres i en bestemt datagruppe. En god måde at kategorisere tjenester på er at anbringe dem i grupper, baseret på deres indflydelse i organisationen. Alle tjenester placeres som standard i gruppen **Ingen tilladte forretningsdata**. Du administrerer tjenesterne i en datagruppe, når du opretter eller ændrer egenskaberne for en DLP-politik fra Administrationscenter.

## <a name="how-data-is-shared-between-data-groups"></a>Hvordan data deles mellem datagrupper
Data kan ikke deles mellem tjenester, der er placeret i forskellige grupper. Hvis du f.eks. placerer SharePoint og Salesforce i gruppen **Kun forretningsdata**, og du placerer Facebook og Twitter i gruppen **Ingen forretningsdata tilladt**, kan du ikke oprette et flow, der flytter data mellem SharePoint og Facebook. Selvom data ikke kan deles mellem tjenester i forskellige grupper, kan du dele data mellem tjenesterne inden for en bestemt gruppe. Da SharePoint og Salesforce var placeret i den samme datagruppe i det foregående eksempel, kan de flows, som dine slutbrugere opretter, dele data mellem SharePoint og Salesforce. På samme måde kan slutbrugerne oprette flows og Power Apps, der deler data mellem Facebook og Twitter. Det vigtigste er, at tjenester i en bestemt gruppe kan dele data, mens tjenester i forskellige grupper ikke kan dele data.  

Derudover skal én datagruppe angives som *standard*gruppe. Som udgangspunkt er gruppen **Ingen tilladte virksomhedsdata** *standard*gruppen, og alle tjenester er i datagruppen. En administrator kan kun ændre standarddatagruppen til datagruppen **Kun virksomhedsdata**. **Bemærk!** Enhver ny tjeneste, der føjes til flowet, bliver placeret i den datagruppe, der er valgt som *standardgruppe*. Det anbefales derfor, at du bevarer **Ingen tilladte virksomhedsdata** som standardgruppe og manuelt føjer tjenester til gruppen **Kun virksomhedsdata**, når din organisation har vurderet effekten af at tillade, at forretningsdata deles med den nye tjeneste.

## <a name="add-services-to-a-data-group"></a>Føje tjenester til en datagruppe
I denne gennemgang føjer vi SharePoint og Salesforce til datagruppen **Kun virksomhedsdata** for DLP-politikken (forhindring af datatab). 

1. Vælg linket **+ Tilføj**, der findes i gruppefeltet **Kun virksomhedsdata** for DLP-politik:    
   ![Tilføj billede](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Vælg SharePoint og Salesforce, og vælg derefter **Tilføj tjenester** for at føje begge til gruppen kun med virksomhedsdata:    
   ![Tilføje tjenestebillede](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Vælg **Gem politik** i menuen øverst:  
   ![Gem politikken](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Bemærk, at både SharePoint og Salesforce nu er i gruppen Kun virksomhedsdata:  
   ![opdateret gruppe med virksomhedsdata](./media/introduction-to-data-groups/add-to-data-group-3.png)   

I denne gennemgang har du føjet SharePoint og Salesforce til datagruppen **Kun virksomhedsdata** for DLP-politikken. Hvis en person, der er del af miljøet for en politik til forebyggelse af datatab, opretter en app, der deler data mellem SharePoint eller Salesforce og en tjeneste i gruppen **Ingen forretningsdata tilladt**, vil appen ikke kunne køres.

## <a name="remove-services-from-a-data-group"></a>Fjerne tjenester fra en datagruppe
Da alle tjenester skal være i en af de tilgængelige datagrupper, kan du fjerne en tjeneste fra en bestemt gruppe ved ganske enkelt at føje tjenesten til en anden gruppe og derefter gemme politikken.  

## <a name="change-the-default-data-group"></a>Skifte standarddatagruppe
I denne gennemgang ændrer vi standarddatagruppen fra datagruppen **Ingen tilladte virksomhedsdata** til datagruppen **Kun virksomhedsdata**.  

**Vigtigt!** Enhver ny tjeneste, der føjes til flowet, placeres i den valgte *standardgruppe*. Det anbefales derfor, at du bevarer **Ingen tilladte virksomhedsdata** som standardgruppen og manuelt føjer tjenester til gruppen **Kun virksomhedsdata**.

1. Vælg **...**, der er placeret i øverste højre hjørne i den datagruppe, du vil angive som standarddatagruppe:    
   ![skifte standardgruppe](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Vælg **Benyt som standardgruppe**:  
   ![skifte standardgruppe](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Vælg **Gem politik** i menuen øverst:  
   ![skifte standardgruppe](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Bemærk, at datagruppen nu er angivet som standarddatagruppe:  
   ![skifte standardgruppe](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Næste trin
* [Få mere at vide om DLP-politikkerne til forebyggelse af datatab](prevent-data-loss.md)
* [Få mere at vide om miljøer](environments-overview-admin.md)   

