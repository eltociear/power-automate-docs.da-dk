---
title: Spørgsmål og svar vedrørende Flow-tilmelding i organisationen | Microsoft Docs
description: Ofte stillede spørgsmål og svar vedrørende Flow-licenser, -administration og -brugertilmelding i din Office 365-lejer
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/05/2016
ms.author: stepsic
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 22fa35d40dbb198b376150f144d4de11585fc7ca
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74375177"
---
# <a name="flow-in-your-organization-qa"></a>Flow i organisationen, Ofte stillede spørgsmål
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
I dette emne beskrives det, hvordan brugere i organisationen kan bruge Flow, og hvordan du kan styre tjenesten Flow.

## <a name="signing-up-for-flow"></a>Tilmelding til Flow
### <a name="what-is-power-automate"></a>Hvad er Power Automate?
Power Automate er en offentlig cloudtjeneste, der hjælper enkeltpersoner og teams med at konfigurere automatiserede arbejdsprocesser mellem deres favoritprogrammer og -tjenester for at synkronisere filer, få meddelelser, indsamle data og meget mere. 

### <a name="how-do-people-sign-up-for-flow"></a>Hvordan tilmelder man sig Flow?
Enkeltpersoner kan tilmelde sig Flow på to måder gennem webportalen:

#### <a name="option-1"></a>Mulighed 1
Alle kan tilmelde sig ved at gå til [flow.microsoft.com](https://flow.microsoft.com), vælge **Tilmeld dig gratis** og derefter fuldføre tilmeldingsprocessen for Flow via [admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) eller [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Mulighed 2
Alle kan tilmelde sig ved at gå til [flow.microsoft.com](https://flow.microsoft.com), vælge **Log på**, logge på med deres arbejds- eller skolemail eller personlige mail og acceptere vilkårene for anvendelse af Flow.    

Når en bruger i organisationen tilmelder sig Flow med mulighed 2, får den pågældende bruger automatisk tildelt en gratis Power Automate-licens.

Du finder flere oplysninger under [Tilmeld dig Flow](sign-up-sign-in.md).

### <a name="what-is-the-power-automate-free-plan"></a>Hvad er den gratis plan til Power Automate?

Den gratis plan i Power Automate bruges kun til sporingsformål. Aktivering eller deaktivering af planen har ingen effekt på en brugers mulighed for at oprette flow. Hvis du deaktiverer den gratis plan i Power Automate, aktiveres den igen, når en bruger logger på. Dette er den forventede funktionsmåde.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>Kan jeg blokere for en anden persons tilmelding til Flow?
Power Automate er en fuldt offentlig cloudtjeneste, og alle i verden kan tilmelde sig og bruge den til at automatisere deres daglige opgaver. Hvis du vil bruge Power Automate, er der er intet krav om, at brugerne har eller bruger en Office 365-konto. Derfor findes der ingen mekanisme, der på nuværende tidspunkt giver dig mulighed for at forhindre en person i at bruge Flow (da det er muligt for alle mennesker i verden, uanset deres mailadresse).

Men hvis en person tilmelder sig Power Automate, og du vælger ikke at understøtte dem i din organisation, kan de på ingen måde påføre virksomheden omkostninger. Når en person tilmelder sig Power Automate, er relationen mellem denne person og Microsoft, som det er tilfældet med mange andre cloudtjenester fra Microsoft, f.eks. Bing, Wunderlist, OneDrive eller Outlook.com. Enkeltpersoners brug af Power Automate indebærer på ingen måde, at tjenesten leveres af din organisation.

Hvis din virksomhed ønsker at begrænse brugen af data, der kun vedrører organisationen, i Power Automate, er dette muligt via politikker til forebyggelse af datatab (DLP).

### <a name="how-can-people-gain-access-to-the-paid-features-of-power-automate"></a>Hvordan kan man få adgang til de betalte funktioner i Power Automate?
Enkeltpersoner kan få adgang til de betalte funktioner i Power Automate på tre forskellige måder:

1. De kan enkeltvis tilmelde sig en Flow Plan 1- eller Flow Plan 2-prøveversion gratis i 90 dage
2. Du kan tildele en Flow-licens til dem i Office 365-administrationsportalen.
3. Brugeren har fået tildelt Office 365- og Dynamics 365-planer, der omfatter adgang til tjenesten Flow. Se [siden med Flow-priser](https://flow.microsoft.com/pricing/) for at få vist en liste over Office 365- og Dynamics 365-planer, der omfatter Flow-funktioner.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>Kan jeg blokere for, at en anden person bruger de betalte funktioner i Flow?
Alle enkeltpersoner kan afprøve de betalte funktioner i Power Automate i 90 dage, og der påløber ingen omkostninger. Men du kan fuldt ud styre tildelingen af de licenser, der betales permanent, inden for virksomheden via Office 365-administrationsportalen.

Som med de gratis tilbud gælder det, at hvis en enkeltperson vælger at tilmelde sig prøveversionen, er det et direkte forhold mellem enkeltpersonen og Microsoft, der ikke nødvendigvis er godkendt af din virksomhed.

## <a name="administration-of-flow"></a>Administration af Flow
### <a name="why-has-the-flow-icon-appeared-in-the-office-365-app-launcher"></a>Hvorfor vises Flow-ikonet vises i Office 365-appstarteren?
Som annonceret i August er Power Automate nu en grundlæggende del af Office 365-pakken. Tre måneder efter denne annoncering blev Power Automate aktiveret som en tjeneste som en del af alle eksisterende SKU'er til Office 365. Da brugere overalt i verden nu kan bruge Power Automate, vises det til dem i appstarteren.

Se afsnittet nedenfor, hvis du som standard vil fjerne feltet Flow fra appstarteren.

### <a name="how-do-i-remove-power-automate-from-the-app-launcher-for-my-organization"></a>Hvordan fjerner jeg Power Automate fra appstarteren i min virksomhed?
Hvis en bruger fik tildelt en Flow Plan 1- eller Flow Plan 2-licens, kan du gøre følgende for at fjerne Flow-licensen for den pågældende bruger, og derved fjernes Flow-ikonet fra appstarteren:

1. Gå til [Office 365-administrationsportalen](https://portal.microsoftonline.com/).
2. Vælg **Brugere** i venstre navigationspanel, og vælg derefter **Aktive brugere**.
3. Find den bruger, du vil fjerne licensen for, og vælg derefter den pågældendes navn.
4. I ruden med brugerdetaljer skal du vælge **Rediger** i afsnittet **Produktlicenser**.
5. Find licensen med navnet **Power Automate Plan 1** eller **Power Automate Plan 2**, angiv til/fra-knappen til **Fra**, og vælg derefter **Gem**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Hvis en bruger har adgang til Flow gennem Office 365- og Dynamics 365-planlicensen, kan du deaktivere vedkommendes adgang til de ekstra funktioner, der er inkluderet i denne plan, ved at gøre følgende:

1. Gå til [Office 365-administrationsportalen](https://portal.microsoftonline.com/).
2. Vælg **Brugere** i venstre navigationspanel, og vælg derefter **Aktive brugere**.
3. Find den bruger, du vil fjerne adgangen for, og vælg derefter den pågældendes navn.
4. I ruden med brugerdetaljer skal du vælge **Rediger** i afsnittet **Produktlicenser**.
5. Udvid brugerens Office 365- eller Dynamics 365-licens, deaktiver adgang til tjenesten med navnet **Flow for Office 365** eller **Flow for Dynamics 365**, og vælg derefter **Gem**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

Massesletning af licenser er også mulig via PowerShell. Se et detaljeret eksempel i [Fjern licenser fra brugerkonti med Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx).   Du kan desuden finde flere oplysninger om massesletning af tjenester inden for en licens i [Deaktiver adgang til tjenester med Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

Når Flow-licensen eller -tjenesten fjernes fra en bruger i din organisation, resulterer det i, at Flow-ikonet fjernes fra følgende placeringer for den pågældende bruger:

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Office 365-appstarter
   
   ![](./media/organization-q-and-a/office-waffle.png)

Bemærk, at som standard fjernes kun feltet Flow. En bruger kan stadig vælge at bruge Power Automate som enkeltperson.

### <a name="why-did-10000-licenses-for-power-automate-show-up-in-my-office-365-tenant"></a>Hvorfor blev der vist 10.000 licenser til Power Automate i min Office 365-lejer?
Alle kan afprøve Power Automate Plan 1 eller 2 i 90 dage, og disse prøvelicenser repræsenterer den tilgængelige kapacitet for nye Flow-brugere i din lejer. Der er intet gebyr for disse licenser. Der er specifikt to mulige grunde til, at der muligvis vises en kapacitet på 10.000 (prøve) licenser til Flow i Office 365-administrationsportalen:

1. Hvis mindst én bruger i din lejer deltog i den offentlige prøveversion af Flow, der var tilgængelig fra april 2016 til oktober 2016, så vil du se 10.000 licenser, der er forsynet med mærkaten "Microsoft Power Apps og logiske flow"
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Hvis mindst én bruger i din lejer har tilmeldt sig en prøveversion af Flow Plan 2 ved hjælp af tilmeldingen til prøveversionen **mulighed 1**, der blev beskrevet i afsnittet [Hvordan tilmelder brugerne sig Power Apps](#how-do-people-sign-up-for-flow), så vil du få vist 10.000 licenser, der er forsynet med mærkaten "Microsoft Power Apps og Flow"
   
    ![](./media/organization-q-and-a/licenses1.png)

Du kan selv vælge at tildele yderligere licenser til brugerne via Office 365-administrationsportalen, men du skal være opmærksom på, at der er tale om prøvelicenser til Power Automate Plan 2, og at de udløber 90 dage efter, at de er tildelt til en bruger.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Er det gratis? Skal jeg betale for disse licenser?
Ingen bruger kan påføre din organisation omkostninger uden dit udtrykkelige samtykke, så hverken gratis licenser eller prøvelicenser kan medføre, at din organisation debiteres for gebyrer. Desuden kan de heller ikke bruge kvoter, f.eks. kørselskvoter.

### <a name="i-removed-the-power-automate-free-license-and-users-can-still-access-flow"></a>Jeg fjernede den gratis licens til Power Automate, og brugerne har stadig adgang til Flow. Hvorfor?
Den gratis licens til Power Automate er kun inkluderet til sporingsformål. Som beskrevet i første afsnit, er det ikke muligt at forhindre, at en anden person bruger Power Automate til individuelle formål. Derfor tildeler eller fjerner tilstedeværelsen af den gratis licens til Power Automate ikke nogen egenskaber.

### <a name="why-cant-i-see-all-flow-licenses-in-the-office-365-admin-portal"></a>Hvorfor kan jeg ikke se alle Flow-licenser på Office 365 Administrationsportal?
Brugerne kan bruge Power Automate som enkeltpersoner eller som en del af deres organisation. Licenser på organisationsniveau vil altid være synlige på Office 365-portalen. Hvis en bruger tilmelder sig en prøveversion som enkeltperson, administreres den ikke af Office 365-administratoren og vises ikke på portalen.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>Hvordan finder man som enkeltperson ud af, hvilket abonnement man har?
Alle kan se deres abonnement ved at besøge siden med Flow-priser på [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). Deres abonnement eller prøveversion vises der.

### <a name="will-power-automate-sign-up-impact-the-identities-in-my-organization"></a>Vil tilmelding til Power Automate påvirke identiteterne i min organisation?
Hvis organisationen allerede har et eksisterende Office 365-miljø, og alle brugere i organisationen har en Office 365-konto, påvirkes identitetsstyringen ikke.

Hvis organisationen allerede har et eksisterende Office 365-miljø, men ikke alle brugere i organisationen har en Office 365-konto, oprettes de pågældende brugere i lejeren og får tildelt licenser, der er baseret på deres arbejds- eller skolemailadresse. Det betyder, at antallet af brugere, som du administrerer på et givent tidspunkt, vokser, efterhånden som brugerne i organisationen tilmelder sig tjenesten.

Hvis organisationen ikke har ikke et Office 365-miljø med forbindelse til dit maildomæne, ændres administrationen af identiteter ikke. Brugerne føjes til en ny cloudbrugermappe, og du har mulighed for at overtage som lejeradministrator og administrere dem.

### <a name="a-new-tenant-was-created-by-power-automate-how-do-i-manage-this"></a>En ny lejer blev oprettet af Power Automate; hvordan håndterer jeg dette?
Hvis en ny lejer blev oprettet af Power Automate, kan du gøre krav på og administrere den pågældende lejer ved hjælp af følgende trin:

1. Tilmeld dig lejeren ved at tilmelde dig Flow ved hjælp af et mailadressedomæne, der svarer til det lejerdomæne, du vil administrere. Hvis Microsoft f.eks. oprettede lejeren contoso.com, skal du tilmelde dig lejeren med en mailadresse, der slutter på @contoso.com.
2. Gør krav på administrationen ved at bekræfte ejerskabet af domænet: Når du er i lejeren, kan du give dig selv administratorrollen ved at bekræfte ejerskabet af domænet. Hvis du vil gøre dette, skal du følge disse trin:    
   
   1. Gå til [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Vælg ikonet Appstarter øverst til venstre, og vælg Admin.
   3. Læs vejledningen på siden **Become the admin**, og vælg derefter **Yes, I want to be the admin**.  
      
       **BEMÆRK**! Hvis denne indstilling ikke vises, er der allerede en Office 365-administrator.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Kan jeg styre den Office 365-lejer, brugerene føjes til, hvis jeg har flere domæner?
Hvis du ikke gør noget, oprettes der en lejer for hvert brugermaildomæne og -underdomæne.

Hvis du ønsker, at alle brugere skal være i den samme lejer uanset deres mailadresseudvidelser:  

* Oprette en destinationslejer på forhånd, eller bruge en eksisterende lejer. Tilføj alle de eksisterende domæner og underdomæner, der skal konsolideres i den pågældende lejer. Derefter tilmeldes alle brugere med mailadresser, der slutter på disse domæner og underdomæner automatisk destinationslejeren, når de tilmelder sig.

**VIGTIGT**! Der er ingen understøttede automatiserede metode til flytning af brugerne på tværs af lejere, efter at de er oprettet. Du finder flere oplysninger om tilføjelse af domæner til en enkelt Office 365-lejer under [Add your users and domain to Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Hvordan kan jeg begrænse mine brugeres mulighed for at få adgang til organisationens forretningsdata?
Power Automate giver dig mulighed for at oprette datazoner for forretningsdata og ikke-forretningsdata, som vist nedenfor. Når disse politikker til forebyggelse af datatab implementeres, forhindres brugerne i at designe eller køre Flow, der kombinerer forretningsdata og ikke-forretningsdata. Du kan finde yderligere oplysninger i [Politikker til forebyggelse af datatab (DLP)](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

