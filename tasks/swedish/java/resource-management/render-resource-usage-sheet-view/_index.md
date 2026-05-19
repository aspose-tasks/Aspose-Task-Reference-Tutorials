---
date: 2026-01-15
description: Lär dig hur du sparar projekt som PDF och renderar MS Project Resource
  Usage‑ och Sheet‑vyer med Aspose.Tasks för Java. Följ vår steg‑för‑steg‑guide för
  att enkelt exportera projektet till PDF.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Spara projekt som PDF – rendera resursanvändning och bladvy i Aspose.Tasks
url: /sv/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara projekt som PDF – Rendera resursanvändning och bladvy i Aspose.Tasks

## Introduction
I den här handledningen kommer du att upptäcka hur du **sparar projekt som PDF** samtidigt som du renderar vyerna Resursanvändning och Blad i en Microsoft Project‑fil. Oavsett om du behöver skapa en utskrivbar rapport för intressenter eller konvertera MPP‑filer till ett universellt läsbart format, gör Aspose.Tasks för Java processen enkel – ingen Microsoft Project‑installation krävs.

## Quick Answers
- **Vad gör “save project as pdf”?** Det konverterar en projektfil (MPP) till ett PDF‑dokument som bevarar den valda vyn.  
- **Vilken vy kan exporteras?** Resursanvändning, Blad, Gantt, Uppgiftsanvändning och fler.  
- **Kan jag ändra tidslinjen i PDF‑filen?** Ja – alternativ inkluderar Days, ThirdsOfMonths och Months.  
- **Behöver jag ha Microsoft Project installerat?** Nej, Aspose.Tasks fungerar oberoende.  
- **Krävs en licens för produktion?** Ja, en kommersiell licens behövs för icke‑testanvändning.

## What is “save project as PDF”?
Att spara ett projekt som PDF skapar en statisk, högupplöst representation av en vald projektvy. Detta är idealiskt för delning med kunder, arkivering eller utskrift utan att avslöja den underliggande projektfilen.

## Why use Aspose.Tasks to export project to PDF?
- **Inga externa beroenden** – fungerar på alla plattformar som stöder Java.  
- **Finjusterad kontroll** – du kan välja vy, tidslinje och layout.  
- **Hög noggrannhet** – PDF‑filen speglar exakt utseendet på den ursprungliga projektvyn.  
- **Automatiseringsklar** – integrera i CI‑pipelines, rapporttjänster eller batch‑konverterare.

## Prerequisites
Innan vi börjar, se till att du har:

1. **Java Development Kit (JDK)** – senaste versionen rekommenderas.  
2. **Aspose.Tasks for Java** – ladda ner från [download page](https://releases.aspose.com/tasks/java/).  

## Import Packages
Först, importera de nödvändiga klasserna till ditt Java‑projekt:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Step‑by‑Step Guide

### Step 1: Read the Source Project
Läs in MPP‑filen du vill konvertera.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Step 2: Define SaveOptions with Required Timescale (Export Project to PDF)
Konfigurera PDF‑exportalternativen och ange önskad tidslinje.  
*Här använder vi **Days** som exempel.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Step 3: Set the Presentation Format to ResourceUsage
Välj den vy du vill rendera. I detta fall **Resource Usage**‑vyn.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Step 4: Save the Project (Convert MPP to PDF)
Utför konverteringen och generera PDF‑filen.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Step 5: Render Views for Other Timescale Settings (Change Timescale PDF)
Upprepa föregående steg för att producera PDF‑filer med olika tidslinjer såsom **ThirdsOfMonths** och **Months**.

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

## Common Issues and Solutions
- **File not found errors** – Verifiera att `dataDir` pekar på rätt mapp och att MPP‑filnamnet är exakt korrekt.  
- **Blank PDF output** – Säkerställ att `PresentationFormat` matchar en vy som innehåller data (t.ex. ResourceUsage).  
- **Incorrect timescale** – Dubbelkolla att `options.setTimescale()` anropas innan varje `project.save()`.

## Frequently Asked Questions

### Can Aspose.Tasks render other views besides Resource Usage and Sheet?
Aspose.Tasks stöder rendering av olika vyer såsom Gantt‑diagram, Uppgiftsanvändning och Kalender‑vyer, bland andra.

### Is Aspose.Tasks compatible with different versions of Microsoft Project files?
Ja, Aspose.Tasks stödjer ett brett spektrum av Microsoft Project‑filformat, inklusive MPP, MPT och XML‑format.

### Can I customize the appearance of rendered views using Aspose.Tasks?
Absolut! Aspose.Tasks erbjuder omfattande alternativ för att anpassa utseendet och layouten på renderade vyer så att de passar dina specifika krav.

### Does Aspose.Tasks require Microsoft Project to be installed on the system?
Nej, Aspose.Tasks är ett fristående bibliotek och kräver ingen installation av Microsoft Project för att fungera.

### Is technical support available for Aspose.Tasks users?
Ja, Aspose.Tasks‑användare kan få teknisk support via [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---