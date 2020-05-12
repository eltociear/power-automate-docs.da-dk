I dette emne kan du se, hvordan du kører flow, der er planlagt på forhånd, ved hjælp af en udløser kaldet **Gentagelse**.  Du skal oprette et flow til Contosos markedsføringsteam, der automatisk henter kundernes mailadresser fra en Excel-tabel på OneDrive. Du skal konfigurere flowet således, at nye mailadresser føjet til regnearket én gang om dagen herefter føjes til kundelisten MailChimp. 

## <a name="create-a-scheduled-flow"></a>Opret et planlagt flow
1. Åbn **Power Automate**, vælg **Mine flow**, og vælg derefter **Opret fra bunden**. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. Vælg **Søg blandt hundredvis af connectors og udløsere**.
3. Søg efter tjenesten **Tidsplan**, og vælg derefter udløseren **Tidsplan - Gentagelse**.
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. Angiv **Hyppighed** til **Dag** og **Interval** til **1**. Vælg **Nyt trin**, og vælg **Tilføj en handling**. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. Søg efter **Excel**, vælg tjenesten **Excel**, og vælg handlingen **Excel – Hent rækker**. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **Bemærk**: Sørg for at vælge **Hent rækker**, ikke **Hent række**. 
6. Vælg **Filnavn** og gå til filplaceringen. Vælg **Tabelnavn**, og vælg den ønskede tabel i regnearket. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. Tilføj en ny handling 
   
    ![](./media/learning-recurrence/new-step.png)
8. Søg efter tjenesten **MailChimp**, og vælg derefter handlingen **MailChimp – Føj medlemmer til listen**.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **Bemærk:** MailChimp er en *premium* connector. Du skal muligvis tilmelde dig en prøveversion for at bruge denne connector, afhængigt af din Power Automate-licens.
9. Tilføj felterne **Liste-id** og **Status** fra rullemenuerne:
   
   * **Liste-id** – Vælg den ønskede MailChimp-adresseliste
   * **Status** – Vælg **Abonnement** 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. I **Mailadresse** skal du bruge funktionen dynamisk indhold til at tilføje feltet **ContactEmail**. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     Bemærk, at flowet automatisk opretter et ekstra trin. Flowet registrerer, at du vil angive en handling, der kræver en yderligere handling. Hver gang flowet læser en ny mailadresse, opretter det også en ny handling for hver række. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. Brug dynamisk indhold til at udfylde felterne **Fornavn** og **Efternavn**:
    
    * **Fornavn** – FirstName
    * **Efternavn** – LastName
      
      ![](./media/learning-recurrence/mailchimp-names.png)

Dette flow vil nu køre én gang om dagen og hente nye række fra Excel-tabellen, snuppe mailadresse og navn og bruge disse til at udfylde MailChimp Contoso-adresselisten, og du sparer både tid og penge. 

