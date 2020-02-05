---
title: 'Eksempel: Arbejd med forretningsprocesflow | MicrosoftDocs'
description: I eksemplet vises, hvordan du arbejder programmatisk med forretningsprocesforløb som f.eks. hentning af forekomsterne af forretningsprocesforløbet for en objektpost, hentning af en aktiv sti for en forekomst af et forretningsprocesforløb og dets procesfaser samt ændring af den aktive fase.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 4f7566c6d6430c9167c0d1b7cc082792d0939780
ms.sourcegitcommit: 835b005284b9ae21ae1742a7d36b574ba3884bef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/29/2020
ms.locfileid: "74364712"
---
# <a name="sample-work-with-business-process-flows"></a>Eksempel: Arbejd med forretningsprocesflow
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

I eksemplet vises, hvordan du arbejder programmatisk med forretningsprocesforløb som f.eks. hentning af forekomsterne af forretningsprocesforløbet for en objektpost, hentning af en aktiv sti for en forekomst af et forretningsprocesforløb og dets procesfaser samt ændring af den aktive fase. Du kan finde oplysninger om disse begreber under [Arbejd med forretningsprocesforløb ved hjælp af kode](business-process-flows-code.md)  

 Dette eksempel kan downloades fra [Eksempel: Arbejd med forretningsprocesflow](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Forudsætninger  
 Før du kan køre eksemplet:  

1. Du skal have adgang til et Common Data Service-miljø.  

2. Du skal have de relevante rettigheder for de kundeemne-, salgsmulighed- og arbejdsprocesobjekter samt de objektposter for forretningsprocesforløb, der anvendes i dette eksempel.  

3. Du skal have Visual Studio 2015 eller nyere for at køre eksemplet.  

4. Du skal have en internetforbindelse for at hente projekteksemplet og gendanne de NuGet-pakker, der bruges i projekteksemplet.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Det gør eksemplet  

1.  Opretter et eksempel på en kundeemnepost. Dette opretter automatisk en forekomst af forretningsprocesforløbet "Kundeemne til salgsproces for salgsmulighed" for kundeemneposten.  

2.  Konverterer kundeemneposten til en salgsmulighedspost.  


4.  Henter de forekomster af forretningsprocesforløbet, der er tilknyttet posten "Salgsmulighed", ved hjælp af meddelelsen `RetrieveProcessInstances`. Den første post i den returnerede samling er den aktive forekomst af forretningsprocesforløbet for salgsmulighedsposten, som er "Kundeemne til salgsproces for salgsmulighed" i dette tilfælde.  

5.  Henter den aktive sti og procesfaserne for forekomsten af "Kundeemne til salgsproces for salgsmulighed" ved hjælp af meddelelsen `RetrieveActivePath`.  

6.  Henter den aktuelt aktive fase for forekomsten "Kundeemne til salgsproces for salgsmulighed" og beder brugeren om at gå til næste fase. Efter bekræftelsen af dette angives den næste fase i den aktive sti som den aktive fase for forekomsten af "Kundeemne til salgsproces for salgsmulighed".  

7.  Til sidst bliver brugeren bedt om at slette de poster, der er oprettet i løbet af kørselseksemplet.  

     Her er outputtet af eksemplet:  

    ![Eksempel på output](media/work-with-bpf-sample-output.png "Eksempel på output")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Kør eksemplet  

1. [Download](https://go.microsoft.com/fwlink/p/?LinkId=846108) WorkWithBPF Visual Studio-projekteksemplet, og pak det ud i en mappe på din computer.  

2. Find filen `WorkWithBPF.sln` i den udpakkede mappe, og åbn den i Visual Studio.  

3. Projekteksemplet bruger NuGet-pakker, der skal gendannes, før du kører eksemplet. Sørg for, at den automatiske gendannelse af NuGet-pakker er aktiveret i Visual Studio. Flere oplysninger: [Aktivering og deaktivering af gendannelse af NuGet-pakker](https://go.microsoft.com/fwlink/?linkid=846106)  

    Du kan også vælge **Projekt** > **Administrer NuGet-pakker** og derefter vælge **Gendan** for at gendanne de pakker, der bruges i eksemplet, manuelt.  

4. Tryk på F5, eller vælg **Fejlfind** > **Start fejlfinding**.  

5. Hvis du ikke tidligere har kørt et af eksemplerne, skal du angive oplysninger for at køre koden. I modsat fald skal du angive nummeret på en af de forekomster, du tidligere har konfigureret.  


   |                                 Spørg                                  |                                                                                             Beskrivelse                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Angiv et Dynamics 365-servernavn og en port [crm.dynamics.com]       | Skriv navnet på din Dynamics 365-server. Standarden er Dynamics 365 (online) (crm.dynamics.com) i Nordamerika.<br /><br /> Eksempel: <br />crm5.Dynamics.com |
   | Er denne organisation klargjort til Microsoft Online Services (y/n) [n] |                                                 Skriv **y**, Hvis dette er en organisation, der er klargjort til Microsoft Online Services. Ellers skal du skrive **n**.                                                  |
   |                          Angiv domæne\brugernavn                          |                                                                                    Skriv din Microsoft konto.                                                                                     |
   |                             Angiv adgangskode                              |                      Skriv din adgangskode. Tegnene vises som "\*" i vinduet. Din adgangskode gemmes sikkert i Microsoft Legitimationsstyring til senere brug.                       |
   |                Angiv et organisationsnummer (1-n) [1]                 |                      Skriv nummeret på den organisation på listen, som du tilhører. Standarden er 1, hvilket er den første organisation på listen.                       |


6. Eksemplet udfører de handlinger, der er beskrevet i [Det gør eksemplet](#what-this-sample-does), og du kan blive bedt om at angive flere indstillinger.  

7. Når eksemplet er fuldført, skal du trykke på ENTER for at lukke konsolvinduet.  

