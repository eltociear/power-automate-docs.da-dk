I et tidligere emne så du, hvordan du opretter en proces omkring tweets, der er gemt på en SharePoint-liste.  I dette emne får du vist, hvordan det ser ud, når en godkender modtager en ny godkendelsesanmodning. 

## <a name="create-and-process-a-request"></a>Opret og behandl en anmodning
Først skal vi føje et element til vores SharePoint-liste, og derefter kan vi behandle en godkendelsesanmodning for det pågældende element.

1. Åbn SharePoint-listen **ContosoTweets**, som blev konfigureret i et tidligere emne.  Vælg **Ny** for at oprette et nyt tweet. 
   
    ![SharePoint-liste](./media/learning-approval-request/sharepoint-list-home.png)
2. Føj følgende værdier til felterne, og vælg **Gem**.
   
   * **Titel** – Kampagner
   * **TweetContent** – Tjek den nye linje for Contoso Flooring #ohsocontoso
   * **TweetDate** – Dags dato
     
     ![SharePoint – Nyt element](./media/learning-approval-request/sharepoint-new-tweet.png)
3. Vælg **Mine flow** i **Power Automate**. 
4. Vælg flowet **Post listeelementer til Twitter efter godkendelse**, som blev konfigureret i forrige afsnit, og vælg derefter det kørende flow under **KØRSELSOVERSIGT**.
   
    ![Kørselshistorik](./media/learning-approval-request/run-history.png)
5. Vælg udløseren **Når der er oprettet et nyt element**. Kontrollér, at oplysningerne for det listeelement, du netop har oprettet, vises.
   
    ![Flowudløser](./media/learning-approval-request/approval-flow.png)
6. I **Outlook** skal du åbne mailen med den automatiserede godkendelse og derefter vælge **Godkend**. 
   
    ![Outlook-anmodning](./media/learning-approval-request/outlook-mail.png)
7. Se oplysningerne vedrørende anmodningen i **Godkendelsescenter**, tilføj en kommentar,og vælg **Bekræft**. 
   
    ![Godkendelsescenter](./media/learning-approval-request/approval-center.png)
8. I **SharePoint** skal du opdatere listen **ContosoTweets** og kontrollere, at **ApprovalStatus** er **Ja** og at den kommentar, du har angivet, vises. 
   
    ![SharePoint – Opdater liste](./media/learning-approval-request/sharepoint-list-approved.png)

I dette emne har du set, hvordan det ser ud fra godkenderens side - fra modtagelse af en mail med en godkendelsesanmodning til behandling af anmodningen i Godkendelsescenter.

