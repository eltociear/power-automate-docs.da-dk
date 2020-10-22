---
title: Power Automate US Government
description: Indeholder oplysninger om Power Automate US Government-servicebeskrivelse, -planer og -begrænsninger
services: ''
suite: flow
author: msftman
ms.service: flow
ms.devlang: na
ms.topic: article
ms.date: 10/08/2020
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 1322dc6b3d391033e3283356798bf5d91a729aba
ms.sourcegitcommit: eedb45292b26b4729d74e09262706c5085327dba
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/08/2020
ms.locfileid: "3970182"
---
# <a name="power-automate-us-government"></a>Power Automate US Government


Microsoft har oprettet Power Automate US Government-planer for at imødegå de entydige krav i den offentlige sektor i USA, som hele tiden ændres. Dette afsnit indeholder en oversigt over funktioner, der er specifikke for Power Automate US Government. Vi anbefaler, at du læser dette supplerende afsnit samt emnet [Introduktion](https://docs.microsoft.com/flow/getting-started) for Power Automate-tjenesten. Denne tjeneste er almindeligvis omtalt som Power Automate Government Community Cloud (GCC) eller Power Automate Government Community Cloud – High (GCC High).

Beskrivelsen af Power Automate US Government-servicen er et tillæg til den generelle beskrivelse af Power Automate-servicen. Den definerer de entydige forpligtelser og forskelle sammenlignet med de generelle Power Automate-tilbud, der har været tilgængelige for vores kunder siden oktober 2016.

## <a name="about-power-automate-us-government-environments-and-plans"></a>Om Power Automate US Government-miljøer og -planer

Power Automate US Government-planer er månedsabonnementer, og de kan gives i licens til et ubegrænset antal brugere.

Power Automate GCC-miljøet overholder de angivne føderale krav til cloudtjenester, herunder FedRAMP High og DoD DISA IL2. Det overholder også kravene fra de strafferetlige systemer (CJI-datatyper).

Ud over funktionerne og egenskaberne i Power Automate kan de organisationer, der bruger Power Automate US Government, drage nytte af følgende unikke funktioner:

- Din organisations kundeindhold er fysisk adskilt fra kundeindholdet i kommercielle Power Automate-tilbud.

- Din organisations kundeindhold opbevares i USA.

- Adgang til din organisations kundeindhold er begrænset til et bestemt udvalg af Microsoft-medarbejdere.

- Power Automate US Government overholder alle certificeringer og godkendelser, som er påkrævet af kunder i den amerikanske offentlige sektor.

Fra september 2019 kan berettigede kunder vælge at installere Power Automate US Government i **Høj GCC**-miljøet, som muliggør enkeltlogon og problemfri integration med Microsoft Office 365 GCC High-udrulninger. 

Microsoft har designet platformen og vores driftsprocedurer til at kunne opfylde kravene i DISA SRG IL4-overholdelsesstrukturen. Vi forventer, at underleverandører til det amerikanske forsvarsministerium og andre føderale myndigheder, der i øjeblikket udnytter Office 365 GCC High, så de kan bruge GCC High-udrulningsmuligheden i Power Automate US Government. Dette muliggør og kræver, at kunden bruger Azure AD Government til kundeidentiteter, i modsætning til GCC, som bruger det offentlige Azure AD. Til vores amerikanske forsvarsministeriums kontraktansatte kundebase driver Microsoft servicen på en måde, som gør det muligt for disse kunder at opfylde ITAR-forpligtelsen og DFARS-anskaffelsesregler, som dokumenteret og påkrævet af deres kontrakter med det amerikanske forsvarsministerium.

## <a name="customer-eligibility"></a>Kundens berettigelse

Power Automate US Government er tilgængelig for (1) amerikanske føderale, statslige, lokale, tribale og regionale offentlige institutioner og (2) andre enheder, der håndterer data, der er underlagt offentlige krav og bestemmelser, samt i de tilfælde, hvor brugen af Power Automate US Government er egnet til at imødekomme disse krav, såfremt det vurderes, at kunden er berettiget til denne brug. Microsofts validering af berettigelse omfatter bekræftelse af håndtering af data i henhold til ITAR (International Traffic in Arms Regulations), retshåndhævelsesdata i henhold til FBI's CJIS-politik (Criminal Justice Information Services) eller andre offentligt regulerede eller kontrollerede data. Validering kan kræve sponsorat af en offentlig myndighed med specifikke krav til håndteringen af data.

Objekter med spørgsmål om berettigelse til Power Automate US Government skal se deres kundegruppe. Microsoft validerer berettigelse igen, når kundekontrakter om Power Automate US Government fornyes.

## <a name="power-automate-us-government-plans"></a>Power Automate US Government-planer

Adgang til Power Automate US Government-planer er begrænset til de tilbud, der er beskrevet i følgende afsnit; hver enkelt plan tilbydes som et månedsabonnement og kan gives i licens til et ubegrænset antal brugere:

- Power Automate pr. flowplan for offentlig myndighed
- Power Automate pr. brugerplan for offentlig myndighed

- Ud over de enkeltstående planer inkluderer Microsoft 365 US Government- og Dynamics 365 US Government-planer også Power Apps- og Power Automate-funktionerne, der giver kunderne mulighed for at udvide og tilpasse Microsoft 365- og Customer Engagement-apps (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service og Dynamics 365 Project Service Automation). 

Yderligere oplysninger samt oplysninger om forskellene i funktionaliteten mellem disse licensgrupper er beskrevet mere detaljeret her: [Power Automate-licensoplysninger](https://flow.microsoft.com/pricing/).

Power Automate US Government er tilgængelig gennem volumenlicens og Cloud Solution Provider-købskanaler. Programmet Cloud Solution Provider er ikke i øjeblikket tilgængeligt for kunder med GCC High.

## <a name="differences-between-customer-data-and-customer-content"></a>Forskelle i kundedata og kundeindhold

Kundedata, som de er defineret i onlineservicevilkår, vil sige alle data, herunder alle tekst-, lyd- eller billedfiler samt software, der sendes til Microsoft af, eller på vegne af, kunder via brugen af en CRM-onlineservice.

Kundeindhold henviser til en bestemt del af kundedata, der er direkte oprettet af brugere, f.eks. indhold, der er lagret i databaser via poster i [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)-objekter (f.eks. kontaktoplysninger). Indhold opfattes generelt som fortrolige oplysninger, og som et led i normale servicehandlinger sendes de ikke ukrypteret via internettet.

Du kan finde flere oplysninger om, hvordan Power Automate beskytter kundedata, på [Microsoft Sikkerhedscenter for onlinetjenester](https://www.microsoft.com/trustcenter/cloudservices/business-application-platform/default.aspx).

## <a name="data-segregation-for-government-community-cloud"></a>Opdeling af data for Government Community Cloud

Når Power Automate-tjenesten er klargjort som en del af Power Automate US Government, tilbydes den i overensstemmelse med National Institute of Standards and Technology (NIST) Special Publication 800-145.

Ud over den logiske opdeling af kundeindhold på programniveau giver Power Automate Government-tjenesten din organisation et sekundært lag af fysisk opdeling af kundeindhold ved hjælp af infrastrukturer, der er adskilt fra den infrastruktur, der anvendes til kommercielle Power Automate-kunder. Dette omfatter brug af Azure-tjenester i Azures Government Cloud. Du kan få mere at vide under [Azure Government](https://azure.microsoft.com/global-infrastructure/government/).

## <a name="customer-content-located-within-the-united-states"></a>Kundeindhold, der findes i USA

Power Automate US Government kører i datacentre, som fysisk er placeret i USA, og her gemmes kundeindhold som inaktive data i datacentre, der fysisk kun er placeret i USA.

## <a name="restricted-data-access-by-administrators"></a>Begrænset dataadgang af administratorer

Adgang til Power Automate US Government-kundeindhold for Microsoft-administratorer er begrænset til medarbejdere, der er amerikanske statsborgere. Disse personer gennemgår baggrundsundersøgelser i overensstemmelse med relevante offentlige standarder.

Power Automate-support og tekniske servicemedarbejdere har ikke løbende adgang til kundeindhold, der har Power Automate US Government som vært. Alle medarbejdere, der anmoder om midlertidig tilladelsesudvidelse, som vil give adgang til kundeindhold, skal først have bestået følgende baggrundstjek.

|Screening og baggrundstjek af Microsoft-personale <sup>1</sup>| Beskrivelse|
|---------------------------------------------------------------|-----------------------------------|
| Amerikansk statsborgerskab| Verificering af amerikansk statsborgerskab |
| Kontrol af ansættelseshistorik| Verificering af syv (7) års ansættelseshistorik|
| Verificering af uddannelse | Verificering af højeste uddannelse|
| Søgning efter personnummer (CPR)| Bekræftelse af, at medarbejdernes CPR-nummer er gyldigt|
| Kontrol af straffeattest| Syv (7) års kontrol af straffeattest for kriminelle handlinger og embedsmisbrug på delstats-, regional- og lokalplan samt føderalt|
| OFAC-liste (Office of Foreign Assets Control)| Validering i forhold til skattedepartementets liste over grupper, som amerikanere ikke må engagere i handelsmæssige eller økonomiske transaktioner|
| BIS-liste (Bureau of Industry and Security)| Validering i forhold til handelsministeriets liste over enkeltpersoner og grupperinger, der er bandlyst fra eksportaktiviteter|
| DDTC-liste (Office of Defense Trade Controls Debarred Persons) | Validering i forhold til udenrigsministeriets liste over enkeltpersoner og grupperinger, der er bandlyst fra eksportaktiviteter vedrørende våbenindustrien|
| Fingeraftrykskontrol| Kontrol af fingeraftryk i forhold til FBI-databaser|
| CJIS-baggrundsscreening| Delstatsrevision af den føderale og delstatslige kriminelle baggrund af delstats-CSA-udpeget myndighed i hver delstat, der har tilmeldt sig Microsoft CJIS IA-programmet |

<sup>1</sup> Gælder kun for personer med midlertidig eller løbende adgang til kundeindhold, der er hostet i Power Automate US Government (GCC).

## <a name="certifications-and-accreditations"></a>Certificeringer og godkendelser

Power Automate US Government er udviklet til at understøtte Federal Risk and Authorization Management Program-akkrediteringen (FedRAMP) på et niveau med høj effekt. Dette program resulterer i justering iht. DoD DISA IL2. FedRAMP-artefakter er tilgængelige til gennemsyn af føderale kunder, der skal overholde FedRAMP. Føderale myndigheder kan gennemse disse artefakter som et led i deres gennemgang for at udstede en ATO (dvs. driftsgodkendelse).

>[!NOTE]
>Power Automate er godkendt som en tjeneste i Azure Government FedRAMP ATO. Du kan finde flere oplysninger, herunder hvordan du får adgang til FedRAMP-dokumenterne, ved at gennemse [FedRAMP Marketplace](https://marketplace.fedramp.gov/#!/product/azure-government-includes-dynamics-365?sort=productName&productNameSearch=azure%20government).



Power Automate US Government har funktioner, der er designet til et understøtte kunders krav til CJIS-politik for retshåndhævende myndigheder. Gå til produktsiden for Power Automate US Government i Center for sikkerhed og rettigheder for at få flere detaljerede oplysninger om certificeringer og akkrediteringer.

Microsoft har udviklet platformen og driftsprocedurerne, så de opfylder kravene, der er tilpasset strukturen for overholdelse af DISA SRG IL4-standarderne. Microsoft forventer, at vores amerikanske forsvarsministeriums kontraktansatte kundebase og andre føderale myndigheder, der i øjeblikket benytter Microsoft Office 365 GCC High, vil bruge GCC High-udrulningen for Power Automate US Government, som gør det muligt for og kræver, at kunder benytter Azure AD Government til kundeidentiteter, i modsætning til GCC, som udnytter det offentlige Azure AD. Til vores amerikanske forsvarsministeriums kontraktansatte kundebase driver Microsoft servicen på en måde, som gør det muligt for disse kunder at opfylde ITAR-forpligtelsen og DFARS-anskaffelsesregler.

## <a name="power-automate-us-government-and-other-microsoft-services"></a>Power Automate US Government og andre Microsoft-tjenester

Power Automate US Government indeholder flere funktioner, der tillader brugere at oprette forbindelse til og integrere med andre af Microsofts servicetilbud til store virksomheder, f.eks. Office 365 US Government, Dynamics 365 US Government og Power Apps US Government.

Power Automate US Government kører i Microsoft-datacentre i overensstemmelse med en offentlig skyimplementeringsmodel for flere lejere. Dog er klientprogrammer, herunder men ikke begrænset til webbrugerklienten, Power Automate-mobilapplikationen (når tilgængelig) og alle tredjepartsklientprogrammer, der kan oprette forbindelse til Power Automate US Government, ikke omfattet af akkrediteringsgrænsen for Power Automate US Government. Government-kunder er ansvarlige for at administrere disse.

Power Automate US Government udnytter Office 365-kundeadministratorens brugergrænseflade til administration af kunder og fakturering.

Power Automate US Government vedligeholder de faktiske ressourcer, informationsstrømme og datastyring og anvender Office 365 til at levere de visuelle layouttyper, der præsenteres for kundeadministratoren gennem deres administrationskonsol. Med henblik på FedRAMP ATO-arv udnytter Power Automate US Government Azure (herunder Azure for Government) ATO'er til henholdsvis infrastruktur og platformservice.

Hvis du implementerer brugen af Active Directory Federation Services (AD FS) 2.0 og konfigurerer politikker for at sikre, at brugerne opretter forbindelse til tjenester via enkeltlogon, er alt kundeindhold, der midlertidigt er gemt, placeret i USA.

## <a name="power-automate-us-government-and-third-party-services"></a>Power Automate US Government og tjenester fra tredjepart

Power Automate US Government giver mulighed for at integrere tredjepartsprogrammer i servicen via [connectorer](https://docs.microsoft.com/connectors/index). Disse tredjepartsprogrammer og -tjenester kan omfatte lagring, overførsel og behandling af kundedata i din organisation på tredjepartssystemer, der ligger uden for Power Automate US Government-infrastrukturen og derfor ikke er omfattet af Power Automate US Governments databeskyttelse.

> [!TIP]
> Gennemse erklæringerne om beskyttelse af personlige oplysninger og overholdelse af angivne standarder, som angivet af tredjeparter, når den relevante brug af disse services i din organisation skal vurderes.

[Power Apps- og Power Automate-styringsspørgsmål](https://docs.microsoft.com/power-platform/admin/governance-considerations) kan hjælpe din organisation med at skabe opmærksomhed omkring de muligheder, der er tilgængelige på tværs af flere relaterede temaer, f.eks. arkitektur, sikkerhed, advarsel og handling samt overvågning.

## <a name="configure-mobile-clients"></a>Konfigurere mobilklienter

Her er de trin, du skal udføre for at logge på med Power Apps-mobilklienten.

1. Vælg ikonet med tandhjulet i nederste højre hjørne på logonsiden.
1. Vælg **Områdeindstillinger**.
1. Vælg en af følgende:
   - GCC: US Government GCC
   - GCC High: US Government GCC High.
1. Vælg OK.
1. Vælg **Log på** på logonsiden.

Mobilprogrammet bruger nu US Government Cloud.

## <a name="power-automate-us-government-and-azure-services"></a>Power Automate US Government og Azure Services

Power Automate US Government-services er installeret på Microsoft Azure Government. Azure Active Directory( Azure AD) er ikke en del af Power Automate US Government-akkrediteringsgrænsen, men er afhængig af en kundes [Azure AD](https://azure.microsoft.com/services/active-directory/) lejer for kundens lejer- og identitetsfunktioner, herunder autorisation, godkendelse i organisationsnetværket og licenser.

Når en bruger i en organisation, der bruger ADFS, forsøger at få adgang til Power Automate US Government, omdirigeres brugeren til en logon-side, der hostes af organisationens ADFS-server.

Brugeren angiver sine legitimationsoplysninger på organisationens ADFS-server. Organisationens ADFS-server forsøger at godkende legitimationsoplysningerne ved hjælp af organisationens Active Directory-infrastruktur.

Hvis godkendelsen lykkes, udsteder organisationens ADFS-server en SAML-anmodning (Security Assertion Markup Language), der indeholder oplysninger om brugerens id og gruppemedlemskab.

ADFS-kundeserveren underskriver denne billet ved hjælp af halvdelen af et asymmetrisk nøglepar og sender derefter billetten til Azure AD via krypteret TLS. Azure AD validerer signaturen ved hjælp af den anden halvdel af det asymmetriske nøglepar og giver derefter adgang baseret på billetten.

Oplysningerne om brugerens identitet og gruppemedlemskab forbliver krypterede i Azure AD. Med andre ord gemmes kun begrænsede brugeridentificerbare oplysninger i Azure AD.

Flere oplysninger om Azure AD-sikkerhedsarkitektur og implementering af kontrolelementer findes i Azure SSP.

Azure AD-kontoadministrationstjenester er tilknyttet fysiske servere, der administreres af Microsoft Global Foundation Services (GFS). Netværksadgang til disse servere styres af GFS-styrede netværksenheder ved hjælp af regler, der er angivet af Azure. Brugere interagerer ikke direkte med Azure AD.

## <a name="power-automate-us-government-service-urls"></a>URL-adresser til Power Automate US Government-service

Du kan bruge forskellige URL-adresser til at få adgang til Power Automate US Government-miljøer som vist i følgende tabel. Tabellen indeholder også de kommercielle URL-adresser som kontekstafhængig reference, du muligvis allerede kender.


Kommerciel version | US Government-version
------ | --------
[https://flow.microsoft.com](https://flow.microsoft.com) | [https://gov.flow.microsoft.us (GCC)](https://gov.flow.microsoft.us) og [https://high.flow.microsoft.us (GCC High)](https://high.flow.microsoft.us)
[https://admin.powerplatform.microsoft.com/](https://admin.powerplatform.microsoft.com/) | [https://gov.admin.flow.microsoft.us (GCC)](https://gov.admin.flow.microsoft.us) og [https://high.admin.flow.microsoft.us (GCC High)](https://high.admin.flow.microsoft.us)
[https://flow.microsoft.com/connectors](https://flow.microsoft.com/connectors) | [https://gov.flow.microsoft.us/connectors (GCC)](https://gov.flow.microsoft.us/connectors) og [https://high.flow.microsoft.us/connectors (GCC High)](https://high.flow.microsoft.us/connectors)


For de kunder, der implementerer netværksbegrænsninger, skal du sikre, at adgang til følgende domæner er tilgængelig for slutbrugerens adgangspunkter:

### <a name="gcc-customers"></a>GCC-kunder:
* .microsoft.us
* .azure-apihub.us
* .azure.us
* .usgovcloudapi.net
* .microsoftonline.com
* .microsoft.com
* .windows.net
* .azureedge.net
* .azure.net
* .crm9.dynamics.com

Se [IP-områder](https://www.microsoft.com/download/confirmation.aspx?id=57063) for AzureCloud. usgovtexas og AzureCloud. usgovvirginia for at give adgang til Common Data Service-forekomster, som brugere og administratorer kan oprette i din lejer. 

### <a name="gcc-high-customers"></a>GCC High-kunder:
* .microsoft.us
* .azure-apihub.us
* .azure.us
* .usgovcloudapi.net
* .microsoftonline.us
* .azureedge.net
* .azure.net
* .crm.microsoftdynamics.us

Se [IP-områder](https://www.microsoft.com/download/confirmation.aspx?id=57063) for AzureCloud. usgovtexas og AzureCloud. usgovvirginia for at give adgang til Common Data Service-forekomster, som brugere og administratorer kan oprette i din lejer. 


## <a name="connectivity-between-power-automate-us-government-and-public-azure-cloud-services"></a>Forbindelse mellem Power Automate US Government og Public Azure Cloud Services

Azure distribueres blandt flere skyer. Som standard har lejere tilladelse til at åbne firewallregler for en cloudspecifik instans, men det er anderledes for netværk på tværs af cloudmiljøer, hvor der kræves åbning af specifikke firewallregler for at kommunikere mellem tjenester. Hvis du er Power Automate-kunde, og du har eksisterende SQL-instanser i den offentlige Azure-cloud, som du skal bruge til at få adgang, skal du åbne specifikke firewallporte i SQL til Azure Government Cloud IP-pladsen for følgende datacentre:

- USGov Virginia
- USGov Texas

Se dokumentet [Azure IP-intervaller og -servicetags – US Government Cloud](https://www.microsoft.com/download/confirmation.aspx?id=57063) med fokus på AzureCloud.usgovtexas og AzureCloud.usgovvirginia. Bemærk også, at disse er de påkrævede IP-intervaller, for at dine slutbrugere kan få adgang til URL-adresserne for tjenesten.

## <a name="on-premises-data-gateway-configuration"></a>Konfiguration af datagateway i det lokale miljø

Installér en [datagateway i det lokale miljø](https://docs.microsoft.com/flow/gateway-manage) for at overføre data hurtigt og sikkert mellem en lærredsapp, der er bygget i Power Automate og en datakilde, der ikke er i cloudmiljøet. Eksempler omfatter SQL Server-databaser eller SharePoint-websites i det lokale miljø.

Hvis din organisation (lejer) allerede har konfigureret og oprettet forbindelse til datagatewayen i det lokale miljø for Power BI US Government, vil den proces, som din organisation udførte for at aktivere den, også muliggøre forbindelse til Power Automate i det lokale miljø. Hvis du ikke kan oprette forbindelse til din lejer, skal du muligvis gå gennem en "hvidlistningsproces", som aktiverer denne egenskab for lejeren. Hvis denne situation opstår, kan du åbne en supportanmodning for at få taget højde for dine behov. Supportteamet følger en fastlagt proces i forbindelse med løsningen af din anmodning.

## <a name="power-automate-us-government-feature-limitations"></a>Power Automate US Government-funktionsbegrænsninger

Nogle af de funktioner, der er tilgængelige i den kommercielle version af Flow, er ikke tilgængelige for Flow US Government-kunder. Flow-teamet arbejder aktivt på at gøre disse funktioner tilgængelige for US Government-kunder og opdaterer denne artikel, når funktionerne bliver tilgængelige.

- [AI Builder](https://docs.microsoft.com/ai-builder/) er endnu ikke tilgængelig til GCC- og GCC High-lejere.

- Der findes [godkendelser](./modern-approvals.md) til GCC- og GCC High-lejere, som er underlagt følgende:
  * Der er ingen handlingssupport, der skal godkendes. Godkendelsesmails indeholder links til Power Automate-godkendelsescenter, som brugerne kan svare på.
  * Der er ingen markdown-understøttelse af godkendelsesmail. 

- [Indsendelse af skabeloner](https://docs.microsoft.com/flow/publish-a-template)

- [Connectorer](https://docs.microsoft.com/connectors/index) – De mest populære connectorer, der bruges i vores kommercielle service (baseret på brugstelemetri), er blevet udgivet. Hvis der findes en connector i det kommercielle tilbud, som du ikke kan se udrullet, kan du kontakte support, hvorefter din anmodning gennemgås.

- [Power BI](https://docs.microsoft.com/connectors/powerbi/)– Power Automate US Government understøtter ikke Power BI på nuværende tidspunkt.

- [Power Platform Administration](https://docs.microsoft.com/power-platform/admin/admin-documentation) – Du kan brug administrationen til at [åbne supportanmodninger](https://docs.microsoft.com/power-platform/admin/get-help-support), men andre funktioner er i øjeblikket ikke tilgængelige for US Government-lejere.

### <a name="see-also"></a>Se også

- [Flows for brugergrænseflade](https://docs.microsoft.com/power-automate/ui-flows/overview).

- [Dynamics 365 US Government](https://docs.microsoft.com/power-platform/admin/microsoft-dynamics-365-government).

- [Power Apps US Government](https://docs.microsoft.com/power-platform/admin/powerapps-us-government).
