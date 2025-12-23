---
date: 2025-12-23
description: Leer hoe u een MPP‑samenvatting maakt en de projectauteur bijwerkt met
  Aspose.Tasks voor Java. Stel projectinformatie in en haal deze moeiteloos op.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe een MPP-samenvatting maken en de projectauteur bijwerken met Aspose.Tasks
url: /nl/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MPP-projectsamenvatting schrijven in Aspose.Tasks

## Introductie
In deze tutorial maak je **MPP-samenvatting** informatie voor een Microsoft Project‑bestand en leer je hoe je **projectauteur** details bijwerkt met behulp van de Aspose.Tasks‑bibliotheek voor Java. Of je nu een project‑managementtool bouwt of rapportage automatiseert, het programmatisch beheren van samenvattende eigenschappen bespaart tijd en zorgt voor consistentie in al je projecten.

## Snelle antwoorden
- **Wat betekent “create MPP summary”?** Het betekent het instellen van de hoog‑niveau projecteigenschappen (author, revision, keywords, etc.) die verschijnen in het dialoogvenster Project Summary Information van Microsoft Project.  
- **Welke bibliotheek behandelt dit?** Aspose.Tasks for Java biedt een fluente API om die eigenschappen te lezen en te schrijven.  
- **Heb ik een licentie nodig?** Er is een gratis proefversie beschikbaar, maar een commerciële licentie is vereist voor productiegebruik.  
- **Kan ik de auteur ook wijzigen nadat het bestand is opgeslagen?** Ja – je kunt **projectauteur bijwerken** door `project.set(Prj.AUTHOR, "New Author")` aan te roepen en vervolgens het bestand opnieuw op te slaan.  
- **Welke bestandsformaten worden ondersteund?** Zowel MPP als XML (SaveFileFormat.Xml) worden volledig ondersteund.

## Wat is create MPP summary?
Het maken van een MPP‑samenvatting houdt in dat je de metadata van het project invult — author, revision‑nummer, keywords, comments, creation‑date en printed‑date. Deze metadata wordt opgeslagen in het record Project Summary Information en wordt weergegeven in de **File → Info**‑sectie van Microsoft Project.

## Waarom projectauteur bijwerken?
Het nauwkeurig houden van de **projectauteur**‑informatie is essentieel voor audit‑trails, samenwerking en rapportage. Wanneer meerdere teamleden bijdragen, moet je mogelijk de **projectauteur** bijwerken om de laatste wijzigingen weer te geven of het werk correct toe te wijzen.

## Vereisten
1. Java Development Kit (JDK) geïnstalleerd op je machine.  
2. Aspose.Tasks for Java – download het vanaf [hier](https://releases.aspose.com/tasks/java/).  
3. Een IDE zoals IntelliJ IDEA, Eclipse of NetBeans.

## Pakketten importeren
Importeer eerst de benodigde pakketten in je Java‑klasse:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Stap 1: Project instellen en samenvattingsinformatie definiëren
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
In de bovenstaande code maken we **MPP‑samenvatting**‑velden zoals author, revision en keywords. Je kunt later ook de **projectauteur** bijwerken door `project.set(Prj.AUTHOR, "New Name")` aan te roepen.

## Stap 2: Project‑samenvattingsinformatie opslaan
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Het opslaan van het project bewaart alle samenvattingsgegevens die je zojuist hebt gedefinieerd.

## Stap 3: Project‑samenvattingsinformatie lezen
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Dit fragment toont hoe je de samenvattingsinformatie **terugleest**, waarmee wordt bevestigd dat de **create MPP summary**‑operatie geslaagd is.

## Veelvoorkomende problemen en oplossingen
- **Null‑waarden na het lezen:** Zorg ervoor dat het project succesvol is opgeslagen voordat je het opnieuw laadt. Controleer bestands‑paden en rechten.  
- **Verschillen in datumopmaak:** `project.get(Prj.CREATION_DATE)` retourneert een `java.util.Date`. Gebruik `SimpleDateFormat` als je een aangepast weergaveformaat nodig hebt.  
- **Licentie niet ingesteld:** Zonder een geldige licentie draait Aspose.Tasks in evaluatiemodus en kan een watermerk worden toegevoegd. Registreer je licentie vroeg in de code.

## Veelgestelde vragen
**Q: Kan ik Aspose.Tasks for Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Tasks for Java kan naadloos worden geïntegreerd met andere Java‑bibliotheken om je project‑managementmogelijkheden te verbeteren.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks for Java?**  
A: Ja, je kunt een gratis proefversie downloaden vanaf [hier](https://releases.aspose.com/).

**Q: Hoe vaak wordt Aspose.Tasks for Java bijgewerkt?**  
A: Aspose.Tasks for Java wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste versies van Java en Microsoft Project‑bestanden te waarborgen.

**Q: Kan ik de project‑samenvattingsinformatie verder aanpassen?**  
A: Absoluut, Aspose.Tasks for Java biedt uitgebreide opties om de project‑samenvattingsinformatie aan te passen aan je specifieke eisen.

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Tasks for Java?**  
A: Je kunt ondersteuning krijgen via het Aspose.Tasks‑communityforum [hier](https://forum.aspose.com/c/tasks/15).

## Conclusie
In deze tutorial hebben we laten zien hoe je **MPP‑samenvatting**‑gegevens maakt, de **projectauteur** bijwerkt, en die wijzigingen verifieert met Aspose.Tasks for Java. Door deze stappen te automatiseren krijg je volledige controle over projectmetadata, waardoor je applicaties robuuster worden en je projectrapporten nauwkeuriger.

---

**Laatst bijgewerkt:** 2025-12-23  
**Getest met:** Aspose.Tasks for Java 24.10  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}