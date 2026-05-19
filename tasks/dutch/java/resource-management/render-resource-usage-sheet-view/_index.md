---
date: 2026-01-15
description: Leer hoe u een project als PDF opslaat en de Resource Usage‑ en Sheet‑weergaven
  van MS Project rendert met Aspose.Tasks voor Java. Volg onze stapsgewijze handleiding
  om moeiteloos een project naar PDF te exporteren.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Project opslaan als PDF – Resourcegebruik en bladweergave renderen in Aspose.Tasks
url: /nl/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project opslaan als PDF – Resource Usage en Sheet‑weergave renderen in Aspose.Tasks

## Inleiding
In deze tutorial ontdek je hoe je een **project opslaat als PDF** terwijl je de Resource Usage‑ en Sheet‑weergaven van een Microsoft Project‑bestand rendert. Of je nu een afdrukbaar rapport voor belanghebbenden moet genereren of MPP‑bestanden wilt omzetten naar een universeel bekijkbaar formaat, Aspose.Tasks voor Java maakt het proces eenvoudig—geen Microsoft Project‑installatie vereist.

## Snelle antwoorden
- **Wat doet “project opslaan als pdf”?** Het converteert een Project‑bestand (MPP) naar een PDF‑document waarbij de geselecteerde weergave behouden blijft.  
- **Welke weergave kan worden geëxporteerd?** Resource Usage, Sheet, Gantt, Task Usage en meer.  
- **Kan ik de tijdschaal in de PDF wijzigen?** Ja—opties omvatten Days, ThirdsOfMonths en Months.  
- **Heb ik Microsoft Project geïnstalleerd nodig?** Nee, Aspose.Tasks werkt onafhankelijk.  
- **Is een licentie vereist voor productie?** Ja, een commerciële licentie is nodig voor niet‑trial gebruik.

## Wat is “project opslaan als PDF”?
Een project opslaan als PDF creëert een statische, hoge‑resolutie‑representatie van een gekozen Project‑weergave. Dit is ideaal voor delen met klanten, archiveren of afdrukken zonder het onderliggende projectbestand bloot te stellen.

## Waarom Aspose.Tasks gebruiken om een project naar PDF te exporteren?
- **Geen externe afhankelijkheden** – werkt op elk platform dat Java ondersteunt.  
- **Fijnmazige controle** – je kunt de weergave, tijdschaal en lay‑out selecteren.  
- **Hoge getrouwheid** – de PDF spiegelt het uiterlijk van de originele Project‑weergave.  
- **Automatisering‑klaar** – integreer in CI‑pipelines, rapportageservices of batch‑converters.

## Voorvereisten
Voordat we beginnen, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – de nieuwste versie wordt aanbevolen.  
2. **Aspose.Tasks for Java** – download van de [download page](https://releases.aspose.com/tasks/java/).  

## Pakketten importeren
Importeer eerst de benodigde klassen in je Java‑project:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Stapsgewijze handleiding

### Stap 1: Lees het bronproject
Laad het MPP‑bestand dat je wilt converteren.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Stap 2: Definieer SaveOptions met vereiste tijdschaal (Project exporteren naar PDF)
Configureer de PDF‑exportopties en stel de gewenste tijdschaal in.  
*Hier gebruiken we **Days** als voorbeeld.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Stap 3: Stel het Presentatieformaat in op ResourceUsage
Kies de weergave die je wilt renderen. In dit geval de **Resource Usage**‑weergave.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Stap 4: Sla het project op (MPP naar PDF converteren)
Voer de conversie uit en genereer het PDF‑bestand.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Stap 5: Render weergaven voor andere tijdschaal‑instellingen (Tijdschaal PDF wijzigen)
Herhaal de vorige stappen om PDF‑bestanden te maken met verschillende tijdschalen, zoals **ThirdsOfMonths** en **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Veelvoorkomende problemen en oplossingen
- **Bestand niet gevonden‑fouten** – Controleer of `dataDir` naar de juiste map wijst en of de MPP‑bestandsnaam exact overeenkomt.  
- **Lege PDF‑output** – Zorg ervoor dat `PresentationFormat` overeenkomt met een weergave die gegevens bevat (bijv. ResourceUsage).  
- **Onjuiste tijdschaal** – Controleer of `options.setTimescale()` wordt aangeroepen vóór elke `project.save()`.

## Veelgestelde vragen

### Kan Aspose.Tasks andere weergaven renderen naast Resource Usage en Sheet?
Aspose.Tasks ondersteunt het renderen van diverse weergaven zoals Gantt Chart, Task Usage en Calendar‑weergaven, onder andere.

### Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?
Ja, Aspose.Tasks ondersteunt een breed scala aan Microsoft Project‑bestandsformaten, waaronder MPP, MPT en XML‑formaten.

### Kan ik het uiterlijk van gerenderde weergaven aanpassen met Aspose.Tasks?
Absoluut! Aspose.Tasks biedt uitgebreide opties om het uiterlijk en de lay‑out van gerenderde weergaven aan te passen aan jouw specifieke eisen.

### Vereist Aspose.Tasks dat Microsoft Project op het systeem is geïnstalleerd?
Nee, Aspose.Tasks is een zelfstandige bibliotheek en vereist geen installatie van Microsoft Project voor het functioneren.

### Is technische ondersteuning beschikbaar voor Aspose.Tasks‑gebruikers?
Ja, Aspose.Tasks‑gebruikers kunnen technische ondersteuning krijgen via het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---