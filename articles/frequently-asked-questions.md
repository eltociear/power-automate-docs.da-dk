---
title: Ofte stillede spørgsmål | Microsoft Docs
description: Svar på mange almindelige spørgsmål om Power Automate
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
ms.date: 06/18/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d14d32ced99b7e717328369bfcbd87f069db0298
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900330"
---
# <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

## <a name="audience-and-strategy"></a>Målgruppe og strategi
### <a name="what-is-power-automate"></a>Hvad er Power Automate?
Power Automate er en skybaseret tjeneste, der gør det praktisk og enkelt for line-of-business-brugere at oprette arbejdsprocesser, der automatiserer tidskrævende virksomhedsopgaver og -processer på tværs af applikationer og tjenester.

### <a name="who-is-the-intended-audience-for-power-automate"></a>Hvem er målgruppen for Power Automate?
Power Automate har to adskilte målgrupper:

* Line of business-integratorer i store virksomheder, der arbejder sammen med it-afdelingen om at flytte ansvaret for forretningsløsninger tættere på selve forretningen.
* It-beslutningstagere, der vil gøre det muligt for line of business-partnere at oprette deres egne løsninger, så professionelle it-brugere og integrationsspecialister kan fokusere deres ekspertise på mere avancerede integrationsværktøjer, for eksempel Azure Logic Apps.

### <a name="how-do-power-automate-and-logic-apps-relate-to-each-other"></a>Hvordan er Power Automate og Logic Apps relateret til hinanden?
Power Automate indeholder funktioner, der hjælper line of business-brugere med at oprette automatiserede arbejdsprocesser. Logic Apps er en Azure-tjeneste, der indeholder alle de samme fantastiske funktioner som Power Automate samt ekstra funktioner som integration i Azure Resource Manager og Azure Portal, PowerShell og xPlat CLI, Visual Studio og yderligere connectorer. [Få mere at vide om Logic Apps](https://azure.microsoft.com/services/app-service/logic/).

### <a name="how-does-power-automate-fit-in-microsofts-overall-business-application-platform-strategy"></a>Hvordan passer Power Automate i Microsofts overordnede strategi for virksomhedsprogramplatforme?
Power Automate er en del af en stærkt og fleksibel virksomhedsprogramplatform, der omfatter Power Apps, Common Data Service, Dynamics 365 og Office 365. Denne platform gør det muligt for vores kunder, vores partnere og vores softwareproducentpartnere at udvikle særlige løsninger til deres egne virksomheder, deres branche, til funktionelle roller eller endda til bestemte geografiske områder. De line of business-brugere, der forstår deres forretningsmæssige behov bedst muligt, kan nu nemt analysere, oprette og forenkle data og processer. Professionelle udviklere kan nemt udvide deres line of business inden for automatisering, analyse og apps til at bruge Azure-tjenester som Functions, App Service og Logic Apps. API-connectorer, gateways og Common Data Service gør det muligt at få mere værdi ud af de tjenester eller data, der allerede er i brug, enten i cloudmiljøet eller i det lokale miljø.

## <a name="functionality"></a>Funktionalitet

### <a name="what-do-i-need-to-use-power-automate"></a>Hvad behøver jeg for at kunne bruge Power Automate?
Hvis du vil bruge Power Automate, skal du blot have en webbrowser og en mailadresse.

### <a name="what-browsers-and-devices-can-i-use-with-power-automate"></a>Hvilke browsere og enheder kan jeg bruge sammen med Power Automate?

Du kan køre Power Automate på alle moderne enheder og i alle browsere.

#### <a name="supported-devices"></a>Understøttede enheder

Power Automate kører perfekt på moderne enheder. Hvis du har brug for at administrere Power Automate fra en mobilenhed, kan du prøve Power Automate-mobilappen, der er tilgængelig til [iPhone](https://itunes.apple.com/app/microsoft-flow/id1094928825?ls=1&mt=8), [Android](https://play.google.com/store/apps/details?id=com.microsoft.flow) og [Windows Phone](https://www.microsoft.com/p/microsoft-flow/9nkn0p5l9n84?rtc=1#activetab=pivot:overviewtab).

#### <a name="supported-browsers"></a>Understøttede browsere

Vi anbefaler, at du bruger den nyeste browser, der er kompatibel med operativsystemet. Vi understøtter følgende browsere:

* Microsoft Edge
* Internet Explorer 11
* Safari
* Chrome
* Firefox

### <a name="which-email-addresses-are-supported"></a>Hvilke mailadresser understøttes?
Power Automate understøtter alle mailadresser undtagen dem, der slutter på .gov og. mil.  

### <a name="is-power-automate-available-on-premises"></a>Er Power Automate tilgængelig i det lokale miljø?
Power Automate er kun en offentlig cloudtjeneste. Du kan dog forbinde dine tjenester i det lokale miljø via datagatewayen i det lokale miljø på en sikker måde.

### <a name="what-services-can-power-automate-connect-to"></a>Hvilke tjenester kan Power Automate oprette forbindelse til?
Power Automate kan som standard oprette forbindelse til mere end 100 datakilder, og vi tilføjer hele tiden flere. Eksempler på datakilder og tjenester omfatter følgende:

* SharePoint
* Dynamics 365
* OneDrive
* OneDrive for Business
* Google Drev
* Google Sheets
* Trello
* Twitter
* Box
* Facebook
* SalesForce.com
* Mailchimp
* Kunde-API'er

Du kan se en komplet liste over de tilgængelige forbindelser [her](https://go.microsoft.com/fwlink/?LinkId=832211).

Du kan få adgang til datakilderne i din egen it-infrastruktur via [datagatewayen i det lokale miljø](gateway-manage.md).

### <a name="what-are-templates"></a>Hvad er skabeloner?

Skabeloner er færdigbyggede flows til populære og almindelige scenarier. Brugen af en skabelon kræver kun, at du har adgang til tjenesterne i skabelonen, og at du udfylder de nødvendige indstillinger.

### <a name="what-data-sources-will-i-be-able-to-connect-to"></a>Hvilke datakilder kan jeg oprette forbindelse til?

Du kan oprette forbindelse til mere end 100 standardtjenester fra Microsoft og tredjeparter, f.eks. Office 365, Twitter, SharePoint, OneDrive, Dropbox, SQL Server og flere. Du kan også oprette forbindelse til kvalitetstjenester, som Salesforce og Common Data Service.

### <a name="how-do-i-connect-to-a-rest-api-in-my-flow"></a>Hvordan opretter jeg forbindelse til en REST-API i mit flow?

Du kan oprette forbindelse til alle REST-API'er, der bruger JSON og understøtter mindst én af flere end 10 godkendelsesmetoder, ved at oprette [en brugerdefineret forbindelse](developer/register-custom-api.md).

### <a name="how-do-i-connect-to-sql-server-and-other-on-premises-data-sources"></a>Hvordan opretter jeg forbindelse til SQL Server og andre datakilder i det lokale miljø?

Du kan oprette forbindelse til tjenester på dit eget lokale netværk ved at bruge [datagatewayen i det lokale miljø](gateway-manage.md).

### <a name="can-i-share-the-flows-i-create"></a>Kan jeg dele de flows, jeg opretter?

Du kan dele flows på en af følgende måder:

* Du kan tilføje kolleger eller grupper i organisationen som ejere på dine flows, så de også kan redigere og styre flowet.
* For flows, der kan køres manuelt, kan du også give andre personer eller grupper i din organisation tilladelse til blot at køre flowet.

### <a name="how-many-flows-can-i-have"></a>Hvor mange flows kan jeg have?

Du kan oprette et ubegrænset antal flow. Det afhænger af den [licenstype](https://flow.microsoft.com/pricing), du har.

### <a name="where-do-i-get-started-with-power-automate"></a>Hvor kan jeg komme i gang med Power Automate?

Kom i gang med følgende ressourcer:

* [Blog](https://flow.microsoft.com)
* [YouTube-kanal](https://youtube.com/playlist?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF)
* [Emne](getting-started.md)
* [Community](https://powerusers.microsoft.com)

### <a name="what-operating-systems-does-the-mobile-app-for-power-automate-support"></a>Hvilke operativsystemer understøtter mobilappen til Power Automate?

Power Automate-mobilappen er tilgængelig på [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) eller [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="can-flows-be-turned-off-or-disabled"></a>Kan flows deaktiveres eller slås fra?

Ja. Alle flows har en til/fra-parameter, som du kan bruge til at stoppe det enkelte flow, så det ikke behandler anmodninger.

Så tabellen nedenfor for at få mere at vide om, hvordan flowet reagerer, når det slås til igen.

Udløsertype|Beskrivelse
-------|--------
Forespørgsel, f.eks. udløseren **Gentagelse**|Alle ikke-behandlede/ventende begivenheder behandles, når flowet aktiveres igen. Slet dit flow, hvis du ikke vil behandle ventende elementer.
Webhook|Når flowet slås til igen, behandles kun begivenheder, som genereres, når flowet er slået til.

### <a name="what-regions-and-languages-does-power-automate-support"></a>Hvilke områder og sprog understøtter Power Automate?

Power Automate er tilgængelig på 42 sprog og i [seks områder](regions-overview.md). Sådan får du vist de tilgængelige sprog:

1. Log på [Power Platform Administration > Miljøer](https://admin.powerplatform.microsoft.com/environments)
1. Vælg dit miljø
1. Vælg **Indstillinger** på den øverste menulinje.
1. Vælg **Produkt > Sprog**

### <a name="how-does-power-automate-compare-to-sharepoint-designer-2013"></a>Hvordan er Power Automate sammenlignet med SharePoint Designer 2013?

Power Automate er efterfølgeren til SharePoint Designer for mange almindelige virksomhedsscenarier som f.eks. godkendelser, dokumentgennemsyn og onboarding/offboarding. Det vil fremover være standardværktøjet til oprettelse af funktioner til forretningsautomatisering i SharePoint.

### <a name="how-does-power-automate-ensure-that-corporate-data-isnt-accidentally-released-to-social-media-services"></a>Hvordan sikrer Power Automate, at virksomhedens data ikke ved et uheld frigives til sociale medier?

Administratorer kan oprette [politikker til forebyggelse af datatab](https://docs.microsoft.com/power-platform/admin/prevent-data-loss) for at sikre, at der kun kan anvendes godkendte tjenester i Power Automate.

### <a name="does-power-automate-support-service-accounts"></a>Understøtter Power Automate tjenestekonti?

Du kan oprette flows med en tjenestekonto, men vi anbefaler, at du ikke gør det, hvis legitimationsoplysningerne for tjenestekontoen er delte.

## <a name="licensing"></a>Licensering
### <a name="will-power-automate-still-have-a-free-or-trial-option"></a>Vil det stadig være muligt at få en gratis version eller prøveversion af Power Automate?
Ja. Du har mulighed for et gratis tilbud med begrænsede brugerrettigheder, eller du kan tilmelde dig en gratis 90-dages prøveversion af Power Automate. Du kan til enhver tid aktivere dit abonnement i løbet af prøveperioden.

### <a name="what-pricing-plans-do-you-offer"></a>Hvilke planer for prissætning tilbyder I?
Power Automate tilbyder både gratis og betalte serviceniveauer. [Få mere at vide om prisfastsættelse](billing-questions.md).

## <a name="learn-more"></a>Få mere at vide

* Få en [guidet rundvisning](https://docs.microsoft.com/learn/paths/automate-process-using-flow) i Power Automate
* Få et grundlæggende kendskab til Power Automate i [introduktionsvejledningen](getting-started.md)
