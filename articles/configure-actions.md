---
title: Konfigurer handlinger for arbejdsprocesser i Power Apps | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- Power Apps
author: Mattp123
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9157159a263bb2b8be41445aebb478fc6aa2ddb3
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74360549"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Konfigurer brugerdefinerede handlinger fra en arbejdsproces
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Du kan aktivere en brugerdefineret handling fra en arbejdsproces uden at skrive kode. Flere oplysninger: [Aktivér brugerdefinerede handlinger fra en arbejdsproces](invoke-custom-actions-workflow-dialog.md).  
  
 Du kan også oprette en handling, så en udvikler kan bruge den i koden, eller hvis du skal redigere en handling, der tidligere er blevet defineret. På samme måde som ved arbejdsprocesser skal du overveje følgende:  
  
-   Hvad skal handlingen kunne gøre?  
  
-   Under hvilke betingelser skal handlingen udføres?  
  
 
I modsætning til arbejdsprocesser behøver du ikke at angive følgende indstillinger:  
  
- **Start, når**: Handlinger starter, når kode kalder den meddelelse, der er genereret for koden.  
  
- **Omfang**: Handlinger kører altid i konteksten af den kaldende bruger.  
  
- **Kør i baggrunden**: Handlinger er altid arbejdsprocesser i realtid.  
  
Handlinger har også noget, som arbejdsprocesser ikke har – input- og outputargumenter. Flere oplysninger: [Definer procesargumenter](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Opret en handling  
  
> [!IMPORTANT]
>  Hvis du opretter en handling, der skal medtages som en del af en løsning, der skal distribueres, kan du oprette den i konteksten af løsningen. Gå til **[Indstillinger](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **Løsninger**, og find den ikke-administrerede løsning, som denne handling skal være en del af. Vælg derefter **Ny** > **Proces** i menulinjen. Dette sikrer, at det tilpasningspræfiks, der er forbundet med navnet på handlingen, er konsistent med andre komponenter i løsningen. Når du har oprettet handlingen, kan du ikke ændre præfikset.  
  
 På samme måde som arbejdsprocesser har handlinger følgende egenskaber i dialogboksen **Opret proces**.  
  
 **Process Name**  
 Når du har angivet et navn til processen, oprettes et entydigt navn for processen ved at fjerne eventuelle mellemrum eller specialtegn i procesnavnet.  
  
 **Kategori**  
 Denne egenskab fastsætter, at dette er en handlingsproces. Du kan ikke ændre dette, når du har gemt processen.  
  
 **Enhed**  
 I forbindelse med handlingsprocesser kan du vælge et objekt til angivelse af kontekst for arbejdsprocessen på samme måde som andre typer processer, men du kan også vælge **None (global)** . Brug denne indstilling, hvis din handling ikke kræver konteksten for et bestemt objekt. Du kan ikke ændre dette, når du har gemt processen.  
  
 **Type**  
 Brug denne egenskab til at vælge, om du bygger en ny handling fra bunden eller starter fra en eksisterende skabelon.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Rediger en handling  
 Du skal deaktivere processer, før du kan redigere dem.  
  
 Du kan redigere en handling, der blev oprettet som en del af en ikke-administreret løsning, eller som er inkluderet i en løsning, der er installeret i din organisation. Hvis denne løsning er en administreret løsning, kan du muligvis ikke redigere den. Løsningsudgiveren har mulighed for at redigere de administrerede egenskaber, så den handling, der er installeret sammen med en administreret løsning, ikke kan redigeres.  
  
 Når en handling gemmes, genereres et entydigt navn baseret på navnet på processen. Dette entydige navn har det tilpasningspræfiks, der tilføjes af løsningsudgiveren. Dette er navnet på den meddelelse, som en udvikler bruger i sin kode.  
  
 Når du redigerer en handling, har du følgende muligheder:  
  
 **Procesnavn**  
 Når processen er oprettet, og det entydige navn er genereret ud fra procesnavnet, kan du redigere procesnavnet. Du kan anvende en navngivningskonvention for at gøre det nemmere at finde bestemte processer.  
  
 **Entydigt navn**  
 Når en handling gemmes, genereres et entydigt navn baseret på navnet på processen. Dette entydige navn har det tilpasningspræfiks, der tilføjes af løsningsudgiveren. Dette er navnet på den meddelelse, som en udvikler bruger i sin kode. Du skal ikke ændre dette entydige navn, hvis processen er blevet aktiveret, og der er kode, der forventer at kalde handlingen ved hjælp af dette navn.  
  
> [!IMPORTANT]
>  Når handlingen er aktiveret, og kode er udviklet til at bruge et entydigt navn, må det entydige navn ikke ændres uden også at ændre den kode, der refererer til det entydige navn.  
  
 **Aktivér annullering af opdatering**  
 Generelt vil processer, der understøtter transaktioner, "fortryde" (eller annullere) hele handlingen, hvis en del af processerne mislykkes. Der er dog visse undtagelser til dette. Nogle af de handlinger, som udviklere skriver i kode, der igangsættes af handlingen, understøtter muligvis ikke transaktioner. Hvis koden for eksempel udfører handlinger i andre systemer, der er uden for transaktionens rammer. De kan ikke fortrydes af den handling, der kører i en app. Nogle meddelelser i platformen understøtter ikke transaktioner. Men alt, hvad du kan foretage dig i brugergrænsefladen for handlingen, understøtter transaktioner. Alle de handlinger, der er en del af en arbejdsproces i realtid, opfattes som værende i transaktionen, men med handlinger har du mulighed for at fravælge dette.  
  
 Du bør kontakte den udvikler, der skal bruge denne meddelelse, for at bestemme, om den skal være i transaktionen eller ej. En handling skal normalt være i transaktionen, hvis de handlinger, der udføres af forretningsprocessen, ikke giver mening, medmindre de alle fuldføres. Det klassiske eksempel er overførsel af midler mellem to bankkonti. Hvis du hæver penge fra én konto, skal du sætte dem ind på en anden. Hvis den ene mislykkes, mislykkes begge.  
  
> [!NOTE]
>  Du kan ikke aktivere annullering, hvis en brugerdefineret handling kaldes direkte fra en arbejdsproces. Du kan aktivere annullering, hvis en handling udløses af en webtjenestemeddelelse i Power Apps.  
  
 **Aktivér som**  
 Som alle andre processer kan du aktivere processen som en skabelon og bruge den som et avanceret startpunkt for processer, der følger et ens mønster.  
  
 **Definer procesargumenter**  
 I dette område skal du angive alle de data, som handlingen forventes at starte, og hvilke data der udelades af handlingen. Flere oplysninger: [Definer procesargumenter](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Tilføj faser, betingelser og handlinger**  
 Som med andre processer angiver du, hvilke handlinger der skal udføres, og hvornår de skal udføres. Flere oplysninger: [Tilføj faser, betingelser og handlinger](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Definer procesargumenter  
 Når en udvikler bruger en meddelelse, begynder vedkommende muligvis med nogle data, som de kan medtage i meddelelsen. Hvis du f.eks. vil oprette en ny sagspost, er det muligvis sagstitelværdien, der medtages som et inputargument.  
  
 Når meddelelsen er færdig, skal udvikleren muligvis overføre nogle data, der blev ændret eller genereret af meddelelsen, til en anden handling i deres kode. Disse data er outputargumentet.  
  
 Både input- og outputargumenter skal have et navn, en type, og nogle oplysninger, f.eks. om argumentet altid er påkrævet. Du kan også angive en beskrivelse.  
  
 Navnet på meddelelsen og oplysningerne om alle procesargumenterne repræsenterer meddelelsens "signatur". Når en handling er aktiveret og bruges i kode, må signaturen ikke ændres. Hvis denne signatur ændres, mislykkes den kode, der bruger meddelelsen. Den eneste undtagelse til dette er ved at ændre en af parametrene, så det ikke er altid påkrævet.  
  
 Du kan ændre rækkefølgen af argumenterne ved at sortere dem eller flytte dem op eller ned, da argumenterne er identificeret efter navn og ikke i rækkefølge. Kode, der bruger meddelelsen, ødelægges heller ikke, når du ændrer beskrivelsen.  
  
#### <a name="action-process-argument-types"></a>Argumenttyper for handlingsprocesser  
 I nedenstående tabel beskrives argumenttyperne for handlingsprocesser.  
  
|Type|Beskrivelse|  
|----------|-----------------|  
|Boolesk|En `true` eller `false` værdi.|  
|DateTime|En værdi, der gemmer oplysninger om dato og klokkeslæt.|  
|Decimal|En talværdi med decimalpræcision. Bruges, når præcision er yderst vigtigt.|  
|Entity|En post for det angivne objekt. Når du vælger Entity, aktiveres rullelisten, og du kan vælge objekttypen.|  
|EntityCollection|En samling af objektets poster.|  
|EntityReference|Et objekt, der indeholder navnet, id'et og typen for en objektpost, som entydigt identificerer posten. Når du vælger EntityReference, aktiveres rullelisten, og du kan vælge objekttypen.|  
|Float|En talværdi med decimalpræcision. Bruges, når data kommer fra en måling, der ikke er helt præcis.|  
|Integer|Et helt tal.|  
|Money|En værdi, der gemmer data om en vis mængde penge.|  
|Picklist|En værdi, der repræsenterer en indstilling for attributten OptionSet.|  
|String|En tekstværdi.|  
  
> [!NOTE]
> **EntityCollection**-argumentværdier kan ikke angives i brugergrænsefladen for betingelser eller handlinger. Disse angives til brug af udviklere i brugerdefineret kode. Flere oplysninger: [Opret dine egne handlinger](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Tilføj faser og trin  
 Handlinger er en type processer, der er meget lig arbejdsprocesser i realtid. Alle de trin, der kan bruges i arbejdsprocesser i realtid, kan bruges i handlinger. Du kan finde oplysninger om de trin, der kan bruges til både arbejdsprocesser i realtid og handlinger, i [Arbejdsprocesfaser og -trin](configure-workflow-steps.md).  
  
 Ud over de trin, som kan bruges til arbejdsprocesser i realtid, har handlinger også trinnet **Tildel værdi**.  I handlinger kan disse kun bruges til at angive outputargumenter. Du kan bruge formularassistenten til at angive outputargumenter til specifikke værdier eller, mere sandsynligt, til værdier fra den post, som handlingen kører imod, poster, der er relateret til den pågældende post med en mange til én-relation, poster, der er oprettet i et tidligere trin, eller værdier, der er en del af selve processen.  
  
## <a name="next-steps"></a>Næste trin  
 [Handlinger](actions.md)  

 [Aktivér brugerdefinerede handlinger fra en arbejdsproces](invoke-custom-actions-workflow-dialog.md)   
 [Overvågning af arbejdsprocesser i realtid og handlinger](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
