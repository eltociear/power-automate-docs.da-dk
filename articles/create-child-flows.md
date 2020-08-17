---
title: Kalde underordnede flows
description: Flows kan nu kalde andre flows og sende parametre til dem.
author: MSFTMAN
ms.reviewer: deonhe
ms.date: 07/21/2020
ms.assetid: 6e6d3c34-b209-ea11-a811-000d3a4f1cdd
ms.topic: article
ms.service: business-applications
ms.author: deonhe
dynamics365pdf: true
ms.openlocfilehash: 1c7ac66d271820ba2b8a3e83041816a088fbb9ee
ms.sourcegitcommit: 9c893b055bdff2e1a6de04aa750289e2a13db96c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614257"
---
# <a name="create-child-flows"></a>Oprette underordnede flows

I dag oprettes brugere flows, der kræver dusinvis eller hundredvis af trin. Når du vil føje alle disse handlinger til et _enkelt_ flow, kan det være svært at navigere rundt i og bevare det pågældende flow. 

Du kan bruge underordnede flows for nemt at administrere flows og undgå flows med hundredvis af trin. Denne fremgangsmåde er især fordelagtig, hvis du vil genbruge opgaver flere steder i et flow eller endda over flere flows.

Her kan du se et eksempel, hvor du har et underordnet flow, hvor du vil oprette eller opdatere en kontakt i Common Data Service på baggrund af navnet på den pågældende kontaktpersons navn.

Du skal bruge en løsning med to flows:
- Et *underordnet* flow. Dette er det flow, der er indlejret i det *overordnede* flow, og som indeholder de mindre opgaver, du vil køre.
- Et *overordnet* flow. Dette flow kan have alle typer udløsere og kalde det underordnede flow.

## <a name="create-the-child-flow-in-a-solution"></a>Oprette det underordnede flow i en løsning

1. Log på Power Automate, vælg **Løsninger**, og vælg derefter en eksisterende løsning. 
   
   Du kan også oprette en løsning. 

1. Vælg **Ny** > **Flow** > **Knapflow** > **Udløs et flow manuelt**. 

   >[!TIP]
   >Du kan også bruge **Power Apps** eller udløsere for **Når en HTTP-anmodning er modtaget** for underordnede flows.

1. Vælg **Tilføj et input**.
   Det input, du definerer her, overføres til det underordnede flow fra det overordnede flow.

    ![Det input, der kommer fra overordnede flows](./media/call-child-flow/add-trigger-input.png "Det input, der kommer fra overordnede flows")

1. I forbindelse med denne gennemgang opretter det underordnede flow en kontaktperson, så der er behov for **Kontaktpersons navn** og **Kontaktpersons email**.

   ![Input til underordnet flow](./media/call-child-flow/input-definition.png "Input til underordnet flow")

1. Byg den logik, som det underordnede flow skal køre. Denne logik kan indeholde lige så mange trin, som du har behov for. 

   Når du har gennemført disse trin, skal du returnere data til det overordnede flow. I dette tilfælde kan du bruge en af to handlinger:

   i. **Besvar en Power App eller et flow** (under Power Apps-connectoren).
   
   ii. **Svar** (på Premium-connector for HTTP-anmodning/svar).

1. Som med udløseren kan du definere lige så mange output, som du vil have returneret fra det underordnede flow. I følgende billede kan vi svare med kontaktpersonens id.

   ![Svar på underordnet flow](./media/call-child-flow/response-output.png "Svar på underordnet flow")

1. Giv dit flow et beskrivende navn, og gem det derefter. 

   Derefter skal du teste dit underordnede flow. Da du kan udløse dette flow manuelt, er det meget nemt at udføre en test direkte i designeren. Afprøv det med et par forskellige input, og kontrollér, at outputtene er, som du forventer.

1. Hvis flowet bruger andet end indbyggede handlinger eller Common Data Service-connectoren (nuværende miljø), skal du opdatere flowet for at bruge de forbindelser, der er **integreret** i flowet. Hvis du vil gøre det, skal du vælge knappen Tilbage for at gå til siden med egenskaber for det underordnede flow og derefter vælge **Rediger** i feltet **Kør kun brugere**.

1. I den rude, der vises for hver connector, der bruges i flowet, skal du vælge **Brug denne forbindelse (<_forbindelses navn>_)** i stedet for **Leveret af bruger, der kun er kørt**.

1. Vælg **Gem**. På nuværende tidspunkt kan du ikke videresende forbindelser fra det overordnede flow til det underordnede flow. Hvis du ikke gør dette, får du vist en fejlmeddelelse om, at navnet ikke kan bruges som en underordnet arbejdsproces, da underordnede arbejdsprocesser kun understøtter integrerede forbindelser.

## <a name="create-the-parent-flow-in-a-solution"></a>Oprette det overordnede flow i en løsning

1. Byg det overordnede flow i den samme løsning, hvor du har oprettet det underordnede flow.
   
   Du kan også hente et eksisterende flow til den pågældende løsning. Det overordnede flow kan have alle typer udløsere.

1. Find det sted i dit *overordnede flow*, hvorfra du vil kalde det underordnede flow, og tilføj derefter handlingen **Kør et underordnet flow**, der er placeret under connectoren **Flows** på fanen **Indbygget**.

1. Vælg det underordnede flow, du oprettede tidligere. 

   >[!NOTE]
   >Du kan kun se de flows, du har adgang til, og som er placeret i en løsning. Underordnede flows skal også have et af de tre udløsere, der er nævnt tidligere.

   ![Vælge det underordnede flow, du vil køre](./media/call-child-flow/select-child-flow.png "Vælge det underordnede flow, du vil køre")

1. Når du har valgt det underordnede flow, kan du se de _input_, du definerede. Efter handlingen for det underordnede flow kan du bruge ethvert _output_ fra det underordnede flow.

   ![Inputs](./media/call-child-flow/view-child-flow-input.png "Inputs")

   Når det overordnede flow kører, venter det på, at det underordnede flow fuldføres i i flowets levetid (et år for flows, der bruger indbyggede forbindelser, og Common Data Service eller 30 dage for alle andre flows).

1. Gem og test dette flow. 

   >[!TIP]
   >Når du eksporterer den løsning, der indeholder disse to flows, og importerer den til et andet miljø, tilknyttes de nye overordnede og underordnede flows automatisk, så du ikke behøver opdateres URL-adresserne. 
   