I dette emne kan du se, hvordan Contoso Flooring bruger Power Automate til automatisk at konvertere dokumenter til et standardformat og derefter gemme dem i SharePoint Online, så de opbevares sikkert i skyen. Du opretter et flow, der registrerer, når der føjes en ny fil til mappen OneDrive for Business, og konverterer derefter filen til PDF og gemmer den i en SharePoint Online-mappe. 

## <a name="prerequisites"></a>Forudsætninger
Til dette formål skal du bruge en konto hos **Muhimbi**, en tjeneste til PDF-konvertering. Hvis du ikke allerede har en Muhimbi-konto, du kan tilmelde dig en [gratis 30-dages prøveversion](http://www.muhimbi.com/Products/PDF-Converter-for-SharePoint/Products-PDF-Converter-for-SharePoint-Free-Trial.aspx). Følg instruktionerne på denne side for at installere appen via dit SharePoint Online-websted. 

## <a name="create-the-source-and-target-folders"></a>Opret kilde- og destinationsmapper
Først skal du oprette kilde- og destinationsmapper i OneDrive for Business og SharePoint Online. 

1. Opret en mappe med navnet **Færdige dokumenter** under **Filer** i OneDrive for Business. 
   
    ![](./media/learning-create-pdf/onedrive-folder.png)
2. Opret en mappe med navnet **PDF – færdige filer** i **Delte dokumenter** i SharePoint Online. 
   
    ![](./media/learning-create-pdf/sharepoint-folder.png)

## <a name="create-the-flow"></a>Opret flowet
1. I Power Automate skal du vælge **Mine flow** og derefter vælge **Opret fra bunden**. 
   
    ![](./media/learning-create-pdf/create-blank-flow.png)
2. Vælg **Søg blandt hundredvis af connectors og udløsere**.
3. Søg efter **OneDrive**, vælg **OneDrive for Business**, og vælg derefter udløseren **OneDrive for Business - når en fil oprettes**. I **Mappe** skal du vælge mappeikonet og vælge mappen **Færdige dokumenter** mappe, som du oprettede i det forrige trin. 
   
    ![](./media/learning-create-pdf/onedrive-trigger.png)
4. Vælg **Nyt trin**, og vælg derefter **Tilføj en handling**. 
   
    ![](./media/learning-create-pdf/new-action.png)
5. Søg efter **Muhimbi**, vælg connectoren **Muhimbi PDF** og vælg handlingen **Muhimbi PDF – Konverter dokument**.
   
    ![](./media/learning-create-pdf/muhimbi-action.png)
6. På dette tidspunkt beder Power Automate dig muligvis om at godkende Muhimbi. Du skal registrere Muhimbi ved hjælp af dit **SharePoint-lejer-id**, for at Power Automate kan bruge Muhimbi-tjenesten. 
   
   1. For at finde dit lejer-id skal du vælge tandhjulikonet **Indstillinger** i SharePoint Online og vælge **Indstillinger for websted**.
   2. Under **Administration af gruppe af websteder** skal du vælge **App-tilladelser for gruppe af websteder**. Dit lejer-id er den identifikator, der følger efter symbolet "**@**" i enhver app-oversigt. 
      
       ![](./media/learning-create-pdf/tenant-id.png)
7. Angiv følgende værdier i handlingen **Konverter dokument**:
   
   * **Kildefilnavn**: Vælg **Filnavn** fra listen over dynamisk indhold.
   * **Kildefilens indhold**: Vælg **Filindhold** fra listen over dynamisk indhold.
   * **Outputformat**: Vælg **PDF** på rullelisten.
     
     ![](./media/learning-create-pdf/muhimbi-configuration.png)

Indtil videre har du konfigureret dit flow med følgende trin: 

1. Flowet udløses, når der føjes en ny fil til en bestemt OneDrive for Business-mappe 
2. Muhimbi-tjenesten konverterer den pågældende fil til PDF. 

I det sidste trin skal du tilføje en handling, der flytter PDF-dokumentet til en SharePoint Online-mappe, hvor teamet kan få adgang til det.  

1. Vælg **Nyt trin**, og vælg derefter **Tilføj en handling**.  Søg efter **SharePoint**, og vælg handlingen **SharePoint – Opret fil**. 
   
    ![](./media/learning-create-pdf/sharepoint-create-file.png)
2. Angiv følgende værdier i handlingen **Opret fil**:
   
   * **Webstedsadresse**: URL-adressen til dit SharePoint-websted.  
   * **Mappesti**: Vælg mappeikonet, og gå til mappen **PDF – Færdige filer**.
   * **Filnavn**: Fra listen over dynamisk indhold for **Konverter dokument** skal du vælge **Basisfilnavn** og derefter tilføje "**.pdf**", så filen gemmes i SharePoint med det filtypenavn. 
   * **Filindhold**: Fra listen over dynamisk indhold for **Konverter dokument** skal du vælge **Behandlet filindhold**.
3. Vælg **Opret flow** øverst på siden for at gemme dit arbejde.
   
    ![](./media/learning-create-pdf/sharepoint-configure-file.png)

## <a name="test-the-flow"></a>Test flowet
1. Du tester flowet ved at føje en ny fil til mappen **Færdige dokumenter** i OneDrive for Business. 
2. I Flow skal du vælge **Mine flow** og derefter vælge et nyt flow for at få vist kørselsoversigten. Som standard konfigureres flowet til at køre hvert femte minut. 
3. Når flowet har kørt, skal du kontrollere, at filen blev konverteret til PDF og gemt i SharePoint-mappen **PDF – Færdige filer**. 
   
    ![](./media/learning-create-pdf/test-the-flow.png)

