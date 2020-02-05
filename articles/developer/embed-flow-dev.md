---
title: Integrer Power Automate på websteder og i programmer | Microsoft Docs
description: Integrer Power Automate på dit websted eller i dit program.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 6ca077b6a7b0d04f184ddf8a716dd677713e0667
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74364620"
---
# <a name="integrate-power-automate-with-websites-and-apps"></a>Integrer Power Automate på websteder og i programmer
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Integrer Power Automate i dit program eller på dit websted ved hjælp af *flowwidgets* for at give dine brugere en enkel måde at automatisere deres personlige eller professionelle opgaver på.

Flowwidgets er iframes, der er placeret i et værtsdokument. Dette dokument peger på en side i Power Automate-designeren. Disse widgets integrerer specifikke Power Automate-funktioner i tredjepartsprogrammet.

Widgets kan være enkle. Det kan f.eks. være en widget, der gengiver en liste over skabeloner uden kommunikation mellem værten og iframe. Widgets kan også være komplekse. Det kan f.eks. være en widget, der klargør et flow fra en skabelon og derefter udløser flowet via tovejskommunikation mellem værten og widgetten.

## <a name="prerequisites"></a>Forudsætninger

- en **Microsoft-konto** eller
- en arbejds- eller skolekonto

## <a name="use-the-unauthenticated-widget"></a>Brug den ikke-godkendte widget
Hvis du vil bruge den ikke-godkendte skabelonwidget, skal du integrere den direkte i værtsprogrammet ved hjælp af en iframe. Du behøver ikke JS SDK'et eller et adgangstoken. 

### <a name="show-templates-for-your-scenarios"></a>Vis skabeloner til dine scenarier
Du starter ved at tilføje denne kode for at vise Power Automate-skabelonerne på dit websted:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Parameter | Beskrivelse |
| --- | --- |
| landestandard |Koden på fire bogstaver for visning af skabelonen. F.eks. repræsenterer `en-us` amerikansk engelsk, og `de-de` repræsenterer tysk. |
| søgeord |Søgeordet til de skabeloner, du vil have vist i visningen. Søg f.eks. på `wunderlist` for at få vist skabeloner til Wunderlist. |
| antallet af skabeloner |Det antal skabeloner, du vil have vist i visningen. |
| destination |Den side, der åbnes, når brugeren vælger skabelonen. Angiv `details` for at vise oplysningerne om skabelonen, eller angiv `new` for at åbne Power Automate-designeren. |
| category |Filtrerer til den angivne skabelonkategori. | 
| parameters.{name} |Yderligere kontekst, der sendes til flowet. |


Hvis destinationsparameteren er `new`, åbnes Power Automate-designeren, når brugerne vælger en skabelon. Brugerne kan derefter oprette et flow i designeren. Se næste afsnit, hvis du vil have hele oplevelsen med widgetten.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Overførsel af yderligere parametre til flowskabelonen

Hvis brugeren er i en specifik kontekst på dit websted eller i dit program, kan du overføre denne kontekst til flowet. F.eks. åbner en bruger måske en skabelon til *Giv mig besked, når et element føjes til en liste*, mens vedkommende ser på en bestemt liste i Wunderlist. Følg disse trin for at overføre liste-id'et som en *parameter* til flowet:

1. Angiv parameteren i flowskabelonen, inden du udgiver den. En parameter ser sådan ud `@{parameters('parameter_name')}`.
1. Overfør parameteren i iframe-kildens forespørgselsstreng. Tilføj f.eks `&parameters.listName={the name of the list}`, hvis du har en parameter med navnet **listName**.

### <a name="full-sample"></a>Komplet eksempel

Hvis du vil vise de øverste fire Wunderlist-skabeloner på tysk og starte brugeren med **myCoolList**, skal du bruge denne kode:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Brug de godkendte flowwidgets

I følgende tabel vises listen over Power Automate-widgets, der understøtter den fulde oplevelse i widgetten ved hjælp af et adgangstoken til brugergodkendelse. Du skal bruge Javascript Software Developer Kit (JS SDK) for Power Automate til at integrere widgets og levere det påkrævede brugeradgangstoken.

| Widgettype    | Understøttet funktion                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| flow          | Viser en liste over flow under en fane for personlige og delte flow. Rediger et eksisterende flow, eller opret et nyt flow fra en skabelon eller en tom. | 
| flowCreation   | Opretter et flow fra et skabelon-id, der leveres af værtsprogrammet.                                                                | 
| kørsel        | Udløser et manuelt flow eller et hybridudløserflow, der leveres af værtsprogrammet.                                                        | 
| approvalCenter | Integrerer godkendelsesanmodninger og sendte godkendelser.                                                                                        | 
| skabeloner      | Viser en liste over skabeloner. Brugeren vælger en for at oprette et nyt flow.                                                                         | 

Brug det godkendte Flow SDK til at giver brugerne tilladelse til at oprette og administrere flow direkte fra dit websted eller program (i stedet for at navigere til Power Automate). Du skal logge brugeren på med vedkommendes Microsoft-konto eller Azure Active Directory, før det godkendte SDK kan bruges.

> [!NOTE]
> Det er ikke muligt at skjule Power Automate-mærkningen, når du bruger widgets.

## <a name="widget-architecture"></a>Widgetarkitektur

Power Automate-widgets fungerer ved at integrere en iframe, der refererer til Power Automate i et værtsprogram. Værten leverer det adgangstoken, der kræves af Power Automate-widgetten. JS SDK for Power Automate gør det muligt for værtsprogrammet at initialisere og administrere livscyklussen for widgetten.

![widgetarkitektur](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Oplysninger om JS SDK

Power Automate-teamet leverer JS SDK'et for at facilitere integration af Flow-widgets i tredjepartsprogrammer. JS SDK'et for Flow er tilgængeligt som et offentligt link i Flow-tjenesten og gør det muligt for værtsprogrammet at håndtere hændelser fra widgetten og interagere med Flow-programmet ved at sende handlinger til widgetten. Widgethændelser og -handlinger er specifikke for widgettypen.

### <a name="widget-initialization"></a>Initialisering af widget

Referencen til Flow JS SDK skal føjes til værtsprogrammet, før widgetten initialiseres.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Opret en forekomst af JS SDK ved at overføre valgfrie værdier for hostName og landestandard i et JSON-objekt.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Navn     | Påkrævet/valgfri | Beskrivelse                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Valgfri          | Power Automate-værtsnavn, f.eks. https://flow.microsoft.com        | 
| `locale`   | Valgfri          | Klientlandestandarden for widgetten (som standard `en-Us`, hvis der ikke er angivet noget) | 


Når du har oprettet forekomsten af JS SDK'et, kan du initialisere og integrere en Power Automate-widget i et overordnet element i værtsprogrammet. Det gør du ved at tilføje en HTML-div:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Initialiser derefter Power Automate-widgetten med `renderWidget()`-metoden for JS SDK'et. Husk at angive widgettypen og tilhørende indstillinger.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Her er et formateksempel for den objektbeholder, som du kan ændre, så den stemmer overens med værtsprogrammets dimensioner.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Dette er parametrene for `renderWidget()`: 

| Parameter        | Påkrævet/valgfri | Beskrivelse                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Påkrævet          | Id'et for et DIV-element på værtssiden, hvor widgetten skal integreres.                   | 
| `environmentId`    | Valgfri          | Widgets skal have et miljø-id. Hvis du ikke angiver et id, bruges standardmiljøet | 
| `flowsSettings`    | Valgfri          | Objekt for Power Automate-indstillinger                                                                        | 
| `templateSettings` | Valgfri          | Objekt for skabelonindstillinger                                                                    | 
| `approvalSettings` | Valgfri          | Objekt for godkendelsesindstillinger                                                                    | 

### <a name="access-tokens"></a>Adgangstokens

Efter JS SDK'et `renderWidget()` har kørt, initialiserer JS SDK'et en iframe, der peger på URL-adressen til Power Automate-widgetten. Denne URL-adresse indeholder alle indstillinger i parametre for forespørgselsstrenge. Værtsprogrammet skal have et Power Automate-adgangstoken for brugeren (Azure Active Directory JWT-token med målgruppen https://service.flow.microsoft.com), før det initialiserer widgetten. Widgetten sender en hændelse af typen `GET_ACCESS_TOKEN` for at anmode om et adgangstoken fra værten. Værten skal håndtere hændelsen og overføre dette token til widgetten:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

Værtsprogrammet er ansvarlig for at vedligeholde tokenet og overføre det med en gyldig udløbsdato til widgetten, når der anmodes om det. Hvis widgetten er åben i længere perioder, skal værten kontrollere, om tokenet er udløbet, og opdatere tokenet, hvis det er nødvendigt, før det overføres til widgetten.

### <a name="detecting-if-the-widget-is-ready"></a>Registrering af, om widgetten er klar

Efter fuldført initialisering sender widgetten en hændelse for at give besked om, at widgetten er klar. Værten kan lytte til hændelsen `WIDGET_READY` og udføre yderligere værtskode.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Widgetindstillinger

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings kan bruges til at tilpasse funktionaliteten af Power Automate-widgetten.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parameter | Påkrævet/valgfri | Beskrivelse | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Påkrævet | Brug skabelonens GUID, når brugeren vælger knappen **Opret fra bunden** i Flow-widgetten. | 
| `flowsFilter` | Valgfri | Power Automate-widgetten anvender det angivne filter, når der angives flow. Vis f.eks. flow, der refererer til et specifikt SharePoint-websted. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Valgfri | Som standard vises den aktive fane i Power Automate-widgetten. <br /> F.eks. <br /> ```tab:'sharedFlows' ``` viser fanen Team,<br /> og ``` tab:'myFlows' ``` viser fanen Mine flow. |   

### <a name="templatessettings"></a>TemplatesSettings 

Dette gælder for alle widgets, der gør det muligt for dig at oprette flow fra en skabelon, herunder Flow, FlowCreation og skabelonwidgets.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Parameter |Påkrævet/valgfri | Beskrivelse                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Valgfri          | Tidsparametre for design, der skal bruges, når du opretter et flow fra en skabelon, f. eks.: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Valgfri          | Gyldige værdier er "new" eller "details". Når den angives til "details", vises en side med detaljer, når du opretter et flow fra en skabelon.     |
| `pageSize` | Valgfri          | Antallet af skabeloner, der skal vises. Standardstørrelse = 6 | 
| `searchTerm` | Valgfri          | Vis skabeloner, der stemmer overens med det angivne søgeord.| 
| `templateCategory` | Valgfri          | Vis skabeloner i en specifik kategori.| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Gælder for ApprovalCenter-widgets.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Parameter | Påkrævet/valgfri | Beskrivelse | 
|------------|-------------------|--------------| 
| `hideLink`| Valgfri | Når den angives til `true`, skjuler widgetten de modtagne og sendte godkendelseslinks | 
| `autoNavigateToDetails`| Valgfri | Når den angives til `true`, åbner widgetten automatisk godkendelsesdetaljerne, når der kun findes én godkendelse | 
| `approvalsFilter`| Valgfri | Godkendelseswidgetten anvender det angivne godkendelsesfilter, når godkendelserne anføres, f.eks.:    Godkendelseswidgetten anvender det angivne godkendelsesfilter, når godkendelserne anføres, f.eks.: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Valgfri | Den aktive fanes vises som standard i Flow-widgetten. <br/> Gyldige værdier: "receivedApprovals", "sentApprovals" | 
| `showSimpleEmptyPage`| Valgfri | Viser en tom side, når der ikke er nogen godkendelser | 
| `hideInfoPaneCloseButton` | Valgfri | Skjuler knappen Luk i ruden med oplysninger (eller værten har allerede knappen Luk) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Widgethændelser

Power Automate-widgetten understøtter hændelser, som lader værten lytte til hændelser for widgettens livscyklus. Power Automate-widgetten understøtter to typer af hændelser: hændelser for ensrettede meddelelser (f.eks. Widget\_Ready) og hændelser, der sendes fra widgetten for at hente data fra værten (Get\_Access\_Token). Værten skal bruge metoden widget.listen() til at lytte til specifikke hændelser, der sendes fra widgetten.

### <a name="usage"></a>Forbrug

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Understøttede hændelser efter widgettype

| Widgethændelse      | Detaljer                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Widgetten blev indlæst                                      | 
| `WIDGET_RENDERED`   | Widgetten blev indlæst og gengivelse af brugergrænsefladen er fuldført                      | 
| `GET_ACCESS_TOKEN`  | Widgetanmodning om integration af brugeradgangstoken                      | 
| `GET_STRINGS`       | Gør det muligt for værten at tilsidesætte et sæt brugergrænsefladestrenge, der vises i widgetten | 

### <a name="runtime-widget"></a>Widgetten Runtime

| Widgethændelse                    | Detaljer                                     | Data                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Udløst og kørslen af flowet blev startet      |           | 
| `RUN_FLOW_COMPLETED`              | Kørsel af flow blev udløst             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Brugeren valgte knappen Udført for kørsel af flow       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Brugeren valgte knappen Annuller for kørsel af flow     |           | 
| `FLOW_CREATION_SUCCEEDED`         | Flowet blev oprettet           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Udløses, når værten bør lukke widgetten |       | 

### <a name="flow-creation-widget"></a>Widgetten Oprettelse af flow

| Widgethændelse             | Detaljer                                  | Data  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Oprettelse af flow mislykkedes                     |       | 
| `WIDGET_CLOSE`             | Udløses, når værten bør lukke widgetten  |       | 
| `TEMPLATE_LOAD_FAILED`     | Skabelonen blev ikke indlæst              |       | 
| `FLOW_CREATION_SUCCEEDED`  | Flowet blev oprettet        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widgetten Godkendelse

| Widgethændelse                      | Detaljer                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Modtaget godkendelsesstatus blev ændret  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Sendt godkendelsesstatus blev ændret      | 

Med hændelsen **GET\_STRINGS** kan du tilpasse teksten for nogle af de elementer i brugergrænsefladen, der vises i widgetten. Følgende strenge kan tilpasses:

| Strengnøgle                     | Brug i widgetten                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Tekst, der vises på knappen Opret flow i både widgetten Oprettelse af flow og Runtime.                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Den oprindelige værdi, der skal bruges til flownavnet i widgetten Oprettelse af flow. Bruges kun, når indstillingen allowCustomFlowName er aktiveret. | 
| `FLOW_CREATION_HEADER`           | Overskrift, der kan bruges, når der oprettes et flow i både widgetten Oprettelse af flow og Runtime.                                                    | 
| `INVOKE_FLOW_HEADER`             | Overskrift, der skal bruges, når der kaldes et flow i widgetten Runtime.                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Tekst, der vises på knappen, der bruges til at kalde/køre et flow i widgetten Runtime                                                       | 

### <a name="example"></a>Eksempel

Kalder `widgetDoneCallback`, der overfører et JSON-objekt, med nøgleværdipar for en strengnøgle og tekst til at tilsidesætte standardværdien.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Widgethandlinger

Værten bruger widgethandlinger til at sende en specifik handling eller en meddelelse til widgetten. Widget JS SDK indeholder metoden `notify()`, som bruges til at sende en meddelelse eller JSON-nyttedata til widgetten. Hver widgethandling understøtter en specifik nyttedatasignatur.

### <a name="usage"></a>Brug

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Eksempel 

Kald et flow ved at sende følgende kommando til en widget til runtime 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widgetten Runtime

| Widgethandling                               | Detaljer                                                      | Parametergrænseflade  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Udløser en kørsel af flow                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Udløser en kørsel af flow af skabelonen                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Henter udløserskemaet for et flow                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Annullerer eventuelle ventende aktiviteter og sender hændelsen WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widgetten Oprettelse af flow

| Widgethandling                               | Detaljer                                                      | Parametergrænseflade  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Opretter et flow for den valgte skabelon                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Opretter et flow for den valgte skabelondefinition          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Annullerer eventuelle ventende aktiviteter og sender hændelsen WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widgetten Godkendelse

| Widgethandling  | Detaljer                                           | Parametergrænseflade  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Lukker ruden med oplysninger, hvor godkendelsesdetaljerne vises  | I/T                  | 

## <a name="configuring-your-client-application"></a>Konfiguration af dit klientprogram

Du skal konfigurere dit klientprogram med områder for Flow-tjenesten (delegeret tilladelser). Hvis Azure Active Directory-programmet (AAD), der bruges til at integrere widgetten, bruger et godkendelesflow af typen "code grant", skal AAD-programmet forudkonfigureres med delegerede tilladelser, der understøttes af Power Automate. Dette giver delegerede tilladelser, der giver programmet mulighed for:

-   at administrere godkendelser
-   at læse godkendelser
-   at læse aktiviteter
-   at administrere flow
-   at læse flow

Følg disse trin for at vælge en eller flere delegerede tilladelser:

1.  Gå til https://portal.azure.com 
2.  Vælg **Azure Active Directory**.
3.  Vælg **Programregistreringer** under **Administrer**.
4.  Angiv det tredjepartsprogram, der skal konfigureres for området for Flow-tjenesten.
5.  Vælg **Indstillinger**.
      ![widgetarkitektur](../media/embed-flow-dev/AAD-App-Settings.png)
6. Vælg **Påkrævede tilladelser** under **API-adgang**/
7. Vælg **Tilføj**.
8. Vælg **Vælg en API**.
      ![widgetarkitektur](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Søg efter **Power Automate-tjenesten**, og vælg den. Bemærk! Før du kan se Power Automate-tjenesten, skal der være logget mindst én AAD-bruger på din lejer på Flow-portalen (<https://flow.microsoft.com>).
10. Vælg de påkrævede Flow-områder for dit program, og vælg derefter **Gem**.
      ![widgetarkitektur](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Dit program får nu vist et token til Flow-tjenesten, der indeholder delegerede tilladelser i kravet \'scp' i JWT-tokenet.

## <a name="sample-application-embedding-flow-widgets"></a>Eksempelprogram til integration af flowwidgets 

I ressourceafsnittet er der et eksempel på en JavaScript SPA (Single Page Application), så du kan eksperimentere med integration af flowwidgets på en værtsside. Brug af eksempelprogrammet kræver, at du registrerer et AAD-program med implicit tildeling af flow aktiveret.

### <a name="registering-an-aad-app"></a>Registrering af et AAD-program

1.  Log på [Azure Portal](https://portal.azure.com/).
2.  I navigationsruden til venstre skal du vælge **Azure Active Directory** og derefter vælge **Programregistreringer** (prøveversion) \> Ny registrering.
3.  Når siden **Registrer et program** vises, skal du angive et navn på dit program.
4.  Under **Understøttede kontotyper** skal du vælge **Konti** i et hvilket som helst organisationskatalog.
5.  Under afsnittet **URL-adresse til omdirigering** skal du vælge webplatformen og angive værdien til programmets URL-adresse afhængigt af din webserver.\'  Konfigurer denne værdi til http://localhost:30662/ for at køre eksempelprogrammet.
6.  Vælg **Registrer**.
7.  På siden **Oversigt** over program skal du notere værdien for program-id'et (klient).
8.  Eksemplet kræver, at [implicit tildeling af flow](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) er aktiveret. I navigationsruden til venstre i det registrerede program skal du vælge **Godkendelse**.
9.  Under **Avancerede indstillinger** under **Implicit tildeling** skal du markere begge afkrydsningsfelter **Id-tokens** og **Adgangstokens**. Id-tokens og adgangstokens er påkrævet, da dette program skal logge brugerne på og kalde Flow-API.
10. Vælg **Gem**.

### <a name="running-the-sample"></a>Kørsel af eksemplet
<!-- todo where should I download from? -->
1.  Download eksemplet, og kopiér det til en lokal mappe på din enhed.
2.  Åbn filen index.html i mappen FlowSDKSample, og rediger `applicationConfig` for at opdatere `clientID` til det program-id, du registrerede tidligere.
    ![widgetarkitektur](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  Eksempelprogrammer er konfigureret til at bruge Flow-områderne **Flows.Read.All** og **Flow.Manage.All.** Du kan konfigurere yderligere områder ved at opdatere egenskaben **flowScopes** i objektet **applicationConfig**.
4.  Kør disse kommandoer for at installere afhængigheden og køre eksempelprogrammet:
    > \> npm install \> node server.js
5. Åbn browseren, og angiv derefter http://localhost:30662
6. Vælg knappen **Log på** for at godkende mod AAD og hente et adgangstoken til flow.
7. Tekstfeltet **Adgangstoken** indeholder det pågældende adgangstoken.
    ![widgetarkitektur](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Vælg **Widgetten Indlæs flow** eller **Widgetten Indlæs skabeloner** for at integrere de tilsvarende widgets.
    ![widgetarkitektur](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

[Downloadlink](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip) til eksempelprogram.

## <a name="resources"></a>Ressourcer

### <a name="widget-test-pages"></a>Testsider til widget

Få mere at vide om integration af og indstillinger for widget:

- Widgetten Skabeloner: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Widgetten FlowCreation: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Widgetten Runtime: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Widgetten Godkendelsescenter: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widgetten Flow: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Understøttede landestandarder for widget

Hvis den initialiserede landestandard ikke er angivet, vil Flow som standard bruge den nærmeste understøttede landestandard.

| Landestandard     | Sprog                   | 
|------------|----------------------------| 
| bg-bg      | Bulgarsk (Bulgarien)       | 
| ca-es      | Catalansk (Spanien)            | 
| cs-cz      | Tjekkisk (Tjekkiet)     | 
| da-dk      | Dansk (Danmark)           | 
| de-de      | Tysk (Tyskland)           | 
| el-gr      | Græsk (Grækenland)             | 
| en-Us      | Engelsk (USA)    | 
| es-es      | Spansk (castiliansk)        | 
| et-ee      | Estisk (Estland)         | 
| eu-es      | Baskisk (Spanien)             | 
| fi-fi      | Finsk (Finland)          | 
| fr-fr      | Fransk (Frankrig)            | 
| gl-es      | Galicisk (Spanien)           | 
| hi-HU      | Ungarsk (Ungarn)        | 
| hi-in      | Hindi (Indien)              | 
| hr-hr      | Kroatisk (Kroatien)         | 
| id-Id      | Indonesisk (Indonesien)     | 
| it-It      | Italiensk (Italien)            | 
| jp-Jp      | Japansk (Japan)           | 
| kk-kz      | Kasakhisk (Kasakhstan)        | 
| ko-kr      | Koreansk (Korea)             | 
| lt-LT      | Litauisk (Litauen)     | 
| lv-lv      | Lettisk (Letland)           | 
| ms-my      | Malajisk (Malaysia)           | 
| nb-no      | Norsk (bokmål, Norge)         | 
| nl-nl      | Nederlandsk (Nederlandene)        | 
| pl-pl      | Polsk (Polen)            | 
| pt-br      | Portugisisk (Brasilien)        | 
| pt-pt      | Portugisisk (Portugal)      | 
| ro-ro      | Rumænsk (Rumænien)         | 
| ru-ru      | Russisk (Rusland)           | 
| sk-sk      | Slovakisk (Slovakiet)          | 
| sl-si      | Slovensk (Slovenien)       | 
| sr-cyrl-rs | Serbisk (kyrillisk, Serbien) | 
| sr-latn-rs | Serbisk (latin, Serbien)    | 
| sv-se      | Svensk (Sverige)           | 
| th-th      | Thai (Thailand)            | 
| tr-tr      | Tyrkisk (Tyrkiet)           | 
| uk-ua      | Ukrainsk (Ukraine)        | 
| vi-vn      | Vietnamesisk (Vietnam)      |
