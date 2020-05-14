---
title: Brug dialogbokse i Common Data Service til automatiserede processer (frarådet) | Microsoft Docs
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
ms.openlocfilehash: 69b8d448a3bb2636f4804fe75645467ca6bd081d
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3298413"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Brug dialogbokse i Common Data Service til automatiserede processer (frarådet)


[Dialogbokse frarådes](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Du bør erstatte dialogbokse med forretningsprocesforløb eller lærredsapps. Flere oplysninger: [Udskift dialogbokse med forretningsprocesforløb eller lærred-apps](replace-dialogs.md) 

Dialoger er synkrone eller interaktive processer i Common Data Service, der indsamler og behandler oplysninger ved hjælp af trinvise scripts, der vejleder brugerne gennem en proces. Du kan for eksempel oprette dialoger, der fungerer som en vejledning for dine servicerepræsentanter til sagsløsning og sagseskalering. Du kan også oprette dialogbokse til at standardisere salgsprocesser som f.eks. kvalificering af salgsmuligheder og oprettelse af pointmodeller for kundeemner.

## <a name="differences-between-workflows-and-dialogs"></a>Forskelle mellem arbejdsprocesser og dialogbokse

Følgende tabel indeholder oplysninger om forskellene mellem arbejdsprocesser og dialogbokse i Common Data Service.  


| Arbejdsprocesser     |    Dialogbokse      |
|---------------|--------------|
|                                                                                                  Kan enten startes af en bruger eller kan automatiseres.                                                                                                   |                                                                                          Skal startes af en bruger.                                                                                          |
|                                  Er asynkrone eller processer i realtid og kræver ikke input fra brugeren til at køre for udførelse. Asynkrone processer køres i baggrunden, mens processer i realtid køres umiddelbart.                                   | Er processer i realtid, der kræver input fra brugeren til at køre for udførelse. Når du kører disse processer, præsenteres en guidelignende grænseflade til dig, så du kan foretage de relevante valg til at køre processerne. |
|                                                    Den enhed, der gemmer oplysninger om en asynkron arbejdsproces er `AsyncOperation`, mens en `Process` bruges til en arbejdsproces i realtid.                                                     |                                                       Den enhed, der lagrer oplysninger, der er genereret af en løbende dialog, er `ProcessSession` enheden.                                                       |
|                  Udløsere understøttes for arbejdsprocesser. Du kan se en liste over understøttede udløsere under [Understøttede typer, udløsere og objekter for processer](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Udløsere understøttes ikke for dialogbokse.                                                                                    |
  
### <a name="see-also"></a>Se også
[Erstat dialogbokse med forretningsprocesforløb eller lærredsapps](replace-dialogs.md)
