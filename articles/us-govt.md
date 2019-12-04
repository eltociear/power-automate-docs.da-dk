---
title: Power Automate til den amerikanske regering
description: Indeholder oplysninger om beskrivelse, planer og begrænsninger i forbindelse med Power Automate US Government-tjenesten
services: ''
suite: flow
author: msftman
ms.service: flow
ms.devlang: na
ms.topic: article
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 2b2b53b833711311c039678a9196a2833d50c84c
ms.sourcegitcommit: 52e739e5d53464b80e572928f131890562fc0396
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/21/2019
ms.locfileid: "74370853"
---
# <a name="power-automate-us-government"></a>Power Automate til den amerikanske regering
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

For at imødegå de unikke krav, der er under stadig ændring, i den offentlige sektor i USA har Microsoft oprettet Power Automate US Government-planer. I dette afsnit kan du se en oversigt over funktioner, der er specifikke for Power Automate US Government. Vi anbefaler, at du læser dette supplerende afsnit samt emnet [Introduktion](https://docs.microsoft.com/flow/getting-started) til Power Automate-tjenesten. Denne tjeneste kaldes ofte bare *Flow GCC*.

Beskrivelsen af Power Automate US Government-tjenesten er et tillæg til generelle beskrivelse af Power Automate-tjenesten. Den definerer de entydige forpligtelser og forskelle i forhold til de generelle Power Automate-tilbud, der har været tilgængelige for vores kunder siden oktober 2016.

## <a name="about-power-automate-us-government-environments-and-plans"></a>Om Power Automate US Government-miljøer og -planer

Power Automate US Government-planer er månedsabonnementer, og de kan gives i licens til et ubegrænset antal brugere.

Power Automate GCC-miljøet overholder de angivne føderale krav til cloudtjenester, herunder FedRAMP High og DoD DISA IL2. Det overholder også kravene fra de strafferetlige systemer (CJI-datatyper).

Ud over funktionerne og egenskaberne i Power Automate kan de organisationer, der bruger Power Automate US Government, drage nytte af følgende unikke funktioner:

- Din organisations kundeindhold er fysisk adskilt fra kundeindholdet i kommercielle Power Automate-tilbud.

- Din organisations kundeindhold er gemt i USA.

- Adgang til din organisations kundeindhold er begrænset til godkendt Microsoft-personale.

- Power Automate US Government overholder alle certificeringer og godkendelser, som er påkrævet af kunder i den amerikanske offentlige sektor.

Fra september 2019 kan berettigede kunder vælge at udrulle Power Automate US Government til **GCC High**-miljøet, hvilket muliggør enkeltlogon og problemfri integration med udrulninger af Microsoft Office 365 GCC High. 

Microsoft har udviklet platformen og driftsprocedurerne, så de opfylder kravene, der er tilpasset strukturen for overholdelse af DISA SRG IL4-standarderne. Vi forventer, at underleverandører til det amerikanske forsvarsministerium og andre føderale myndigheder, der i øjeblikket udnytter Office 365 GCC High, så de kan bruge GCC High-udrulningsmuligheden i Power Automate. Dette muliggør og kræver, at kunden bruger Microsoft Azure Active Directory Government til kundeidentiteter, i modsætning til GCC, som bruger den offentlige Microsoft Azure Active Directory. Til underleverandører til det amerikanske forsvarsministerium bruger Microsoft tjenesten på en måde, der gør det muligt for disse kunder at overholde ITAR- og DFARS-reglerne, som det dokumenteres og kræves i deres kontrakter med det amerikanske forsvarsministerium.

## <a name="customer-eligibility"></a>Berettigelse for kunden

Power Automate US Government er tilgængelig for (1) amerikanske føderale, statslige, lokale, tribale og regionale offentlige institutioner og (2) andre enheder, der håndterer data, der er underlagt offentlige krav og bestemmelser, samt i de tilfælde, hvor brugen af Power Automate US Government er egnet til at imødekomme disse krav, såfremt det vurderes, at kunden er berettiget til denne brug. Microsofts validering af berettigelse omfatter bekræftelse af håndtering af data i henhold til ITAR (International Traffic in Arms Regulations), retshåndhævelsesdata i henhold til FBI's CJIS-politik (Criminal Justice Information Services) eller andre offentligt regulerede eller kontrollerede data. Validering kan kræve sponsorat af en offentlig myndighed med specifikke krav til håndteringen af data.

Enheder med spørgsmål om berettigelse til Power Automate US Government skal kontakte deres kontoteam. Microsoft validerer berettigelsen igen, når kundekontrakter om Power Automate US Government fornyes.

## <a name="power-automate-us-government-plans"></a>Planer i forbindelse med Power Automate US Government-planer

Adgang til Power Automate US Government-planer er begrænset til de tilbud, der er beskrevet i følgende afsnit; hver enkelt plan tilbydes som et månedsabonnement og kan gives i licens til et ubegrænset antal brugere:

- Power Automate/Power Apps Plan 1 US Government

- Power Automate/Power Apps Plan 2 US Government

- Ud over de separate planer er Power Automate- og Power Apps-funktionerne også inkluderet i visse Office 365 US Government- og Dynamics 365 US Government-planer, hvilket giver kunderne mulighed for at udvide og tilpasse Office 365 og Dynamics 365 med Power Automate- og Power Apps-funktioner.

> [!NOTE]
> Licenser er tilgængelige i kundelejere fra midten af april 2019.

Yderligere oplysninger samt oplysninger om forskellene i funktionaliteten mellem disse licensgrupper er beskrevet mere detaljeret her: [Power Automate-licensoplysninger](https://flow.microsoft.com/pricing/).

Power Automate US Government er tilgængelig gennem volumenlicens og Cloud Solution Provider-købskanaler.

## <a name="differences-between-customer-data-and-customer-content"></a>Forskelle i kundedata og kundeindhold

Kundedata, som defineret i Vilkår for onlinetjenester, betyder alle data, herunder alle tekst-, lyd-, video- eller billedfiler og al software, der er leveret til Microsoft af eller på vegne af kunder ved hjælp af en onlinetjeneste.

Kundeindhold refererer til et bestemt undersæt af kundedata, der er oprettet direkte af brugere, f.eks. indhold, der er gemt i databaser gennem poster i [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)-enhederne (f.eks. kontaktoplysninger). Indhold opfattes generelt som fortrolige oplysninger og som et led i normale tjenestehandlinger sendes de ikke ukrypteret via internettet.

Du kan få flere oplysninger om, hvordan Power Automate beskytter kundedata, i [Microsoft Online Services Center for sikkerhed og rettigheder](https://www.microsoft.com/trustcenter/cloudservices/business-application-platform/default.aspx).

## <a name="data-segregation-for-government-community-cloud"></a>Dataopdeling for Government Community Cloud

Når Power Automate-tjenesten er klargjort som en del af Power Automate US Government, tilbydes den i overensstemmelse med NIST Special Publication 800-145 (National Institute of Standards og Technology).

Microsoft refererer til dette tilbud som Government Community Cloud (GCC).

Ud over den logiske adskillelse af kundeindhold på programlaget giver Power Automate Government-tjenesten din organisation et sekundært lag af fysisk adskillelse i forbindelse med kundeindhold ved hjælp af en infrastruktur, der er adskilt fra den infrastruktur, der bruges til kommercielle Power Automate-kunder. Dette omfatter brugen af Azure-tjenester i Azures Government Cloud. Du kan få mere at vide under [Azure Government](https://azure.microsoft.com/global-infrastructure/government/).

## <a name="customer-content-located-within-the-united-states"></a>Kundeindhold, der er placeret i USA

Power Automate US Government kører i datacentre, som fysisk er placeret i USA, og her gemmes kundeindhold som inaktive data i datacentre, der fysisk kun er placeret i USA.

## <a name="restricted-data-access-by-administrators"></a>Begrænset dataadgang for administratorer

Microsoft-administratorers adgang til Power Automate US Government-kundeindhold er begrænset til medarbejdere, der er amerikanske statsborgere. Der udføres et baggrundstjek af disse medarbejdere i overensstemmelse med de relevante regeringsstandarder.

Power Automate-supportmedarbejdere og tekniske medarbejder har som udgangspunkt ikke adgang til kundeindhold, der hostes i Power Automate US Government. Alle medarbejdere, der anmoder om midlertidig tilladelse, som giver dem adgang til kundeindhold, skal først bestå følgende baggrundstjek.

|Screening og baggrundstjek af Microsoft-personale <sup>1</sup>| Beskrivelse|
|---------------------------------------------------------------|-----------------------------------|
| Amerikansk statsborgerskab| Bekræftelse af amerikansk statsborgerskab |
| Kontrol af ansættelseshistorik| Bekræftelse af syv (7) års ansættelseshistorik|
| Bekræftelse af uddannelse | Bekræftelse af højeste gennemførte uddannelse|
| Søgning efter CPR-nummer| Bekræftelse af, at medarbejdernes CPR-nummer er gyldigt|
| Kontrol af straffeattest| En kontrol af straffeattest for forbrydelser og forseelser på føderalt, statsligt, amtsligt og lokalt niveau i en syvårig (7) periode|
| OFAC-liste (Office of Foreign Assets Control)| Validering i forhold til det amerikanske skatteministeriums liste over grupper, som amerikanske personer ikke må handle eller indgå økonomiske transaktioner med|
| BIS-liste (Bureau of Industry and Security)| Validering i forhold til det amerikanske handelsministeriums liste over enkeltpersoner og enheder, der er udelukket fra at indgå i eksportaktiviteter|
| DETC-liste (Office of Defense Trade Controls Debarred Persons) | Validering i forhold til det amerikanske statsministeriums liste over enkeltpersoner og enheder, som er udelukket fra at indgå i aktiviteter, der er relateret til forsvarsindustrien|
| Kontrol af fingeraftryk| Kontrol af fingeraftryk i forhold til FBI's databaser|
| Screening af CJIS-baggrund| Gennemgang af kriminalhistorik med statslige domfældelser på føderalt og statsligt plan af en statsudnævnt CSA-myndighed i hver enkelt stat, der har tilmeldt sig Microsofts CJIS IA-program |

<sup>1</sup> Gælder kun for medarbejdere med midlertidig eller stående adgang til kundeindhold, der hostes i Power Automate US Government (GCC).

## <a name="certifications-and-accreditations"></a>Certificeringer og akkrediteringer

Power Automate US Government er udviklet til at understøtte FedRAMP-akkreditering (Federal Risk and Authorization Management Program) på niveauet High Impact (Stor indvirkning). Dette program resulterer i justering iht. DoD DISA IL2. FedRAMP-artefakter er tilgængelige til gennemsyn af føderale kunder, som skal overholde FedRAMP. Føderale myndigheder kan gennemse disse artefakter som et led i deres gennemgang for at udstede en ATO (dvs. driftsgodkendelse).

> [!NOTE]
> I øjeblikket gennemgås Power Automate US Government-tjenester i forhold til FedRAMP, men de er tildelt en SAR (Security Assessment Report) af en kvalificeret [3PAO](https://www.fedramp.gov/3pao-requirements-update/).

Da Microsoft vil opdatere FedRAMP-artefakter som en del af standardgennemgangscyklusserne, opdateres indholdet tilsvarende.

Power Automate US Government indeholder funktioner, der er udviklet til at understøtte kundernes CJIS-politikkrav til retshåndhævelsesinstanser. Gå til produktsiden for Power Automate US Government i Center for sikkerhed og rettigheder for at få flere detaljerede oplysninger om certificeringer og akkrediteringer.

Microsoft har udviklet platformen og driftsprocedurerne, så de opfylder kravene, der er tilpasset strukturen for overholdelse af DISA SRG IL4-standarderne. Vi forventer, at underleverandører til det amerikanske forsvarsministerium og andre føderale myndigheder, der i øjeblikket udnytter Microsoft Office 365 GCC High, så de kan bruge GCC High-udrulningsmuligheden i Power Automate, hvilket muliggør og kræver, at kunden bruger Azure AD Government til kundeidentiteter, i modsætning til GCC, som bruger den offentlige Azure AD Til underleverandører til det amerikanske forsvarsministerium bruger Microsoft tjenesten på en måde, der gør det muligt for disse kunder at overholde ITAR- og DFARS-reglerne.

## <a name="power-automate-us-government-and-other-microsoft-services"></a>Power Automate US Government og andre Microsoft-tjenester

Power Automate US Government indeholder flere funktioner, der tillader brugere at oprette forbindelse til og integrere med andre af Microsofts tjenestetilbud til store virksomheder, f.eks. Office 365 US Government, Dynamics 365 US Government og Power Apps US Government.

Power Automate US Government kører i Microsofts datacentre i overensstemmelse med en offentlig cloududrulningsmodel med flere lejere; klientprogrammer, herunder, men ikke begrænset til webbrugerklienten, Power Automate-mobilprogrammet (når det er tilgængeligt) og et vilkårligt klientprogram fra tredjepart, som opretter forbinder til Power Automate US Government, er ikke en del af Power Automate US Governments akkrediteringsgrænse. Government-kunder er ansvarlige for at administrere disse.

Power Automate US Government udnytter brugergrænsefladen for Office 365-kundeadministratorer i forbindelse med kundeadministration og fakturering.

Power Automate US Government vedligeholder de faktiske ressourcer, informationsflow og dataadministration samtidig med, at man stoler på, at Office 365 leverer de visuelle formater, som kundeadministratoren får vist via administrationskonsollen. I forbindelse med FedRAMP ATO-nedarvning anvender Power Automate US Government Azure ATO'er (herunder Azure for Government) til henholdsvis infrastruktur- og platformstjenester.

Hvis du bruger Active Directory Federation Services (AD FS) 2.0 og opretter politikker for at sikre, at brugerne opretter forbindelse til tjenesterne vha. enkeltlogon, vil alt kundeindhold, der er midlertidigt cachelagret, være placeret i USA.

## <a name="power-automate-us-government-and-third-party-services"></a>Power Automate US Government og tredjepartstjenester

Power Automate US Government giver mulighed for at integrere tredjepartsprogrammer i tjenesten via [Connectorer](https://docs.microsoft.com/connectors/index). Disse tredjepartsprogrammer og -tjenester kan omfatte lagring, overførsel og behandling af din organisations kundedata på tredjepartssystemer, der ligger uden for Power Automate US Government-infrastrukturen og derfor ikke er dækket af de angivne standarder og forpligtelser til databeskyttelse, der ligger i Power Automate US Government.

> [!TIP]
> Gennemse erklæringerne om beskyttelse af personlige oplysninger og overholdelse af angivne standarder, som angivet af tredjeparter, når den relevante brug af disse tjenester i din organisation skal vurderes.

## <a name="power-automate-us-government-and-azure-services"></a>Power Automate US Government og Azure-tjenester

Power Automate US Government-tjenesterne udrulles til Microsoft Azure Government. Azure Active Directory (Azure AD) er ikke en del af Power Automate US Government-akkrediteringsgrænsen, men er afhængig af en kundes [Azure AD](https://azure.microsoft.com/services/active-directory/)-lejer i forbindelse med kundens lejer- og id-funktioner, herunder godkendelse, samlet godkendelse og licenser.

Når en bruger i en organisation anvender ADFS forsøg til at få adgang til Power Automate US Government, omdirigeres brugeren til en logonside, der hostes på organisationens ADFS-server.

Brugeren angiver sine legitimationsoplysninger på organisationens ADFS-server. Organisationens ADFS-server forsøger at godkende legitimationsoplysningerne ved hjælp af organisationens Active Directory-infrastruktur.

Hvis godkendelsen lykkes, udsteder organisationens ADFS-server en SAML-anmodning (Security Assertion Markup Language), der indeholder oplysninger om brugerens id og gruppemedlemskab.

Kundens ADFS-server signerer denne anmodning ved hjælp af den ene halvdel af et asymmetrisk nøglepar, og derefter sender den anmodningen til Azure AD via krypteret TLS. Azure AD validerer signaturen ved hjælp af den anden halvdel af det asymmetriske nøglepar, og giver derefter adgang baseret på anmodningen.

Oplysningerne om brugerens id og gruppemedlemskab forbliver krypteret i Azure AD. Det er med andre ord kun begrænsede oplysninger, der kan identificere brugeren, der gemmes i Azure AD.

Du kan finde alle oplysninger om Azure AD-sikkerhedsarkitekturen og kontrolimplementeringen i Azure SSP.

Azure AD-kontoadministrationstjenesterne hostes på fysiske servere, der administreres af Microsoft Global Foundation Services (GFS). Netværksadgangen til disse servere styres af GFS-administrerede netværksenheder ved hjælp af regler, der er angivet af Azure. Brugerne interagerer ikke direkte med Azure AD.

## <a name="power-automate-us-government-service-urls"></a>URL-adresser til Power Automate US Government-tjenesten

Du kan bruge forskellige URL-adresser til at få adgang til Power Automate US Government-miljøer som vist i følgende tabel. Tabellen indeholder også de kommercielle URL-adresser som kontekstafhængig reference, som du muligvis allerede kender.


Kommerciel version | US Government-version
------ | --------
https://flow.microsoft.com | https://gov.flow.microsoft.us (GCC) og https://high.flow.microsoft.us (GCC High)
https://admin.flow.microsoft.com | https://gov.admin.flow.microsoft.us (GCC) og https://high.admin.flow.microsoft.us (GCC High)
https://flow.microsoft.com/connectors | https://gov.flow.microsoft.us/connectors (GCC) og https://high.flow.microsoft.us/connectors (GCC High)


For de kunder, der implementerer netværksbegrænsninger, skal du sørge for, at adgangen til følgende domæner er tilgængelige for dine slutbrugeres adgangspunkter:

### <a name="gcc-customers"></a>GCC-kunder:
* . microsoft.us
* .azure-apihub.us
* . azure.us
* .usgovcloudapi.net
* .microsoftonline.com
* . microsoft.com
* .windows.net
* . azureedge.net
* . azure.net
* .crm9.dynamics.com

Se [IP-områder](https://www.microsoft.com/download/confirmation.aspx?id=57063) for AzureCloud. usgovtexas og AzureCloud. usgovvirginia for at give adgang til Common Data Service-forekomster, som brugere og administratorer kan oprette i din lejer. 

### <a name="gcc-high-customers"></a>GCC High-kunder:
* . microsoft.us
* .azure-apihub.us
* . azure.us
* .usgovcloudapi.net
* .microsoftonline.us
* .azureedge.net
* .azure.net
* .crm.microsoftdynamics.us

Se [IP-områder](https://www.microsoft.com/download/confirmation.aspx?id=57063) for AzureCloud. usgovtexas og AzureCloud. usgovvirginia for at give adgang til Common Data Service-forekomster, som brugere og administratorer kan oprette i din lejer. 


## <a name="connectivity-between-power-automate-us-government-and-public-azure-cloud-services"></a>Forbindelse mellem Power Automate US Government- og Public Azure Cloud-tjenester

Azure er fordelt på flere cloudmiljøer. Som standard har lejere tilladelse til at åbne firewallregler for en cloudspecifik instans, men det er anderledes for netværk på tværs af cloudmiljøer, hvor der kræves åbning af specifikke firewallregler for at kommunikere mellem tjenester. Hvis du er Power Automate-kunde, og du har eksisterende SQL-instanser i den offentlige Azure-cloud, som du skal bruge til at få adgang, skal du åbne specifikke firewallporte i SQL til Azure Government Cloud IP-pladsen for følgende datacentre:

- USGov Virginia
- USGov Texas

Se i dokumentet [Azure IP-intervaller og tjenestetags – US Government Cloud](https://www.microsoft.com/download/confirmation.aspx?id=57063) med fokus på AzureCloud.usgovtexas og AzureCloud.usgovvirginia. Bemærk også, at disse er de påkrævede IP-intervaller, for at dine slutbrugere kan få adgang til URL-adresserne for tjenesten.

## <a name="on-premises-data-gateway-configuration"></a>Konfigurer en datagateway i det lokale miljø

Installér en [datagateway i det lokale miljø](https://docs.microsoft.com/flow/gateway-manage) for at overføre data hurtigt og sikkert mellem en lærredsapp, der er bygget i Power Automate og en datakilde, der ikke er i cloudmiljøet. Eksempler omfatter SQL Server-databaser eller SharePoint-websteder i det lokale miljø.

Hvis din organisation (lejer) allerede har konfigureret og oprettet forbindelse til datagatewayen i det lokale miljø for Power BI US Government, vil den proces, som din organisation udførte for at aktivere den, også muliggøre forbindelse til Power Automate i det lokale miljø. Hvis du ikke kan oprette forbindelse til din lejer, skal du muligvis gå gennem en hvidlistningsproces, som aktiverer denne egenskab for lejeren. Hvis denne situation opstår, kan du åbne en supportanmodning for at få taget højde for dine behov. Supportteamet følger en fastlagt proces i forbindelse med løsningen af din anmodning.

## <a name="power-automate-us-government-feature-limitations"></a>Funktionsbegrænsninger i Power Automate US Government

Nogle af de funktioner, der er tilgængelige i den kommercielle version af Flow, er ikke tilgængelige for Flow US Government-kunder. Flow-teamet arbejder aktivt på at gøre disse funktioner tilgængelige for US Government-kunder og opdaterer denne artikel, når funktionerne bliver tilgængelige.

- Udløs Power Automate US Government-flow *vha.* SharePoint-lister

- Udløs Power Automate US Government-flow *vha.* Dynamics 365 GCC

- [Godkendelser](./modern-approvals.md) – selvom US Government-kunder bruger Power Automate-godkendelser, kan de ikke sende handlingsrettede mails og skal videresende godkendere til godkendelsescenteret. Som en løsning kan Power Automate-oprettere bruge standardmailconnectorer til at underrette andre om, at der er en ventende godkendelse. I dette tilfælde indeholder de også linket i mailen, der peger på det godkendelsescenter, hvor US Government-kunder kan reagere på godkendelserne.

- [Forbrugsanalyse](https://flow.microsoft.com/blog/admin-analytics/)

- [Power Automate-mobilapp](https://docs.microsoft.com/flow/mobile-manage-flows)

- [Indsender skabeloner](https://docs.microsoft.com/flow/publish-a-template)

    > [!NOTE]
    > Indsendelse af skabeloner er deaktiveret i GCC for at imødegå bekymringer i forhold til styring af virksomhedsdata og dataflow.

- [Connectorer](https://docs.microsoft.com/connectors/index) – de mest populære connectorer, der anvendes i vores kommercielle tjeneste (baseret på forbrugstelemetri), er udgivet; hvis der er en connector tilgængelig i det kommercielle tilbud, som du kan se ikke er udrullet, skal du kontakte support, så gennemgår vi din anmodning

- [Power BI](https://docs.microsoft.com/connectors/powerbi/) – Power Automate US Government understøtter ikke Power BI på nuværende tidspunkt.

- [Power Platform Administration](https://docs.microsoft.com/power-platform/admin/admin-documentation) – Du kan bruge Administration til at [åbne supportanmodninger](https://docs.microsoft.com/power-platform/admin/get-help-support), men der er ikke andre funktioner tilgængelig i US Government-lejere i øjeblikket.

### <a name="see-also"></a>Se også

[Power Apps US Government](https://docs.microsoft.com/power-platform/admin/powerapps-us-government)
