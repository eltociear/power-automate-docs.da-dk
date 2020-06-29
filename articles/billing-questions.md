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
ms.date: 05/07/2020
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: a8b4ee39a7d40df41a1c8012a33860a77a51a092
ms.sourcegitcommit: 8714786a5b632dfd60099871629cf369a31c4125
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346555"
---
# <a name="billing-and-metering-questions"></a>Spørgsmål om fakturering og måling


I denne artikel finder du svar på ofte stillede spørgsmål om fakturering og måling i Power Automate.

>[!NOTE]
> Power Apps og Power Automate bruger en [ny licensmodel](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq), der starter den 1. oktober 2019. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Hvor kan jeg finde ud af, hvilke planer for prisfastsættelse der er tilgængelige?

Se [prissætningssiden](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Hvor kan jeg se min plan?

Se denne [abonnementsside](https://portal.office.com/account/#subscriptions).

## <a name="how-do-i-switch-plans"></a>Hvordan skifter jeg plan?

Vælg **Lær** > **Prisfastsættelse** i den øverste navigationsmenu, og vælg derefter den plan, som du vil skifte til.

![Lær > Prisfastsættelse](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Hvordan kan jeg vide, hvor meget jeg har brugt?

Hvis du har en gratis plan eller en prøveversionsplan, skal du klikke eller trykke på gearikonet i det øverste navigationspanel for at få vist dit aktuelle forbrug i forhold til din plan. 

![Knappen Indstillinger](./media/billing-questions/settings.png)

Hvis du har en betalt plan, samles kørsler i puljer på tværs af alle brugere i organisationen. Vi arbejder på funktioner, der viser tilgængelige kvoter og forbrug på tværs af en organisation.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Hvad sker der, hvis mit forbrug overskrider grænsen?

Power Automate sætter fart på kørslen af dine flows.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Hvor kan jeg finde flere oplysninger om forbrugsgrænserne?

Besøg [siden om prisfastsættelse](https://flow.microsoft.com/pricing/), og se afsnittet **Ofte stillede spørgsmål**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Hvad sker der, hvis jeg forsøger at udføre kørsler for ofte?

Din plan bestemmer, hvor ofte dine flows køres. Hvis du bruger den gratis plan, kan dine flow f.eks. kun køres hvert 15. minut. Hvis et flow udløses mindre end 15 minutter efter dets sidste kørsel, stilles det i kø, indtil de 15 minutter er gået.

## <a name="what-counts-as-a-run"></a>Hvad anses som en kørsel?

Hver gang et flow udløses, uanset om det er automatisk eller manuelt, anses det som en kørsel. Kontrol af nye data anses ikke for at være kørsler.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Er der forskel på Microsoft-konti og arbejds- eller skolekonti, hvad angår fakturering?

Ja. Hvis du logger på med en Microsoft-konto (f.eks. en konto, der ender på @outlook.com eller @gmail.com), kan du kun bruge den gratis version. Hvis du vil udnytte funktionerne i betalingsplanen, skal du logge på med en arbejds- eller skolemailadresse.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Jeg forsøger at opgradere, men får at vide, at min konto ikke er berettiget.

Hvis du vil opgradere, skal du bruge en arbejds- eller skolekonto eller oprette en [Office 365-prøvekonto](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Hvorfor løb jeg tør for kørsler, når mit flow kun havde kørt nogle få gange?

Visse flow køres oftere, end du forventer. Du kan f.eks. oprette et flow, der sender dig en pushmeddelelse, når din chef sender dig en mail. Dét flow skal køre, hver gang du modtager en mail (fra hvem som helst), fordi flowet skal kontrollere, om mailen kommer fra din chef. Denne handling tæller som en kørsel.

Du kan løse dette problem ved at angive alle nødvendige filtre for udløseren. I eksemplet med pushmeddelelse skal du udvide menuen **Avancerede indstillinger** og angive din chefs mailadresse i feltet **Fra**.

## <a name="other-limits-and-caveats"></a>Andre begrænsninger og advarsler

* Hver konto kan have så mange som:
  * 15 brugerdefinerede connectorer.
  * 20 forbindelser pr. API og 100 forbindelser i alt.
* Visse eksterne connectorer, som f.eks. Twitter, implementerer begrænsning af forbindelsen for at styre tjenestens kvalitet. Dine flows kan ikke køre, når begrænsning er aktiveret. Hvis dine flows ikke kan køre, skal du gennemgå de detaljerede oplysninger om kørslen, der ikke kunne køre, i flowets kørselshistorik.
