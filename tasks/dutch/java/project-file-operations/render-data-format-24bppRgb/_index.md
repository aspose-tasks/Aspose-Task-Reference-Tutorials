---
date: 2025-12-17
description: Leer hoe u een project als afbeelding opslaat en de afbeeldingsresolutie
  wijzigt in Java met Aspose.Tasks voor Java. Deze stapsgewijze handleiding toont
  het renderen van MS‑Project‑gegevens met het 24bppRgb‑formaat.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Project opslaan als afbeelding – 24bppRgb‑formaat met Aspose.Tasks
url: /nl/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project opslaan als afbeelding – 24bppRgb-formaat met Aspose.Tasks

## Introduction
In deze tutorial leer je hoe je **save project as image** kunt gebruiken met het 24bppRgb-pixelformaat met Aspose.Tasks voor Java. Het renderen van MS Project-gegevens naar een afbeelding is handig wanneer je een visueel momentopname van een planning wilt delen, een tijdlijn in een rapport wilt insluiten, of miniaturen voor een project‑portal wilt genereren. We laten je ook zien hoe je **change image resolution java** kunt aanpassen om aan je kwaliteitsvereisten te voldoen.

## Quick Answers
- **Kan ik een project renderen naar een afbeelding?** Ja, Aspose.Tasks laat je een project opslaan als TIFF, PNG, JPEG, enz.  
- **Welk pixelformaat biedt de beste kleurdiepte?** `Format24bppRgb` levert true‑color (24‑bit) afbeeldingen.  
- **Hoe pas ik de afbeeldingsresolutie aan?** Gebruik `setHorizontalResolution` en `setVerticalResolution` op `ImageSaveOptions`.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor niet‑evaluatiegebruik.  
- **Is dit compatibel met alle Java‑versies?** Werkt met Java 8 en nieuwer.

## What is “save project as image”?
Het opslaan van een project als afbeelding zet de visuele weergave van een Microsoft Project‑bestand (`.mpp`) om naar een rasterformaat (bijv. TIFF). Het resulterende bestand kan worden weergegeven in browsers, ingevoegd in documenten, of afgedrukt zonder de originele Project‑applicatie nodig te hebben.

## Why use the 24bppRgb format?
Het 24bppRgb-pixelformaat slaat elke pixel op met 8 bits voor rood, groen en blauw, en levert true‑color kwaliteit zonder een alfakanaal. Dit is ideaal voor rapporten met hoge helderheid waar kleurnauwkeurigheid belangrijk is, terwijl de bestandsgrootte redelijk blijft vergeleken met 32‑bit formaten.

## Prerequisites
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

1. **Java Development Kit (JDK)** – JDK 8 of nieuwer geïnstalleerd op je machine.  
2. **Aspose.Tasks for Java** – Download en installeer van [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – Vertrouwdheid met Java‑syntaxis en projectopzet helpt je de code‑fragmenten te volgen.

## Import Packages
Importeer eerst de benodigde Aspose.Tasks‑klassen in je Java‑project:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Vervang `"Your Data Directory"` door het absolute pad waar je `.mpp`‑bestand zich bevindt.

### Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
Deze regel leest het Microsoft Project‑bestand (`project.mpp`) en maakt een `Project`‑object aan dat Aspose.Tasks kan manipuleren.

### Step 3: Configure Image Save Options
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Hier stellen we het uitvoerformaat in op TIFF, geven we een resolutie van **72 dpi** op (je kunt deze waarden aanpassen aan je behoeften – dit is waar je **change image resolution java**), en selecteren we het 24bppRgb-pixelformaat voor true‑color output.

### Step 4: Save Project Data as Image
```java
project.save(dataDir + "resFile.tif", options);
```
De `save`‑methode schrijft de gerenderde afbeelding naar `resFile.tif` met de hierboven gedefinieerde opties.

## Common Issues and Solutions
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Blank image output** | De projectweergave kan leeg zijn. | Roep `project.setDefaultView(ViewType.Gantt);` aan vóór het opslaan. |
| **Low‑quality image** | Resolutie te laag ingesteld. | Verhoog `setHorizontalResolution` en `setVerticalResolution` (bijv. 150 dpi). |
| **Unsupported pixel format** | Gebruik van een oudere Aspose.Tasks‑versie. | Upgrade naar de nieuwste Aspose.Tasks for Java‑release. |

## Conclusion
Je weet nu hoe je **save project as image** kunt uitvoeren met het 24bppRgb-formaat en de resolutie kunt aanpassen met Aspose.Tasks voor Java. Deze aanpak stelt je in staat duidelijke, kleurnauwkeurige visuele weergaven van je projectschema's te genereren voor delen, rapportage of archiveringsdoeleinden.

## FAQ's
### Q: Kan ik projectgegevens renderen in andere afbeeldingsformaten?
A: Ja, Aspose.Tasks ondersteunt het renderen van projectgegevens naar verschillende afbeeldingsformaten zoals PNG, JPEG, BMP, enz.

### Q: Is Aspose.Tasks compatibel met verschillende versies van MS Project?
A: Ja, Aspose.Tasks ondersteunt meerdere versies van MS Project, inclusief 2003, 2007, 2010, 2013 en 2016.

### Q: Kan ik de resolutie en het pixelformaat van de gerenderde afbeelding aanpassen?
A: Ja, je kunt de resolutie en het pixelformaat aanpassen aan je eisen met behulp van Aspose.Tasks.

### Q: Vereist Aspose.Tasks een licentie voor commercieel gebruik?
A: Ja, je moet een licentie aanschaffen voor commercieel gebruik van Aspose.Tasks. Je kunt een tijdelijke licentie voor testdoeleinden verkrijgen via [here](https://purchase.aspose.com/temporary-license/).

### Q: Waar kan ik ondersteuning krijgen voor Aspose.Tasks?
A: Je kunt ondersteuning voor Aspose.Tasks krijgen via het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}