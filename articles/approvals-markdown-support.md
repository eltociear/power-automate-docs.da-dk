---
title: Brug markdown til at formatere Power Automate-godkendelser | Microsoft Docs
description: Lær, hvordan du kan bruge markdown til at formatere anmodninger om Power Automate-godkendelse.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 6/27/2020
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 19a6380ccdf5d1eb09f872bc0294d79876dee04c
ms.sourcegitcommit: 9bb2e400751338357c66d11cfa7054d65d919fdb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/27/2020
ms.locfileid: "3517270"
---
# <a name="use-markdown-in-power-automate-approval-requests"></a>Brug markdown i Power Automate-godkendelsesanmodninger


I denne artikel lærer du at bruge [Markdown](https://en.wikipedia.org/wiki/Markdown)-syntaksen til at føje avanceret formatering til dine godkendelsesanmodninger.

> [!IMPORTANT]
> Mails med godkendelsesanmodninger er *handlingsrettede meddelelser*. Hvis din [Microsoft Outlook-klient](https://docs.microsoft.com/outlook/actionable-messages/#outlook-version-requirements-for-actionable-messages) ikke understøtter handlingsrettede meddelelser, vises der godkendelsesanmodninger i HTML-format. 

> [!IMPORTANT]
> Alle markdown-gengivelser indeholder implementeringsforskelle. Se afsnittet [Klientsupport](#client-support) for at få flere oplysninger.

> [!IMPORTANT]
> Markdown understøttes ikke i øjeblikket for kunder med GCC og GCC High.

## <a name="client-support"></a>Klientsupport

Markdown-support mellem klienter er ikke ensartet. Power Automate-teamet arbejder på at løse disse uoverensstemmelser, men der er stadig forskelle. I tabellen nedenfor kan du se de kendte begrænsninger for de understøttede klienter.

| Funktion | Power Automate | Power Automate-mobilapp | Outlook-skrivebord | Outlook Web | Grupper | Teams Mobile-app |  
|---------|--------|---------------|-----------------|-------------|-------|--------------|
| **Sidehoveder** | Ja | Ja | Ja | Ja | **_Nej_** | **_Nej_** |
| **Nummererede lister** | Ja | Ja | **_Nej_** | Ja | Ja | Ja |
| **Indlejrede nummererede lister** | Ja | Ja | **_Nej_** | Ja | Ja | Ja |
| **Tabeller** | Ja | Ja | Ja | Ja | **_Nej_** | **_Nej_** |
| **Billeder** | **_Nej_** | **_Nej_** | **_Nej_** | **_Nej_** | **_Nej_** | **_Nej_** |
| **Tvungne linjeskift** | Ja | Ja | **_Nej_** (brug en tom linje i stedet) | Ja | Ja | Ja |
| **Tomme linjer** | **_Nej_** | **_Nej_** | Ja | Ja | **_Nej_** | Ja |

## <a name="headers"></a>Sidehoveder

Strukturér dine kommentarer ved hjælp af overskrifter. Længere kommentarer inddeles under overskrifter, så det er lettere at læse dem.

Start en linje med hash-tegnet `#` for at angive en overskrift. Organiser dine bemærkninger med underoverskrifter ved at starte en linje med yderligere hash-tegn, f.eks. `####`. Op til seks overskriftsniveauer understøttes.

**Eksempel:**  
```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Resultat:**  
![Eksportér flow](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Afsnits- og linjeskift

Gør det lettere at læse din tekst ved at opdele den med afsnits- eller linjeskift. Indtast to mellemrum før linjeskiftet for at tvinge de fleste klienter til at starte en ny linje.  
   
**Eksempel:**  
```Markdown
This is line 1.(space, space)
Now text will appear on the next line.
```

**Resultat:**   
Dette er linje 1.  
Nu vises teksten på næste linje. 

**Eksempel 2**  
```Markdown
This is line 1.(space, space)  

Line 2 has extra space before it.
```

**Resultat:**  
Dette er linje 1.  

Der er mere afstand før linje 2.
  

## <a name="lists"></a>Lister

Organiser lister med relaterede elementer. Du kan tilføje sorterede lister med tal eller usorterede lister med punkttegn.

Sorterede lister starter med et tal efterfulgt af et punktum for hvert element på listen. Usorterede lister starter med en `*`. Du kan starte de enkelte listeelementer på en ny linje. I en Markdown-fil eller -widget kan du angive to mellemrum før linjeskift, hvis du vil starte et nyt afsnit, eller angive to linjeskift efter hinanden, hvis du vil starte et nyt afsnit.   

### <a name="ordered-or-numbered-lists"></a>Sorterede eller nummererede lister

**Eksempel:**  
```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Resultat:**  
1. Første element.
2. Andet element.
3. Tredje element.

### <a name="bullet-lists"></a>Punktopstilling

**Eksempel:**  
```Markdown
- Item 1
- Item 2
- Item 3
```

**Resultat:**  
- Punkt 1
- Punkt 2
- Punkt 3

### <a name="nested-lists"></a>Indlejrede lister

**Eksempel:**  
```Markdown
1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3
```

**Resultat:**  
1. Første element.

    - Punkt 1
    - Punkt 2
    - Punkt 3
2. Andet element.
    - Indlejret element 1
    - Indlejret element 2
    - Indlejret element 3


## <a name="links"></a>Links

URL-adresser, der starter med HTTP eller HTTPS, formateres automatisk som links. 

Du kan angive tekstlinks for din URL-adresse ved hjælp af standardsyntaksen for Markdown-links:

```Markdown
[Link Text](Link URL)
```

**Eksempel:**  
```Markdown
[Power Automate](https://flow.microsoft.com)
```

**Resultat:**  
[Power Automate](https://flow.microsoft.com)

## <a name="tables"></a>Tabeller

Organiser strukturerede data med tabeller. 

- Anbring de enkelte tabelrækker på hver sin linje 
- Adskil tabelceller ved hjælp af en lodret streg `|` 
- De to første linjer i en tabel indikerer kolonneoverskrifterne og justeringen af elementer i tabellen
- Brug koloner (`:`), når du inddeler overskrift og brødtekst i tabeller, for at angive kolonnejustering (til venstre, i midten, til højre) 
- Hvis du vil starte en ny linje, skal du bruge HTML-koden for linjeskift (`<br/>`)
- Husk at afslutte de enkelte rækker med vognretur eller linjeskift. 

**Eksempel:**  
```Markdown
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br>second line of text |  
```


**Resultat:**  

| Overskrift 1 | Overskrift 2 | Overskrift 3 |  
|-----------|:-----------:|-----------:|  
| Celle A1 | Celle A2 | Celle A3 |  
| Celle B1 | Celle B2 | Celle B3<br>anden tekstlinje |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Fremhævelse (fed, kursiv, gennemstreget)  

Du kan fremhæve tekst ved at anvende fed, kursiv eller gennemstreget tekst: 
- Sådan anvender du kursiv: Omgiv teksten med en stjerne `*` eller et understregningstegn `_`   
- Sådan anvender du fed: Omgiv teksten med to stjerner `**`.    
- Sådan anvender du gennemstregning: Omgiv teksten med to tilder `~~`.   

Kombiner disse elementer for at fremhæve tekst på flere måder.    

**Eksempel:**  
```Markdown
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
```

**Resultat:**  
Anvend _fremhævning_ i kommentarer til at udtrykke **stærke** holdninger og pointere <s>rettelser</s>   
**_Fed, kursiv tekst_**   
**~~Fed, gennemstreget tekst~~**  

## <a name="special-characters"></a>Specialtegn

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Syntaks</th>
<th width="350px">Eksempel/noter</th>
</tr>



<tr>
<td>
<p>Hvis du vil indsætte et af følgende tegn, skal du indlede det med en omvendt skråstreg:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Eksempler på indsættelse af specialtegn
<p>Skriv ```\\``` for at få \\ </p>
<p>Skriv ```\_``` for at få _ </p>
<p>Skriv ```\#``` for at få \# </p>
<p>Skriv ```\(``` for at få \( </p>
<p>Skriv ```\.``` for at få \. </p>
<p>Skriv ```\!``` for at få \! </p>
</td>
</tr>

</tbody>
</table>
