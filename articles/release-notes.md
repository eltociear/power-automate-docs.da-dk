---
title: Produktbemærkninger | Microsoft Docs
description: Almindelige problemer og nyheder i Power Automate-versioner
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
ms.date: 05/07/2020
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c020703182becc6460c3630adb4e8735cbdd407b
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900378"
---
# <a name="release-notes"></a>Produktbemærkninger

>[!NOTE]
>Udgivelsesplaner spores nu [her](https://docs.microsoft.com/dynamics365/release-plans/).

## <a name="top-questions"></a>Mest populære spørgsmål
1. Mit flow mislykkedes. Hvordan løser jeg det?
   
   1. Identificer fejlen. Start med at gå til ikonet for meddelelser øverst på webportalen eller vælge fanen **Aktivitet** i mobilappen. Der bør du kunne se dit flow og vælge det.
   2. Flowdetaljerne vises nu. Find trinnet med ikonet med det røde udråbstegn, og fejlmeddelelsen for dit flow burde vises.
   3. Afhængigt af fejlmeddelelsen bør du kunne **Redigere** flowet og løse problemet. [Læs mere om, hvordan du løser almindelige flowfejl](fix-flow-failures.md).
2. Hvordan bruger jeg en avanceret betingelse eller et udtryk?
   
   * Læs om [tilføjelse af betingelser](add-condition.md).
   * Hvis du vil have flere cases i et flow, skal du vælge **Tilføj betingelse** i en eksisterende betingelse.
   * Opret et avanceret udtryk ved at referere til [en funktion i Logic Apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Hvordan fungerer Office 365-licensering?
   
   * Hvis du er Office 365-bruger, får du fuld adgang gennem Power Automate til Office 365-planen. Du kan finde flere oplysninger i [prisplaner for Power Automate](https://flow.microsoft.com/pricing/).
   * Hvis du er administrator, kan du se oplysninger om [licensering for Power Automate](organization-q-and-a.md), herunder med Office 365.

## <a name="known-issues"></a>Kendte problemer
1. SharePoint-lister på Mine websites, som ikke er af typen *Brugerdefineret liste*, understøttes ikke. Du kan omgå problemet ved at oprette en brugerdefineret liste på et SharePoint-standardwebsted.
2. Filudløsere aktiveres ikke for filer, der tilføjes i indlejrede mapper i den valgte mappe.

## <a name="whats-new"></a>Nyheder

Du kan få oplysninger om nye funktioner, der er udgivet til Power Automate, her:
- [Plan for 2020-udgivelse, 1. bølge](https://docs.microsoft.com/power-platform-release-plan/2020wave1/power-automate/planned-features) for nye funktioner, der udgives i løbet af de næste par måneder.
- [Ugentlige produktbemærkninger](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) om nye funktioner, rettelser og forbedringer, der er udgivet i de seneste par uger.

### <a name="release-2018-09-24"></a>Udgave 24-09-2018

- **Administratoradgang til hjælp og support** – Åbn supportanmodninger til Power Automate i Administration på Power-platformen, og angiv yderligere oplysninger om fejlen i din arbejdsproces.
- **Nydesignet Power Automate Community** – det er nu blevet nemmere at finde det, du skal bruge, i Power Automate Community.
- **Forbedringer af Microsoft Teams-connectoren** – Nye udløsere for Microsoft Teams, så du kan køre et flow, når der er nye meddelelser i en kanal.
- **Flere SharePoint-handlinger** – Der er nye handlinger til flytning af filer osv. i SharePoint-connectoren.
- **Nye administratoranalyserapporter** – miljø- og lejerrapporter er føjet til Business Application Platform Administration.
- **Power Query-integration** – En Power Query-oplevelse, der gør det muligt for oprettere at skabe et miks af data fra SQL Server, er under udvikling.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) om denne version.

### <a name="release-2018-08-31"></a>Udgave 31-08-2018

- **Test dit flow ved hjælp af eksempeldata** - Brug eksempeldata fra connectorer til at teste dit flow, når du bygger det i Power Automate-designeren. Når du tester dit flow med eksempeldata, kan du bekræfte, at flowet kører som forventet, når det er udrullet i produktionen.
- **Fem nye connectorer** – Vi har tilføjet fire nye administrationsconnectorer: Power Apps for App Makers:, Power Platform for Admins, Power Apps for Admins, Power Automate til administratorer og Microsoft School Data Sync.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/test-data-management-connectors/) om denne version.

### <a name="release-2018-08-24"></a>Udgave 24-08-2018

- **Nye skabeloner for synkronisering af kalender** – Nye kalenderskabeloner, der kopierer begivenhederne fra Google Kalender og Office 365 eller Outlook.com.
- **Understøttelse af flere værdier for SharePoint** – Læs og skriv til felter med flere værdier i SharePoint af typen Valg, Person eller Opslag.
- **Send godkendelser på vegne af andre brugere i din organisation** – Send godkendelser på vegne af andre brugere i din organisation, f.eks. den person, der har uploadet filen til SharePoint-listen i stedet for den person, der oprettede flowet.
- **Flere inputtyper for knapper** – Knapper har to nye inputtyper: Tal og Ja/Nej.
- **Forbindelsesopdateringer** – En ny NetDocuments-forbindelse, forbedringer af Azure-forbindelser med mere.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/button-types-more/) om denne version.

### <a name="release-2018-08-02"></a>Udgave 02-08-2018

Power Automate-prøveversionsprogrammet giver mulighed for at få tidlig adgang til de kommende funktioner i og opdateringer til Power Automate. Du skal blot oprette og derefter bruge et miljø i området Prøveversion for at få tidlig adgang til de nyeste funktioner.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/flow-preview-program/) om denne version.

### <a name="release-2018-07-23"></a>Udgave 23-07-2018

- **Byg og kør flows fra Excel** – Med den nye knap **Flow** (åbnes via fanen **Data** på båndet) kan du oprette og udløse automatiseringer fra Power Automate for dine tabeldata i Excel. Automatiser databehandling eller kopiering/import af data.
- **Opret et forretningsprocesforløb** – Et forretningsprocesforløb er en ny type interaktiv proces med høj sikkerhed, som er baseret på Common Data Service. Brug disse nye flows til at definere en række faser og trin, som skal følges. De kan flyttes frem og tilbage efter behov.
- **Opret et flow til Microsoft To-Do i Outlook Web App** – Hvis en person er \@nævnt i Outlook Web App, får vedkommende vist en genvej til oprettelse af et flow. Dette flow opretter automatisk opgaver for den \@førnævnte person i Microsoft To-Do på baggrund af indholdet af mailen.
- **Understøttelse af SharePoint-visning** – SharePoint-connectoren understøtter nu valg af en bestemt SharePoint-visning for udløsere og handlinger. Det filtrerer kolonnerne, så der kun vises de felter, der er en del af den valgte visning.
- **Fire nye connectorer** – Tilføjet Azure IoT Central – en yderst skalerbar IoT SaaS-løsning (Software som en service) – Survey 123, LMS365 og ProjectWise Design Integration.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) om denne version.

### <a name="release-2018-06-29"></a>Udgave 29-06-2018

- **Anmodning om afslutningsflow, der er indbygget i SharePoint** – Når du vælger en fil eller et element i SharePoint, får du vist et nyt flow af typen **Anmod om afslutning**. Dette flow kræver ikke nogen konfiguration eller opsætning og sender en afslutningsanmodning med et enkelt klik.
- **To nye connectorer** – Tilføjet Cloud Connect Studio og PoliteMail.
- **Forbedringer af oversigts- og oprettelsesside** – Vi opdaterer kørselsoversigten ved at inkludere de nøjagtige kørselstidspunkter samt oprettelsessiden ved at tilføje en ny gennemgangsvideo.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) om denne version.

### <a name="release-2018-06-08"></a>Udgave 08-06-2018

- **PowerShell-Cmdlet'er** – Både flowoprettere og lejeradministratorer kan nu bruge PowerShell til at administrere deres flow ved hjælp af programmering.
- **Forbedringer af Teams Flow-robotten** – Flow-robotten i Microsoft Teams kan køre flowknapper og beskrive dine flows.
- **Tre nye forbindelser** – Understøttelse af Marketo, ElasticOCR og DynamicSignal er tilføjet. 
- **Yderligere oplysninger om deling** – Yderligere oplysninger tilføjes, når du deler eller kører delte flows. Dermed ved du præcist, hvilke tilladelser andre personer får.
- **Automatisk trimning af URL-adresser for SharePoint** – Når du kopierer og indsætter en URL-adresse for SharePoint i browseren, kan den indeholde tekst, der ikke vedrører websitet. Denne tekst fjernes automatisk, så du bare kan oprette forbindelse til websitet.
- **Dokumentation om GDPR anmodninger** – Vi har oprettet en omfattende vejledning og et omfattende værktøjssæt til store organisationer, så de kan håndtere Data Subject Rights-anmodninger.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) om denne version.

### <a name="release-2018-05-21"></a>Udgave 21-05-2018

- **Flows "ejes af" SharePoint-lister og -biblioteker** – De flows, der kan bruges sammen med SharePoint-lister og -biblioteker, kan deles med disse lister eller biblioteker. I stedet for blive delt med brugere eller grupper, bliver de også delt med alle, der har adgang til listen. Når brugere tilføjes på eller fjernes fra listen eller biblioteket, bliver deres medlemskab automatisk ændret derefter.
- **Analyse med fejloplysninger** – En ny integreret rapport med oplysninger om alle de fejl, der sker i et flow.
- **Del flows med Office 365-grupper** – Du kan gøre en moderne Office 365-gruppe til ejer af et flow, og du kan dele knapflows med Office 365-grupper, så alle i gruppen kan køre flowet.
- **Forbedringer af SharePoint-connectorer** – Der er to nye funktioner for SharePoint-connectorer: Udløs flows, når elementer eller filer slettes, og foretag kald til ethvert HTTP-slutpunkt, som SharePoint REST-API'et understøtter.
- **To nye forbindelser** – Understøttelse af Azure Data Factory og MailParser er tilføjet

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) om denne version.

### <a name="release-2018-05-01"></a>Udgave 01-05-2018

- **Tekst i RTF-format i godkendelsesmeddelelser** – Brug nedskrivning til at formatere de godkendelsesdetaljer, du sender.
- **Knapper med flere valg** – Opret flowknapper, der bruger en liste med flere valg til at indsamle mere end én værdi ad gangen.
- **Arbejd med bredere flows** – Power Automate-mobilappen understøtter nu visning i liggende format, og webdesigneren har et vandret rullepanel.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) om denne version.

### <a name="release-2018-04-12"></a>Udgave 12-04-2018

- **Returner data til Power Apps fra et flow** – Opret flows, der kan kaldes fra en app, som er bygget med Power Apps, og returner data til appen igen. Brug den visuelle træk og placer-flowdesigner til at oprette den logik, du skal bruge til dine apps. 
- **Føj flere poster til matrixinput** – Føj en listegenerator til Power Automate, som f.eks. kan bruges til at tilføje flere vedhæftede filer i en mail.
- **Test flows med tidligere kørte data** – Føj en ny testflowknap til den designer, du kan bruge til at teste dit flow med udløserdata fra tidligere kørte flows.
- **Nye workflow()-felter** – Du kan nu få adgang til miljønavne og viste flownavne vha. udtrykket workflow().

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/return-data-to-powerapps/) om denne version.

### <a name="release-2018-04-04"></a>Udgave 04-04-2018

- **Godkendelser på Common Data Service** – Moderne godkendelser er baseret på den nyeste version af Common Data Service. Det betyder, at du kan udvikle flows, der læser status for de godkendelser, du sender eller modtager med Common Data Service-connectoren.
- **Find fejl, der gælder for hver enkelt** – Hop direkte til fejl i løkker i visningen af flowkørslen, også selvom der er hundredvis af elementer i løkken.
- **Videretildel godkendelser** – Du kan tildele modtagne godkendelser til en anden person i organisationen for at delegere godkendelsen til vedkommende. 
- **Lokalelister** – Office 365 Outlook-connectoren har tilføjet handlinger for at hente lokaledata i din organisation.
- **Få vist detaljer om flowknapper** – Når du kører et flow, der er delt med dig, vises nu alle de handlinger, der anvendes af flowet.
- **Området Storbritannien** – Miljøer kan nu oprettes til lagring af data i Storbritannien.
- **To nye forbindelser** – Understøttelse af AtBot-administrator og Marketing Content-hubben er tilføjet.
- **Ny landingsside til dokumentation** – Opdater landingssiden til dokumentation for at gruppere indhold efter erfaringsniveau: nybegynder, erfaren bruger eller ekspert. 

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) om denne version.

### <a name="release-2018-03-13"></a>Udgave 13-03-2018

- **Godkendelsesoversigt** – Få vist alle de anmodninger om godkendelse, du har sendt, herunder de tilhørende svar, de kommentarer, der er sendt, og det nøjagtige tidspunkt for hændelserne.
- **Fire nye connectorer** – Tilføjet Excel Online (Business), Excel Online (OneDrive), Azure SQL Data Warehouse og Pitney Bowes Tax Calculator.
- **Værktøjstip til dynamisk indhold** – Hold markøren hen over dynamisk indhold for at få vist, hvor det kom fra i handlinger, og få vist eksempler på udtryk uden at åbne editoren med de fuldstændige udtryk.
- **Samtidighedskontrol** – Aktivér samtidighedskontrol for at sikre, at et givet flow kun har én kørsel ad gangen.
- **Eksponentielt gentaget forsøg** – En ny type gentagelsespolitik, der fordeler gentagne forsøg eksponentielt i en tidsperiode.
- **Overenssstemmelse i forbindelse med tilgængelighed** – Udgivet nye dokumenter om overensstemmelse, der beskriver, hvordan Power Automate opfylder standarderne for tilgængelighed.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/approval-history-accessibility/) om denne version.

### <a name="release-2018-02-09"></a>Udgave 09-02-2018

- **Høj tilgængelighed af gateway** – Opret klynger af datagateways med høj tilgængelighed i det lokale miljø for at sikre, at forbindelserne kan køre, når en enkelt maskine går ned.
- **Forbedret Anvend på hver** – Med Flow-plan 1 eller Flow-plan 2 kan du behandle op til 100.000 elementer i en enkelt kørsel og 50 handlinger parallelt i Anvend på hver løkke. 

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) om denne version.

### <a name="release-2018-01-29"></a>Udgave 29-01-2018

- **Flow i Microsoft Teams** – Fra Teams kan du oprette og administrere flows, gennemgå dine modtagne og sendte godkendelser og starte flows direkte i Teams-skrivebordsappen eller på teams.microsoft.com – [få mere at vide her](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Meddelelser om redigering af delte flows** – Når et flow, du ejer, ændres af en kollega, får du en mail med besked om, hvem der har ændret flowet.
- **Nye udtryk** – Der er tilføjet to nye udtryk: Et til at opdele URL-adresser i tekst og et til at arbejde med JSON-objekter.
- **Tre nye forbindelser** – I denne uge er der to nye Plumsail-forbindelser, Plumsail SP og Plumsail Forms, samt en ny forbindelse til kintone.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) om denne version.

### <a name="release-2018-01-17"></a>Udgave 17-01-2018

- **Office 365-profiloplysninger** – Vi har føjet nye handlinger til connectoren Office 365-brugere, som anvender brugerprofiler og -fotos.
- **Føj til strengvariabler** – Du kan tilføje strenge i løkker for at opbygge tabeller og andre lister.
- **Infobip-forbindelse** – Infobip er en tjeneste, der muliggør kommunikation i virksomhedsklassen, herunder taleopkald og mulighed for at reagere på indgående sms'er.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/o365-profile-infobip/) om denne version.

### <a name="release-2017-12-20"></a>Udgave 20-12-2017

Power Automate Analytics er nu tilgængelig i alle Power Automate-områder, hvorfor du kan få indsigt i tilstanden af de flows, der kører i dit miljø.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) om denne version.


### <a name="release-2017-12-14"></a>Udgave 14-12-2017

- **Forbedringer af Outlook-forbindelse** – du kan gemme en mail som en ".eml"-fil, svare på kalenderinvitationer automatisk og udløse flow, når du nævnes i en mailtråd.
- **Forbedringer af forbindelser** – Power Automate kan huske dine senest anvendte forbindelser og viser alle de nyligt tilføjede connectorer.
- **Fem nye forbindelser** – Azure Container Instances, Azure Kusto, Metatask, Microsoft To-Do og Plumsail Documents er blevet tilføjet.
- **HTTP-forbedringer** – HTTP-handlingen understøtter nu Chunked-kodning.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/outlook-connector-more/) om denne version.

### <a name="release-2017-12-05"></a>Udgave 05-12-2017

Power Automate-startpanelet er nu tilgængeligt i alle områder. Dette panel giver dig mulighed for at føje værdier til et flow, når du kører det i din SharePoint-liste eller i et dokumentbibliotek.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) om denne version.


### <a name="release-2017-11-28"></a>Udgave 28-11-2017

- **Administrerede metadata** – Læs data fra og skriv til kolonner i SharePoint, der bruger typen administrerede metadata (dvs. Taksonomitype.
- **Føj til matrixer** – Føj elementer til slutningen af matrixer vha. en ny variabelhandling til tilføjelse til matrixer.
- **Tago** – En ny forbindelse til Tago, som giver nem tilslutning af elektronikenheder med eksterne data for at opnå bedre beslutninger vha. kontekstafhængige analyser.
- **iPhone X** – en ny version af Power Automate-appen, der bruger fuldskærmstilstand på iPhone X, og som har forbedret hastighed ved billedoverførsler.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/managed-metadata-tago/) om denne version.

### <a name="release-2017-11-09"></a>Udgave 09-11-2017

- **OneDrive for Business-integration** – Der er [nu en flowknap i OneDrive for Business](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/), der kan oprette eller udløse flows for valgte filer eller mapper.
- **Planner-udløsere** – starter flow, når en ny opgave oprettes, når en opgave tildeles til dig, eller når en opgave er fuldført.
- **Vedhæftede filer i SharePoint** – Arbejd med vedhæftede filer i elementer på en SharePoint-liste: Vis, hent, tilføj eller slet vedhæftede filer.
- **Forbindelse til flowadministration** – opret flow, der automatiserer administrationen af andre flow i dit miljø (f.eks. ved at føje tilladelser til flow automatisk).
- **Fire nye forbindelser** – Azure Custom Vision Service, D&B Optimizer, Enadoc og Derdak SIGNL4 er blevet tilføjet. 
- **Flere connectorhandlinger** – Kør SQL-forespørgsler, få hurtigere mailudløsere, brug en hvilken som helst metode med HTTP med Azure AD og meget mere.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) om denne version.

### <a name="release-2017-11-02"></a>Udgave 02-11-2017

- **Overvågningslogføring** – Power Automate-overvågningshændelser er nu tilgængelige i Office 365 Security & Compliance Center for alle lejere.
- **Programrettelser til Flow-widget** – problemet i Power Automate-mobilappen, der betød, at knapper ikke blev indlæst i widgetten, er blevet løst.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/security-and-compliance-center/) om denne version.

### <a name="release-2017-10-19"></a>Udgave 19-10-2017

- **Indlejret Anvend på hver** – du kan tilføje Anvend på hver handling samt filtrere og vælge i andre Anvend på hver objektbeholderhandling.
- **Handlinger for dato og klokkeslæt** – nye handlinger til hentning af lokale tidspunkter samt til tilføjelse, fratrækkelse eller formatering af tidspunkter.
- **Fire nye forbindelser** – Content Moderator, Docparser, Microsoft Kaizala og Pitney Bowes Data Validation er blevet tilføjet.
- **Forbedret forbindelsesoplevelse** – Meddelelser i Power Automate-portalen, når en forbindelse er beskadiget, og bedre forbindelsesoplysninger.
- **På farten-samling** – en ny samling skabeloner til [medarbejdere på farten](https://flow.microsoft.com/collections/onthego/).
- **Input fra mailadresseknap** – få mailadresser fra brugere, når de kører knapper.
- **Input fra filknap** – hent uploadede filer, f.eks billeder, fra brugere, når de kører knapper.
- **Første kørsel og automatisk logon** – forbedrede oplevelser ved første kørsel på mobilappen, bl.a. automatisk logon.
- **Hurtigere Microsoft Forms-udløsere** – Forms udløser flow langt hurtigere end før (tidligere én gang i timen).
- **Knapinput på tværs af sessioner** – knapper, der udløses på din mobiltelefon, husker tidligere input.
- **Mobilaktivitetsfeed** – forbedret aktivitetsfeed for at inkludere mere detaljerede kørselsoversigter og oplysninger om fejlfinding.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/nested-apply-to-each/) om denne version.

### <a name="release-2017-10-03"></a>Udgave 03-10-2017

- **Alle skal godkende** – en anmodning om godkendelse skal sendes til mere end én person for at få alle, der har modtaget anmodningen, til at godkende den.
- **Nye OneDrive for Business-handlinger** – Generer PDF'er for filer, der er lagret på OneDrive for Business og fire andre nye handlinger.
- **Apache Impala-forbindelse** – Apache Impala (incubating) er en open source, oprindelig analytisk database til Apache Hadoop.
- **Tilføj flowbeskrivelser** – angiv dine flowbeskrivelser, så dine kolleger kan få vist et resumé af, hvad flowet kan, når du deler det.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) om denne version.

### <a name="release-2017-09-25---q3-update-for-power-automate"></a>Version 2017-09-25 - Q3-opdatering til Power Automate

- **Dybere SharePoint-integration i First Release** – Der er nye brugsklare flows for afsendelse til gennemgang og et Flow-panel til indsamling af input, når du kører et flow for First Release-lejere.
- **Dynamics 365-apps** - Power Automate er nu integreret i brugergrænsefladen for Dynamics 365-apps, f.eks. Dynamics 365 Sales og Dynamics 365 Customer Service.
- **Microsoft Sikkerhedscenter** – Power Automate er nu anført i Microsoft Sikkerhedscenter med certificeringer som f.eks. HIPAA, ISO og SOC.
- **Forbrugsanalyser** – hvert flow indeholder et integreret Power BI-dashboard med grundlæggende forbrugsanalyser.
- **Overvåg logføring i First Release** – Alle flowadministrationshændelser logføres i Office 365 Security and Compliance Center for First Release-lejere.
- **Seks nye connectorer** – Tilføjet LinkedIn, Office 365 Groups, Skype for Business, Adobe Sign, Bizzy og Azure Log Analytics Data Collection.
- **SQL-udløsere** – kør flow, når en ny række tilføjes, eller en række opdateres i en SQL-tabel.
- **Brugerdefinerede forbindelser i det lokale miljø** – brugerdefinerede forbindelser kan nu bruge datagatewayen i det lokale miljø til at oprette forbindelse til interne slutpunkter på netværket.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/q3-2017-update/) om denne version.

### <a name="release-2017-09-21"></a>Udgave 21-09-2017

- **Download flowoversigt** – download kørselsoversigten for et flow som en CSV-fil, der åbnes i Excel.
- **Avanceret gentagelse** – opret tilbagevendende tidsplaner for at udløse flow, så de f.eks. kun udløses på ugedage.
- **IntelliSense** – når du skriver i udtryk, kommer IntelliSense med forslag til parametre.
- **Fire nye connectorer** – Tilføjet connectorer til Azure AD HTTP-tjenester, Amazon Redshift, Azure Event Grid Publish og FlowForma
- **Deling af links** – En ny handling til at generere links, der kan deles, til OneDrive-filer eller Azure Storage-blobs.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/download-history-recurrence/) om denne version.


### <a name="release-2017-08-25"></a>Udgave 25-08-2017
* **Dokumentegenskaber og mere til SharePoint** - [Læs og angiv egenskaber for SharePoint-dokumentbiblioteket](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/), og brug flere felter som links til SharePoint-elementet.
* **Flowsamlinger** – Flowsamlinger er et sæt af skabelonsamlinger, der er organiseret efter rolle eller efter vertikal.
* **Videredeling af knapper** – Når du deler knapper med dine kolleger, kan de også videredele dem med andre.
* **Saml lister fra knapper** – Definer rullelister med indstillinger, som brugerne kan vælge fra, når de trykker på knappen.
* **Syv nye forbindelser** – AWeber, Azure Log Analytics, Azure Tables, DocFusion365, Azure Event Grid, Azure Event Hubs og StaffHub. 
* **Forbedringer af Slack og MySQL** – Opret eller joinforbind kanaler i Slack, så du kan skrive til MySQL-databaser.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/button-updates-seven-connectors/) om denne version.

### <a name="release-2017-08-02"></a>Udgave 02-08-2017
* **Skriv til felterne Person, Valg og Opslag** – Opret element og Opdater element i SharePoint [understøtter nu mulighed for at](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) angive felterne Person, Valg og Opslag.
* **Flere handlingsindstillinger** – der er nu bedre kontrol over, hvordan udløsere og handlinger kører, herunder konfiguration af politikker for nye forsøg og sideinddeling.
* **Fire nye forbindelser** – du kan nu bruge Azure File Storage, Elastic Forms, Plivo og Video Indexer.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/four-connector-action-settings/) om denne version.

### <a name="release-2017-07-27---q2-update-for-power-automate"></a>Version 2017-07-27 - Q2-opdatering til Power Automate
* **Importer og eksporter** – eksporter og importer flowløsninger på tværs af miljøer eller fra test til produktion. 
* **Brug udtryk i handlinger** – angiv udtryk i en hvilken som helst handling, og få indbygget hjælp til brugen af dem.
* **Udvid til Azure Logic Apps** – Gem dine flows som Azure Logic App-ressource, som kan installeres via Visual Studio- eller Azure-portalen.
* **Administrators synlighed** – Download forbrug af Power Automate til din lejer for at se, præcis hvor og hvordan flows bruges.
* **Strømme i dynamik 365** – Brug flows i Dynamics 365 for Operations & Financials, Business Edition.
* **Find scenarier på en nemmere måde** – gennemse alt, hvad en forbindelse kan gøre, og brug derefter en eventuel udløser som startpunkt til oprettelse af flows.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/q2-2017-update/) om denne version.

### <a name="release-2017-07-13"></a>Udgave 13-07-2017
* **Forbedret publicering af skabeloner** – publicer de flows, du opretter, sammen med tilhørende kategorier til det offentlige galleri.
* **Få hændelser i din Outlook-kalender** – en ny handling, der returnerer alle hændelser mellem to tidspunkter i din kalender.
* **Ny mobilfunktionalitet** – kør flows efter behov, og send igen mislykkede kørsler i mobilappen.
* **Dynamiske rullemenuer i brugerdefinerede forbindelser** – opret dynamiske rullemenuer, forespørgselsudløsere, og test dine brugerdefinerede forbindelser.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) om denne version.

### <a name="release-2017-06-28"></a>Udgave 28-06-2017
* **Opdater dine sprogindstillinger** – Du kan tilpasse både det sprog og område, som Power Automate bruger, via menuen Indstillinger.
* **Fem nye forbindelser** – Understøttelse af Adobe Creative Cloud, Bing Kort, Bing Search, JotForm og Freshservice er tilføjet.
* **Konfigurer timeout** – Rediger tidsrummet for handlinger, der kører i lang tid, f.eks godkendelser, inden der opstår timeout, så flowet fortsætter.
* **Medtag kommentarer i Outlook til godkendelse** – når du modtager en anmodning om godkendelse, kan du angive kommentarer uden at gå ud af Outlook.
* **Brugerdefinerede mærkefarver for forbindelser** – Nu kan du angive en farve for dine brugerdefineret forbindelser, som skal bruges til baggrund.
* **Gem som til teamflows** – Tag kopier af vilkårlige flows, herunder teamflows
* **Slet flowoplysninger** – Når du sletter et flow, får du vist listen over alle ventende kørsler for det pågældende flow.
* **Filtrering på siden Forbindelser** – Søg efter de forbindelser, du vil have, på siden Forbindelser, og filtrer efter forbindelsestype.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/language-settings-3-connectors/) om denne version.

### <a name="release-2017-06-19"></a>Udgave 19-06-2017
Du kan nu få vist status for alle anmodninger, du har sendt, som afventer godkendelse. Derudover kan du søge i og reagere på alle dine ventende godkendelser direkte fra din mobilenhed.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) om denne version.

### <a name="release-2017-06-15"></a>Udgave 15-06-2017
* **Konvertering af indhold** – En ny forbindelse, der kan konvertere HTML-indhold til almindelig tekst, er nyttig til håndtering af HTML-formaterede mails.
* **Tre nye databaseforbindelser** – skrivebeskyttet understøttelse af MySQL, PostgreSQL og Teradata er tilføjet. Der oprettes forbindelse til disse forbindelser via datagatewayen i det lokale miljø.
* **Tre andre connectorer** – Opret forbindelse til Azure Application Insights-, Calendly og Teamwork-projekter.
* **Bedre visualisering til fejlhåndtering** – Trin, der kører efter opståede fejl, vises nu med røde punkterede pile, så du nemt kan identificere dem.
* **Detaljeruden for kørsel** – Når et flow mislykkes, vises der nu en ny rude til højre, som indeholder nogle trinvise vejledninger i, hvordan du kan rette dit flow.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/seven-connectors-and-html/) om denne version.

### <a name="release-2017-06-04"></a>Udgave 04-06-2017
* **Generel tilgængelighed for Windows Phone** - [Power Automate-mobilappen er udgivet, så den er generelt tilgængelig for Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Mails ved flowfejl** – Få besked via mail, når du har et flow, der ikke lykkes. Disse mails om fejl udsendes kun én gang om ugen, og de kan slås til og fra af brugeren.
* **Vælg en handling for tabeller** – Brug den nye Select-handling til at ændre det kolonnesæt, der skal inkluderes i tabeller.
* **Microsoft Forms-connector** – Microsoft Forms er en ny del af Office 365 Education, der giver lærere og studerende mulighed for hurtigt og nemt at oprette brugerdefinerede test, undersøgelser, spørgeskemaer, registreringer og meget mere.
* **Office 365 Enterprise K1-plan** – Power Apps og Power Automate er nu inkluderet i Office 365 Enterprise K1-planen med bestemte kvoter.
* **HTTP-headere er lettere** – På samme måde som med Select-handlingen kan du angive et navn og en værdi for headeren ved blot at udfylde tekstfelterne for handlingen.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) om denne version.

### <a name="release-2017-05-23"></a>Udgave 23-05-2017
* **Microsoft Teams-connector** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) er et chatbaserede arbejdsområde i Office 365, der samler personer, samtaler og indhold – sammen med de værktøjer, de forskellige teams skal bruge, så de nemt kan samarbejde og opnå mere.
* **Widgets på iOS og Android** – Power Automate-widgets er knapgenveje, så du lettere og hurtigere kan udløse de enkelte knapper direkte fra startsiden.
* **Opret trin til "fejlhåndtering"** – Definer et eller flere trin for at køre, når en handling mislykkes. Du kan f.eks. få en meddelelse straks, hvis flowet kan ikke oprette en post i Dynamics 365.
* **Heltal og flydende variabler** – Initialiser og forøg eller formindsk tællere i en flowkørsel til at tælle, hvor mange gange et bestemt logiksæt køres.
* **Side med flowoplysninger** – Når du vælger et flow på listen **Mine flows**, vises en side med oplysninger om det pågældende flow, f.eks. hvem der har adgang til det samt kørselsoversigten.
* **Kvoter for flowkørsler for administratorer** – Administratorer kan nu overvåge brugen af flowkørsler på tværs af en organisation i forhold til kvoten for almindelige kørsler i virksomheden. Dermed kan de få en specifikation af kvoterne, så de kan forstå, hvilke licenser der bidrager til deres kvote.
* **Forbedringer af udløsning af HTTP-anmodninger** – Brug forskellige HTTP-metoder, og tilføj stisegmenter for anmodningsudløseren.
* **To partnerconnectorer** – Power Automate kan nu oprette forbindelse til Parserr, en tjeneste til mailfortolkning, samt Cognito Forms, der er en tjeneste til onlineformularer.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/error-handling/) om denne version.

### <a name="release-2017-05-12"></a>Udgave 12-05-2017
* **Integration med SharePoint-dokumentbiblioteker** – Du kan vælge en vilkårlig fil i et dokumentbibliotek og starte et flow, f.eks. sende det til din chef til godkendelse [og meget mere](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Microsoft Planner-forbindelse** – Med Microsoft Planner kan du nemt samle teams, opgaver, dokumenter og samtaler, så du får bedre resultater.
* **Administratorvisning af licenser** – Administratorer kan se alle Power Automate- og Power Apps-licenser (til både prøve- og betalingsversion) i Power Automate Administration.
* **Power Apps Community-plan** – Power Apps Community-planen er en gratis planlægning for de enkelte brugere, så de kan udforske, lære og opbygge færdigheder for Power Apps, Power Automate og Common Data Service.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/planner-community-and-licenses/) om denne version.

### <a name="release-2017-05-09"></a>Udgave 09-05-2017
* **Azure AD-connector** – Der er en ny connector til udførelse af administratorhandlinger fra Power Automate, herunder oprette brugere eller føje dem til grupper.
* **Forbedringer til Office 365 Outlook** – Flows kan nu udløses af delte postkasser og sende mails til en delt postkasse. De kan også oprette eller læse automatiske svar.
* **Tilgængelig i Canada** – Du kan nu oprette dine flows i Canada.
* **Opret brugerdefinerede API-webhooks** – Udviklere af brugerdefinerede forbindelser kan nu føje udløsere til deres brugerdefinerede API'er med webhooks.
* **Administrer flowejere i Administration** – Miljøadministratorer kan administrere flowejere i Power Automate Administration.
* **Forbindelsesdokumentation** – Vi har nu en [komplet forbindelsesdokumentation på docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **To partnertjenester** – To nye partnertjenester er frigivet: Nexmo og Paylocity.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/canada-mailboxes-aad) om denne version.

### <a name="release-2017-04-27"></a>Udgave 27-04-2017
* **Byg flows med parallelle trin** – Opret flows med parallel udførelse: Det betyder, at du kan have to eller flere trin, der kører på præcis samme tid.
* **Fem nye understøttede tjenester** – Fem nye tjenester: Approvals, Benchmark Email, Capsule CRM, LiveChat og Outlook Customer Manager.
* **Overvåg genforsøg for handlinger** – Power Automate vil prøve igen, når der sker fejl med tjenester. Se nu, hvor mange automatiske forsøg, der forekom, og oplysninger om, hvad der er sket.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/parallel-actions/) om denne version.

### <a name="release-2017-04-17---q1-update-for-power-automate"></a>Version 2017-04-17 - Q1-opdatering til Power Automate
* **Moderne godkendelsesoplevelser** – Opret arbejdsprocesser, hvor godkendere kan godkende sikkert i Power Automate-mobilappen eller via det samlede godkendelsescenter på Power Automate-websitet.
* **Offentlig tilgængelighed af teamflows** – Flere personer kan eje og administrere et flow sammen med teamflows, der nu er offentligt tilgængelige.
* **Byg connectorer til Power Automate** – Alle kan sende deres egen Power Automate-connector gratis, så resten af verden kan bruge dem.
* **En "kost"-designer** – For visse skabeloner præsenterer en ny version af designeren kun de felter, der kræves for at oprette et flow. Det forenkler oplevelsen.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/q1-2017-update/) om denne version.

### <a name="release-2017-04-11"></a>Udgave 11-04-2017
* **Nye handlinger til oprettelse af tabeller og lister** – Nye handlinger, Opret HTML-tabel, Opret CSV-tabel og Joinforbind, som kan behandle lister over elementer (i stedet for den tidligere Anvend kun for hver enkelt).
* **Indsæt trin hvor som helst** – Du kan nu indsætte et nyt trin et vilkårligt sted i arbejdsprocessen uden at skulle trække og placere.
* **Fire nye tjenester** – Power Automate understøtter nu 10 til 8-planlægning, Act!, Inoreader og Computer Vision-API. Med Computer Vision API'et kan du behandle billeder for at få tekstindholdet (kendt som OCR) eller mærke billeder automatisk baseret på deres indhold.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) om denne version.

### <a name="release-2017-04-03"></a>Udgave 03-04-2017
* **Windows Phone-beta** – Windows Phone-betaprogrammet er tilgængeligt, så du kan få vist et eksempel af appen på din Windows Phone. [Læs mere](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF** – Du kan nu konvertere Microsoft Word-filer til PDF-format, tilføje vandmærker, flette dokumenter og meget mere med Muhimbi PDF. [Læs mere](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Udløs flows fra fysiske knapper** – Meddelelse om partnerskaber med to af de førende produkter inden for området fysiske knapper: Flic fra Shortcut Labs og Bttn fra The Button Corporation. [Læs mere](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Udgave 22-03-2017
* **Opret en kopi af dit flow** – Du kan nu oprette en kopi af dit flow, så du kan arbejde på et udkast, eller du kan duplikere et flow, du tidligere har oprettet.
* **To nye tjenester** – Tilføjelse af understøttelse af Toodledo – Administrer din opgaveliste ved at oprette og opdatere opgaver, og Zendesk, som giver dig en platform til kundeservice og understøtter supportanmodninger.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/make-a-copy/) om denne version.

### <a name="release-2017-03-15"></a>Udgave 15-03-2017
* **Del knapper med kolleger** – Du kan nu dele flowknapper med andre, hvilket gør det nemt for enhver virksomhedsbruger at udføre hurtige opgaver.
* **Udløs knapper fra startskærmen** – Genveje til flowknapper fra startskærmen eller låseskærmbilleder på mobile enheder gør det hurtigere end nogensinde at udløse et flow.
* **Teamflows i Power Automate-appen** – Du kan nu se de flows, der har andre ejere, i Power Automate-appen til iOS eller Android.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/button-sharing/) om denne version.

### <a name="release-2017-03-10"></a>Udgave 10-03-2017
* **Forbedret oplevelse af brugerdefineret forbindelse** – Du kan nu bruge en Postman-samling til at oprette en brugerdefineret forbindelse og redigere, tilføje og teste handlinger.
* **To nye tjenester** – Tilføjet Power Apps-meddelelser og understøttelse af PivotalTracker.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/new-updates-custom-api/) om denne version.

### <a name="release-2017-02-27"></a>Udgave 27-02-2017
* **Udløs dine flowknapper** – Du kan nu udløse flowknapper direkte fra Power Automate. Når du kigger på listen over flows, skal du blot vælge menuen "..." og vælge kommandoen Kør nu.
* **Fem nye tjenester** – Understøttelse af Oracle Database, Intercom, FreshBooks, LeanKit og WebMerge er tilføjet.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) om denne version.

### <a name="release-2017-02-21"></a>Udgave 21-02-2017
* **Få vist miljøflows** – miljøadministratorer kan nu få vist en komplet liste over alle flows i et givet miljø samt aktivere, deaktivere eller slette flows.
* **To nye tjenester** – Understøttelse af Azure Automation og Basecamp 2 er tilføjet.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) om denne version.

### <a name="release-2017-02-16"></a>Udgave 16-02-2017
* **Fem nye tjenester** – Understøttelse af Azure Data Lake, Bitbucket (en web baseret værtstjeneste for projekter, der benytter GIT-revisionskontrol), Eventbrite, Infusionsoft og Pipedrive er tilføjet.
* **Brugerdefineret HTTP-godkendelse,** – I flowdesigneren er det nu muligt at bruge godkendelse med brugerdefinerede HTTP-slutpunkter.
* **Fortolk JSON-meddelelser** – Du kan fortolke JSON-data fra HTTP-anmodningsudløseren eller data, der er returneret fra HTTP-handlingen.
* **Filtrering ved flowkørsel** – Forbedret filtrering til flowkørsler med mere specifikke indstillinger, herunder visning af kørende flows eller annullerede kørsler.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) om denne version.

### <a name="release-2017-02-06"></a>Udgave 06-02-2017
* **Teamflows** – Teamflows gør det muligt for flere personer at eje og administrere et flow sammen, og hvis nogen forlader organisationen, kan de flows, de har oprettet, fortsætte med at køre.
* **Deling af brugerdefinerede forbindelser** – Brugerdefinerede forbindelser kan, ligesom teamflows, deles og administreres samlet i en organisation.
* **Understøttelse af Gmail og LUIS** – Opret forbindelse til Gmail og Azure Cognitive Services' LUIS (Language Understanding Intelligent Service).

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/team-flows/) om denne version.

### <a name="release-2017-01-30"></a>Udgave 30-01-2017
* **Flowknapinput** – Flowknapper kan nu modtage brugerinput på kørselstidspunktet, så flowforfattere kan angive oplysninger, som overføres, når der trykkes på knappen.
* **Outlook-opgaver og HelloSign** – Med tjenesten Outlook-opgaver kan du administrere opgaver, og HelloSign giver mulighed for sikre elektroniske signaturer.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/button-user-inputs/) om denne version.

### <a name="release-2017-01-23"></a>Udgave 23-01-2017
* **Søg efter tjeneste** – Søg efter en tjeneste, når du tilføjer en udløser eller en handling for at få vist alle handlinger for hver enkelt tjeneste.
* **Skifte sag** – Tilføj parameterblokke for at have flere grene af parallel logik.
* **Flere mailhandlinger** – Nye funktioner i tjenesterne i Office 365 Outlook og Outlook.com, som kan arbejde med mails, der er markeret med flag.
* **Fem nye tjenester** – Opret forbindelse til lokale filsystemer eller netværksfilsystemer, betalingstjenesten Stripe, IBM Informix, IBM DB2 og UserVoice.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/search-by-service/) om denne version.

### <a name="release-2017-01-14"></a>Udgave 14-01-2017
* **Send kørsler igen** – Hvis der er fejl i et flow, og du vil forsøge at løse problemet og køre flowet igen, kan du sende den fejlbehæftede kørsel igen.
* **Annuller kørsler** – Når et flow sidder fast, kan du nu udtrykkeligt annullere kørslen.
* **To nye tjenester** – Understøttelse af GoToTraining og GoToWebinar er tilføjet.
* **Mobile links** – Du kan dele skabeloner direkte fra mobilappen, og vi har tilføjet et link til hurtig download af apps øverst på webstedet.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/managing-runs/) om denne version.

### <a name="release-2016-12-29"></a>Udgave 29-12-2016
Power Automate understøtter nu DocuSign for at kunne håndtere eSignatures og digital transaktionsstyring, SurveyMonkey til webbaserede undersøgelser samt OneNote-noteappen (kun erhvervskonti).

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/final-2016-services/) om denne version.

### <a name="release-2016-12-20"></a>Udgave 20-12-2016
* **Kør nu** – Du kan nu udsende en tilbagevendende udløser efter behov – hvis du f.eks. har planlagt en rapport hver dag, men du har brug for, at rapporten også køres **nu**.
* **Seks nye tjenester** – Byg flows, der opretter forbindelse til MSN Vejr, Medium, Google Kontaktpersoner, Buffer, Harvest og TypeForm.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/run-now-and-six-more-services/) om denne version.

### <a name="release-2016-12-14"></a>Udgave 14-12-2016
Du kan nu udnytte værdifulde oplysninger, når du udløser et knapflow, f.eks. hvor knappen blev udløst fra, af hvem, hvornår med mere.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/button-trigger-tokens/) om denne version.

### <a name="release-2016-12-06"></a>Udgave 06-12-2016
* **Introduktion til Guided Learning** – Kom i gang med en sekvenseret samling af kurser, der sammenkobler videoer med dokumentation for at hjælpe dig med at forstå de omfattende og effektive funktioner i Power Automate.
* **To nye tjenester** – Flows kan nu bruge Freshdesk, en kundesupportløsning og GoToMeeting, et værktøj til onlinemøder.
* **Understøttelse af HTTP-Webhook** – Et flow kan nu være et slutpunkt for webhooks, der automatisk registrerer og fjerner registreringen af sig selv.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/guided-learning-and-two-services/) om denne version.

### <a name="release-2016-11-23"></a>Udgave 23-11-2016
* **Understøttelse af Power BI-advarsel i flow** – Omsæt indsigt til handling ved at udløse flows fra vigtige Power BI-databeskeder.
* **Forbedringer af mobilprogrammet** – Muligheden for at oprette flows fra bunden af som en udvidelse af den allerede eksisterende mulighed med oprettelse på basis af skabeloner, er tilføjet. Vi har også forbedret ydeevnen, når der vises kørsler af flows.
* **Otte nye tjenester** – Du kan nu oprette forbindelse til Azure Resource Manager, Azure Queues, Chatter, Disqus, Azure Cosmos DB, Cognitive Services Face API, HipChat og Wordpress.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) om denne version.

### <a name="release-2016-11-15"></a>Udgave 15-11-2016
* **Power Automate-partnerprogram** – Power Automate har nu et certificeret partnerprogram til at knytte forbindelser og drage fordel af forskellige virksomhedens talenter og erfaring med Power Automate over hele verden.
* **Seks nye tjenester** – Vi frigiver også seks tjenester i denne uge: Asana, Campfire, EasyRedmine, JIRA, Redmine og Vimeo.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/partner-program-six-new-services/) om denne version.

### <a name="release-2016-10-31---general-availability"></a>Udgave 31-10-2016 – generel tilgængelighed
* **Prisfastsættelse og licenser** – nu tilgængelig i både gratis og betalte planer samt som en del af Office 365 og Dynamics 365.
* **Power Automate Administration** - Klar til brug i virksomheder med det nye Administration. I Administration kan du administrere miljøer inde i organisationen.
* **Politikker til forebyggelse af datatab** – Administratorer kan oprette politikker til forebyggelse af datatab for at styre dataflowet mellem tjenester.
* **Tilgængelighed i Android** – Power Automate-telefonappen er nu tilgængelig for både iOS og Android. Appen gør det muligt for dig at modtage beskeder, overvåge aktiviteter og starte flows med et tryk på en knap.
* **Designnyheder** – Du kan nu søge i det dynamiske indhold, der overføres fra trin til trin, hvilket gør det meget hurtigere at henvise til de ønskede data.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/announcing-ga/) om denne version.

### <a name="release-2016-10-26"></a>Udgave 26-10-2016
* **Knapflows** – Der er utallige handlinger, vi gerne vil kunne udløse når og hvor som helst. Med knapflows kan du nu få dem klaret med et enkelt klik på en knap fra din mobilenhed.
* **Bekendtgørelse af miljøer** – Miljøer er særlige områder til lagring og administration af organisationens flows. Miljøer er geografisk placeret, hvilket betyder, at flows, apps og virksomhedsdata i et miljø, findes i det område, hvor miljøet er placeret.
* **Seks nye tjenester** – Tilføjet understøttelse af Bit.ly, Cognitive Services Text Analytics, Dynamics NAV, Dynamics 365 for Financials, Instapaper og Pinterest.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/environments-for-makers/) om denne version.

### <a name="release-2016-10-16"></a>Udgave 16-10-2016
* **Brugerdefinerede forbindelser understøtter flere godkendelsestyper** – Brugerdefinerede forbindelser understøtter nu godkendelse af API-nøgler og kan godkende mod enhver tjeneste, der understøtter den fulde OAuth 2.0-specifikation.
* **Tre nye tjenester understøttes** – Vi har tilføjet understøttelse af Basecamp 3, Blogger og PagerDuty.
* **Designerforbedringer** – Forbedret ydeevne: Du kan nu opdatere og reparere dine forbindelser direkte fra menuen "..." for alle handlinger, og vi har tilføjet det nye trin Afslut, du kan bruge til at afslutte kørslen af et flow.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/early-october-updates/) om denne version.

### <a name="release-2016-09-25"></a>Udgave 25-09-2016
Flowoprettelse er nu tilgængelig fra din mobiltelefon. Gennemse vores omfattende skabelongalleri, naviger gennem vores liste over tjenester, eller vælg en skabelonkategori, du kan dykke ned i. [Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/mobile-creation/) om denne version.

### <a name="release-2016-09-22"></a>Udgave 22-09-2016
* **Microsoft Graph-personvælger** – En ny Microsoft Graph-personvælger er integreret direkte i Power Automate-brugergrænseflade og kan hjælpe dig med at vælge den rettee kontakt eller mailadresse.
* **Understøttelse af Microsoft Dynamics AX** – Du kan nu udføre handlinger på dine Dynamics AX Online-handlingsdata inde fra dine flow, det gælder lige fra oprettelse af nye poster til forespørgsel om data.
* **To nye tjenester fra partnere** – Nu kan du bruge appFigures eller Insightly fra dine flow.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/more-september-updates/) om denne version.

### <a name="release-2016-09-14"></a>Udgave 14-09-2016
* **Integration på dit website eller i din app** – Udviklere kan nu integrere Power Automate direkte i deres apps eller på deres websites, så det bliver nemmere for brugerne at automatisere deres personlige eller arbejdsmæssige opgaver.
* **Brug et flow som et HTTP-slutpunkt** – Nu kan du bruge et flow som en HTTP API. I et flow er der en udløser, der kaldes Anmodning, og du kan vælge at besvare den indgående anmodning ved at tilføje et svarkort.
* **Understøttelse af Todoist** – Todoist giver dig overblik over alle dine projekter, både på arbejdet og derhjemme.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/extend-web-site-application/) om denne version.

### <a name="release-2016-09-01"></a>Udgave 01-09-2016
Power Automate er nu tilgængelig for alle – prøveversionen var i starten udelukkende tilgængelig for arbejds- eller skole-mailadresser, f.eks. dem, der blev brugt sammen med Office 365 Business eller Office 365 Enterprise. I dag er prøveversionen officielt tilgængelig og gratis for alle brugere, uanset hvilken mail du har. [Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/available-for-everyone/) om denne version.

### <a name="release-2016-08-31"></a>Udgave 31-08-2016
* **Indlejrede betingelser** – nu kan du tilføje en anden (eller tredje osv.) betingelse i en betingelse.
* **Anvend på alle** – En Anvend på alle-løkke gør det muligt at styre den liste, du bruger som basis for gentagelse.
* **Foretag indtil** – En Foretag indtil-løkke gør det muligt at gentage et trin, indtil en bestemt betingelse er opfyldt.
* **Filtermatrixer** – Der er et enkelt indbygget filtertrin, der kan sikre, at alle elementer på listen svarer til nogle udtryk, du definerer.
* **Sammensæt strengvariabler** – Du kan nu sammensætte en strengvariabel.
* **Områder** – Områder er en nem måde at gruppere to eller flere handlinger på.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/build-advanced-flows/) om denne version.

### <a name="release-2016-08-27"></a>Udgave 27-08-2016
* **Kommentarer til trin** – Kommentarer gør det let at anmærke hver enkelt handling med noter, så du nemt kan huske, hvad flowet har brug for
* **Understøttelse af Smartsheet** – I denne uge har vi tilføjet understøttelse af oprettelse af forbindelse til Smartsheet. Smartsheet er en tjeneste, der gør det nemt at samarbejde om ark i cloudmiljøet.
* **Forbedring af brugergrænsefladen ved godkendelse af flow** – Vi har placeret flownavnet forrest og centreret det samt flyttet knappen Gem til den øverste del af siden, så den er lettere tilgængelig.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/add-comments-smartsheet/) om denne version.

### <a name="release-2016-08-18"></a>Udgave 18-08-2016
Nu kan du se de nye moderne SharePoint Online-lister, der omfatter Power Automate-integration. [Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) om denne version.

### <a name="release-2016-08-13"></a>Udgave 13-08-2016
* **Visual Studio Team Services** – Med Power Automate kan du nu oprette forbindelse mellem VSTS og en lang række tjenester, f.eks. O365 Email, Slack og Trello.
* **Forbedringer af SharePoint** – SharePoint-lister understøtter flere forskellige datatyper, lige fra simple objekter, som enkeltstående tekstlinjer samt Dato og klokkeslæt, til komplekse objekter, som Person eller gruppe, Opslag og Valg.
* **Test af O365 Outlook-forbindelser** – Hver gang du opretter en ny forbindelse i O365 Outlook, testes den nu for at sikre, at du er klar til at bruge den.
* **Boolesk kontrolelement** – Vi har også tilføjet et boolesk kontrolelement for at præcisere, hvilke værdier du skal angive i booleske indtastningsfelter, f.eks. Har vedhæftede filer i udløseren Når der modtages en ny mail.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) om denne version.

### <a name="release-2016-08-08"></a>Udgave 08-08-2016
Offentlig prøveversion af Common Data Service integreret i Power Automate. [Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/flow-and-common-data-model/) om denne version.

### <a name="release-2016-08-05"></a>Udgave 05-08-2016
* **SharePoint i det lokale miljø** – Ligesom med SharePoint Online kan du oprette flow omkring SharePoint-lister og biblioteker i det lokale miljø, enten ved hjælp af foruddefinerede skabeloner eller ved at bygge dem helt fra bunden.
* **Oplysningsbobler i designeren** – Vi har tilføjet oplysningsbobler over hvert trin i dit flow for at beskrive funktionaliteten for hver enkelt udløser og handling.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) om denne version.

### <a name="release-2016-07-15"></a>Udgave 15-07-2016
* **Fire nye tjenester er tilføjet** – Opret forbindelse til Google Kalender, Google Opgaver, YouTube og SparkPost.
* **Omdøb dine handlinger** – Nu kan du skelne forskellige handlinger fra hinanden ved at omdøbe dem.
* **Forsinkelse for forskellige tidsperioder** – Du kan nu vælge et vilkårligt antal sekunder, minutter, timer eller dage.
* **Nemmere at bruge mappebrowser** – Vi har forenklet mappebrowseren – hvis du klikker til venstre, vælger du den pågældende mappe, og hvis du klikker til højre, åbnes mappen, så du kan vælge undermapperne.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/new-google-services-rename-more/) om denne version.

### <a name="release-2016-07-08"></a>Udgave 08-07-2016
Forbindelse til Power Automate i det lokale miljø ved hjælp af datagateway i det lokale miljø. Det gør det muligt at oprette sikre forbindelser til SQL Server og integrere dem i dine flow. [Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/on-premises-data-gateway/) om denne version.

### <a name="release-2016-07-02"></a>Udgave 02-07-2016
* **Understøttelse af Google Ark** – Før i tiden, har vi haft både mulighed for at bruge Excel og Google Drev, men i denne uge tilføjer vi indbygget understøttelse af Google Ark.
* **Kom hurtigere i gang fra skabeloner** – Vi har også foretaget nogle optimeringer af fremgangsmåden, når du starter fra en skabelon. Nu kan du vælge, hvilke konti du vil bruge til en skabelon, direkte fra skabelonsiden.
* **Ingen udløbsgodkendelse for SharePoint og Office 365** – Nu fornyer Power Automate automatisk din adgang til Azure Active Directory-baserede tjenester, så alle dine flow fortsætter med at fungere på tværs af adgangskodeændringer.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/more-june-updates/) om denne version.

### <a name="release-2016-06-20"></a>Udgave 20-06-2016
* **Vi præsenterer den nye mobilapp til Power Automate** – I dag glæder det os at kunne præsentere et andet højdepunkt i vores tilbud: En mobilapp, der nu kan hentes på iOS (snart også på Android) og giver dig mulighed for at administrere, holde styr på og udforske dine automatiserede arbejdsprocesser når som helst og hvor som helst.  
* **Enkeltlogon** – Vi har implementeret enkeltlogon, der gør det muligt at blive godkendt i Power Automate med andre Microsoft-tjenester såsom Office 365.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) om denne version.

### <a name="release-2016-06-18"></a>Udgave 18-06-2016
* **Ny mail-tjeneste** – Du kan nu sende mails direkte fra Power Automate uden at skulle oprette forbindelse til din private mailkonto eller arbejdsmailkonto i Power Automate.
* **Meddelelser i portalen** – Du kan nu få vist meddelelser øverst i portalen, når noget deles med dine flows.
* **Al aktivitet i portalen** – Du kan nu få vist aktivitet på tværs af alle dine flow ved at klikke på fanen Aktivitet på flowwebstedet.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/mail-and-all-activity/) om denne version.

### <a name="release-2016-05-27"></a>Udgave 27-05-2016
* **Gennemse skabeloner efter tjeneste** – Der er nu en måde at få vist alle de tjenester, vi understøtter (uden at skulle logge på). På denne side vises en beskrivelse af hver enkelt tjeneste, og du kan gennemse de skabeloner, vi har for den pågældende tjeneste.
* **Opret og brug dine brugerdefinerede connectorer** – Ligesom du kan oprette brugerdefinerede connectorer i Power Apps, kan du også oprette forbindelse til dine egne API'er på flow.microsoft.com:
* **Test dine flow, før du afslutter** – Når du gemmer et flow, kan resultaterne af flowet køre direkte på siden, hvis du udfører starthandlingen.

[Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) om denne version.

### <a name="release-2016-05-07"></a>Udgave 07-05-2016
Tilføjet to nye tjenester: Microsoft Project Online og Mandrill by Mailchimp. [Få mere at vide, og stil spørgsmål](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) om denne version.

### <a name="release-2016-04-27---public-preview"></a>Version 27-04-2016 – Offentlig prøveversion
Hvis du har brugt logiske flows som en del af [Microsoft Power Apps](https://powerapps.microsoft.com), indeholder prøveversionen af Power Automate flere nye funktioner:

* Du kan nu gennemse et galleri med masser af skabeloner og sortere efter popularitet, navn eller publiceringsdato.
* Du kan [publicere dine egne skabeloner](publish-a-template.md) i galleriet, når du har tilpasset et flow.
* Du kan få vist en oversigt for hver kontrol og kørsel i flowet.
* Når du gemmer et flow, kan du [straks få det vist i aktion](see-a-flow-run.md) ved blot at udføre den udløsende handling.
* Vi har et [nyt community](https://go.microsoft.com/fwlink/?LinkID=787467), hvor du kan diskutere Power Automate eller [indsende dine idéer](https://go.microsoft.com/fwlink/?LinkID=787474).

>[!NOTE]
>Udgivelsesplaner spores nu [her](https://docs.microsoft.com/dynamics365/release-plans/).

## <a name="next-steps"></a>Næste trin
Hvis du har nogen problemer, der ikke allerede er dækket af disse produktbemærkninger eller af [Ofte stillede spørgsmål](frequently-asked-questions.md), kan du [tilmelde dig vores community](https://go.microsoft.com/fwlink/?LinkID=787467) for at stille spørgsmål eller [kontakte support](https://go.microsoft.com/fwlink/?LinkID=787479).

