---
title: Lær, hvordan du automatiserer gentagne opgaver vha. knapflows, som tager brugerinput | Microsoft Docs
description: Power Automate gør det nemt at automatisere gentagne opgaver. Din flows kan også tage brugerinput, når du kører en tilbagevendende opgave.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5a2fa063b5379999a5dcbe37a56271fccf435cae
ms.sourcegitcommit: 84fb0547e79567efa19d7c16857176f7f1b53934
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/12/2020
ms.locfileid: "79192364"
---
# <a name="introducing-button-flows-with-user-input"></a>Introduktion til knapflows med brugerinput

Opret et knapflow til at køre rutineopgaver med blot et tryk på en knap. Tilpas dit flow ved at tillade brugeren at angive bestemte oplysninger, der skal bruges, når knapflowet køres. Dette emne gennemgår oprettelsen af et knapflow, der tager imod input fra brugeren og derefter kører knapflowet og fremhæver, hvordan brugerinput leveres.

Du kan oprette et knapflow på Power Automate-webstedet eller i mobilappen til Power Automate. Du skal bruge webstedet til dette emne.

### <a name="prerequisites"></a>Forudsætninger
* En konto på Power Automate-webstedet.

## <a name="open-the-template"></a>Åbn skabelonen
1. Log på [Power Automate-webstedet](https://flow.microsoft.com), indtast **Visual Studio** i søgefeltet, og klik eller tryk derefter på søgeikonet for at finde alle skabeloner, der vedrører Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Vælg skabelonen **Åbn en fejl med andenprioritet i Visual Studio**:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Vælg knappen **Brug denne skabelon**:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Denne skabelon bruger VSTS (Visual Studio Team Services) og tjenesten for pushmeddelelser. Du skal logge på disse tjenester, hvis du ikke har en forbindelse til nogen af dem. **Log på**-knappen vises kun, hvis du vil logge på en tjeneste.
4. Når du logger på alle de nødvendige tjenester, skal du vælge **Fortsæt**-knappen:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (valgfrit) Skift navnet på flowet ved at indtaste et navn efter eget valg i feltet øverst i portalen:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Tilpas brugerinput
1. Vælg **Rediger** på udløserkortet:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Vælg **+** -ikonet for at udvide siden, så du kan tilføje brugerdefinerede inputfelter:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Indtast **inputtitlen** og **inputbeskrivelsen** af hvert brugerdefinerede felt, du vil gøre tilgængeligt, når en person kører dit flow.  
   
    I dette eksempel opretter du to brugerdefinerede inputfelter (**Gendannelsestrin i forbindelse med fejl** og **Fejlens alvorsgrad**), så alle, der bruger dette flow, kan angive trinnene for gendannelse af fejlen og fejlens alvorsgrad:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Tilpas fejlen
1. Tryk på **Opret nyt arbejdselement**-kortets titellinje:
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Foretag valgene, der passer til dit VSTS-miljø, og vælg derefter **Rediger**:
   
    Opret f.eks. forbindelse til myinstance.visualstudio.com ved at indtaste **myinstance**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Vælg **Vis avancerede indstillinger** for at vise de andre felter på dette kort:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Placer markøren foran **Titlen på fejl**-tokenet, og angiv derefter "alvorsgrad:" i **titlens** tekstfelt.
5. Lad markøren forblive i titlens tekstfelt, og vælg **Fejlens alvorsgrad**-tokenet, og indtast derefter "--".  
6. I tekstfeltet **Beskrivelse** skal du placere markøren lige efter **Fejlbeskrivelses**-tokenet og derefter trykke på Enter for at starte en ny linje.
7. Placer markøren på den nye linje, og vælg derefter **Gendannelsestrin i forbindelse med fejl**-tokenet:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Tilpas pushmeddelelsen
1. Tryk på titellinjen på **Send en pushmeddelelse**-kortet for at udvide den.
2. Vælg **Se mere** på listen over dynamiske indholdstokener, og tilføj derefter **URL**-tokenet i tekstfeltet **Link**.
3. I tekstfeltet for **etiketter til links** tilføjes **Id**-tokenet:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Tryk på **Opret flow** i menuen for at oprette dit flow: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Kør dit flow
I denne gennemgang, skal du bruge mobilappen til Power Automate til at køre det knapflow, du netop har oprettet. Du skal angive alt det brugerinput, der er nødvendigt, for at oprette en fejl med en titel, en beskrivelse, gendannelsestrin og en alvorsgrad.  

1. Tryk på fanen **Knapper** i mobilappen til Power Automate, og tryk derefter på knappen **Opret fejlrapport med trin**.
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Indtast titlen på den fejl, du rapporterer, og tryk derefter på **Næste**. Eksempel:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Indtast beskrivelsen af den fejl, du rapporterer, og tryk derefter på **Næste**. Eksempel:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Angiv trinnene, der skal tages for at gendanne fejlen, du rapporterer, og tryk derefter på **Næste**. Eksempel:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Indtast alvorsgraden af den fejl, du rapporterer, og tryk derefter på **Udført**.  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    Flowet køres.
6. (valgfrit) Tryk på fanen **Aktivitet** for at få vist resultaterne.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (valgfrit) Se de detaljerede resultater af det kørte flow ved at trykke på trinnet **Opret et nyt arbejdselement**.
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Brug forskellige inputtyper

Dine knapflow kan også acceptere udvidede datatyper. Her er listen over datainputtyper, som knapflow accepterer: 

- Tekst
- Rullelister (f.eks. alternativknapper)
- Mailadresse
- Fil (f.eks. et foto på din telefon)
- Afkrydsningsfelt for ja eller nej
- Tal
- Dato (med en kalendervælger)

Hvis du vil bruge disse inputtyper, skal du tilføje udløseren **Udløs et flow manuelt** og derefter føje en af disse typer til dit flow:

![Inputindstillinger](media/button-flow-with-user-input-tokens/input-options.png)

Du kan også vælge at angive noget input som påkrævet og andet som valgfrit. Brug handlingsmenuen (... til højre) for de enkelte inputfelter. Der er en grænse på fem input pr. knap.

![Vælg valgfrie tokens](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Næste trin
* [Del knapflows](share-buttons.md)
* [Få mere at vide om knapflows](introduction-to-button-flows.md)  
* [Få mere at vide om knapflows med udløsertokens](introduction-to-button-trigger-tokens.md)  

