---
title: Power Automate-tilmelding til spørgsmål og svar i organisationen | Microsoft Docs
description: Almindelige spørgsmål og svar om licenser, administration og brugere, der tilmeldes Power Automate i din Office 365-lejer.
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
ms.locfileid: "3340089"
---
# <a name="power-automate-in-your-organization-qa"></a>Spørgsmål og svar om Power Automate i din organisation

I dette emne beskrives det, hvordan brugere i organisationen kan bruge Power Automate, og hvordan du kan styre servicen Power Automate.

## <a name="signing-up-for-power-automate"></a>Melde dig til Power Automate
### <a name="what-is-power-automate"></a>Hvad er Power Automate?
Power Automate er en offentlig cloudtjeneste, der hjælper enkeltpersoner og teams med at konfigurere automatiserede arbejdsprocesser mellem deres favoritapps og -tjenester for at synkronisere filer, få beskeder, indsamle data med mere. 

### <a name="how-do-people-sign-up-for-power-automate"></a>Hvordan tilmelder man sig Power Automate?
Enkeltpersoner kan tilmelde sig Power Automate på to måder gennem webportalen:

#### <a name="option-1"></a>Indstilling 1
Alle kan tilmelde sig ved at gå til [flow.microsoft.com](https://flow.microsoft.com), vælge **Tilmeld dig gratis** og derefter fuldføre tilmeldingsprocessen for Power Automate via [admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) eller [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Indstilling 2
Alle kan tilmelde sig ved at gå til [flow.microsoft.com](https://flow.microsoft.com), vælge **Log på**, logge på med deres arbejds- eller skolemail eller personlige mail og acceptere vilkårene for anvendelse af Power Automate.    

Når en bruger i organisationen tilmelder sig Power Automate med Mulighed 2, får den pågældende bruger automatisk tildelt en gratis Power Automate-licens.

Du finder flere oplysninger under [Tilmeld dig Flow](sign-up-sign-in.md).

### <a name="what-is-the-power-automate-free-plan"></a>Hvad er Power Automate Free Plan?

Power Automate Free Plan er kun inkluderet til sporingsformål. Aktivering eller deaktivering af planen har ingen effekt på en brugers mulighed for at oprette flow. Hvis du deaktiverer Power Automate Free Plan, aktiveres den igen, når en bruger logger på. Det er den forventede funktionsmåde.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>Kan jeg blokere for en anden persons tilmelding til Flow?
Power Automate er en fuldt offentlig cloudtjeneste, og alle mennesker i verden kan tilmelde sig og bruge Flow til at automatisere deres daglige opgaver. Hvis du vil bruge Power Automate, er der er intet krav om, at brugerne har eller bruger en Office 365-konto. Derfor findes der ingen mekanisme, der på nuværende tidspunkt giver dig mulighed for at forhindre en person i at bruge Power Automate (da det er muligt for alle mennesker i verden, uanset deres mailadresse).

Men hvis en person tilmelder sig Power Automate, og du vælger ikke at understøtter dem i din organisation, kan de på ingen måde påføre virksomheden omkostninger. Når en person tilmelder sig Power Automate, er relationen mellem denne person og Microsoft, som det er tilfældet med mange andre cloudtjenester fra Microsoft, f.eks. Bing, OneDrive eller Outlook.com. En persons brug af Power Automate indebærer på ingen måde, at tjenesten leveres af din organisation.

Endelig, hvis din virksomhed ønsker at begrænse brugen af organisationsdata, der kun findes i Power Automate, er det muligt via DLP-politikker (forhindring af datatab).

### <a name="how-can-people-gain-access-to-the-paid-features-of-power-automate"></a>Hvordan kan personer få adgang til de betalte funktioner i Power Automate?
Enkeltpersoner kan få adgang til de betalte funktioner i Power Automate på tre forskellige måder:

1. De kan enkeltvis tilmelde sig en Flow Plan 1- eller Flow Plan 2-prøveversion gratis i 90 dage
2. Du kan tildele dem en Power Automate-licens i Office 365-admin-portalen.
3. Brugeren har fået tildelt Office 365- og Dynamics 365-planer, der omfatter adgang til Power Automate. Se [siden med Power Automate-priser](https://flow.microsoft.com/pricing/) med en liste over Office 365 og Dynamics 365-planer, der indeholder Power Automate-funktioner.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>Kan jeg blokere for, at en anden person bruger de betalte funktioner i Flow?
Alle enkeltpersoner kan afprøve de betalte funktioner i Power Automate i 90 dage, og der påløber ingen omkostninger. Men du kan fuldt ud styre tildelingen af de licenser, der betales permanent, inden for virksomheden via Office 365-administrationsportalen.

Som med de gratis tilbud gælder det, at hvis en enkeltperson vælger at tilmelde sig prøveversionen, er det et direkte forhold mellem enkeltpersonen og Microsoft, der ikke nødvendigvis er godkendt af din virksomhed.

## <a name="administration-of-flow"></a>Administration af Flow
### <a name="why-has-the-power-automate-icon-appeared-in-the-office-365-app-launcher"></a>Hvorfor er Power Automate-ikonet vist i Office 365-programstarteren?
Som annonceret i august er Power Automate nu en grundlæggende del af Office 365-pakken. Tre måneder efter denne annoncering blev Power Automate aktiveret som en tjeneste som en del af alle eksisterende Office 365-SKU'er. Da brugere overalt i verden nu kan bruge Power Automate, vises programmet til dem i appstarteren.

Se afsnittet nedenfor, hvis du som standard vil fjerne feltet Power Automate fra appstarteren.

### <a name="how-do-i-remove-power-automate-from-the-app-launcher-for-my-organization"></a>Hvordan fjerner jeg Power Automate fra appstarteren i min virksomhed?
Hvis en bruger fik tildelt en Flow Plan 1- eller Flow Plan 2-licens, kan du gøre følgende for at fjerne Power Automate-licensen for den pågældende bruger, og derved fjernes Power Automate-ikonet fra appstarteren:

1. Gå til [Office 365-administrationsportal](https://portal.microsoftonline.com/).
2. Vælg **Brugere**på venstre navigationslinje, og vælg derefter **Aktive brugere**.
3. Find den bruger, du vil fjerne licensen for, og vælg derefter navnet.
4. Vælg **Rediger** i sektionen **Produktlicenser** i ruden med brugerdetaljer.
5. Find licensen med navnet **Power Automate Plan 1** eller **Power Automate Plan 2**, indstil omskifteren til **Fra**, og vælg derefter **Gem**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Hvis en bruger har adgang til Power Automate gennem sin Office 365- og Dynamics 365-planlicens, kan du deaktivere vedkommendes adgang til de ekstra funktioner, der er inkluderet i denne plan, ved at gøre følgende:

1. Gå til [Office 365-administrationsportal](https://portal.microsoftonline.com/).
2. Vælg **Brugere**på venstre navigationslinje, og vælg derefter **Aktive brugere**.
3. Find den bruger, du vil fjerne adgang for, og vælg derefter navnet.
4. Vælg **Rediger** i sektionen **Produktlicenser** i ruden med brugerdetaljer.
5. Udvid brugerens Office 365- eller Dynamics 365-licens, deaktiver adgang til tjenesten med navnet **Flow for Office 365** eller **Flow for Dynamics 365**, og vælg derefter **Gem**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

Massefjernelse af licenser er også muligt via PowerShell. Se et detaljeret eksempel i [Fjerne licenser fra brugerkonti med Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx).   Endelig kan du finde yderligere vejledning i, hvordan du fjerner en masse tjenester, i [Deaktivere adgang til tjenester med Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

Når Power Automate-licensen eller -servicen fjernes fra en bruger i din organisation, resulterer det i, at Power Automate-ikonet fjernes fra følgende placeringer for den pågældende bruger:

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Office 365-appstarter
   
   ![](./media/organization-q-and-a/office-waffle.png)

Bemærk, at som standard fjernes kun feltet Power Automate. En bruger kan stadig bruge Power Automate som enkeltperson.

### <a name="why-did-10000-licenses-for-power-automate-show-up-in-my-office-365-tenant"></a>Hvorfor vises 10.000 licenser til Power Automate i min Office 365-lejer?
Alle kan afprøve Power Automate Plan 1 eller 2 i 90 dage, og disse prøvelicenser repræsenterer den tilgængelige kapacitet for nye Power Automate-brugere i din lejer. Der er intet gebyr for disse licenser. Der er især to mulige årsager til, at du måske kan se en kapacitet på 10.000 (prøvelicenser) til Power Automate i Office 365-administrationsportalen:

1. Hvis mindst én bruger i din lejer deltog i den offentlige Power Automate-prøveversion fra april 2016 til oktober 2016, får du vist 10.000 licenser mærket som "Microsoft Power Apps og logiske flows"
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Hvis mindst én bruger i din lejer har tilmeldt sig en prøveversion af Flow Plan 2 Plan ved hjælp af tilmeldingen til prøveversionen **Mulighed 1**, der er beskrevet i afsnittet [Hvordan tilmelder brugerne sig Power Apps](#how-do-people-sign-up-for-power-automate), så vil du få vist 10.000 licenser, der er mærket "Microsoft Power Apps og Flow"
   
    ![](./media/organization-q-and-a/licenses1.png)

Du kan selv vælge at tildele yderligere licenser til brugere via Office 365-administrationsportalen, men du skal være opmærksom på, at der er tale om prøvelicenser til Power Automate Plan 2, og at de udløber 90 dage efter, at de er tildelt til en bruger.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Er dette gratis? Skal jeg betale for disse licenser?
Ingen bruger kan påføre din organisation omkostninger uden dit udtrykkelige samtykke, så hverken gratis licenser eller prøvelicenser kan medføre, at din organisation debiteres for gebyrer. Desuden kan de heller ikke bruge kvoter, f.eks. kørselskvoter.

### <a name="i-removed-the-power-automate-free-license-and-users-can-still-access-flow"></a>Jeg fjernede den gratis Power Automate-licens, og brugerne har stadig adgang til Flow?
Den gratis Power Automate-licens er kun inkluderet til sporingsformål. Som beskrevet i første afsnit, er det ikke muligt at forhindre, at en anden person bruger Power Automate til individuelle formål. Derfor tildeler eller fjerner tilstedeværelsen af en gratis Power Automate-licens ikke nogen funktioner.

### <a name="why-cant-i-see-all-power-automate-licenses-in-the-office-365-admin-portal"></a>Hvorfor vises alle Power Automate-licenser ikke på Office 365-administrationsportalen?
Brugerne kan bruge Power Automate som enkeltpersoner eller som en del af deres organisation. Licenser på organisationsniveau vil altid være synlige på Office 365-portalen. Hvis en bruger tilmelder sig en prøveversion som enkeltperson, administreres den ikke af Office 365-administratoren og vises ikke på portalen.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>Hvordan finder man som enkeltperson ud af, hvilket abonnement man har?
Alle kan få vist deres abonnement ved at besøge siden med Power Automate-priser på [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). Deres abonnement eller prøveversion vises der.

### <a name="will-power-automate-sign-up-impact-the-identities-in-my-organization"></a>Vil tilmelding til Power Automate påvirke identiteterne i min organisation?
Hvis organisationen allerede har et eksisterende Office 365-miljø, og alle brugere i organisationen har en Office 365-konto, påvirkes identitetsstyringen ikke.

Hvis organisationen allerede har et eksisterende Office 365-miljø, men ikke alle brugere i organisationen har Office 365-konti, skal vi oprette en bruger i lejeren og tildele licenser på baggrund af brugerens arbejds- eller skolemailadresse. Det betyder, at det antal brugere, du administrerer på et bestemt tidspunkt, vokser, efterhånden som brugerne i din organisation tilmelder sig tjenesten.

Hvis der ikke er knyttet et Office 365-miljø til dit e-maildomæne i organisationen, er der ingen ændringer i, hvordan du administrerer identitet. Brugerne føjes til en ny brugermappe, der kun er i skyen, og du har mulighed for at overtage lejeradministrationen og styre dem.

### <a name="a-new-tenant-was-created-by-power-automate-how-do-i-manage-this"></a>En ny lejer blev oprettet af Power Automate, hvordan håndterer jeg dette?
Hvis en ny lejer blev oprettet af Power Automate, kan du gøre krav på og administrere den pågældende lejer vha. følgende trin:

1. Deltag i lejeren ved at tilmelde dig Power Automate med et e-mailadressedomæne, der stemmer overens med det lejerdomæne, du vil administrere. Hvis Microsoft f.eks. har oprettet contoso.com som lejer, skal du tilmelde dig lejeren med en e-mailadresse, der slutter på @contoso.com.
2. Kræv administrationskontrol ved at verificere domæneejerskabet: Når du er i lejeren, kan du forfremme dig selv til administratorrollen ved at bekræfte ejerskabet af domænet. Det gøres ved at benytte følgende fremgangsmåde:    
   
   1. Gå til [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Vælg ikonet Appstarter øverst til venstre, og vælg Admin.
   3. Læs instruktionerne på siden **Bliv administrator**, og vælg derefter **Ja, jeg vil gerne være administrator**.  
      
       **BEMÆRK!** Hvis denne indstilling ikke vises, er Office 365-administratoren allerede på plads.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Hvis jeg har flere domæner, kan jeg så styre Office 365-lejeren, som brugere føjes til?
Hvis du intet gør, oprettes der en lejer for hvert bruger-e-maildomæne og underdomæne.

Hvis alle brugere skal have samme lejer, uanset deres udvidelser af e-mailadresse:  

* Opret en mållejer på forhånd, eller brug en eksisterende lejer. Tilføj alle eksisterende domæner og underdomæner, der skal konsolideres i den pågældende lejer. Derefter deltager alle brugere med e-mailadresser, der ender på disse domæner og underdomæner, automatisk i mållejeren, når de tilmelder sig.

**VIGTIGT**! Der er ikke en understøttet automatiseret mekanisme, der kan flytte brugerne på tværs af lejere, når de først er blevet oprettet. Du kan få mere at vide om, hvordan du føjer domæner til en enkelt Office 365-lejer, under [Føje brugere og domæne til Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Hvordan kan jeg begrænse mine brugeres mulighed for at få adgang til organisationens forretningsdata?
Power Automate giver dig mulighed for at oprette datazoner til virksomhedsdata og ikke-virksomhedsdata, som vist nedenfor. Når disse politikker til forebyggelse af datatab er implementeret, kan brugerne ikke udforme eller køre Power Automate, der kombinerer virksomhedsdata og ikke-virksomhedsdata. Du kan finde flere oplysninger under [Politikker for forhindring af datatab](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

