---
date: 2026-03-29
description: Leer hoe je trefwoorden en de aanmaakdatum instelt in een MPP‑project
  met Aspose.Tasks voor Java. Stapsgewijze gids met codevoorbeelden.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe trefwoorden instellen in MPP‑projectsamenvatting met Aspose.Tasks
url: /nl/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe trefwoorden instellen in MPP‑projectsamenvatting met Aspose.Tasks

## Introductie
In deze tutorial ontdek je **hoe trefwoorden in te stellen** en andere samenvattingsinformatie voor een MPP‑projectbestand met behulp van Aspose.Tasks voor Java. Of je nu auteursgegevens, revisienummers of een aangepaste aanmaakdatum wilt opnemen, deze gids leidt je stap voor stap door de exacte handelingen, compleet met kant‑klaar code. Aan het einde kun je trefwoorden instellen, set creation date java, en de gegevens weer uit het bestand ophalen.

## Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** Aspose.Tasks for Java  
- **Primair doel?** Trefwoorden, auteurinfo en aanmaakdatum instellen in een MPP‑bestand  
- **Hoeveel code‑stappen?** Drie eenvoudige codeblokken (initialiseren, opslaan, lezen)  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie  
- **Ondersteunde Java‑versie?** Java 8 en hoger  

## Wat is “hoe trefwoorden in te stellen” in een MPP‑bestand?
Trefwoorden zijn metadata‑velden die opgeslagen worden binnen een Microsoft Project (MPP)‑bestand. Ze helpen projecten te categoriseren, maken snel zoeken mogelijk en bieden contextuele informatie voor downstream‑tools. Aspose.Tasks stelt de eigenschap `Prj.KEYWORDS` beschikbaar, waardoor het eenvoudig is om deze waarde programmatisch te schrijven of bij te werken.

## Waarom Aspose.Tasks voor Java gebruiken om trefwoorden en aanmaakdatum in te stellen?
* **Volledige .MPP‑compatibiliteit** – werkt met alle Project 2007‑2023‑formaten.  
* **Geen COM‑ of Office‑installatie vereist** – pure Java, perfect voor server‑side omgevingen.  
* **Rijke API** – naast trefwoorden kun je auteur, revisie, opmerkingen en data in één oproep instellen.  
* **Prestaties geoptimaliseerd** – snelle lees‑/schrijfbewerkingen zelfs voor grote projectbestanden.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:
1. **Java Development Kit (JDK)** – JDK 8 of nieuwer geïnstalleerd.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, of een andere editor naar keuze.

## Importeer pakketten
Importeer eerst de klassen die je nodig hebt. Deze imports geven je toegang tot het `Project`‑object, de `Prj`‑enumeratie voor samenvattingsvelden, en de `SaveFileFormat`‑enum voor het opslaan.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Stap 1: Project instellen en samenvattingsinformatie definiëren
Maak een `Project`‑instantie aan en gebruik vervolgens de `set`‑methode om de gewenste metadata te schrijven. Let op hoe we **de trefwoorden instellen** en **set creation date java** gebruiken met een `Calendar`‑object.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Stap 2: Project‑samenvattingsinformatie opslaan
Nadat de velden zijn ingevuld, sla je de wijzigingen op. Hier slaan we het project op als XML voor eenvoudige inspectie, maar je kunt ook terug opslaan als MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Stap 3: Project‑samenvattingsinformatie lezen
Om te verifiëren dat de metadata correct is geschreven, laad je het bestand opnieuw en lees je elke eigenschap uit. Deze stap toont dat **hoe trefwoorden in te stellen** daadwerkelijk end‑to‑end werkt.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|----------|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | De kalender is nooit ingesteld vóór het opslaan. | Zorg ervoor dat je `project.set(Prj.CREATION_DATE, cal.getTime())` aanroept vóór `save()`. |
| **Keywords not appearing in Microsoft Project UI** | Het bestand werd als XML opgeslagen en direct in Project geopend. | Sla opnieuw op als MPP (`SaveFileFormat.MPP`) of open de XML via *Import* in Project. |
| **Date values shifted by timezone** | Java `Date` bevat tijdzone‑informatie. | Gebruik `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` als je UTC‑datums nodig hebt. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks voor Java gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Tasks voor Java kan naadloos worden geïntegreerd met andere Java‑bibliotheken om je projectmanagementmogelijkheden uit te breiden.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).

**Q: Hoe vaak wordt Aspose.Tasks voor Java bijgewerkt?**  
A: Aspose.Tasks voor Java wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste versies van Java en Microsoft Project‑bestanden te waarborgen.

**Q: Kan ik de project‑samenvattingsinformatie verder aanpassen?**  
A: Absoluut, Aspose.Tasks voor Java biedt uitgebreide opties om de project‑samenvattingsinformatie aan te passen aan jouw specifieke eisen.

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?**  
A: Je kunt ondersteuning krijgen via het Aspose.Tasks‑communityforum [hier](https://forum.aspose.com/c/tasks/15).

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}