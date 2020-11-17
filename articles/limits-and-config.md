---
title: Grænser og konfiguration | Microsoft Docs
description: Grænser og konfiguration
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 336c3ec69ce6f226c881b68deaee4215382df83b
ms.sourcegitcommit: 7a3df04b817ecf8ad99ca7bb551804fe83b0861d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/25/2020
ms.locfileid: "4109948"
---
# <a name="limits-and-configuration-in-power-automate"></a>Grænser og konfiguration i Power Automate

Dette emne indeholder oplysninger om de aktuelle grænser for og konfigurationsoplysninger om flows.

>[!TIP]
>Se [prissætningen](https://flow.microsoft.com/pricing) for at få flere oplysninger om de forskellige planer, der er tilgængelige.

## <a name="request-limits"></a>Anmodningsgrænser
Disse er grænser for en enkelt udgående anmodning.

### <a name="timeout"></a>Timeout

| Navn | Grænse |
| --- | --- |
| Anmod om timeout for synkrone kald |120 sekunder |
| Anmod om timeout for asynkrone kald|Kan konfigureres. Maksimum er 30 dage. |

>[!NOTE]
>Hvis du tester et flow, der kører i længere end 10 minutter, kan du få en timeoutmeddelelse i Power Automate, selvom flowet fortsat kører i baggrunden. Hvis det sker, skal du åbne visningen igen for at modtage den aktuelle status. 

### <a name="message-size"></a>Meddelelsesstørrelse

| Navn | Grænse | Noter |
| --- | --- | --- |
| Meddelelsesstørrelse |100 MB |Det er ikke alle API'er, der understøtter de fulde 100 MB. |
| Grænse for evaluering af udtryk |131.072 tegn |`@concat()`, `@base64()`, `string` må ikke overskride denne grænse. |

### <a name="retry-policy"></a>Prøv politik igen

| Navn | Grænse |Noter|
| --- | --- | --- |
| Antal nye forsøg |90 | Standard er 2. Hvis du vil ændre standarden, skal du bruge indstillingerne for handling. | 
| Maks. forsinkelse ved nyt forsøg |1 dag |  |
| Min. forsinkelse ved nyt forsøg |5 sekunder |  |

## <a name="run-duration-and-retention"></a>Varighed af kørsel og opbevaring
Disse er grænserne for en enkelt flowkørsel.

| Navn | Grænse | Noter |
| --- | --- | --- |
| Varighed af kørsel |30 dage |Omfatter arbejdsprocesser med ventende trin, såsom godkendelser. Efter 30 dage opstår der timeout for eventuelle afventende trin. |
| Lageropbevaring |30 dage |Dette er fra starttidspunkt for kørslen. |
| Min. interval for gentagelse |1 minut | |
| Maks. interval for gentagelse |500 dage | |
| Maks. opbevaring af kørselshistorik |28 dage ifølge GDPR-reglerne. | |
|Mindste interval for udsættelse – gratis licens og Plan 1-licens|5 sekunder||
|Mindste interval for udsættelse – Plan 2-licens|1 sekund||

>[!TIP]
>De enkelte connectorer kan også have deres egne grænser.

## <a name="looping-and-debatching-limits"></a>Grænser for løkker og fjernelse af batchinddeling
Disse er grænserne for en enkelt flowkørsel. 

| Navn | Grænse | Noter |
| --- | --- | --- |
| Anvend for hver enkelt element – Office 365 og gratis licenser|5.000 |Du kan bruge filterhandlingen til at filtrere større matrixer efter behov. |
| Anvend for hver enkelt element – licenser af typen Plan 1, Plan 2, Pr. bruger og Pr. flow|100.000 |Du kan bruge filterhandlingen til at filtrere større matrixer efter behov. |
| Indtil gentagelser |5.000 | |
| SplitOn-elementer – Office 365 og gratis licenser |5.000 ||
| SplitOn-elementer – licenser af typen Plan 1, Plan 2, Pr. bruger og Pr. flow |100.000 ||
| Anvend for hver parallelitet |50 |Som standard køres løkker i rækkefølge (i bund og grund er parallelitet 1). Du kan konfigurere op til 50 parallelt. |
| Handlinger for samtidige udgående kald – gratis, Office 365, Plan 1-licenser og prøveversioner | ~500 | Reducer antallet af samtidige anmodninger, eller reducer varigheden efter behov. |
| Handlinger med samtidige udgående opkald – licenser af typen Plan 2, Pr. bruger og Pr. flow | ~2.500 | Reducer antallet af samtidige anmodninger, eller reducer varigheden efter behov. | 

## <a name="daily-limits"></a>Daglige grænser
Der anvendes daglige grænser i et 24-timers glidende vindue. Grænser for dataforbrug refererer til den mængde lager, der bruges til at gemme oversigten over flowet.  Dette er de maksimumgrænser, der er tilladt for lagerstyring i planen. Du kan finde flere oplysninger om Power Platform-daglige grænser under [anmodningsgrænser og tildelinger](https://aka.ms/platformlimits).

| **Brugerlicenser**                                        |    **Handlinger/24 timer**                       |    **Dataforbrug/24 timer**   |
|----------------------------------------------------------|-------------------------------------------------|--------------------------------------|
| Power Automate-plan pr. flow                             | 15.000 pr. flow med licenseret flow               | 50 GB                                 |
| Dynamics 365 Enterprise-applikationer<sup>1</sup>         | 20.000 på tværs af alle flow, der ejes af en enkelt bruger  | 10 GB                                 |
| Dynamics 365 Professional<sup>2</sup>                   | 10.000 på tværs af alle flow, der ejes af en enkelt bruger  | 10 GB                                 |
| Dynamics 365 for Team Members, Power Apps pr. bruger, Power Automate pr. brugerplan | 5.000 på tværs af alle flow, der ejes af en enkelt bruger   | 10 GB            | 
| Office-licenser (de inkluderer Power Apps/Power Automate)<sup>3</sup>, Power Apps pr. app-planer, programbruger/ikke-interaktive brugere | 2.000 på tværs af alle flow, der ejes af en enkelt bruger | 1 GB                        |

<sup>1</sup>Dynamics 365 Enterprise-programmer omfatter Dynamics 365 Sales Enterprise, Dynamics 365 Customer Service Enterprise, Dynamics 365 Field Service, Dynamics 365 Project Service Automation, Dynamics 365 Retail, Dynamics 365 Talent, Dynamics 365 Customer Engagement-plan.

<sup>2</sup>Dynamics 365 Professional omfatter Dynamics 365 Sales Professional og Dynamics 365 Customer Service Professional.

<sup>3</sup>Se **Tillæg C** til Microsoft 365-licenser, der omfatter Power Apps- og Power Automate-funktioner, i [Licensvejledningen](https://go.microsoft.com/fwlink/p/?linkid=2085130).

## <a name="throughput-limits"></a>Grænser for gennemløb

|Navn|Grænse|Noter|
|---|---|---|
|Slutpunkt for kørsel – antal læste kald tilladt for hver 5. minut – gratis, Office 365, Plan 1-licenser og prøveversioner|6,000||
|Slutpunkt for kørsel – antal læste kald tilladt for hver 5. minut – betalte licenser af typen Plan 2, Pr. bruger og Pr. flow|60,000||
|Slutpunkt for kørsel: Aktivér kald for hver 5. minut – gratis, Office 365, Plan 1-licenser og prøveversioner|4,500||
|Slutpunkt for kørsel: Antal aktiverede kald tilladt for hver 5. minut – betalte licenser af typen Plan 2, Pr. bruger og Pr. flow|45,000||
|Mængden af tilladt gennemløb for hver 5. minut – gratis, Office 365, Plan 1-licenser og prøveversioner|600 MB||
|Mængden af tilladt gennemløb for hver 5. minut – betalte licenser af typen Plan 2, Pr. bruger og Pr. flow|6 GB||

## <a name="flow-limits"></a>Flowgrænser
Dette er grænser for flows.

| Navn | Grænse | Noter |
| --- | --- | --- |
| Handlinger pr. arbejdsproces |500|Du kan tilføje indlejrede arbejdsprocesser for at udvide efter behov. |
| Tilladt dybde for handlingsindlejring |8 |Du kan tilføje indlejrede arbejdsprocesser for at udvide efter behov. |
| Maksimalt antal tegn pr. udtryk |8,192 | |
| `action`/`trigger` navnegrænse |80 | |
| `description` længdegrænse |256 | |
| Løsningsagnostiske flows pr. bruger  |600 | |

## <a name="sharepoint-limits"></a>SharePoint-grænser
Der er [begrænsninger](https://docs.microsoft.com/connectors/sharepointonline/#limits) for, hvordan du kan bruge Microsoft SharePoint sammen med Power Automate og Power Apps.

[!INCLUDE [sharepoint-detailed-docs](includes/sharepoint-detailed-docs.md)]

## <a name="ip-address-configuration"></a>Konfiguration af IP-adresse
Den IP-adresse, Power Automate-anmodninger sendes fra, afhænger af det [område](regions-overview.md), hvor det [miljø](environments-overview-admin.md), som indeholder flowet, er placeret. Vi publicerer i øjeblikket ikke FQDN'er, der er tilgængelige for flowscenarier.

>[!IMPORTANT]
> Nogle kald af et flow kommer fra de IP-adresser, der er angivet i dokumentationen til [Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses). Følgende er eksempler på disse kald: HTTP eller HTTP + OpenAPI.

### <a name="logic-apps"></a>Logikapps
Kald, der foretages fra et flow, går direkte gennem servicen Azure Logic App. Følgende er eksempler på disse kald: HTTP eller HTTP + OpenAPI. Se [i dokumentationen til Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses), hvilke IP-adresser der anvendes af denne tjeneste.

### <a name="connectors"></a>Connectors
Kald fra en connector i et flow (f.eks. SQL-API eller SharePoint-API), kommer fra de IP-adresser, der er angivet her:

| Område | Udgående IP-adresse |
| --- | --- |
| Asien og Stillehavsområdet | 13.75.36.64 – 13.75.36.79, 13.67.8.240 – 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australien  | 13.70.72.192 – 13.70.72.207, 13.72.243.10, 13.77.50.240 – 13.77.50.255, 13.70.136.174 |
| Canada | 13.71.170.208 – 13.71.170.223, 13.71.170.224 – 13.71.170.239, 52.237.24.126, 40.69.106.240 – 40.69.106.255, 52.242.35.152|
| Europa | 13.69.227.208 – 13.69.227.223, 52.178.150.68, 13.69.64.208 – 13.69.64.223, 52.174.88.118, 137.117.161.181 |
|Tyskland|51.116.60.192, 51.116.158.97, 51.116.158.96, 51.116.211.212 og 51.116.236.78|
| Indien  | 104.211.81.192 – 104.211.81.207, 52.172.211.12, 40.78.194.240 – 40.78.194.255, 13.71.125.22, 104.211.146.224 – 104.211.146.239, 104.211.189.218 |
| Japan | 13.78.108.0 – 13.78.108.15, 13.71.153.19, 40.74.100.224 – 40.74.100.239, 104.215.61.248 |
| Sydamerika | 191.233.203.192 – 191.233.203.207, 104.214.19.48 – 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| De Forenede Arabiske Emirater | 40.120.8.0 – 40.120.8.31, 20.37.74.192 – 20.37.74.207, 20.45.67.28|
| Storbritannien | 51.140.148.0 – 51.140.148.15, 51.140.80.51, 51.140.211.0 – 51.140.211.15, 51.141.47.105 |
| USA | 13.89.171.80 – 13.89.171.95, 52.173.245.164, 40.71.11.80 – 40.71.11.95, 40.71.249.205, 40.70.146.208 – 40.70.146.223, 52.232.188.154, 52.162.107.160 – 52.162.107.175, 52.162.242.161, 40.112.243.160 – 40.112.243.175, 104.42.122.49|
| Eksempel (USA)  | 13.71.195.32 – 13.71.195.47, 52.161.102.22, 13.66.140.128 – 13.66.140.143, 52.183.78.157 |

Hvis du f.eks. skal godkende IP-adresser for SQL Azure-databasen, skal du bruge disse adresser.

### <a name="required-services"></a>Påkrævede services
I følgende tabel vises de tjenester, som Power Automate opretter forbindelse til. Kontrollér, at ingen af disse services er blokeret på netværket.

Domæner | Protokoller | Anvendelser
--------|  ---------| -----
management.azure.com|https|Adgang til Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Adgang til Active Directory Authentication Library (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Adgang til Azure AD Graph API - for hentning af brugeroplysninger som f.eks. et profilbillede.
*.azure-apim.net|https|Adgang til Runtime for forbindelser.
*.flow.microsoft.com|https|Adgang til Power Automate-websitet.
*.powerapps.com|https|Adgang til Power Apps-websitet.
*.azureedge.net|https|Adgang til Power Automate CDN.
nps.onyx.azure.net|https|Adgang til NPS (Net Promotor Score).
webshell.suite.office.com|https|Adgang til Office i forbindelse med header og søgning. Du kan finde flere oplysninger under [URL-adresser til og intervaller for Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)

### <a name="approval-email-delivery"></a>Levering af mail til godkendelse
Du kan finde flere oplysninger om godkendelse af e-mail-routing i [artiklen om levering af mail til godkendelse](https://go.microsoft.com/fwlink/?linkid=2128304).

### <a name="ui-flows-required-services"></a>Påkrævede services for flow for brugergrænseflade
I følgende tabel vises slutpunktsdatakrav for forbindelse fra en brugers maskine til en vellykket installation af flows for brugergrænseflade og kørsler.

Slutpunkttype | Domæner | Protokoller | Anvendelser
--------| --------|  ---------| -----
Verdensomspændende slutpunkter|ocsp.digicert.com<br>ocsp.msocsp.com<br>mscrl.microsoft.com<br>crl3.digicert.com<br>crl4.digicert.com|http|Adgang til CRL-serveren for den offentlige cloud.
U.S. Government GCC- og GCC High-slutpunkter|ocsp.digicert.com<br>crl3.digicert.com<br>crl4.digicert.com|http|Adgang til CRL-serveren for US Government-cloud.
Slutpunkter drevet af 21Vianet|crl.digicert.cn<br>ocsp.digicert.cn|http|Adgang til de CRL-servere for 21Vianet, der drives i cloud.
Alle slutpunkter|msedgedriver.azureedge.net<br>chromedriver.storage.googleapis.com|https|Adgang til WebDriver-downloadere til flow for brugergrænseflade.
