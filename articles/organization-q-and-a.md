---
title: Spørgsmål og svar vedrørende Power Automate-tilmelding i organisationen | Microsoft Docs
description: Ofte stillede spørgsmål og svar om licenser, administration og brugertilmelding til Power Automate i din Office 365-lejer.
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
ms.openlocfilehash: fbadbf62760544410cf8fee74f4cecb43cbdefd5
ms.sourcegitcommit: 4b9261984a554dfccb0d0d77f3d5fdca60e26433
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/06/2020
ms.locfileid: "82852758"
---
# <a name="power-automate-in-your-organization-qa"></a>Spørgsmål og svar vedrørende Power Automate i din organisation

I dette emne beskrives, hvordan brugere i organisationen kan anvende Power Automate, og hvordan du kan kontrollere Power Automate-tjenesten.

## <a name="signing-up-for-power-automate"></a>Tilmelding til Power Automate
### <a name="what-is-power-automate"></a>Hvad er Power Automate?
Power Automate er en offentlig cloudtjeneste, der hjælper enkeltpersoner og teams med at konfigurere automatiserede arbejdsprocesser mellem deres favoritprogrammer og -tjenester for at synkronisere filer, få meddelelser, indsamle data og meget mere. 

### <a name="how-do-people-sign-up-for-power-automate"></a>Hvordan tilmelder man sig Power Automate?
Enkeltpersoner kan tilmelde sig Power Automate på to måder gennem webportalen:

#### <a name="option-1"></a>Valgmulighed 1
Alle kan tilmelde sig ved at gå til [flow.microsoft.com](https://flow.microsoft.com), vælge **Tilmeld dig gratis** og derefter fuldføre tilmeldingsprocessen for Power Automate via [admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) eller [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Valgmulighed 2
Alle kan tilmelde sig ved at gå til [flow.microsoft.com](https://flow.microsoft.com), vælge **Log på**, logge på med deres arbejds- eller skolemail eller personlige mail og acceptere vilkårene for anvendelse af Power Automate.    

Når en bruger i organisationen tilmelder sig Power Automate med mulighed 2, får den pågældende bruger automatisk tildelt en gratis Power Automate-licens.

Du finder flere oplysninger under [Tilmeld dig Flow](sign-up-sign-in.md).

### <a name="what-is-the-power-automate-free-plan"></a>Hvad er den gratis plan til Power Automate?

Den gratis plan i Power Automate bruges kun til sporingsformål. Aktivering eller deaktivering af planen har ingen effekt på en brugers mulighed for at oprette flow. Hvis du deaktiverer den gratis plan i Power Automate, aktiveres den igen, når en bruger logger på. Dette er den forventede funktionsmåde.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>Kan jeg blokere for en anden persons tilmelding til Flow?
Power Automate er en fuldt offentlig cloudtjeneste, og alle i verden kan tilmelde sig og bruge den til at automatisere deres daglige opgaver. Hvis du vil bruge Power Automate, er der er intet krav om, at brugerne har eller bruger en Office 365-konto. Derfor findes der ingen mekanisme, der på nuværende tidspunkt giver dig mulighed for at forhindre en person i at bruge Power Automate (da det er muligt for alle mennesker i verden, uanset deres mailadresse).

Men hvis en person tilmelder sig Power Automate, og du vælger ikke at understøtte dem i din organisation, kan de på ingen måde påføre virksomheden omkostninger. Når en person tilmelder sig Power Automate, er relationen mellem denne person og Microsoft, som det er tilfældet med mange andre cloudtjenester fra Microsoft, f.eks. Bing, OneDrive eller Outlook.com. Enkeltpersoners brug af Power Automate indebærer på ingen måde, at tjenesten leveres af din organisation.

Hvis din virksomhed ønsker at begrænse brugen af data, der kun vedrører organisationen, i Power Automate, er dette muligt via politikker til forebyggelse af datatab (DLP).

### <a name="how-can-people-gain-access-to-the-paid-features-of-power-automate"></a>Hvordan kan man få adgang til de betalte funktioner i Power Automate?
Enkeltpersoner kan få adgang til de betalte funktioner i Power Automate på tre forskellige måder:

1. De kan enkeltvis tilmelde sig en Flow Plan 1- eller Flow Plan 2-prøveversion gratis i 90 dage
2. Du kan tildele dem en licens til Power Automate på Office 365-administrationsportalen.
3. Brugeren har fået tildelt Office 365- og Dynamics 365-planer, der omfatter adgang til Power Automate. Se [siden med Power Automate-priser](https://flow.microsoft.com/pricing/) for at få vist en liste over Office 365- og Dynamics 365-planer, der inkluderer Power Automate-egenskaber.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>Kan jeg blokere for, at en anden person bruger de betalte funktioner i Flow?
Alle enkeltpersoner kan afprøve de betalte funktioner i Power Automate i 90 dage, og der påløber ingen omkostninger. Men du kan fuldt ud styre tildelingen af de licenser, der betales permanent, inden for virksomheden via Office 365-administrationsportalen.

Som med de gratis tilbud gælder det, at hvis en enkeltperson vælger at tilmelde sig prøveversionen, er det et direkte forhold mellem enkeltpersonen og Microsoft, der ikke nødvendigvis er godkendt af din virksomhed.

## <a name="administration-of-flow"></a>Administration af Flow
### <a name="why-has-the-power-automate-icon-appeared-in-the-office-365-app-launcher"></a>Hvorfor vises Power Automate-ikonet i Office 365-appstarteren?
Som annonceret i August er Power Automate nu en grundlæggende del af Office 365-pakken. Tre måneder efter denne annoncering blev Power Automate aktiveret som en tjeneste som en del af alle eksisterende SKU'er til Office 365. Da brugere overalt i verden nu kan bruge Power Automate, vises det til dem i appstarteren.

Se nedenstående sektion, hvis du vil fjerne Power Automate-feltet fra appstarteren som standard.

### <a name="how-do-i-remove-power-automate-from-the-app-launcher-for-my-organization"></a>Hvordan fjerner jeg Power Automate fra appstarteren i min virksomhed?
Hvis en bruger fik tildelt en Flow Plan 1- eller Flow Plan 2-licens, kan du gøre følgende for at fjerne Power Automate-licensen for den pågældende bruger, og derved fjernes Power Automate-ikonet fra appstarteren:

1. Gå til [Office 365-administrationsportalen](https://portal.microsoftonline.com/).
2. I navigationspanelet til venstre skal du vælge **Users** og derefter vælge **Active Users**.
3. Find den bruger, du vil fjerne licensen fra, og vælg derefter vedkommendes navn.
4. I detaljeruden for brugeren skal du i sektionen **Product licenses** vælge **Edit**.
5. Find licensen med navnet **Power Automate Plan 1** eller **Power Automate Plan 2**, angiv til/fra-knappen til **Fra**, og vælg derefter **Gem**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Hvis en bruger har adgang til Power Automate gennem Office 365- og Dynamics 365-planlicensen, kan du deaktivere vedkommendes adgang til de ekstra funktioner, der er inkluderet i denne plan, ved at gøre følgende:

1. Gå til [Office 365-administrationsportalen](https://portal.microsoftonline.com/).
2. I navigationspanelet til venstre skal du vælge **Users** og derefter vælge **Active Users**.
3. Find den bruger, du vil fjerne adgangen fra, og vælg derefter vedkommendes navn.
4. I ruden med brugerdetaljer skal du vælge **Rediger** i afsnittet **Produktlicenser**.
5. Udvid brugerens Office 365- eller Dynamics 365-licens, deaktiver adgang til tjenesten med navnet **Flow for Office 365** eller **Flow for Dynamics 365**, og vælg derefter **Gem**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

Massesletning af licenser er også mulig via PowerShell. Du kan se et detaljeret eksempel under [Fjern licenser fra brugerkonti med Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx).   Desuden kan du få yderligere vejledning om fjernelse af flere tjenester under en licens på én gang under [Deaktiver adgang til tjenester i Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

Når Power Automate-licensen eller -tjenesten fjernes fra en bruger i din organisation, resulterer det i, at Power Automate-ikonet fjernes fra følgende placeringer for den pågældende bruger:

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Office 365-appstarter
   
   ![](./media/organization-q-and-a/office-waffle.png)

Bemærk, at som standard fjernes kun feltet Power Automate. En bruger kan stadig vælge at bruge Power Automate som enkeltperson.

### <a name="why-did-10000-licenses-for-power-automate-show-up-in-my-office-365-tenant"></a>Hvorfor blev der vist 10.000 licenser til Power Automate i min Office 365-lejer?
Alle kan afprøve Power Automate Plan 1 eller 2 i 90 dage, og disse prøvelicenser repræsenterer den tilgængelige kapacitet for nye Power Automate-brugere i din lejer. Der er ingen opkrævning for disse licenser. Der er især to mulige grunde til, at du muligvis kan se en kapacitet på 10.000 (prøve)licenser til Power Automate på Office 365-administrationsportalen:

1. Hvis mindst én bruger i din lejer deltog i den offentlige prøveversion af Power Automate, der var tilgængelig fra april 2016 til oktober 2016, så vil du se 10.000 licenser, der er forsynet med mærkaten "Microsoft Power Apps og logiske flow"
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Hvis mindst én bruger i din lejer har tilmeldt sig en prøveversion af Flow Plan 2 ved hjælp af tilmeldingen til prøveversionen **mulighed 1**, der blev beskrevet i afsnittet [Hvordan tilmelder brugerne sig Power Apps](#how-do-people-sign-up-for-power-automate), så vil du få vist 10.000 licenser, der er forsynet med mærkaten "Microsoft Power Apps og Flow"
   
    ![](./media/organization-q-and-a/licenses1.png)

Du kan selv vælge at tildele yderligere licenser til brugerne via Office 365-administrationsportalen, men du skal være opmærksom på, at der er tale om prøvelicenser til Power Automate Plan 2, og at de udløber 90 dage efter, at de er tildelt til en bruger.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Er det gratis? Skal jeg betale for disse licenser?
Ingen bruger kan påføre din organisation omkostninger uden dit udtrykkelige samtykke, så hverken gratis licenser eller prøvelicenser kan medføre, at din organisation debiteres for gebyrer. Desuden kan de heller ikke bruge kvoter, f.eks. kørselskvoter.

### <a name="i-removed-the-power-automate-free-license-and-users-can-still-access-flow"></a>Jeg fjernede den gratis licens til Power Automate, og brugerne har stadig adgang til Flow. Hvorfor?
Den gratis licens til Power Automate er kun inkluderet til sporingsformål. Som beskrevet i første afsnit, er det ikke muligt at forhindre, at en anden person bruger Power Automate til individuelle formål. Derfor tildeler eller fjerner tilstedeværelsen af den gratis licens til Power Automate ikke nogen egenskaber.

### <a name="why-cant-i-see-all-power-automate-licenses-in-the-office-365-admin-portal"></a>Hvorfor kan jeg ikke se alle Power Automate-licenser på Office 365-administrationsportalen?
Brugerne kan bruge Power Automate som enkeltpersoner eller som en del af deres organisation. Licenser på organisationsniveau vil altid være synlige på Office 365-portalen. Hvis en bruger tilmelder sig en prøveversion som enkeltperson, administreres den ikke af Office 365-administratoren og vises ikke på portalen.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>Hvordan finder man som enkeltperson ud af, hvilket abonnement man har?
Alle kan se deres abonnement ved at besøge siden med Power Automate-priser på [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). Deres abonnement eller prøveversion vises der.

### <a name="will-power-automate-sign-up-impact-the-identities-in-my-organization"></a>Vil tilmelding til Power Automate påvirke identiteterne i min organisation?
Hvis organisationen allerede har et eksisterende Office 365-miljø, og alle brugere i organisationen har en Office 365-konto, påvirkes identitetsstyringen ikke.

Hvis organisationen allerede har et eksisterende Office 365-miljø, men det ikke er alle brugerne i organisationen, der har Office 365-konti, opretter vi en bruger i lejeren og tildeler licenser på baggrund af brugernes arbejds- eller skolemailadresser. Det betyder, at antallet af brugere, som du administrerer på et givent tidspunkt, vokser, efterhånden som brugerne i organisationen tilmelder sig tjenesten.

Hvis organisationen ikke har ikke et Office 365-miljø med forbindelse til dit maildomæne, ændres administrationen af identiteter ikke. Brugerne føjes til en ny brugermappe udelukkende for cloudmiljøet, og du får mulighed for at overtage administrationen af lejeren og administrere dem.

### <a name="a-new-tenant-was-created-by-power-automate-how-do-i-manage-this"></a>En ny lejer blev oprettet af Power Automate; hvordan håndterer jeg dette?
Hvis en ny lejer blev oprettet af Power Automate, kan du gøre krav på og administrere den pågældende lejer ved hjælp af følgende trin:

1. Deltag i lejeren ved at tilmelde dig Power Automate med et mailadressedomæne, der stemmer overens med det lejerdomæne, du vil administrere. Hvis Microsoft f.eks. oprettede lejeren contoso.com, skal du forbinde lejeren med en mailadresse, der slutter med @contoso.com.
2. Få administratorkontrol ved at bekræfte ejerskabet over domænet: Når du har adgang til lejren, kan du forfremme dig selv til administratorrollen ved at bekræfte ejerskabet over domænet. Det gør du ved at gennemgå disse trin:    
   
   1. Gå til [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Vælg ikonet Appstarter øverst til venstre, og vælg Admin.
   3. Læs instruktionerne på siden **Become the admin**, og vælg derefter **Yes, I want to be the admin**.  
      
       **BEMÆRK**! Hvis denne indstilling ikke vises, er der allerede en Office 365-administrator.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Kan jeg kontrollere den Office 365-lejer, som brugerne er føjet til, hvis jeg har flere domæner?
Hvis du ikke gør noget, oprettes der en lejer for hvert brugermaildomæne og -underdomæne.

Hvis du ønsker, at alle brugere skal være i den samme lejer uanset deres mailadresseudvidelser:  

* Opret en destinationslejer i forvejen, eller brug en eksisterende lejer. Tilføj alle eksisterende domæner og underdomæner, der skal konsolideres i den pågældende lejer. Derefter deltager alle brugerne med mailadresser, der slutter med de pågældende domæner og underdomæner, automatisk i destinationslejeren, når de tilmelder sig.

**VIGTIGT**! Der er ingen understøttede automatiserede metode til flytning af brugerne på tværs af lejere, efter at de er oprettet. Hvis du vil have mere at vide om tilføjelse af domæner til en enkelt Office 365-lejer, skal du se [Føj dine brugere og domæner til Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Hvordan kan jeg begrænse mine brugeres mulighed for at få adgang til organisationens forretningsdata?
Power Automate giver dig mulighed for at oprette datazoner for forretningsdata og ikke-forretningsdata, som vist nedenfor. Når disse politikker om forebyggelse af datatab er implementeret, forhindres brugerne i at designe eller køre Power Automate, der kombinerer forretningsrelaterede og ikke-forretningsrelaterede data. Du kan finde flere oplysninger under [Politikker om forebyggelse af datatab (DLP)](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

