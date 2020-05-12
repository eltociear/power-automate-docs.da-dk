I et tidligere emne viste vi dig, hvordan du på en nem måde kan styrke dit Twitter-feed med en SharePoint-liste. I dette emne lærer du, hvordan du kan opbygge et mere brugervenligt scenarie ved hjælp af godkendelser. På denne måde kan alle, der har adgang til SharePoint-listen, bidrage med tweets, og teamet, der varetager sociale medier, kan enten godkende eller afvise disse tweets. Teamet bibeholder kontrol med kontoen og det indhold, der offentliggøres til kunderne. 

## <a name="create-an-approval-request-flow"></a>Opret et flow for en godkendelsesanmodning
1. På startsiden for **Power Automate** skal du vælge **Godkendelser**, vælg **Opret godkendelsesflow**, og rul derefter ned og vælg skabelonen **Post listeelementer til Twitter efter godkendelse**. 
   
    ![Vælg skabelon](./media/learning-approval-center/create-approval.png)
2. Bekræft dine legitimationsoplysninger til **SharePoint**, **Godkendelser** og **Twitter**, og vælg **Fortsæt**. 
   
    ![Bekræft legitimationsoplysninger](./media/learning-approval-center/verify-credentials.png)

Som standard starter denne skabelon en godkendelsesproces, hver gang et nyt element oprettes på en specifik liste, og hvis elementet godkendes, poster skabelonen et tweet til Twitter. I dette emne redigerer du denne proces ved at tilføje trin, der opdaterer SharePoint-listen med et godkendelsessvar, angiver, om et element blev godkendt eller ej, og tilføjer eventuelle kommentarer, som godkenderen har føjet til det foreslåede tweet. 

1. Føj to nye kolonner til SharePoint-listen **ContosoTweets**, som du oprettede tidligere:
   
   1. Vælg plustegnet "**+**", og vælg **Ja/Nej**
   2. Angiv **ApprovalStatus** , og vælg **Opret**
   3. Vælg plustegnet "**+**", og vælg **Enkelt tekstlinje**
   4. Angiv **ApproverComments** , og vælg **Gem**
      
      ![Tilføj kolonner](./media/learning-approval-center/new-columns.png)
2. Når du er tilbage i **Power Automate**, skal du angive følgende værdier for handlingen **Når der oprettes et nyt element**:
   
   * **Webstedsadresse**: teamets URL-adresse til SharePoint
   * **Listenavn**: ContosoTweets
     
     ![Websted og liste](./media/learning-approval-center/site-address.png)
3. I handlingen **Start en godkendelse** skal du vælge **Rediger** for at få vist alle felter. 
   
    ![Rediger felter](./media/learning-approval-center/edit-all-fields.png)
4. I **Titel** skal du angive **Nyt tweet for** og vælge **Titel** fra listen over dynamisk indhold. 
   
    ![Titel](./media/learning-approval-center/tweet-title.png)
5. I **Tildelt til** skal du angive og vælge dit navn eller et testbrugernavn. 
   
    ![Tildelt til](./media/learning-approval-center/tweet-assigned-to.png)
6. I **Detaljer** skal du fjerne standardelementet og tilføje **TweetContent**, **TweetDate** og **Oprettet af DisplayName** fra listen over dynamisk indhold, forbundet med ordene **den** og **af**. 
   
    ![Detaljer](./media/learning-approval-center/tweet-details.png)
7. I **Elementlink** skal du kopiere og indsætte URL-adressen til din SharePoint-liste, og i **Beskrivelse af elementlink** skal du angive **listen Contoso Tweet**. 
   
    ![Elementlink](./media/learning-approval-center/tweet-item-link.png)
8. I handlingen **Betingelse** skal du holde musen over feltet **HVIS JA**, vælge plustegnet "**+**" og vælge **Tilføj en handling**. 
   
    ![Tilføj en handling](./media/learning-approval-center/add-an-action.png)
9. Søg efter **opdater element**, vælg **SharePoint**-connectoren, og vælg handlingen **SharePoint – Opdater element**.
   
    ![SharePoint – Opdater element](./media/learning-approval-center/update-item.png)
10. I **Webstedsadresse** og **Listenavn** skal du angive URL-adressen til dit websted og listen **ContosoTweets** igen, og i **Id** skal du angive **id** fra listen over dynamisk indhold. 
    
     ![Websted, liste og id](./media/learning-approval-center/address-list-id.png)
11. Vælg feltet **Titel**, og søg efter **titel** på listen over dynamisk indhold. Vælg elementet **Titel** fra handlingen **Når der oprettes et nyt element**. 
    
     ![Ny titel](./media/learning-approval-center/add-title.png)
12. Vælg **ApprovalStatus**, og angiv værdien til **Ja**. Vælg derefter **ApproverComments**, og indstil værdierne til **Kommentarer** fra listen over dynamisk indhold. 
    
     ![Status og kommentarer](./media/learning-approval-center/approver-status.png)
13. Vælg **Tilføj en handling** nederst i feltet **HVIS NEJ, GØR INTET**.
    
     ![Tilføj en tom handling](./media/learning-approval-center/add-a-no-action.png)
14. Ved hjælp af de samme trin, som du brugte til konfigurationen **HVIS JA**, skal du oprette handlingen **SharePoint – Opdater element** og konfigurere felterne med de samme værdier med undtagelse af, at **ApprovalStatus** skal indstilles til **Nej**. 
    
     ![Status = nej](./media/learning-approval-center/status-no.png)
15. Vælg handlingen **Post et tweet**, vælg **Rediger**, og angiv **Tweet-tekst** til **TweetContent** fra den dynamiske indholdsliste.  Vælg **Opret flow** øverst på siden for at gemme dit arbejde. 
    
     ![Post, og gem](./media/learning-approval-center/post-tweet.png)

Dette er kun én måde, hvorpå Power Automate kan styrke dit teams produktivitet. Dit team kan bidrage med idéer, relevante nyheder eller produktvejledning, og du bevarer stadig kontrollen over, hvad der tweetes videre til kunderne.

I vores næste emne ser vi, hvordan det ser ud, når en godkender modtager en ny anmodning for et foreslået tweet. 

