---
title: Power Automate til virksomhedsudviklere, ISV'er og partnere | Microsoft Docs
description: En introduktion til udvikling af løsninger for Power Automate.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 85a480599c908dfddc17d2d3f78a0570efa3b5aa
ms.sourcegitcommit: 13dec60229deeac4233c66e625a3d0cf33dfbc43
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/31/2020
ms.locfileid: "3644202"
---
# <a name="power-automate-for-enterprise-developers-isvs-and-partners"></a>Power Automate til virksomhedsudviklere, ISV'er og partnere
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Som udvikler kan du udvide Power Automate, så organisationer og kunder får endnu mere effektive løsninger.

## <a name="power-automate-for-enterprise-developers"></a>Power Automate til virksomhedsudviklere

Som virksomhedsudvikler sætter du din organisation i stand til at bygge robuste, skræddersyede løsninger i Power Automate.

- **Byg brugerdefinerede connectorer**: Udvikl brugerdefinerede connectorer for at oprette forbindelse til organisationens data og webtjenester via Power Automate. [Få mere at vide](https://docs.microsoft.com/connectors/custom-connectors/)

- **Byg Azure Functions**: Byg Azure Functions for at udvide apps med brugerdefineret logik på serversiden. [Få mere at vide](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Integrer Power Automate**: Integrer Power Automate direkte på dit website for at oprette integrerede løsninger, der indeholder arbejdsprocesser eller processer, hvor personer i organisationen allerede udfører deres arbejde. [Få mere at vide](embed-flow-dev.md)

## <a name="power-automate-for-isvs-and-microsoft-partners"></a>Power Automate til ISV'er og Microsoft-partnere

Som Microsoft-partner eller uafhængig softwareproducent (ISV) kan du sætte skub i kundens implementering ved at udvide dine produkter, så de kan integreres med kundernes data og forretningsprocesser. Du kan også tilføje og tilpasse arbejdsgange for at automatisere forretningsprocesser som en del af dit program. Når du har gennemgået de syv trin nedenfor, kan dit program udnytte et robust program for arbejdsgange i cloudmiljøet, som kan oprette forbindelse til mere end 200 forskellige tjenester.

| Fase | Trin | Hvornår er der brug for det? |
| --- | --- | --- |
| Udvikling | 1. Byg en brugerdefineret connector til dine data | Hvis du vil vise dine egne ISV-data i Power Apps eller Power Automate |
| Udvikling | 2. Tilføj support til din applikation for at godkende brugere med Azure Active Directory (Azure AD) | Hvis du vil integrere brugergrænsefladen eller listen for Power Automate i Microsoft AppSource | 
| Udvikling | 3. Integrer brugergrænsefladen for Power Automate i din applikation ved hjælp af vores webbaserede iframe | Hvis du vil inkludere flowoprettelse eller -administration i dit program | 
| Udvikling | 4. Opret og publicer flowskabeloner | Hvis du vil bygge flows til dine kunder på forhånd | 
| Udvikling | 5. Tilføj applikationslogik for at udrulle flows programmatisk | Hvis du automatisk vil udrulle dine forudbyggede flows for dine kunder | 
| Distribution | 6. Tildel dine kunder licenser til Microsoft Flow via Microsoft Cloud Solution Provider-programmet | Hvis dine kunder ikke har licens til Office 365 eller Dynamics 365 |
| Distribution | 7. Vis din løsning på Microsoft AppSource | Anbefales til at øge synligheden af din ISV-løsning |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. Oprettelse af forbindelse til dine API'er ELLER mulighed for af oprette forbindelse til dine API'er for kunder

Som ISV har du ofte data, der er beskyttet af ejendomsret, som dine kunder skal have adgang til via dine flows. Du kan give adgang til dine data via en brugerdefineret connector. [Få mere at vide](https://docs.microsoft.com/connectors/custom-connectors/)

Når der er oprettet adgang, er der to måder, du kan gøre connectoren tilgængelig for dine kunder på:
- Connectoren kan udrulles i kundens lejer via REST API'er eller PowerShell.
- Hvis du vil gøre den brugerdefinerede connector offentligt tilgængelig, kan du indsende connectoren til certificering. [Få mere at vide](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Godkendelse 

Hvis du vil kalde REST API'er og integrere en godkendt brugergrænseflade, skal din applikation bruge enkeltlogon, samlet i Azure AD, for at godkende slutbrugere og kunder. [Her](https://identity.microsoft.com/) kan du finde oplysninger om, hvordan du aktiverer samlet SSO i AAD. Vi understøtter ikke uautoriseret adgang eller adgang med andre identitetsudbydere end Azure AD. 

### <a name="3-embedding-ui-components"></a>3. Integration af brugergrænsefladekomponenter

Integrer Power Automate i din app for at aktivere dyb integration i kontekst mellem din app og alle de andre tjenester, som understøttes af Power Automate. [Få mere at vide](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Opret og publicer flowskabeloner

Når du har fået en connector, skal du udgive skabeloner, der viser, hvordan din tjeneste bruges. Disse skabeloner fungerer som eksempler for brugerne, som derefter kan udvikle deres egne unikke arbejdsprocesser. [Få mere at vide](../publish-a-template.md)

### <a name="5-deployment"></a>5. Implementering

Hvis du vil give slutbrugerne adgang til flows, de kan bruge automatisk, skal du udrulle disse flows i brugerens Azure AD-lejer. Brug en udviklingspakke, som du udruller vha. vores REST API'er eller PowerShell. [Få mere at vide]( https://docs.microsoft.com/powerapps/administrator/export-import-packages)

### <a name="6-licensing"></a>6. Licensering

hvis dine kunder allerede har enten Office 365 eller Dynamics 365, og disse licenser er knyttet til de identiteter, brugerne logger på Azure AD med, kræves der ikke yderligere licenser af dig for at anvende standard-connectorer. Brugerne skal have en af [Power Automate-licenserne](https://preview.flow.microsoft.com/pricing/) for at bruge Premium- og brugerdefinerede connectorer. Hvis dine kunder ikke bruger Office 365 eller Dynamics 365, skal du dog have brugsrettigheder til Power Automate på deres vegne, så de har licens til at udnytte disse integrerede komponenter i dit program.

Vi tilbyder [Microsoft Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider)-programmet, så du kan få licenser på vegne af dine kunder. Der er to forskellige [prisplaner](https://flow.microsoft.com/pricing/) til Power Automate, hvor du kan se flere oplysninger om planerne og funktionerne.

### <a name="7-list-on-appsource"></a>7. Vis på AppSource

Når du har integreret Power Automate i din applikation, kan du få den vist i AppSource. Ved hjælp af AppSource kan du generere nye kundeemner til din virksomhed ved at oprette en app og publicere den på AppSource, så nye kunder kan teste den. [Få mere at vide](dev-appsource-test-drive.md)
