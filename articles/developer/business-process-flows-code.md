---
title: Arbejd med forretningsprocesforløb ved hjælp af kode | MicrosoftDocs
description: Få mere at vide om, hvordan du arbejder programmatisk med forretningsprocesforløb for at oprette mere effektive og strømlinede forretningsprocesser.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: d65be1552c3e748e4910c4fb942a60322f6f1e19
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296565"
---
# <a name="work-with-business-process-flows-using-code"></a>Arbejd med forretningsprocesflows ved hjælp af kode
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Med et *forretningsprocesforløb* kan du oprette mere effektive og strømlinede salgs- og serviceprocesser samt andre forretningsprocesser. Der oprettes en visualisering af din forretningsproces ved at placere specielle kontrolelementer øverst i objektformularerne. Brugere bliver ført gennem forskellige faser af salgs-, marketing- og serviceprocesser hen mod afslutning. Hver proces understøtter flere faser og trin. Du kan tilføje eller fjerne trin, ændre rækkefølgen af trin eller føje nye objekter til forretningsprocesforløbet.  
  
Forskellige forekomster af forretningsprocesforløb kan køre samtidigt i den samme objektpost. Brugerne kan skifte mellem samtidige forretningsprocesforekomster og genoptage deres arbejde i en aktuel fase i processen. 

Dette emne indeholder oplysninger om, hvordan du programmeringsmæssigt kan arbejde med forretningsprocesforløb.

> [!NOTE]
> Du behøver ikke at skrive kode for at arbejde med forretningsprocesforløb. Du kan få flere oplysninger om brug af brugergrænsefladen til at oprette og administrere forretningsprocesforløb under [Oversigt over forretningsprocesforløb](../business-process-flows-overview.md).  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Forudsætninger for forretningsprocesforløb 

Brugerdefinerede poster og poster med opdaterede brugergrænsefladeformularer kan indgå i et forretningsprocesforløb. De opdaterede brugergrænsefladeobjekter har egenskaben <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> indstillet til `true`. 

Hvis du vil aktivere et objekt for forretningsprocesforløbet, skal du indstille egenskaben <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> til `true`.

> [!IMPORTANT]
>  Aktivering af et objekt for forretningsprocesforløb er en envejsproces. Du kan ikke tilbageføre den.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definer forretningsprocesforløb
  
Du kan bruge den visuelle designer til forretningsprocesforløb til at definere et forretningsprocesforløb. Flere oplysninger: [Opret et forretningsprocesforløb](../create-business-process-flow.md)

Forretningsprocesforløb oprettes som standard i tilstanden `Draft`.  

Et forretningsprocesforløb gemmes i objektet <xref:Microsoft.Dynamics.CRM.workflow>, og faseoplysningerne om forretningsprocesforløbet gemmes i objektet <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Aktivér forretningsprocesforløb  
 Før du kan bruge procesforløbet, skal det aktiveres. Du skal have rettigheden `prvActivateBusinessProcessFlow` for objektet `Workflow` for at aktivere forløbet. Brug meddelelsen <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> til at angive tilstanden for objektposten `Workflow` til `Activated`. Flere oplysninger: [Udfør specialiserede handlinger ved hjælp af Opdater](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > Du kan også bruge den visuelle designer til forretningsprocesforløb til at aktivere et forretningsprocesforløb. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Objekt i forretningsprocesforløb 
 Når du aktiverer en definition af et forretningsprocesforløb ved at ændre tilstanden for den tilsvarende objektpost `Workflow` eller ved hjælp af designeren til forretningsprocesforløb, oprettes et brugerdefineret objekt med følgende navn automatisk for at gemme forekomster af det aktiverede forretningsprocesforløb: "*\<activesolutionprefix >*_*\<uniquename >*", hvor uniquename er afledt af det navn, du angiver.  
  
 Hvis du f.eks. angav "My Custom BPF" som navn på definitionen af forretningsprocesforløbet og bruger standardudgiveren (new) til din aktive løsning, bliver navnet på det brugerdefinerede objekt, der oprettes til lagring af procesforekomster, "new_mycustombpf".  
  
 Hvis værdien `uniquename` ikke er tilgængelig for en definition af et forretningsprocesforløb, hvis forretningsprocesforløbet f.eks. blev importeret som en del af en løsning fra en tidligere version, bliver standardnavnet på det brugerdefinerede objekt "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  Posterne i eksemplet på et forretningsprocesforløb bruger systemobjekter til at lagre de tilsvarende poster for forekomsten af forretningsprocesforløbet.  
>   
>  De nye definitioner for forretningsprocesforløb, som du opretter, vil dog bruge brugerdefinerede objekter til at lagre deres forekomstposter, som forklaret tidligere. 

Du kan hente navnet på objektet for forretningsprocesforløbet på en af følgende måder:

- **Ved hjælp af brugergrænsefladen**: Brug tilpasningsbrugergrænsefladen til at gå til forretningsprocesforløbsobjektet:

    ![](media/bpf-entity-name.png)
- **Ved hjælp af Web-API'EN**: Brug følgende anmodning:

    **Anmodning**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Response**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **Ved hjælp af organisationstjenesten**: Brug følgende kodeeksempel:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity>-egenskaben er `true` til objekter for forretningsprocesflowet. Du kan hente alle objekter for forretningsprocesflowet i din instans ved at køre følgende Web-API-anmodning:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Administrer sikkerhed for forretningsprocesflowet

Det brugerdefinerede objekt, der oprettes automatisk under aktivering af en forretningsprocesforløb for at gemme forekomster af forretningsprocesforløb, overholder standardsikkerhedsmodellen for alle andre brugerdefinerede objekter i Common Data Service. Det betyder, at rettigheder, der er tildelt på disse objekter definerer runtime-tilladelserne for brugerne til forretningsprocesforløb.

Det brugerdefinerede objekt i forretningsprocesforløbet har organisationsomfang. De almindelige tilladelser til oprettelse, hentning, opdatering og sletning for denne enhed definerer den tilladelse, som brugere har baseret på deres tildelte roller. Når det brugerdefinerede objekt for forretningsprocesflowet er oprettet, er det som standard kun sikkerhedsrollerne **Systemadministrator** og **Systemtilpasser**, der tildeles adgang til det, og du skal udtrykkeligt give tilladelser til det nye objekt for forretningsprocesflowet (f.eks. **My Custom BPF**) for andre sikkerhedsroller efter behov.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Opret, hent, opdater og slet poster for objekter for forretningsprocesflowet (procesforekomster)  
 Det brugerdefinerede objekt, der automatisk oprettes under aktivering af en definition af forretningsprocesflowet, gemmer alle procesforekomsterne for definitionen af forretningsprocesflowet. Det brugerdefinerede objekt understøtter den programmeringsmæssige standardoprettelse og -administration af poster (procesforekomster) ved hjælp af Web-API og CRM 2011-slutpunktet.

> [!IMPORTANT]
> Skift til en anden procesforekomst for en objektpost understøttes kun via brugergrænsefladen (klient) eller programmeringsmæssigt ved hjælp af oplysninger, der er tilgængelige i dette afsnit. Du kan ikke længere bruge `SetProcess`-meddelelsen (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> eller <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) til at skifte processer ved hjælp af programmering (angiv et andet forretningsprocesflow som den aktive procesforekomst) for destinationsobjektposten. 

 Lad os se nærmere på følgende eksempel, hvor vi har et forretningsprocesflow på tværs af objekter, "My Custom BPF", med 3 faser: S1:Account, S2:Account og S3:Contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Hent alle poster (instanser) for et objekt for et forretningsprocesflow
 Hvis navnet på dit objekt for forretningsprocesflowet er "new_mycustombpf", kan du bruge følgende forespørgsel til at hente alle poster (procesforekomster) for dit objekt for forretningsprocesflowet:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

På dette tidspunkt får du måske ikke nogen forekomster i dit svar, fordi der ikke er nogen. Du kan køre denne anmodning, når du har oprettet en forekomst for definitionen af dit forretningsprocesforløb senere i dette emne.

> [!NOTE]
> Du kan få flere oplysninger om, hvordan du henter navnet på forretningsprocesforløbsobjektet i det tidligere afsnit [Objekt i forretningsprocesforløb](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Opret en objektpost for et forretningsprocesforløb (procesforekomst) 

Opret en objektpost for et forretningsprocesforløb (procesforekomst) programmatisk, hvis du vil skifte til et andet forretningsprocesforløb for en objektpost uden at benytte brugergrænsefladen. 

Du opretter en objektpost for et forretningsprocesforløb ved at angive følgende værdier: 
- Knyt objektposten for forretningsprocesforløbet til en primær objektpost ved at angive navigationsegenskaben med én værdi ved hjælp af anmærkningen `@odata.bind`. Du finder det navigationsegenskabsnavn, der peger på den primære objektpost for dit forretningsprocesforløb, ved at bruge [CSDL $metadata document](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Knyt objektposten for forretningsprocesforløbet til en gyldig fase i definitionen af forretningsprocesforløbet ved at angive navigationsegenskaben med én værdi ved hjælp af anmærkningen `@odata.bind`. Du finder det navigationsegenskabsnavn (typisk `activestageid`), der peger på faseposten i definitionen af forretningsprocesforløbet, ved at bruge [CSDL $metadata document](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Du kan også hente oplysninger om alle faserne for en definition af et forretningsprocesforløb ved at bruge følgende Web-API-anmodning, hvor det forudsættes, at id'et for definitionen af dit forretningsprocesforløb er 2669927e-8ad6-4f95-8a9a-f1008af6956f:

    **Anmodning**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Response**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

Derefter skal du bruge følgende anmodning til at oprette en forekomst for definitionen af dit forretningsprocesforløb for en kontopost (ID = a176be9e-9a68-e711-80e7-00155d41e206) og den aktive fase angivet som den første fase i procesforekomsten, F1 (ID = 9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Anmodning**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Response**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Bemærk, at hvis du vil oprette en forekomst for definitionen af forretningsprocesforløbet med den aktive fase angivet som en ***anden*** fase end den første fase, skal du også angive `traversedpath` i din anmodning. Den gennemgåede sti er den kommaseparerede tekststreng for procesfase-id'er, der repræsenterer besøgte faser i forekomsten af forretningsprocesforløbet. Følgende anmodning opretter en forekomst for enkontopost (ID= 679b2464-71b5-e711-80f5-00155d513100) og aktiv faseangivet som anden fase, F2 (ID= 19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Opdater en objektpost for et forretningsprocesforløb (procesforekomst)

Du kan opdatere en procesforekomst for at flytte til næste eller forrige fase, afbryde en forekomst af processen, genaktivere en procesforekomst eller afslutte en procesforekomst. 

#### <a name="stage-navigation"></a>Fasenavigation

Du går til en anden fase ved at opdatere en procesforekomstpost for at ændre dets aktive fase-id i overensstemmelse med den gennemgåede sti. Bemærk, at du kun skal flytte til næste eller forrige fase under opdatering af en forekomst af et forretningsprocesforløb.

Hvis du vil navigere i faser, skal du bruge id'et for forekomsten af det forretningsprocesforløb, som du vil opdatere. Du kan få oplysninger om hentning af alle forekomster af dit forretningsprocesforløb i [Hent alle poster (forekomster) for et objekt i et forretningsprocesforløb](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) tidligere.

Hvis vi antager, at id'et for den procesforekomst, du vil opdatere, er dc2ab599-306d-e811-80ff-00155d513100, skal du bruge følgende anmodning for at opdatere den aktive fase fra F1 til F2:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Skift tilstand for en procesforekomst: Afbryd, genaktiver eller afslut 

En procesforekomst kan have en af følgende tilstande: **Aktiv**, **Afsluttet** eller **Afbrudt**. Tilstanden bestemmes af følgende attributter for procesforekomstposten:

- **statecode**: Viser statussen for procesforekomsten.

    |Værdi|Etiket|
    |-----|-----|
    |0    |Aktiv|
    |0    |Inaktiv|

- **statuscode**: Viser oplysninger om status for procesforekomsten.

    |Værdi|Etiket|
    |-----|-----|
    |0    |Aktiv|
    |2    |Udført|
    |3    |Afbrudt|

Hvis du vil **afbryde** en procesforekomst, skal du bruge følgende anmodning, og angive værdierne `statecode` og `statuscode` korrekt:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> Du kan afbryde en procesforekomst i alle faser.

På samme måde skal du for at genaktivere en procesforekomst erstatte værdierne `statecode` og `statuscode` med henholdsvis **0** og **1**.

Hvis du vil angive en procesforekomst' status som **Afsluttet**, hvilket kun er muligt i den sidste fase af en procesforekomst, skal du erstatte værdierne `statecode` og `statuscode` i ovenstående kode med henholdsvis **0** og **2**.

#### <a name="cross-entity-navigation"></a>Navigation på tværs af objekter

Hvis du vil navigere på tværs af objekter i dette eksempel, skal du angive den aktive fase for procesforekomsten til den sidste fase, F3 (ID = a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a) ved at opdatere den gennemgåede stien i overensstemmelse hermed og angive en kontaktpost som den primære objektpost i henhold til definitionen af forretningsprocesforløbet.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Slet en objektpost for et forretningsprocesforløb (procesforekomst)

Brug følgende Web-API-anmodning:

**Anmodning**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Response**

Hvis posten findes, får du et normalt svar med status 204 for at angive, at sletningen blev fuldført. Hvis objektet ikke findes, får du et svar med status 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Brug meddelelserne RetrieveProcessInstances og RetrieveActivePath

Brug meddelelsen `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> eller <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) til at hente alle forekomster af et forretningsprocesforløb for en objektpost på tværs af alle forretningsprocesdefinitioner. Forekomsterne i forretningsprocesforløbet, som er returneret for et objekt, bestilles ud fra attributten `modifiedon` for forekomsten. Den senest ændrede forekomst af forretningsprocesforløb er f.eks. den *første* post i den returnerede samling. Den senest ændrede forekomst af forretningsprocesforløbet er den, der er aktiv i brugergrænsefladen for en objektpost.  
  
Hver forekomstpost i et forretningsprocesforløb, der returneres for en objektpost som følge af brugen af meddelelsen `RetrieveProcessInstances`, gemmer id'et for den aktive fase i attributten `processstageid`, der kan bruges til at finde den aktive fase og derefter flytte til den forrige eller næste fase. Det gør du ved først at finde den aktive sti til en forekomst af et forretningsprocesforløb og de faser, der er tilgængelige i forekomsten af forretningsprocesforløbet, ved hjælp af meddelelsen `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> eller <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Når du har oplysninger om den aktive fase og den aktive sti for et forretningsprocesforløb, kan du bruge oplysningerne til at gå til den forrige eller næste fase på den aktive sti. Hvis du går fremad i faserne, skal det ske i sekvenser, dvs. du kan kun gå videre til den næste fase på den aktive sti.   
  
 Du kan få vist hele kodeeksemplet med brugen af disse to metoder og fasenavigation ved hjælp af [Organization Service](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata) i [Eksempel: Arbejd med forretningsprocesforløb](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Anvend forretningsprocesforløb under oprettelse af en objektpost

Dette afsnit indeholder oplysninger om standardfunktionsmåden for automatisk anvendelse af forretningsprocesforløb på nye objektposter, der er oprettet i Common Data Service, og hvordan du kan tilsidesætte det for at anvende et forretningsprocesforløb efter eget valg på nye objektposter.

For et objekt, hvor der er defineret flere forretningsprocesforløb, anvender systemet som standard et forretningsprocesforløb til det nye objekt ved hjælp af følgende logik i flere trin:
1. Identificer alle forretningsprocesforløb, der gælder for den nye objektpost, på baggrund af attributten **Workflow.PrimaryEntity** i posterne for definitionen af forretningsprocesforløbet.
2. Identificer de definitioner for forretningsprocesforløbet, som den aktuelle bruger har adgang til. Du kan finde oplysninger om, hvordan adgang til et forretningsprocesforløb fastsættes og styres, i [Administrer sikkerhed for forretningsprocesforløb](#BPFSecurity) tidligere i dette emne.<br/>  
3. Alle definitioner af forretningsprocesforløb i systemet er underlagt en global rækkefølge pr. objekt. Rækkefølgen af forretningsprocesforløbet er gemt i attributten **Workflow.ProcessOrder**. Definitionerne af et forretningsprocesforløb for et objekt er sorteret på baggrund af denne rækkefølge, og det objekt med den mindste værdi i rækkefølgen er valgt.
4. Hvis objektposten er oprettet ud fra en forretningsapp (appmodul), anvendes til sidst et eller flere filtreringsniveauer for at vælge det forretningsprocesforløb, der skal anvendes automatisk på den nye objektpost.Når brugerne arbejder i en app, kan de kun få adgang til relevante objekter, forretningsprocesforløb, visninger og formularer, som de har adgang til i henhold til de sikkerhedsroller, der er tildelt til forretningsappen. 
    - Hvis forretningsappen ikke indeholder noget forretningsprocesforløb, anvendes forretningsprocesforløbet som forklaret indtil trin 3.
    - Hvis forretningsappen har et eller flere forretningsprocesforløb, gælder kun de forretningsprocesforløb, der findes i appen. Når brugeren arbejder i en forretningsappkontekst, filtreres listen over forretningsprocesforløb fra trin 3 i dette er tilfælde yderligere med dem, der indgår i den forretningsapp, der allerede findes i appmodulet, og sorteres i procesrækkefølgen. 
    - Hvis der ikke er nogen forretningsprocesforløb i et virksomhedsprogram for objektet eller et, som brugeren har adgang til, anvendes der ikke noget forretningsprocesforløb for den nye objektpost.

Du kan tilsidesætte, at standardlogikken for forretningsprocesforløb anvendes automatisk til nye objektposter. Det gør du ved at angive attributten **ProcessId** for objektet til en af følgende værdier, mens du opretter en ny objektpost:
- Angiv **Guid.Empty** til at springe et forretningsprocesforløb over for nye objektposter. Det kan være en god ide, hvis du masseopretter objektposter, men ikke vil have, at der anvendes forretningsprocesforløb for dem.
- Angiv den til et specifikt objekt for et forretningsprocesforløb (som en objektreference). I dette tilfælde anvender systemet det angivne forretningsprocesforløb i stedet for standardlogik.

Hvis du ikke angiver en værdi for attributten **ProcessId**, mens du opretter en ny objektpost, anvender systemet standardlogikken, som forklaret tidligere.

> [!NOTE]
> Tilsidesættelse af, at standardlogikken for forretningsprocesforløb anvendes automatisk til nye objektposter, understøttes kun programmatisk. Du kan ikke gøre dette ved hjælp af brugergrænsefladen.

## <a name="legacy-process-related-attributes-in-entities"></a>Ældre procesrelaterede attributter i objekter

De ældre procesrelaterede attributter (f.eks **ProcessId**, **StageId** og **TraversedPath**) for objekter, der er aktiveret for forretningsprocesforløb, frarådes allerede. Manipulation af disse ældre procesrelaterede attributter for målobjektposter garanterer ikke overensstemmelse med tilstanden for forretningsprocesforløbet, og er ***ikke*** et understøttet scenarie. Den anbefalede måde er at bruge attributterne for forretningsprocesforløbet som beskrevet tidligere i afsnittet [Opret, hent, opdater og slet objektposter i forretningsprocesforløb (procesforekomster)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances)

Den eneste undtagelse til dette er ved at ændre attributten **ProcessId** programmatisk, samtidig med at du opretter en objektpost til at tilsidesætte standardanvendelsen af forretningsprocesforløbet til den nye post, som forklaret i det forrige afsnit : [Anvend forretningsprocesforløb, mens du opretter en objektpost](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Understøttelse på klientsiden af programmering til forretningsprocesforløb  
 Der er et objekt på klientsiden, som du kan bruge til at interagere med forretningsprocesforløb i formularscripts. Forretningsprocesforløb udløser hændelser på klientsiden, hver gang der enten anvendes en proces til en post, fasen ændres, eller dens status ændres til `Active`, `Finished` eller `Aborted`. Flere oplysninger: [formContext.data.process (klient-API-reference)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Det maksimale antal processer, faser og trin  
 Standardværdien for det maksimale antal aktiverede forretningsprocesforløb er 10 pr. objekt. Du kan angive en anden værdi ved hjælp af `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`-attributten. Hvis værdien imidlertid er større end 10, vil systemets ydeevnen måske blive forringet, når du skifter processer eller åbner en post, der har et tildelt forretningsprocesforløb. Det kan være særlig mærkbart, hvis processerne strækker sig over flere objekter.  
  
 Følgende indstillinger kan ikke tilpasses:  
  
-   Det maksimale antal faser pr. objekt i processen er 30.  
  
-   Det maksimale antal trin i hver fase er 30.  
  
-   Det maksimale antal objekter, der kan deltage i procesforløbet, er 5.  

