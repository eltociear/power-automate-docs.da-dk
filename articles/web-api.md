---
title: Flow gemmes nu i Common Data Service og bruger den omfattende web-API
description: Flow gemmes nu i Common Data Service og bruger den omfattende web-API.
author: stepsic-microsoft-com
ms.reviewer: deonhe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: stepsic
audience: Power user
ms.openlocfilehash: 7cce365213f22854b8a3b97808ad7172c3af3409
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74369680"
---
# <a name="power-automate-web-api"></a>Power Automate-web-API
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Fremover gemmes alle flow i Common Data Service og gør brug af [den omfattende web-API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api).

Dette indhold dækker administrationen af flow, som er inkluderet under fanen **Løsninger** i Power Automate. I øjeblikket understøtter disse API'er ikke flow under **Mine flow**.

## <a name="compose-http-requests"></a>Udarbejd HTTP-anmodninger

Du skal starte med at skabe URL-adressen for at komme i gang med at oprette anmodninger. Formatet af den grundlæggende URL-adresse til web-API'en til Power Automate er: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. De to parametre er:

- **Organisations-id'et** er et entydigt navn på det miljø, der gemmer dine flows. Du kan se organisations-id'et i miljøskifteren øverst til højre i Power Automate. Bemærk, at **organisations-id'et** adskiller sig fra **miljø-id'et**, som er det GUID, der vises i flowets URL-adresse.

     ![Miljøskifter](media/web-api/get-organization-id.png "Miljøskifter")

- **Underdomænet for området** afhænger af placeringen af dit miljø. Når du logger på Power Automate, kan du se området for dit miljø i websidens URL-adresse. Brug dét områdenavn til at finde det respektive underdomæne i følgende tabel:

     ![URL-adresse til Flow](media/web-api/get-region-name.png "URL-adresse til Flow")

     | Område         | Underdomæne   |
     | -------------- | ----------- |
     | USA  | crm         |
     | Sydamerika  | crm2        |
     | Canada         | crm3        |
     | Europa         | crm4        |
     | Asien og Stillehavsområdet   | crm5        |
     | Australien      | crm6        |
     | Japan          | crm7        |
     | Indien          | crm8        |
     | US Government  | crm9        |
     | Storbritannien | crm11       |

Du kan også hente listen over forekomster, der er tilgængelige for dig, programmatisk via metoden [Hent forekomster](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) i API'en til Online Management.

Hver anmodning til web-API'en skal have headerne `Accept` og `Content-type` angivet til `application/json`.

Udfyld til sidst headeren `Authorization` med et Azure AD-ihændehavertoken. [Få mere at vide om](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth), hvordan du får et Azure AD-ihændehavertoken til Common Data Service. Se f.eks. denne anmodning:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

Svaret indeholder en liste over flow fra dette miljø:

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

## <a name="list-flows"></a>Liste over flow

Som vist ovenfor kan du hente listen over arbejdsprocesser ved at kalde `GET` på `workflows`. Hver arbejdsproces har mange egenskaber, men de mest relevante er:

| Navn på egenskab     | Beskrivelse                                              |
| ----------------- | -------------------------------------------------------- |
| category          | Kategorien for flowet. De forskellige typer er: 0 − klassiske arbejdsprocesser i Common Data Service, 1 − klassiske dialogbokse i Common Data Service, 2 − forretningsregler, 3 − klassiske handlinger i Common Data Service, 4 − forretningsprocesforløb og 5 − automatiserede, øjeblikkelige eller planlagte flow. |
| statecode         | Statussen for flowet. Statussen kan være **0** − Fra eller **1** − Til.|
| workflowuniqueid  | Det entydige id for denne installation af flowet. |
| workflowid        | Det entydige id for et flow på tværs af alle importer. |
| createdon         | Den dato, hvor flowet blev oprettet. |
| _ownerid_value    | Det entydige id for den bruger eller det team, der ejer flowet. Dette er et id fra objektet systemusers i Common Data Service. |
| modifiedon        | Den sidste gang, flowet blev opdateret. |
| ismanaged         | Angiver, om flowet blev installeret via en administreret løsning. |
| name              | Det viste navn, du har givet flowet. |
| _modifiedby_value | Den sidste bruger, som opdaterede flowet. Dette er et id fra objektet systemusers i Common Data Service. |
| _createdby_value  | Den bruger, som oprettede flowet. Dette er et id fra objektet systemusers i Common Data Service. |
| type              | Angiver, om flowet er et kørende flow eller en skabelon, der kan bruges til at oprette yderligere flow. 1 − flow, 2 − aktivering eller 3 − skabelon. |
| beskrivelse       | Den brugerangivne beskrivelsen af flowet. |
| clientdata        | En strengkodet JSON af et objekt, der indeholder connectionReferences og definitionen af flowet. |

Du kan også anmode om bestemte egenskaber, filtrere listen over flow m.m., som beskrevet i [dokumentationen for forespørgsel om data i API til Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api). Denne forespørgsel returnerer f.eks. kun de automatiserede, øjeblikkelige eller planlagte flow, der i øjeblikket er på:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Opret et flow

Kald `POST` i samlingen `workflows` for at oprette et flow. De krævede egenskaber for automatiserede, øjeblikkelige og planlagte flow er: category, name, type, primaryentity og clientdata. Brug `none` som primaryentity for disse typer flow.

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

| Navn på egenskab  | Beskrivelse                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Identificerer forbindelsen. Du kan se connectionName ved at gå til siden **Forbindelser** og derefter kopiere det fra forbindelsens URL-adresse. |
| source         | Enten `Embedded` eller `Invoker`. `Invoker` er kun gyldig til øjeblikkelige flow, som er dem, hvor brugeren vælger en knap til at køre flowet, og angiver, at slutbrugeren leverer forbindelsen. I dette tilfælde bruges connectionName kun på designtidspunktet. Hvis forbindelsen er `Embedded`, betyder det, at det connectionName, du angiver, altid bruges. |
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
> Formatet `odata.bind` bruges i syntaksen for ændring af ejeren. Det betyder, at du i stedet for at reparere \_ownerid_value field directly, føjer `@odata.bind` til navnet på egenskaben og derefter ombryder id'et med `systemusers()`.

I et andet eksempel kan du slå et flow til ved hjælp af dette kald:

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

Slet et flow med et enkelt kald af typen `DELETE`:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Du kan ikke slette et flow, der er slået til. Du skal først slå flowet fra (se **Opdatering af et flow** tidligere). Ellers får du vist fejlen: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Se alle brugere, som et flow er delt med

Til angivelse af en liste over brugere med adgang bruges en *funktion* i Common Data Service. Denne funktion anvender en enkelt parameter af `Target`:

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

Du kan dele et flow ved hjælp af handlingen `GrantAccess`.

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
| None         | Ingen adgang                                           |
| ReadAccess   | Ret til at læse flowet.                          |
| WriteAccess  | Ret til at opdatere flowet.                        |
| DeleteAccess | Ret til at slette flowet.                        |
| ShareAccess  | Ret til at dele flowet.                         |
| AssignAccess | Ret til at ændre ejeren af flowet.           |

Du kan kombinere tilladelser ved hjælp af et komma. Angiv f.eks. både muligheden for at læse og opdatere et flow ved at skrive `ReadAccess,WriteAccess`.

Du kan *annullere deling* af et flow ved hjælp af handlingen `RevokeAccess`. Her er et eksempel:

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

## <a name="export-flows"></a>Eksportér flow

Brug handlingen `ExportSolution` til at eksportere flow til en .zip-fil. Føj først de ønskede flow til en [løsning](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/).

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

## <a name="import-flows"></a>Importér flow

Kald handlingen `ImportSolution` for at importere en løsning.

| Navn på egenskab                    | Beskrivelse                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Hvis der er eksisterende forekomster af disse flow i Common Data Service, skal dette flag angives til `true` for at importere dem. Ellers overskrives de ikke. |
| PublishWorkflows                 | Angiver, om klassiske arbejdsprocesser i Common Data Service aktiveres ved import. Denne indstilling gælder ikke for andre typer af flow. |
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

Da importen er en længerevarende handling, vil svaret på handlingen ImportSolution være `204 No content`. For at spore statussen skal du kalde `GET` for objektet `importjobs`, hvor du angiver `ImportJobId`, som du inkluderede i den oprindelige `ImportSolution`-handling.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Dette kald returnerer statussen for importhandlingen, herunder `progress` (procentdelen af fuldførelsen), `startedon` og `completedon` (hvis importen er afsluttet).

Når importen er fuldført, skal du konfigurere forbindelserne til flowet, da `connectionNames` sandsynligvis vil være anderledes i destinationsmiljøet (hvis forbindelserne overhovedet findes). Hvis du konfigurerer nye forbindelser i destinationsmiljøet, skal ejeren af de forskellige flow oprette dem i Power Automate-designeren. Hvis forbindelserne allerede er konfigureret i det nye miljø, kan du udføre handlingen `PATCH` for flowets `clientData` og angive navnene på forbindelserne.
