Til dette flow opretter du en **SharePoint**-liste, hvor markedsføringsteamet hos **Contoso Flooring** gemmer deres **Twitter-posts** og dato for opslaget. Herefter kan du oprette et flow, der automatisk sender tweetets indhold til markedsføringsteamet. 

## <a name="connect-power-automate-services"></a>Opret forbindelse til Power Automate-tjenester
I dette emne bruger du tjenesterne **SharePoint** og **Twitter**. Hvis du bruger en tjeneste, som er ny for dig, skal du første oprette forbindelse til den nye tjeneste. 

1. I Power Automate skal du vælge **tandhjulikonet** og derefter **Forbindelser**,
   
    ![Få forbindelse](./media/learning-push-notifications/2-get-connection.png) 
2. Vælg **+ Opret forbindelse**.
   
    ![Opret forbindelse](./media/learning-push-notifications/3-create-connection.png) 
3. Rul ned på listen, find Twitter, og vælg **+**.
   
    ![Klik på plus](./media/learning-push-notifications/4-click-plus.png)
4. For at godkende en Twitter-konto skal du angive dit brugernavn eller din mail og din adgangskode og derefter vælge **Godkend app**.
   
    ![Opret id og adgangskode](./media/learning-push-notifications/5-create-id-pswd.png)
5. Hvis du vil kontrollere dine forbindelser, skal du vælge **tandhjulikonet** og **Forbindelser**.
   
    ![Mine forbindelser](./media/learning-push-notifications/6-my-connections.png)
   
    Du kan se din nye Twitter-forbindelse og andre forbindelser, som du har oprettet. 
   
    ![Opret forbindelse til Twitter](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>Opret en SharePoint-liste
Det første, skal du gøre, er at oprette en ny SharePoint Online-liste til Contoso Flooring. 

1. Vælg **Ny** i SharePoint Online, og vælg derefter **Liste**.
   
    ![Opret ny liste](./media/learning-push-notifications/1-new-list.png)
2. Navngiv listen et **Contoso Tweets**. 
3. Fjern markeringen i afkrydsningsfeltet **Vis i webstedsnavigation**, og vælg **Opret**.
   
    ![Opret liste](./media/learning-push-notifications/2-name-create-list.png)
   
    Når du vælger **Opret**, fører SharePoint dig til din nye liste.
4. Som standard har listen én enkelt kolonne - **Titel**. Tilføj endnu en kolonne, og navngiv den **Tweet-indhold**. Det, du skriver i dine tweets, lander her. 
   
   1. Vælg plustegnet, og vælg derefter **Mere...**
      
       ![Opret liste](./media/learning-push-notifications/3-add-more-column-types.png)
   2. Vælg **Flere linjer tekst**, og vælg derefter **OK**.
      
       ![Opret liste](./media/learning-push-notifications/4-add-column.png)
5. Tilføj en kolonne til dato og klokkeslæt for tweetet, og navngiv den **Tweet-dato**.
   
   1. Som med **Tweet-indhold** ovenfor skal du vælge plustegnet og derefter vælge **Mere...**
      
       ![Kolonnen Dato og klokkeslæt](./media/learning-push-notifications/5-date-time-col.png)
   2. Rul ned til **Dato- og klokkeslætsformat**. Vælg **Dato og klokkeslæt**, så begge medtages.
      
       ![Dato og klokkeslæt](./media/learning-push-notifications/6-date-time-must-do.png)
   3. Vælg **OK**. Du kan listen **Contoso Tweets** på dit SharePoint-websted, og du kan føje nye elementer til listen.

## <a name="build-the-flow"></a>Opbyg flowet
Din liste er oprettet, så nu kan du oprette flowet.

### <a name="choose-a-trigger"></a>Vælg en udløser
1. I Power Automate skal du gå til **Mine flow** og derefter vælge **Opret fra bunden**.
   
    ![Opret fra bunden](./media/learning-push-notifications/8-create-from-blank.png)
2. Vælg **Når der oprettes et element**.
   
    ![Tilføj udløser](./media/learning-push-notifications/9-add-trigger.png)
   
    Vi ønsker, at vores udløser aktiveres, når der tilføjes en række med nyt tweet-indhold.
3. Vælg dit SharePoint-websted, og vælg derefter listen **Contoso Tweets**, som du konfigurerede tidligere.
   
    ![Nyt element oprettet](./media/learning-push-notifications/11-set-trigger.png)

Sådan! Det var det for udløseren.

### <a name="add-an-action-to-delay-posting"></a>Tilføj en handling for at forsinke et opslag
1. Vælg **+ Nyt trin**, og vælg derefter **Tilføj en handling**. 
   
    ![Tilføj trin og handling](./media/learning-push-notifications/12-add-step-and-action.png)
2. Under tjenesten **Tidsplan** skal du vælge **Udskyd indtil**. 
   
    ![Udskyd indtil](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. Angiv værdien for udskydelsen.
   
   1. Klik eller tryk på feltet **Tidsstempel**. 
   2. Når feltet med dynamisk indhold åbner, skal du rulle ned til bunden, hvor du finder de tre kolonner fra SharePoint-listen: **Titel**, **Tweet-dato** og **Tweet-indhold**.
   3. Vælg **Tweet-dato**. 
      
       ![Udskyd indtil tidsstempel](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       Nu, hvor nogen har føjet noget til din SharePoint-liste, vil det udskyde enhver handling indtil den dato og det klokkeslæt, du har angivet i kolonnen **Tweet-dato**.
      
       ![Dynamisk tidsstempel](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>Tilføj en handling for at poste et Tweet
Nu skal du tilføje en anden handling for flowet, så det henter den dato og det klokkeslæt, der er angivet i kolonnen**Tweet-dato**.

1. Vælg **+ Nyt trin**, **Tilføj en handling**, og søg efter **Twitter**.
   
    ![Tilføj tweet](./media/learning-push-notifications/16-add-tweet.png) 
2. Vælg handlingen **Twitter - Post et tweet**.
   
    ![Post et tweet](./media/learning-push-notifications/17-post-tweet.png) 
3. Klik eller tryk på feltet **Tweet tekst**, og vælg **Tweet-indhold** i feltet med dynamisk indhold. Her er den sekvens, du har oprettet. 
   
    ![Dato for tweet-indhold](./media/learning-push-notifications/18-tweet-date-content.png)
4. Vælg **Opret flow...**.
   
    ![Opret flow](./media/learning-push-notifications/19-tiny-create.png) 
5. Vælg **Udført**.
   
    ![Klik på udført](./media/learning-push-notifications/19-click-done.png)
   
    Nu er flowet færdigt.
   
    ![Flow er færdigt](./media/learning-push-notifications/20-flow-is-done.png)
   
    Når der oprettes et nyt element på din SharePoint-liste, udskyder flowet opslaget indtil den forudindstillede dato. På datoen poster flowet teksten fra kolonnen **Tweet-indhold** på din liste på Twitter.

## <a name="next-lesson"></a>Næste lektion
I den næste lektion lærer du, hvordan du **kører flow i henhold til en tidsplan** ved hjælp af en udløser kaldet **Gentagelse**.

