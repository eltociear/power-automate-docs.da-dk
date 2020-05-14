---
title: Aktivering af brugerdefinerede handlinger fra en arbejdsproces | Microsoft Docs
description: Lær, hvordan du aktiverer en brugerdefineret handling fra en arbejdsproces
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a35523209e3db8444da71c0757db29fa21de08b3
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3297907"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Aktivere brugerdefinerede handlinger fra en arbejdsproces


Arbejdsprocesser har mange funktioner, der understøtter forskellige virksomhedsscenarier. Kald af grundlæggende databehandlinger for en post, f.eks opret, opdater og slet fra en arbejdsproces, er svaret på forholdsvis mange virksomhedsscenarier. Men hvis du parer funktionerne i arbejdsprocesserne med brugerdefinerede handlinger, der aktiveres direkte fra en arbejdsproces, kan du føje en hel ny række virksomhedsscenarier til dit program uden at skulle skrive kode.  
  
 Lad os se på det scenario, hvor en brugerdefineret handling aktiveres fra en arbejdsproces. Vi aktiverer en brugerdefineret handling for at anmode om den overordnedes godkendelse, når en rabat for en bestemt salgsmulighed overstiger 20 %.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Eksempel: Opret en brugerdefineret handling ved hjælp af salgsmulighedsobjektet
  
1. Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg **Processer**.  
  
2.  Vælg **Ny** på navigationslinjen. Giv processen et navn, og vælg kategorien **Handling**.  
  
 Hvis du vil anmode om godkendelse af rabatten, bruger vi en brugerdefineret handling, vi kalder **Godkendelsesproces**. Vi har tilføjet en inputparameter, **SpecialNotes** og et **Send e-mail**-trin til at oprette en ny meddelelse og sende en anmodning om lederens godkendelse, som vist her.  
  
 ![Tilføj et trin – send mail](media/enable-custom-action-approval-proces-sadd-email.png "Tilføj et trin – send mail")  
  
 Hvis du vil konfigurere mailmeddelelsen, skal du vælge **Angiv egenskaber**. Når formularen åbnes, kan du bruge **formularassistenten** til at tilføje bemærkninger og andre oplysninger i mailen, som fremhævet i skærmbilledet. Du tilføjer de særlige bemærkninger ved at placere markøren, hvor du vil have bemærkningerne vist i meddelelsen, og derefter skal du i **formularassistenten**under **Søg efter** vælge **Argumenter** i den første rulleliste og vælge **SpecialNotes** i den anden rulleliste og derefter vælge **OK**.  
  
 ![Konfigurere mail](media/enable-custom-action-approval-process-setup-email.png "Konfigurer mail")  
  
 Før du kan aktivere handlingen fra en arbejdsproces, skal du aktivere den. Når du har aktiveret handlingen, du kan få vist dens egenskaber ved at vælge **Vis egenskaber**.  
  
 ![Aktivér brugerdefineret handling – godkendelsesproces](media/enable-custom-action-approval-process-activate-action.png "Aktivér brugerdefineret handling – godkendelsesproces")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Aktivér en brugerdefineret handling fra en arbejdsproces  
  
1. Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg **Processer**.   
  
2.  Vælg **Ny** på navigationslinjen. Giv processen et navn, og vælg kategorien **Arbejdsproces**.  
  
 Vi har oprettet en arbejdsproces, der kalder den brugerdefinerede handling i **godkendelsesprocessen**, når lederens godkendelse af en rabat på over 20% for en salgsmulighed er påkrævet.  
  
 ![Angiv handlingsegenskaber fra arbejdsproces](media/enable-custom-action-from-workflow.png "Angiv handlingsegenskaber fra arbejdsproces")  
  
 Du kan angive egenskaber for handlingens inputegenskaber ved at vælge **Angiv egenskaber**. Vi har tilføjet et navn på den konto, der er relateret til salgsmuligheden i de særlige bemærkninger. I **formularassistenten**under **Søg efter** skal du vælge **Firma** i den første rulleliste, vælge **Firmanavn** i den anden rulleliste og derefter vælge **OK**. Egenskaben **Mål** er påkrævet, og den udfyldes af systemet. **{Opportunity(Opportunity)}** i egenskaben **Destination** er den samme salgsmulighed, som den kaldende arbejdsproces kører på. Du kan også vælge en bestemt salgsmulighed for egenskaben Target ved hjælp af opslag.  
  
 ![Angiv inputparametre for handlingen ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Angiv inputparametre for handlingen ApprovalProcess")  
  



