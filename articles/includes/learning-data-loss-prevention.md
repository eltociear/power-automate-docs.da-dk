Med en voksende liste over [tjenester](https://flow.microsoft.com/services), der kan oprette arbejdsprocesser i [Power Automate](https://flow.microsoft.com), kan du være nødt til at beskytte følsomme eller vigtige forretningsdata, der lagres i virksomhedstjenester som SharePoint eller Salesforce. Du kan opleve, at din organisation er nødt til at oprette en politik, der sikrer, at følsomme forretningsdata ikke udgives på forbrugertjenester som Twitter og Facebook. Med Power Automate kan du nemt oprette politikker til [**forberedelse af datatab** (DLP)](https://docs.microsoft.com/power-platform/admin/prevent-data-loss), så du får en tæt styring med, hvilke forbrugertjenester dine forretningsdata kan deles med, når brugerne opretter flow.  

## <a name="terms-you-should-get-familiar-with"></a>Begreber, du bør være fortrolig med

| Begreb | Beskrivelse |
| --- | --- |
| **DLP** |Dette er en forkortelse for forebyggelse af datatab. Du skal oprette en DLP-politik for at administrere delingen af data mellem **tjenester**. |
| **Tjenester** |[Tjenester](https://flow.microsoft.com/services) er programmer som Salesforce, SharePoint og Twitter. Brug disse tjenester, og mange flere, til oprettelse af flows. |
| **Datagruppe** |En logisk gruppering af tjenester. Du placerer tjenester, der har tilladelse til at dele data, i den samme datagruppe. Der er to datagrupper: **Kun forretningsdata** og **Ingen forretningsdata tilladt**. |
| **Miljø** |En DLP anvendes på et [miljø](../environments-overview-admin.md). Et miljø indeholder brugere. |
| **Brugere** |Brugerne er medlemmer af den organisation, som en DLP-politik skal gælde for, baseret på deres medlemskab i et miljø. |
| **Flow** |Et flow er en arbejdsprocesapp, der bruger enhver kombination af de tilgængelige tjenester. |

## <a name="all-about-how-dlp-policies-work"></a>Alt om, hvordan DLP-politikker fungerer
En DLP-politik er blot en navngivet regel, der placerer hver tjeneste i en af to gensidigt udelukkende datagrupper. Denne regel anvendes derefter på et miljø. Et miljø er en logisk gruppering af brugere. Brugere har ikke tilladelse til at oprette flows, der deler data mellem de tjenester, du har placeret i forskellige datagrupper. Dine brugere kan med andre ord kun oprette flows, der deler data mellem tjenesterne inden for en **enkelt** datagruppe. Deling på tværs af datagrupper er ikke tilladt.  

| **Datagruppenavn** | **Beskrivelse af datagruppe** |
| --- | --- |
| **Kun forretningsdata** |Alle tjenester i denne gruppe kan dele data indbyrdes. De kan ikke dele data med datagruppen **Ingen forretningsdata tilladt**. |
| **Ingen forretningsdata tilladt** |Alle tjenester i denne gruppe kan dele data indbyrdes. De kan ikke dele data med datagruppen **Kun forretningsdata**. |

**Bemærk!** Når en tjeneste tilføjes i én datagruppe, fjernes den automatisk fra den anden datagruppe. Hvis Twitter f.eks. i øjeblikket er placeret i datagruppen **Kun forretningsdata**, og du ikke vil tillade, at forretningsdata deles på Twitter, skal du blot tilføje tjenesten Twitter til datagruppen **Ingen forretningsdata er tilladt**. Dette vil fjerne Twitter fra datagruppen **Kun forretningsdata**.

## <a name="heres-what-you-need-to-create-a-dlp"></a>Her er, hvad du skal bruge for at oprette en DLP
* Adgang til Power Automate [Power Platform Administration](https://admin.powerplatform.microsoft.com/)  
* En konto i administratorrollen for miljøet  
* Et miljø med brugere, der er tildelt til det  

## <a name="create-a-dlp-policy"></a>Opret en DLP-politik
Her er en hurtig oversigt over, hvordan du opretter en DLP-politik:  

1. Navngiv politikken
2. Vælg det miljø, hvor politikken skal anvendes
3. Tilføj tjenesterne til en af de to datagrupper. Husk, at kun tjenester, der er placeret i en bestemt gruppe, kan dele data. Så ethvert flow, der er oprettet til at dele data mellem tjenester, der er placeret i de to datagrupper, blokeres automatisk, når opretteren gemmer det.  

Der er også adgang til en mere [detaljeret gennemgang](https://docs.microsoft.com/power-platform/admin/prevent-data-loss) af DLP-politikker.  

## <a name="examples"></a>Eksempler
* Hvis du vil oprette en politik, der begrænser flow til kun at dele forretningsdata mellem SharePoint, Office 365-brugere, Office 365 Outlook, OneDrive for Business, Dynamics 365, SQL Server og Salesforce, vil den se ud på denne måde:  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* Sådan vil det se ud, hvis du beslutter at oprette en politik, der ikke tillader nogen som helst af medlemmerne af et bestemt miljø at oprette et flow, der deler SharePoint-data. Bemærk, at SharePoint er den eneste tjeneste i datagruppen **Kun forretningsdata**:  
  ![Kun forretningsdata](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

