---
title: Spørgsmål om fakturering og måling | Microsoft Docs
description: Svar på ofte stillede spørgsmål om fakturering og måling i Power Automate
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 3ea993f30f34a9997a1a3a3580b0151e93223d7a
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74356777"
---
# <a name="billing-and-metering-questions"></a>Spørgsmål om fakturering og måling
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

I denne artikel finder du svar på ofte stillede spørgsmål om fakturering og måling i Power Automate.

>[!NOTE]
> Fra og med den 1. oktober 2019 bruger Power Apps og Power Automate en [ny licensmodel](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq). 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Hvor kan jeg finde ud af, hvilke planer for prisfastsættelse der er tilgængelige?

Se [prissiden](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Hvor kan jeg se min plan?

Se [prissiden](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Hvordan skifter jeg plan?

Vælg **Få mere at vide om** > **priser** i den øverste navigationsmenu, og vælg derefter den plan, som du vil skifte til.

![Få mere at vide > Prisfastsættelse](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Hvordan kan jeg vide, hvor meget jeg har brugt?

Hvis du har en gratis version eller en prøveversion, skal du klikke eller trykke på gearikonet i det øverste navigationspanel for at få vist dit aktuelle forbrug i forhold til versionen. 

![Knappen Indstillinger](./media/billing-questions/settings.png)

Hvis du har en betalt plan, samles kørsler i puljer på tværs af alle brugere i organisationen. Vi arbejder på funktioner, der viser tilgængelige kvoter og forbrug på tværs af en organisation.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Hvad sker der, hvis mit forbrug overskrider grænsen?

Power Automate sætter fart i dine kørsler af flow.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Hvor kan jeg finde flere oplysninger om forbrugsgrænserne?

Besøg [siden om prisfastsættelse](https://flow.microsoft.com/pricing/), og se afsnittet **Ofte stillede spørgsmål**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Hvad sker der, hvis jeg forsøger at udføre kørsler for ofte?

Din version bestemmer, hvor ofte dine flows køres. Hvis du bruger den gratis version, kan dine flow f.eks. kun køres hvert 15. minut. Hvis et flow udløses mindre end 15 minutter efter dets sidste kørsel, stilles det i kø, indtil de 15 minutter er gået.

## <a name="what-counts-as-a-run"></a>Hvad anses som en kørsel?

Hver gang et flow udløses, uanset om det er automatisk eller startes manuelt, anses det som en kørsel. Kontrol af nye data, der ikke anses for at være kørsler.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Er der forskel på Microsoft-konti og arbejds- eller skolekonti, hvad angår fakturering?

Ja. Hvis du logger på med en Microsoft-konto (såsom en konto, der ender på @outlook.com eller @gmail.com), kan du kun bruge den gratis version. Hvis du vil udnytte funktionerne i betalingsversionen, skal du logge på med et arbejds- eller skolemailadresse.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Jeg forsøger at opgradere, men får at vide, at min konto ikke er berettiget.

Hvis du vil opgradere, skal du bruge en arbejds- eller skolekonto eller oprette en [Office 365-prøvekonto](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Hvorfor løb jeg tør for kørsler, når mit flow kun havde kørt nogle få gange?

Visse flow køres oftere, end du forventer. Du kan f.eks. oprette et flow, der sender dig en pushmeddelelse, når din leder sender dig en mail. Dét flow skal køre, hver gang du modtager en mail (fra hvem som helst), fordi strømmen skal kontrollere, om mailen kommer fra din leder. Denne handling tæller som en kørsel.

Du kan løse dette problem ved at angive alle nødvendige filtre for udløseren. I eksemplet med pushmeddelelse skal du udvide menuen for **Avancerede indstillinger** og angive din leders mailadresse i feltet **Fra**.

## <a name="other-limits-and-caveats"></a>Andre begrænsninger og advarsler

* Hver konto kan have så mange som:
  * 250 flows.
  * 15 brugerdefinerede connectors.
  * 20 forbindelser pr. API og 100 forbindelser i alt.
* Du kan installere en gateway udelukkende i standardmiljøet.
* Visse eksterne forbindelseskomponenter, som Twitter, implementerer begrænsning (throttling) af forbindelsen for at styre tjenestens kvalitet. Dine flows kan ikke køre, når begrænsning (throttling) er aktiveret. Hvis dine flows ikke kan køre, skal du gennemgå de detaljerede oplysninger om kørslen, der ikke kunne køre, i flowets kørselshistorik.
