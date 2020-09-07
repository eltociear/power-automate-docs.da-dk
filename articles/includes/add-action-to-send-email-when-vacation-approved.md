1. Vælg **Tilføj en handling** på grenen **Hvis ja** på betingelsen.

    ![tilføj nyt trin](media/modern-approvals/add-action-after-condition.png)
1. Angiv **send mail** i søgefeltet på kortet **Vælg en handling**.
1. Vælg handlingen **Send en mail – Office 365 Outlook**.

    ![vælg handlingen send en mail](media/modern-approvals/select-send-email-yes.png)
1. Konfigurer mailkortet, så det passer til dine behov.

     >[!NOTE]
     > **Til**, **Emne** og **Brødtekst** er påkrævet.

     Dette kort er en skabelon for den mail, der sendes, når status for anmodningen om ferie ændres.

     I feltet **Brødtekst** på kortet **Send en mail**, skal du bruge tokenet **Kommentarer** fra handlingen **Godkendelser – Start en godkendelse**.
