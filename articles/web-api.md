---
title: Flows gemmes nu i Common Data Service og bruger den omfattende web-API
description: Flows gemmes nu i Common Data Service og bruger den omfattende web-API.
author: msftman
ms.reviewer: deonhe
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: deonhe
audience: Power user
ms.openlocfilehash: 425e74cca78d53dca8c6e184bcfc63206f36c9f7
ms.sourcegitcommit: 2971e852bdb76efbe012b9de8df8e7f492063184
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/29/2020
ms.locfileid: "3900402"
---
# <a name="power-automate-web-api"></a>Web API til Power Automate


Fremover gemmes alle flows i Common Data Service og gør brug af [den omfattende web-API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api).

Dette indhold dækker administrationen af flows, som er inkluderet på fanen **Løsninger** i Power Automate. I øjeblikket understøtter disse API'er ikke flows under **Mine flows**.

## <a name="compose-http-requests"></a>Udarbejd HTTP-anmodninger

Du skal starte med at skabe URL-adressen for at komme i gang med at oprette anmodninger. Formatet af den grundlæggende URL-adresse til web-API'en til Power Automate er: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. De to parametre er:

- **Organisations-id** er et entydigt navn på det miljø, der gemmer dine flows. 

- **Underdomæne for område** afhænger af placeringen af dit miljø.

Sådan hentes disse to parametre:
1. Gå til [Power Platform Administration](https://admin.powerplatform.microsoft.com/).
2. Vælg det miljø, du bruger til at bygge flows.

 ![URL-adresse for flow](media/web-api/power-platform-admin-center.png "URL-adresse for flow")

3. Kopier organisationens id og områdets underdomæne fra miljøets URL-adresse.

 ![URL-adresse for flow](media/web-api/power-platform-admin-center-environment-URL.png "URL-adresse for flow")


Du kan også oprette et program for at hente listen over de forekomster, der er tilgængelige for dig, via metoden [Hent forekomster](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) i API'en til onlineadministration.

Hver anmodning til web-API'et skal have headerne `Accept` og `Content-type` angivet til `application/json`.

Udfyld til sidst headeren `Authorization` med et Azure AD-ihændehavertoken. Du kan [lære](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth), hvordan du får et Azure AD-ihændehavertoken for Common Data Service. Se f.eks. denne anmodning:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

Svaret indeholder en liste over flows fra dette miljø:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in Common Data Service.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Liste over flows

Som vist ovenfor kan du hente listen over arbejdsprocesser ved at kalde `GET` på `workflows`. Hver arbejdsproces har mange egenskaber, men de mest relevante er:

| Egenskabsnavn     | Beskrivelse                                              |
| ----------------- | -------------------------------------------------------- |
| kategori          | Kategorien for flowet. De forskellige typer er: 0 − klassiske arbejdsprocesser i Common Data Service, 1 − klassiske dialogbokse i Common Data Service, 2 − forretningsregler, 3 − klassiske handlinger i Common Data Service, 4 − flows for forretningsprocesser og 5 − automatiserede, øjeblikkelige eller planlagte flows. |
| statecode         | Status af flowet. Status kan være **0** − Fra eller **1** − Til.|
| workflowuniqueid  | Det entydige id for denne installation af flowet. |
| workflowid        | Det entydige id for et flow på tværs af alle importer. |
| createdon         | Den dato, hvor flowet blev oprettet. |
| _ownerid_value    | Det entydige id for den bruger eller det team, der ejer flowet. Dette er et id fra objektet systemusers i Common Data Service. |
| modifiedon        | Den sidste gang, flowet blev opdateret. |
| ismanaged         | Angiver, om flowet blev installeret via en administreret løsning. |
| name              | Det viste navn, du har givet flowet. |
| _modifiedby_value | Den sidste bruger, som opdaterede flowet. Dette er et id fra objektet systemusers i Common Data Service. |
| _createdby_value  | Den bruger, som oprettede flowet. Dette er et id fra objektet systemusers i Common Data Service. |
| type              | Angiver, om flowet er et kørende flow eller en skabelon, der kan bruges til at oprette yderligere flows. 1 − flow, 2 − aktivering eller 3 − skabelon. |
| beskrivelse       | Den brugerangivne beskrivelsen af flowet. |
| clientdata        | En strengkodet JSON af et objekt, der indeholder connectionReferences og definitionen af flowet. |

Du kan også anmode om bestemte egenskaber, filtrere listen over flows m.m., som beskrevet i [dokumentationen om Common Data Service API'er til oprettelse af forespørgsler om data](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api). Denne forespørgsel returnerer f.eks. kun de automatiserede, øjeblikkelige eller planlagte flows, der i øjeblikket er slået til:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Opret et forløb

Kald `POST` i samlingen `workflows` for at oprette et flow. De krævede egenskaber for automatiserede, øjeblikkelige og planlagte flows er: category, name, type, primaryentity og clientdata. Brug `none` som primaryentity for disse typer flows.

Du kan også angive description og statecode.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from Common Data Service.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.Power Apps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

Det vigtigste afsnit er `clientdata`, der indeholder de connectionReferences, som flowet bruger, og flowets [definition](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language). connectionReferences er tilknytningerne til hver forbindelse, som flowet bruger.

Der er tre egenskaber:

| Egenskabsnavn  | Beskrivelse                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Identificerer forbindelsen. Du kan se connectionName ved at gå til siden **Forbindelser** og derefter kopiere det fra forbindelsens URL-adresse. |
| kilde         | Enten `Embedded` eller `Invoker`. `Invoker` er kun gyldigt til øjeblikkelige flows, som er dem, hvor brugeren vælger en knap til at køre flowet, og angiver, at slutbrugeren leverer forbindelsen. I dette tilfælde bruges connectionName kun på designtidspunktet. Hvis forbindelsen er `Embedded`, betyder det, at det connectionName, du angiver, altid bruges. |
| id             | Identifikator for connectoren. Id'et starter altid med `/providers/Microsoft.PowerApps/apis/` og efterfølges derefter af navnet på connectoren, som du kan kopiere fra forbindelsens URL-adresse eller ved at vælge connectoren på siden **Connectorer**. |

Når du udfører anmodningen `POST`, modtager du headeren `OData-EntityId`, som indeholder `workflowid` for dit nye flow.

## <a name="update-a-flow"></a>Opdater et flow

Du kan kalde `PATCH` for arbejdsprocessen for at opdatere et flow eller slå det til eller fra. Brug egenskaben `workflowid` for at foretage disse kald. Du kan f.eks. opdatere beskrivelsen og ejeren af flowet ved hjælp af følgende kald:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> Formatet `odata.bind` bruges i syntaksen for ændring af ejeren. Det betyder, at du i stedet for at reparere feltet \_ownerid_value direkte, føjer du `@odata.bind` til navnet af egenskaben og derefter ombryder id'et med `systemusers()`.

I et andet eksempel kan du slå et flow til vha. dette kald:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Slet et flow

Slet et flow med et enkelt `DELETE`-kald:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Du kan ikke slette et flow, der er slået til. Du skal først slå flowet fra (se **Opdatering af et flow** tidligere). Ellers vises fejlen: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Se alle brugere, som et flow er delt med

Angivelse af brugerne med adgang til en *funktion* i Common Data Service. Denne funktion anvender en enkelt parameter af `Target`:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

Parameteren `Target` er en JSON-lignende streng, hvor en enkelt egenskab kaldes `@odata.id`. Erstat id'et for arbejdsprocessen i eksemplet ovenfor. Det returnerer:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Del eller annuller deling af et flow

Du kan dele et flow vha. handlingen `GrantAccess`.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

Parameteren `AccessMask` er et felt med følgende værdier for forskellige tilladelsesniveauer:

| Navn         | Beskrivelse                                          |
| ------------ | ---------------------------------------------------- |
| Intet         | Ingen adgang.                                           |
| Læseadgang   | Ret til at læse flowet.                          |
| WriteAccess  | Ret til at opdatere flowet.                        |
| DeleteAccess | Ret til at slette flowet.                        |
| ShareAccess  | Ret til at dele flowet.                         |
| AssignAccess | Ret til at ændre ejeren af flowet.           |

Du kan kombinere tilladelser ved hjælp af et komma. Angiv f.eks. både muligheden for at læse og opdatere et flow ved at skrive `ReadAccess,WriteAccess`.

Du kan *annullere deling* af et flow vha. handlingen `RevokeAccess`. Her er et eksempel:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

`RevokeAccess` fjerner alle tildelte tilladelser i `AccessMask`.

## <a name="export-flows"></a>Eksporter flows

Brug handlingen `ExportSolution` til at eksportere flows til en .zip-fil. Føj først de ønskede flows til en [løsning](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/).

Når flowet er i en løsning, kan du kalde følgende handling:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution` returnerer en grundlæggende 64-kodet streng i egenskaben `ExportSoutionFile`.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

Du kan derefter gemme denne fil i versionsstyring og/eller bruge en hvilken som helst version af administrations- eller distributionssystemet, du vil.

## <a name="import-flows"></a>Importer flows

Kald handlingen `ImportSolution` for at importere en løsning.

| Egenskabsnavn                    | Beskrivelse                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Hvis der findes forekomster af disse flows i Common Data Service, skal dette flag angives til `true` for at importere dem. Ellers overskrives de ikke. |
| PublishWorkflows                 | Angiver, om klassiske arbejdsprocesser i Common Data Service aktiveres ved import. Denne indstilling gælder ikke for andre typer af flows. |
| ImportJobId                      | Giver et nyt entydigt GUID, som kan bruges til at spore importjobbet. |
| CustomizationFile                | En grundlæggende 64-kodet zip-fil, der indeholder løsningen. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

Da importen er en længerevarende handling, vil svaret på handlingen ImportSolution være `204 No content`. Du kan spore status ved at kalde `GET` for objektet `importjobs`, hvor du angiver `ImportJobId`, som du inkluderede i den oprindelige `ImportSolution`-handling.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Dette kald returnerer status for importhandlingen, herunder `progress` (procentdelen af fuldførelsen), `startedon` og `completedon` (hvis importen er afsluttet).

Når importen er fuldført, skal du konfigurere forbindelserne til flowet, da `connectionNames` sandsynligvis vil være anderledes i destinationsmiljøet (hvis forbindelserne overhovedet findes). Hvis du konfigurerer nye forbindelser i destinationsmiljøet, skal ejeren af de forskellige flows oprette dem i Power Automate-designeren. Hvis forbindelserne allerede er konfigureret i det nye miljø, kan du udføre handlingen `PATCH` for flowets `clientData` og angive navnene på forbindelserne.
