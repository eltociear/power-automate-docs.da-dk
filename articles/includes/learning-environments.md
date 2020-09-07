## <a name="what-is-an-environment"></a>Hvad er et miljø:
Et miljø er et virtuelt område, der bruges til at gemme, administrere og dele apps, flow og forretningsdata i Common Data Service. Miljøer er geolokaliseret, så alle apps og data, der er gemt i en database i et miljø, er også geolokaliseret.  

## <a name="terms-you-should-get-familiar-with"></a>Begreber, du bør være fortrolig med

| **Begreb** | **Beskrivelse** |
| --- | --- |
| **Administration** |Administration er en [webportal](https://admin.powerplatform.microsoft.com/) til administration af alle dine miljøer og politikker til forebyggelse af datatab. |
| **Common Data Service** |Med Common Data Service kan du føje datalagring og modelleringsfunktioner til dine apps. |
| **Miljøroller** |De to miljøroller er Miljøadministrator og Miljøopretter. |
| **Brugerroller** |De to standardbrugerroller er Organisationsbruger og Databaseejer. Du kan tilføje roller og tilknytte tilladelser til disse roller. |

## <a name="purposes-for-an-environment"></a>Formål med et miljø
Du kan bruge miljøer til at:  

* Adskille apps, flows og virksomhedsdata baseret på forskellige roller, sikkerhedskrav eller brugere.  
* Adskille apps, flows og virksomhedsdata baseret på placeringen af dine teams eller afdelinger.
* Administrere test- og produktionsmiljøer.  

## <a name="how-to-use-environments"></a>Sådan bruges miljøer
Miljøer kan tjene flere forskellige formål, afhængigt af organisationens behov, som eksempler kan nævnes:  

* Du kan vælge at oprette alle dine apps og flows i et enkelt miljø. 
* Du kan vælge at oprette et miljø til forskellige typer af apps og flows. Du kan f.eks. oprette et miljø til test og et andet miljø til produktion.  
* Du kan også vælge at oprette miljøer baseret på organisationens struktur eller endda baseret på den geografisk placering af dine teams eller afdelinger. Hvis du f.eks. har teams i Australien, Mexico og Europa, kan du skabe et miljø for hver af disse placeringer og administrere dem uafhængigt.  

**Bemærk!** Miljøer er ikke synlige for brugerne, så de behøver ikke at bekymre om, hvilke miljøer de befinder sig i. Miljøer er et værktøj til administratorer til at kategorisere, administrere og dele organisatoriske apps og flows.  

## <a name="what-are-roles"></a>Hvad er roller?
En person med adgang til et miljø skal enten være tildelt rollen **Miljøadministrator** eller **Miljøopretter**. Miljøadministratorer kan udføre alle administrative opgaver i et miljø. En miljøopretter kan oprette ressourcer i et eksisterende miljø. En person kan have begge roller samtidig.  

**Bemærk**! Alle Flow-brugere har adgang til et standardmiljø, når brugerne har fået adgang til Power Automate. Brugere kan have adgang til flere miljøer.  

## <a name="create-an-environment"></a>Opret et miljø
Du opretter miljøer fra [Power Platform Administration](https://admin.powerplatform.microsoft.com/) ved hjælp af disse trin:  

1. Navngiv dit miljø.
2. Vælg et område, hvor miljøet skal hostes.
3. Eller du kan vælge at oprette en database til dit miljø. Du kan oprette en database, når du har oprettet et miljø, hvis du ønsker.
4. Og du kan vælge, hvem der har adgang til databasen. Du kan enten begrænse adgangen eller give alle adgang til databasen. 

## <a name="add-users-to-an-environment"></a>Tilføje brugere i et miljø
Når du har oprettet et miljø, kan du tilføje brugere til enten rollen Miljøadministrator eller rollen Miljøopretter. Som med alle andre administrative opgaver gør du dette fra Administration.  

Når du har oprettet miljøet og tilføjet brugere, vil du måske oprette en politik til forebyggelse af datatab (DLP) som en hjælp til at styre brugen af dine forretningsdata. Det beskriver vi i næste emne. 

