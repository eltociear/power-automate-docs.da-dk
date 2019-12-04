---
title: Power Automate-mobilappen understøtter nu administration af mobilprogrammer i Microsoft Intune. | Microsoft Docs
description: Power Automate-mobilappen understøtter nu administration af mobilprogrammer i Microsoft Intune.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: adfbf357d1ebe31621ecf1703573d86d1e549ca8
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74354730"
---
# <a name="power-automate-mobile-app-supports-microsoft-intune"></a>Power Automate-mobilappen understøtter Microsoft Intune
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Power Automate-mobilappen til iOS og Android understøtter administration af mobilapps (MAM – Mobile Application Management) i Intune uden tilmelding af enheden. Ved hjælp af MAM kan it-administratorer oprette og gennemtvinge politikker for mobildata for at beskytte organisationsdata.

## <a name="why-intune-support-is-important"></a>Hvorfor er understøttelse af Intune vigtig?

Organisationer vil gerne have mere kontrol over de data, der er placeret på medarbejdernes mobilenheder. Organisationer vil måske begrænse, hvordan disse data flyttes til enheden, og sikre, at dataene fjernes, hvis medarbejderen forlader organisationen.

## <a name="what-is-microsoft-application-management-mam"></a>Hvad er administration af mobilapps (MAM)?

MAM gør det muligt for organisationer at oprette politikker, der styrer, hvordan apps bruges i en lejer. Dette omfatter gennemtvingelse af kryptering af appdata, begrænsning af muligheden for at kopiere eller udtrække data til kun godkendte programmer eller gennemtvingelse af en pinkode på en enhed.

### <a name="prerequisites"></a>Forudsætninger

- En [beskyttelsespolitik for apps](https://docs.microsoft.com/intune/app-protection-policies) i Intune.
- En Azure Active Directory-gruppe (Azure AD).
- Firmaportal. En af de vigtigste fordele ved at bruge MAM er, at enhederne ikke behøver at være tilmeldt MAM i Intune. Det eneste, der kræves, er Firmaportal, som er tilgængelig fra App Store og Google Play Butik.
- Version 2.31.0 af Power Automate-mobilappen til iOS, Android eller Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Opret en beskyttelsespolitik for apps, tildel apps til politikken, definer indstillinger, og føj brugere til en Azure AD-gruppe

Før du kan administrere Power Automate-mobilappen, skal du gøre følgende:

1. Opret en beskyttelsespolitik for apps.
1. Tildel Power Automate-mobilappen til beskyttelsespolitikken for apps.
1. Tildel politikindstillingerne. Du kan f.eks. tildele politikken til at kræve en pinkode for at få adgang til den mobilenhed, der kører Power Automate-mobilappen.
1. Anvend beskyttelsespolitikken for apps på en specifik Azure AD-gruppe.
1. Føj alle brugere, som beskyttelsespolitikken for apps gælder for, til Azure AD-gruppen.

Følg disse trin for at oprette en [beskyttelsespolitik for apps](https://docs.microsoft.com/intune/app-protection-policies), der kræver, at brugere af Power Automate-mobilappen angiver en pinkode, før de kan få adgang til appen. 


## <a name="test-the-app-protection-policy"></a>Test beskyttelsespolitikken for apps

Når du har oprettet beskyttelsespolitikken for apps og tildelt brugere til Azure AD-gruppen, er det tid til at bruge Power Automate-mobilappen og bekræfte, at politikken fungerer.

Følg disse trin for at bekræfte, at politikken fungerer:

1. Installér Power Automate-mobilappen på en enhed, hvis platform stemmer overens med en af de platforme, du har defineret i beskyttelsespolitikken for apps.
1. Log på mobilappen med en konto, der er i Azure AD-gruppen, og som begrænser brugen af mobilappen til brugere, der har en pinkode.

Du bliver derefter bedt om følgende:
1. Installér Firmaportal.
1. Angiv din pinkode, hvis du ikke allerede har en pinkode, der overholder kriterierne for beskyttelsespolitikken for apps.


## <a name="learn-more"></a>Få mere at vide

Få mere at vide om, hvordan du opretter en [beskyttelsespolitik for apps](https://docs.microsoft.com/intune/app-protection-policies).

