---
title: Brug Common Data Service-dialogbokse til vejledte processer (frarådes) | MicrosoftDocs
description: Dialogbokse er de synkrone eller interaktive processer, som indsamler og behandler oplysninger ved hjælp af trinvise scripts for at dirigere brugere gennem en proces
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8af38dd57834df4b93f952ff0b62ac452f82dbf0
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74370784"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Brug Common Data Service-dialogbokse til vejledte processer (frarådes)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[Dialogbokse frarådes](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Du bør erstatte dialogbokse med forretningsprocesforløb eller lærredsapps. Flere oplysninger: [Erstat dialogbokse med forretningsprocesforløb eller lærredsapps](replace-dialogs.md) 

Dialogbokse er de synkrone eller interaktive processer i Common Data Service, som indsamler og behandler oplysninger ved hjælp af trinvise scripts for at dirigere brugere gennem en proces. Du kan f.eks. oprette dialogbokse, der fungerer som en vejledning for dine kundeservicemedarbejdere i forbindelse med sagsløsning og -eskalering. Du kan også oprette dialogbokse til at standardisere salgsprocesser som f.eks. kvalificering af salgsmuligheder og oprettelse af pointmodeller for kundeemner.

## <a name="differences-between-workflows-and-dialogs"></a>Forskelle mellem arbejdsprocesser og dialogbokse

I følgende tabel vises oplysninger om forskellene mellem arbejdsprocesser og dialogbokse i Common Data Service.  


| Arbejdsprocesser     |    Dialogbokse      |
|---------------|--------------|
|                                                                                                  Kan enten startes af en bruger eller kan automatiseres.                                                                                                   |                                                                                          Skal startes af en bruger.                                                                                          |
|                                  Er asynkrone eller processer i realtid og kræver ikke brugerinput for at blive fuldført. Asynkrone processer kører i baggrunden, mens processer i realtid kører med det samme.                                   | Er processer i realtid, der kræver brugerinput for at blive fuldført. Når du kører disse processer, vises en guidelignende grænseflade, så du kan foretage de relevante valg for at køre processerne. |
|                                                    Det objekt, der lagrer oplysninger om en løbende asynkron arbejdsproces er `AsyncOperation`, mens `Process` bruges til realtidsarbejdsprocesser.                                                     |                                                       Det objekt, der lagrer oplysninger, der er genereret af en igangværende dialogboks, er objektet `ProcessSession`.                                                       |
|                  Udløsere understøttes for arbejdsprocesser. Du kan se en liste over understøttede udløsere under [Understøttede typer, udløsere og objekter for processer](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Udløsere understøttes ikke for dialogbokse.                                                                                    |
  
### <a name="see-also"></a>Se også
[Erstat dialogbokse med forretningsprocesforløb eller lærredsapps](replace-dialogs.md)
