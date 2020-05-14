---
title: Konfigurere handlinger for arbejdsprocesser i Power Apps | MicrosoftDocs
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
ms.openlocfilehash: cba86e3e10591bb5e1ac36a68840ff7954146329
ms.sourcegitcommit: d336e5ffb6cf07e5c8fefe19a87dd7668db9e074
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/26/2020
ms.locfileid: "3296961"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Konfigurere brugerdefinerede handlinger fra en arbejdsproces


Du kan aktivere en brugerdefineret handling fra en arbejdsproces uden at skrive kode. Flere oplysninger: [Aktivér brugerdefinerede handlinger fra en arbejdsproces](invoke-custom-actions-workflow-dialog.md).  
  
 Du kan også oprette en handling, så en udvikler kan bruge den i koden, eller hvis du skal redigere en handling, der tidligere er blevet defineret. Som med processer i arbejdsprocessen skal du overveje følgende:  
  
-   Hvad skal handlingen foretage sig?  
  
-   Under hvilke betingelser skal handlingen udføres?  
  
 
I modsætning til processer i arbejdsprocessen behøver du ikke at angive følgende indstillinger :  
  
- **Start når**: Handlinger starter, når kode kalder den meddelelse, der er oprettet for dem.  
  
- **Omfang**: Handlinger køres altid i forbindelse med kald til bruger.  
  
- **Kør i baggrunden**: Handlinger er altid arbejdsprocesser i realtid.  
  
Handlinger har også noget, som arbejdsprocesser ikke har – input- og outputargumenter. Flere oplysninger: [Definer procesargumenter](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Opret en handling  
  
> [!IMPORTANT]
>  Hvis du opretter en handling, der skal medtages som en del af en løsning, der skal distribueres, kan du oprette den i konteksten af løsningen. Gå til **[Indstillinger](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Løsninger**, og find den ikke-administrerede løsning, som denne handling skal være en del af. Derefter skal du vælge **Ny** > **Proces** på menulinjen. Derved sikres, at det tilpasningspræfiks, der er knyttet til navnet på handlingen, er konsistent med andre komponenter i løsningen. Når du har oprettet handlingen, kan du ikke ændre præfikset.  
  
 Som i processer i arbejdsprocessen har handlinger følgende egenskaber i dialogboksen **Opret proces**.  
  
 **Procesnavn**  
 Når du har indtastet et navn til processen, oprettes der et entydigt navn for den ved at fjerne eventuelle mellemrum eller specialtegn i procesnavnet.  
  
 **Kategori**  
 Denne egenskab fastslår, at dette er en handlingsproces. Du kan ikke ændre dette, når du har gemt processen.  
  
 **Enhed**  
 Med handlingsprocesser kan du vælge et objekt for at give en kontekst for arbejdsprocessen på samme måde som andre typer processer, men du har også mulighed for at vælge **Ingen (organisation)**. Brug denne indstilling, hvis din handling ikke kræver konteksten for et bestemt objekt. Du kan ikke ændre dette, når du har gemt processen.  
  
 **Type**  
 Brug denne egenskab til at vælge, om du vil oprette en ny handling fra bunden, eller om du vil starte ud fra en eksisterende skabelon.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Rediger en handling  
 Du skal deaktivere processer, før du kan redigere dem.  
  
 Du kan redigere en handling, som er oprettet som en del af en ikke-administreret løsning eller inkluderet i en løsning, der er installeret i organisationen. Hvis det er en administreret løsning, kan du muligvis ikke redigere den. Løsningsudgiveren har mulighed for at redigere de administrerede egenskaber, så den handling, der installeres sammen med en administreret løsning, ikke kan redigeres.  
  
 Når en handling gemmes, oprettes der et entydigt navn på basis af procesnavn. Det entydige navn er tildelt tilpasningspræfikset fra løsningsudgiveren. Det er navnet på den meddelelse, som en udvikler bruger i kode.  
  
 Når du redigerer en handling, har du følgende muligheder:  
  
 **Procesnavn**  
 Når processen er oprettet, og det entydige navn er genereret ud fra procesnavnet, kan du redigere procesnavnet. Du kan evt. anvende en navngivningskonvention for at gøre det nemmere at finde bestemte processer.  
  
 **Entydigt navn**  
 Når en handling gemmes, oprettes der et entydigt navn på basis af procesnavn. Det entydige navn er tildelt tilpasningspræfikset fra løsningsudgiveren. Det er navnet på den meddelelse, som en udvikler bruger i kode. Du skal ikke ændre det entydige navn, hvis processen er aktiveret, og der er kode, som forventer kald til handlingen ved hjælp af dette navn.  
  
> [!IMPORTANT]
>  Når handlingen er aktiveret, og koden er skrevet, så den bruger et entydigt navn, må det entydige navn ikke ændres uden også at ændre den kode, der henviser til det.  
  
 **Aktivér annullering af opdatering**  
 Generelt fortryder (eller annullerer) processer, der understøtter transaktioner, hele handlingen, hvis en del af dem mislykkes. Der er visse undtagelser. Visse handlinger, som udviklere kan foretage i kode, der er startet af handlingen, understøtter måske ikke transaktioner. Det kan f.eks. være, hvis koden udfører handlinger i andre systemer, der er uden for omfanget af transaktionen. Disse kan ikke annulleres af den handling, der kører i en app. Nogle meddelelser på platformen understøtter ikke transaktioner. Men alt det, du kun kan gøre med brugergrænsefladen for handlingen, understøtter transaktioner. Alle handlinger, der er en del af en arbejdsproces i realtid, overvejes i transaktionen, men med handlinger har du mulighed for at fravælge dette.  
  
 Du bør henvende dig til den udvikler, der skal anvende denne meddelelse, for at finde ud af, om den skal være i transaktionen eller ej. Generelt skal en handling være i transaktionen, hvis de handlinger, der udføres af forretningsprocessen ikke giver mening, medmindre de alle er fuldført. Det klassiske eksempel er overførsel af arbejdskapital mellem to bankkonti. Hvis du hæver arbejdskapital fra én konto, skal du deponere den i den anden. Hvis den ene ikke lykkes, mislykkes begge.  
  
> [!NOTE]
>  Du kan ikke aktivere annullering af opdateringen, hvis en brugerdefineret handling aktiveres direkte inde fra en arbejdsproces. Du kan aktivere annullering af opdateringen, hvis en handling er udløst af en meddelelse fra en Power Apps-webtjeneste.  
  
 **Aktivér som**  
 På samme måde som med alle processer kan du aktivere processen som en skabelon og bruge den som et avanceret udgangspunkt for processer, der følger et lignende mønster.  
  
 **Definere procesargumenter**  
 I dette område skal du angive alle de data, som handlingen forventes at starte, og hvilke data der udelades af handlingen. Flere oplysninger: [Definer procesargumenter](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Tilføje faser, betingelser og handlinger**  
 Som med andre processer angiver du, hvilke handlinger der skal udføres, og hvornår de skal udføres. Flere oplysninger: [Tilføj faser, betingelser og handlinger](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Definer procesargumenter  
 Når en udvikler bruger en meddelelse, begynder vedkommende måske med data, som han eller hun kan føre ind i meddelelsen. Hvis du f.eks. vil oprette en ny sagspost, er det måske sagens titelværdi, der skal overføres som inputargument.  
  
 Når meddelelsen er færdig, skal udvikleren muligvis overføre visse data, der er ændret eller genereret af meddelelsen, til en anden handling i koden. Disse data er outputargumentet.  
  
 Både input- og outputargumenter skal have et navn, en type og visse oplysninger, der fortæller, om argumentet altid er påkrævet. Du kan også angive en beskrivelse.  
  
 Navnet på meddelelsen og oplysningerne om alle procesargumenter repræsenterer "signaturen" for meddelelsen. Når en handling er aktiveret, og den bruges i kode, må signaturen ikke ændres. Hvis signaturen ændres, medfører det, at kode, der bruger meddelelsen, mislykkes. Den eneste undtagelse er, at du kan ændre en af de parametrene, så den ikke altid er påkrævet.  
  
 Du kan ændre rækkefølgen af argumenterne ved at sortere dem eller flytte dem op eller ned, fordi argumenterne identificeres ved navn, ikke ved rækkefølgen. Og hvis du ændrer beskrivelsen, afbrydes kode, der bruger meddelelsen, ikke.  
  
#### <a name="action-process-argument-types"></a>Argumenttyper for handlingsprocesser  
 I følgende tabel beskrives argumenttyperne for handlingsprocesser.  
  
|Skriv|Beskrivelse|  
|----------|-----------------|  
|Boolesk|En værdi af typen `true` eller `false`.|  
|DateTime|En værdi, der gemmer oplysninger om dato og klokkeslæt.|  
|Decimal|En talværdi med antal decimaler. Bruges, når præcisionstal er yderst vigtige.|  
|Objekt|En post for det angivne objekt. Når du vælger Objekt, aktiveres rullelisten, hvor du kan vælge objekttypen.|  
|EntityCollection|En samling objektposter.|  
|EntityReference|Et objekt, der indeholder navn, id og typen af objektpost, der entydigt identificerer det. Når du vælger EntityReference, aktiveres rullelisten, hvor du kan vælge objekttypen.|  
|Flydende|En talværdi med antal decimaler. Bruges, når data stammer fra en måleenhed, der ikke er fuldstændig præcis.|  
|Heltal|Et heltal.|  
|Penge|En værdi, der gemmer data om et pengebeløb.|  
|Valgliste|En værdi, der repræsenterer en indstilling for en OptionSet-attribut.|  
|Streng|En tekstværdi.|  
  
> [!NOTE]
> Værdier for argumentet **EntityCollection** kan ikke angives i brugergrænsefladen for betingelser eller handlinger. Disse angives til brug af udviklere i brugerdefineret kode. Flere oplysninger: [Opret dine egne handlinger](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Tilføj faser og trin  
 Handlinger er en type processer, der er meget lig arbejdsprocesser i realtid. Alle de trin, der kan bruges i arbejdsprocesser i realtid, kan bruges i handlinger. Du kan finde oplysninger om de trin, der kan bruges til både arbejdsprocesser i realtid og handlinger, i [Faser og trin i arbejdsprocessen](configure-workflow-steps.md).  
  
 Ud over de trin, der kan bruges til arbejdsprocesser i realtid, har handlinger også trinnet **Tildel værdi**.  I handlinger kan disse kun bruges til at angive outputargumenter. Du kan bruge formularassistenten til at angive outputargumenter til specifikke værdier eller, mere sandsynligt, til værdier fra den post, som handlingen kører imod, poster, der er relateret til den pågældende post med en mange til én-relation, poster, der er oprettet i et tidligere trin, eller værdier, der er en del af selve processen.  
  
## <a name="next-steps"></a>Næste trin  
 [Handlinger](actions.md)  

 [Aktivér brugerdefinerede handlinger fra en arbejdsproces](invoke-custom-actions-workflow-dialog.md)   
 [Overvågning af arbejdsprocesser i realtid og handlinger](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
