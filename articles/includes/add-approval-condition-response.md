1. Vælg **+Nyt trin**, og vælg derefter **Betingelse** på listen over handlinger.
1. i kortet **Betingelse**, og angiv derefter **svar** i søgefeltet på kortet **Tilføj dynamisk indhold fra de apps og tjenester, der bruges i dette flow**.
1. På skærmen **Betingelse** skal du vælge det første felt **Vælg en værdi** for at få vist en liste over indstillinger for dynamisk indhold. Vælg derefter **Svar Godkendersvar**.

    ![vælg svartoken](media/modern-approvals/search-for-response.png)
1. Vælg feltet **Værdi**, og angiv derefter **Godkend** i feltet.

   > [!NOTE]
   > De gyldige svar på handlingen **Godkendelser – Start en godkendelse** er "Godkend" og "Afvis". Der skelnes mellem store og små bogstaver i disse svar.

1. Dit kort **Betingelse** bør nu vise:
    
    * Objektnavn: *Svar*
    * Relation: *Er lig med*
    * Værdi: *Godkend*

    ![Visning af betingelseskortet](media/modern-approvals/response-condition-test.png "Visning af betingelseskortet")
