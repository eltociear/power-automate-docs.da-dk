---
title: Brug Markdown til at formatere Power Automate-godkendelser | Microsoft Docs
description: Lær, hvordan du kan bruge Markdown til at formatere anmodninger om Power Automate-godkendelse.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4633df9687662c49757dd9cbb4d1d88892dfbe51
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79193628"
---
# <a name="use-markdown-in-power-automate-approval-requests"></a>Brug Markdown i anmodninger om Power Automate-godkendelse


I denne artikel lærer du at bruge [Markdown](https://en.wikipedia.org/wiki/Markdown)-syntaksen til at føje avanceret formatering til dine godkendelsesanmodninger.

> [!IMPORTANT]
> Mails med godkendelsesanmodninger er *handlingsrettede meddelelser*. Hvis din [Microsoft Outlook-klient](https://docs.microsoft.com/outlook/actionable-messages/#outlook-version-requirements-for-actionable-messages) ikke understøtter handlingsrettede meddelelser, vises der godkendelsesanmodninger i HTML-format. 

## <a name="headers"></a>Headers (Overskrifter)

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

Gør det lettere at læse din tekst ved at opdele den med afsnits- eller linjeskift. Angiv to mellemrum før linjeskift, hvis du vil starte et nyt afsnit, eller angiv to linjeskift efter hinanden, hvis du vil starte et nyt afsnit.   
   
**Eksempel**

Tilføj linjer mellem teksten vha. Enter.
Det giver bedre plads i teksten og gør den lettere at læse.

**Resultat:**    
Tilføj linjer mellem teksten vha. Enter.      
Det giver bedre plads i teksten og gør den lettere at læse.


**Eksempel 2**

Tilføj to mellemrum før slutningen af linjen.(mellemrum, mellemrum)     
Dette giver plads mellem afsnit.

**Resultat:**  
Tilføj to mellemrum før slutningen af linjen.   

Dette giver plads mellem afsnit.
  

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

1. First item.
2. Second item.
3. Third item.

### <a name="bullet-lists"></a>Punktopstilling

**Eksempel:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Resultat:**

- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Indlejrede lister

**Eksempel:**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Resultat:**  

1. First item.

    - Item 1
    - Item 2
    - Item 3
2. Second item.
    - Nested item 1
    - Nested item 2
    - Nested item 3


## <a name="links"></a>Links

URL-adresser, der starter med HTTP eller HTTPS, formateres automatisk som links. 

Du kan angive tekstlinks for din URL-adresse ved hjælp af standardsyntaksen for Markdown-links:

```Markdown
[Link Text](Link URL)
```

**Eksempel:**
<pre>
&#91;Power Automate](https://flow.microsoft.com)
</pre>

**Resultat:**

[Power Automate](https://flow.microsoft.com)

### <a name="anchor-links"></a>Forankrede links

Der tildeles et forankret id til alle overskrifter, når de gengives i HTML-format. Id er overskriftsteksten, hvor mellemrummene er erstattet af bindestreger (-), og der kun bruges små bogstaver.

**Eksempel:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Resultat:**

Syntaksen for et forankret link til en sektion...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
Id'et består udelukkende af små bogstaver, og der skelnes mellem store og små bogstaver i linket, så sørg for at bruge små bogstaver, også selvom der i selve overskriften bruges store bogstaver.


## <a name="tables"></a>Tabeller

Organiser strukturerede data med tabeller. 

- Anbring de enkelte tabelrækker på hver sin linje 
- Adskil tabelceller ved hjælp af en lodret streg `|` 
- De to første linjer i en tabel indikerer kolonneoverskrifterne og justeringen af elementer i tabellen
- Brug koloner (`:`), når du inddeler overskrift og brødtekst i tabeller, for at angive kolonnejustering (til venstre, i midten, til højre) 
- Brug <br>-koden i HTML for at starte en ny linje (`<br/>`) (fungerer i en wiki, men ikke andre steder)  
- Husk at afslutte de enkelte rækker med vognretur eller linjeskift. 

**Eksempel:**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Resultat:**  

| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:---------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Fremhævelse (fed, kursiv, gennemstreget)  

Du kan fremhæve tekst ved at anvende fed, kursiv eller gennemstreget tekst: 
- Sådan anvender du kursiv: Omgiv teksten med en stjerne `*` eller et understregningstegn `_`   
- Sådan anvender du fed: Omgiv teksten med to stjerner `**`.    
- Sådan anvender du gennemstregning: Omgiv teksten med to tilder `~~`.   

Kombiner disse elementer for at fremhæve tekst på flere måder.    

**Eksempel:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Resultat:**

Use _emphasis_ in comments to express **strong** opinions and point out <s>corrections</s>   
**_Bold, italicized text_**    
**~~Bold, strike-through text~~**  


## <a name="special-characters"></a>Specialtegn

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Syntaks</th>
<th width="350px">Eksempel/noter</th>
</tr>



<tr>
<td>
<p>Hvis du vil indsætte et af følgende tegn, skal du indlede teksten med en omvendt skråstreg:</p>

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
