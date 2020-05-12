I dette emne lærer du, hvordan du **opretter et knapflow** Til Contoso Flooring Company. 

Knapflow kan anvendes til at **sende mail** til et team og **give besked om opgaver**, der skal udføres. **Ejerskab** af flowene **kan tildeles til én** arbejder eller **deles af flere** medlemmer i et team.  

1. Gå først til [Power Automate-webstedet](https://ms.flow.microsoft.com), og log på.
2. Når du er logget på, skal du vælge **Mine flow**, og derefter **Opret fra bunden**.
   
    ![Opret fra bunden](./media/learning-create-button-flow/2-create-from-blank.png)
   
    Det første, du skal bruge, er en udløser. Knapflowet er nemt at bruge. 
3. Hvis det ikke er på din liste, skal du vælge **Søg blandt hundredvis af connectors og udløsere** nederst på siden, angiv **knap**, og dukker op til dig. 
4. Vælg **Flowknap til mobil**.
   
    ![Søgeknap](./media/learning-create-button-flow/3-button-flow.png) 
5. Vælg **Flowknap til mobil – udløs et flow manuelt**.
   
    ![Vælg manuel udløser](./media/learning-create-button-flow/4-press-it.png)
6. Vælg **Tilføj inputtekst** på inputskærmen,
   
    ![Tilføj input](./media/learning-create-button-flow/5-add-input.png)
7. Skriv **Contoso Flooring** i det første tekstfelt og **mail med oplysninger om leverance til Warehouse** i andet tekstfeltet.
   
    ![Tilføj input](./media/learning-create-button-flow/6-text-for-flow.png)
8. Vælg **Nyt trin**. 
   
    ![Inputtekst](./media/learning-create-button-flow/7-input-description.png)
9. Vælg **Tilføj en handling**. 
   
    ![Tilføj handling](./media/learning-create-button-flow/8-add-an-action.png)
10. Vælg connectoren **Office 365 Outlook**. Søg efter **outlook**, hvis den ikke er der.
    
     ![Søg i outlook](./media/learning-create-button-flow/9-search-outlook.png)
11. Vælg **Office 365 Outlook - Send en mail**.
    
     ![Send mail](./media/learning-create-button-flow/10-send-email.png)
    
     Når der trykkes på knappen, sendes en mail til hele Contoso Warehouse-teamet, uanset hvor i bygningen de finder sig, som informerer dem om, at leverancen er nået frem.
12. Udvid felterne, og tilpas mailen til arbejde for Contoso Flooring.
    
    1. Angiv en mailadresse, der er gyldig i din organisation, i feltet **Til**.
    2. Angiv **Leverance modtaget** i feltet **Emne**. 
    3. Bemærk, at feltet **Dynamisk indhold** vises i højre side. Vælg **Dato** og **Tidsstempel** for at få vist den nøjagtige dato og det nøjagtige klokkeslæt for, hvornår der blev trykket på knappen, i emnelinjen. 
       
        ![Dato og klokkeslæt for mail](./media/learning-create-button-flow/11-email-date-time.png)
13. Skriv nu en simpel **brødtekst** til mailen, som f.eks. **Warehouse-team, kom venligst til læsserampen, da dagens leverance er ankommet**.
14. Vælg **Opret flow** for at gemme flowet.
    
     ![Opret flow](./media/learning-create-button-flow/12-create-flow.png)

## <a name="create-a-team-flow"></a>Opret et teamflow
Du kan bruge dette knapflow som et eksempel på, hvordan du opretter et teamflow. Hvad sker der, hvis den person, der har oprettet dette flow, er syg? Hvad sker der, hvis personen forlader virksomheden? Du ønsker at sikre, at dette flow bliver ved at køre. Det gør du ved at tilføje medejere.

1. Vælg **ikonet team** på dit flow at tilføje en medejer.
   
    ![Opret teamflow](./media/learning-create-button-flow/13-create-team-flow.png) 
2. Angiv navne, mailadresser eller brugergrupper for at tilføje medejere.
   
    ![Tilføj medejere](./media/learning-create-button-flow/14-add-co-owners.png)
3. Hvis du vil fjerne medejere, skal du vælge papirkurven til højre for deres navn.
   
    ![Fjern medejere](./media/learning-create-button-flow/15-remove-co-owners.png)
4. Vælg **Fjern denne ejer** for at afslutte.
   
    ![Fjern medejere](./media/learning-create-button-flow/16-agree-to-remove.png)

## <a name="summary"></a>Resumé
I denne lektion har du set, hvordan du **oprette et knapflow**. 

På få minutter gav flowet en lagermedarbejder mulighed for at **informere teamet** om **modtagelse af en leverance**, så teamet ikke skulle stå og vente og spilde værdifuld tid, som de kunne bruge på andre opgaver. 

Medarbejderen delte derefter knappen med teamet, så andre kan udløse samme flow, hvis den pågældende ikke er til stede.

## <a name="next-lesson"></a>Næste lektion
Tjek de næste lektioner for at se, hvordan du opretter et flow, der bruger **pushmeddelelser**.

