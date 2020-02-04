---
title: Aktivér brugerdefinerede handlinger fra en arbejdsproces | MicrosoftDocs
description: Få mere at vide om, hvordan du aktiverer en brugerdefineret handling fra en arbejdsproces
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
ms.openlocfilehash: 15cbfdf61a25287714f0244639ec4a3246bd845c
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74355420"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Aktivér brugerdefinerede handlinger fra en arbejdsproces
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Arbejdsprocesser har mange funktioner, der understøtter forskellige virksomhedsscenarier. Kald af grundlæggende databehandlinger for en post, f.eks opret, opdater og slet fra en arbejdsproces, er svaret på forholdsvis mange virksomhedsscenarier. Hvis du kombinerer funktionerne i arbejdsprocesser med effektiviteten af brugerdefinerede handlinger, der kaldes direkte fra en arbejdsproces, føjer du et helt nyt omfang af virksomhedsscenarier til dit program uden at skulle skrive kode.  
  
 Lad os se på et scenarie, hvor en brugerdefineret handling aktiveres fra en arbejdsproces. Vi aktiverer en brugerdefineret handling for at anmode om den overordnedes godkendelse, når en rabat for en bestemt salgsmulighed overstiger 20 %.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Eksempel: Opret en brugerdefineret handling ved hjælp af salgsmulighedsobjektet
  
1. Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg **Processer**.  
  
2.  Vælg **Ny** på navigationslinjen. Navngiv processen, og vælg kategorien **Handling**.  
  
 Til at anmode om en godkendelse af rabatten bruger vi en brugerdefineret handling, der kaldes **Godkendelsesproces**. Vi har tilføjet en inputparameter **SpecialNotes**, og trinnet **Send mail** for at oprette en ny meddelelse og sende en anmodning til den overordnedes godkendelse, som vist her.  
  
 ![Tilføj et trin – send mail](media/enable-custom-action-approval-proces-sadd-email.png "Tilføj et trin – send mail")  
  
 Vælg **Angiv egenskaber** for at konfigurere meddelelsen. Når formularen åbnes, kan du bruge **Formularassistent** til at føje særlige noter og andre oplysninger til meddelelsen, som vist på skærmbilledet. Du tilføjer særlige noter ved at placere markøren, der hvor du vil have noterne vist i meddelelsen. Vælg derefter **Argumenter** under **Søg efter**  i **Formularassistent** på den første rulleliste, og vælg **SpecialNotes** på den anden rulleliste og derefter **OK**.  
  
 ![Konfigurer mail](media/enable-custom-action-approval-process-setup-email.png "Konfigurer mail")  
  
 Før du kan aktivere handlingen fra en arbejdsproces, skal du aktivere den. Når du har aktiveret handlingen, kan du få vist dens egenskaber ved at vælge **Vis egenskaber**.  
  
 ![Aktivér brugerdefineret handling – godkendelsesproces](media/enable-custom-action-approval-process-activate-action.png "Aktivér brugerdefineret handling – godkendelsesproces")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Aktivér en brugerdefineret handling fra en arbejdsproces  
  
1. Åbn [Løsningsoversigt](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), og vælg **Processer**.   
  
2.  Vælg **Ny** på navigationslinjen. Navngiv processen, og vælg kategorien **Arbejdsproces**.  
  
 Vi har oprettet en arbejdsproces, der aktiverer den brugerdefinerede handling **Godkendelsesproces**, når den overordnedes godkendelse af en rabat på mere end 20 % for en salgsmulighed er påkrævet.  
  
 ![Angiv handlingsegenskaber fra arbejdsproces](media/enable-custom-action-from-workflow.png "Angiv handlingsegenskaber fra arbejdsproces")  
  
 Du kan angive handlingens inputegenskaber ved at vælge **Angiv egenskaber**. Vi har tilføjet et navn for den konto, der er relateret til salgsmuligheden i de særlige noter. Vælg **Konto** under **Søg efter** i **Formularassistent** på den første rulleliste, vælg **Kontonavn** på den anden rulleliste, og vælg derefter **OK**. Egenskaben **Target** er påkrævet og udfyldes af systemet. **{Opportunity(Opportunity)}** i egenskaben **Target** er den samme salgsmulighed, som den kaldende arbejdsproces kører på. Du kan også vælge en bestemt salgsmulighed for egenskaben Target ved hjælp af opslag.  
  
 ![Angiv inputparametre for handlingen ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Angiv inputparametre for handlingen ApprovalProcess")  
  



