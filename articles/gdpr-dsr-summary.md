---
title: Oversigt over anmodninger fra fysiske personer omfattet af GDPR | Microsoft Docs
description: Få mere at vide om, hvordan du besvarer anmodninger i Power Automate om dataemner omfattet af GPDR.
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
ms.date: 08/14/2020
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 9acc41d0aec22f5adcdfb72e0e2dea8583a6013b
ms.sourcegitcommit: 39d7912519ff03dae924023c1a1c320a30efaa81
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2020
ms.locfileid: "3691026"
---
# <a name="responding-to-gdpr-data-subject-requests-for-power-automate"></a>Besvarelse af anmodninger i Power Automate om dataemner omfattet af GDPR


Læs denne artikel for at forberede dig og din organisation på EU's GDPR (General Data Protection Regulation – generel forordning om databeskyttelse). Denne artikel beskriver ikke blot, hvad Microsoft gør for at forberede sig på GDPR, men kommer også med eksempler på, hvad du kan gøre i dag for at overholde GDPR, når du bruger Power Apps, Power Automate og Common Data Service.

## <a name="prerequisites"></a>Forudsætninger

Brugere og administratorer kan udføre handlinger, der er beskrevet i denne artikel.

### <a name="users"></a>Brugere

En bruger skal have en aktiv Azure Active Directory-konto med en [Power Automate-licens](https://preview.flow.microsoft.com/pricing/). Brugere, der ikke opfylder dette krav, skal bede en administrator om at udføre disse handlinger.

### <a name="administrators"></a>Administratorer

Du kan udføre handlinger, der kræver administratorrettigheder, som beskrevet i denne artikel, hvis du logger på [Power Platform Administration](https://admin.powerplatform.microsoft.com/) eller [Power Apps Admin PowerShell](https://go.microsoft.com/fwlink/?linkid=871804) med en konto, der har begge disse tilladelser:

- En betalt licens eller en prøvelicens til Power Apps Plan 2.

    [En licens til en prøveversion](http://make.powerapps.com/trial) udløber efter 30 dage.

- [Office 365-organisationsadministrator](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) eller [Azure Active Directory-organisationsadministrator](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Ikke-administrerede lejere
Hvis du er medlem af en [ikke-administreret lejer](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), dvs., at din Azure AD-lejer ikke har en global administrator, kan du stadig følge de trin, der er beskrevet i denne artikel, til at eksportere og fjerne dine egne personlige data. 

## <a name="responding-to-dsrs-for-power-automate-customer-data"></a>Besvarelse af DSR'er for Power Automate-kundedata

Ifølge GDPR har personer (i forordningen kaldet fysiske personer) ret til at administrere de personlige data, der er blevet indsamlet af en arbejdsgiver eller en anden type agentur eller organisation (kaldet datacontrolleren eller blot controlleren). Personlige data defineres meget bredt under GDPR som data, der vedrører en identificeret eller identificerbar fysisk person. GDPR giver fysiske personer specifikke rettigheder til deres personlige data. Disse rettigheder gør det muligt for brugeren at modtage kopier af personlige data, bede om, at dataene korrigeres, begrænse behandlingen af dem, slette dem eller modtage dem i elektronisk format, så de kan flyttes til en anden controller. En formel anmodning fra en fysisk person til en controller om at behandle dennes personlige data kaldes en DSR-anmodning (Data Subject Rights).

Denne artikel beskriver, hvordan Microsofts produkter, tjenester og administrative værktøjer bruges til at hjælpe domænecontrollere med at finde og behandle personlige data, når de besvarer DSR-anmodninger. I artiklen forklares det især, hvordan du kan finde, få adgang til og behandle personlige data, der er placeret i Microsofts cloud. Her får du et hurtigt overblik over de processer, der er beskrevet i denne vejledning:

1. Søg: Med søge- og registreringsværktøjer kan du nemmere finde kundedata, der er omfattet af en DSR. Når du har indsamlet de dokumenter, der eventuelt skal behandles, kan du udføre en eller flere af de DSR-handlinger, der er beskrevet i følgende trin, for at besvare anmodningen. Det kan også være, at du finder ud af, at anmodningen ikke opfylder din organisations retningslinjer for besvarelse af DSR-anmodninger. [DSR Discovery-dokumentation til Power Automate](gdpr-dsr-discovery.md)

1. Få adgang: Hent de personlige data, der er placeret i Microsofts cloud, og hvis der er anmodet om det, kan du oprette en kopi af dem, der kan være tilgængelige for den fysiske person.

1. Ret: Foretag ændringer eller udfør andre anmodede handlinger på de personlige data, hvor det er relevant.

    Hvis en fysisk person beder dig om at berigtige de personlige data, der findes i din organisation, skal du og din organisation finde ud af, om anmodningen kan imødekommes eller ej.  Korrigering af dataene kan omfatte redigering, ændring eller fjernelse af personlige data.

    Du kan bruge Azure Active Directory til at administrere Power Automate-brugeres identiteter. Erhvervskunder kan håndtere DSR-anmodninger om berigtigelse, herunder begrænsede redigeringsfunktioner, afhængigt af den relevante Microsoft-tjeneste.  Som databehandler giver Microsoft ikke mulighed for at rette logfiler, der oprettes af systemet, da disse logfiler afspejler faktuelle aktiviteter og udgør en historisk fortegnelse over hændelser i Microsoft-tjenester.  [Få mere at vide om DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Begræns: Begræns behandlingen af personlige data ved enten at fjerne licenser til forskellige onlinetjenester eller ved at deaktivere de ønskede tjenester, hvor det er muligt. Du kan også fjerne data fra Microsofts Cloud og bevare dem i det lokale miljø eller på en anden placering.

    De registrerede kan anmode om at begrænse behandlingen af deres personlige data.  Microsoft leverer API'er (Application Programming Interface – programmeringsgrænseflader til programmerer) og brugergrænseflader til dette formål.  På disse grænseflader kan virksomhedskundernes lejeradministratorer administrere DSR-anmodningerne via en kombination af at eksportere data og slette data. En kunde kan (1) eksportere en elektronisk kopi af personlige data for brugeren, herunder konti, systemoprettede logge og tilknyttede logge, og herefter (2) slette kontoen og tilknyttede data, der findes i Microsoft-systemer.

1. Slet: Fjern permanent de personlige data, der er lagret i Microsofts cloud. [Få mere at vide om, hvordan du sletter personlige data](gdpr-dsr-delete.md).

1. Eksportér: Forsyn den registrerede med en elektronisk kopi (i et maskinlæsbart format) af de personlige data. I hvert afsnit i denne artikel beskrives de tekniske procedurer, som en datacontrollerorganisation kan udføre for at besvare en DSR-anmodning om personlige data i Microsofts cloud. [Få mere at vide om, hvordan du eksporterer personlige data](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Systemgenererede logge

I denne [vejledning](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) kan du finde flere oplysninger om systemoprettede logfiler til Power Automate.
