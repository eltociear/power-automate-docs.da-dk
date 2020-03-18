---
title: Oversigt over anmodninger om GDPR-data fra fysiske personer for Microsoft-konti (MSA) | Microsoft Docs
description: Få mere at vide om, hvordan du besvarer anmodninger fra registrerede omfattet af GPDR for Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: c785a900b0b92a22efc7559674965d5a105a5f51
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79194778"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Svar på anmodninger om rettigheder fra fysiske personer omfattet af GDPR


I denne artikel beskrives EU's generelle forordning om databeskyttelse (GDPR), og den indeholder trin til, hvordan du kan overholde GDPR for de Power Automate-brugere, der godkendes via Microsoft-konti (MSA).

## <a name="prerequisites"></a>Forudsætninger

Du skal have en MSA med en [gratis Power Automate-licens](https://flow.microsoft.com/pricing/) for at kunne udføre trinnene i denne artikel.

>[!TIP]
> Oplysninger om overholdelse af GDPR er også tilgængelige for de brugere, som godkendes ved hjælp af [Azure Active Directory-konti](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-power-automate-customer-data"></a>Svar på DSR-anmodninger om Power Automate-kundedata

En formel anmodning fra en fysisk person til en controller om at behandle dennes personlige data kaldes en DSR-anmodning (Data Subject Rights). I GDPR defineres personlige data som **alle de data, der er relateret til en identificeret eller identificerbar fysisk person**. Ifølge GDPR har personer (i forordningen kaldet fysiske personer) ret til at administrere de personlige data, der er blevet indsamlet af en arbejdsgiver, et agentur eller en organisation (kaldet datacontrolleren eller blot controlleren). Disse rettigheder omfatter:

* Hentning af kopier af personlige data.
* Anmodning om rettelser til personlige data.
* Begrænsning af behandlingen af personlige data.
* Sletning af personlige data.
* Modtagelse af personlige data i elektronisk format, så dataene kan flyttes til en anden controller.

Microsoft tilbyder produkter, tjenester og værktøjer, som controllere kan bruge til at behandle personlige data, når de besvarer DSR-anmodninger vedrørende data i clouden.

Her er en oversigt over de processer, der er beskrevet i denne vejledning:

1. **Find**: Med søge- og registreringsværktøjer kan du nemmere finde de kundedata, der er omfattet af en DSR-anmodning. Hvis de dokumenter, du indsamler, opfylder vejledning til at træffe foranstaltninger, kan du udføre en eller flere af de DSR-handlinger, der er beskrevet i følgende trin. Du kan finde flere oplysninger i [Power Automate DSR Discovery-dokumentationen til Microsoft-konti](gdpr-dsr-discovery-msa.md). Eller du finder måske ud af, at anmodningen ikke opfylder din controllers retningslinjer for besvarelse af DSR-anmodninger.

1. **Få adgang**: Hent de personlige data, der er placeret i Microsofts cloud, og hvis der er anmodet om det, kan du oprette en kopi af disse data, som den fysiske person har adgang til.

1. **Korriger**: Foretag ændringer, eller implementer andre handlinger, der er anmodet om, for de private oplysninger, hvis det er relevant.

1. **Begræns**: Begræns behandlingen af de private oplysninger enten ved at fjerne licenser til forskellige onlinetjenester eller ved at deaktivere de relevante tjenester, hvor det er muligt. Du kan også fjerne data fra Microsofts cloud og opbevare dem i det lokale miljø eller et andet sted.

1. **Slet**: Fjern permanent de private oplysninger, der er lagret i Microsoft-cloudmiljøet. Få mere at vide om, hvordan du [sletter personlige data for Microsoft-konti](gdpr-dsr-delete-msa.md). Få mere at vide om, hvordan du [lukker en Microsoft-konto](gdpr-dsr-accountclose-msa.md).

1. **Eksportér**: Opret en elektronisk kopi (i et computerlæsbart format) af de personlige data. [Få mere at vide om, hvordan du eksporterer personlige data for Microsoft-konti](gdpr-dsr-export-msa.md).
