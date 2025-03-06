---
title: Rendera resursanvändning och arkvy i Aspose.Tasks
linktitle: Rendera resursanvändning och arkvy i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du återger MS Project Resource Usage och Sheet-vyer i Aspose.Tasks för Java. Följ vår steg-för-steg-guide för att generera detaljerade PDF-rapporter utan ansträngning.
type: docs
weight: 16
url: /sv/java/resource-management/render-resource-usage-sheet-view/
---
## Introduktion
I den här handledningen kommer vi att lära oss hur man använder Aspose.Tasks för Java för att återge MS Project Resource Usage och Sheet-vyer. Aspose.Tasks är ett kraftfullt Java-bibliotek som låter utvecklare arbeta med Microsoft Project-filer utan att Microsoft Project behöver installeras.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar installerade och konfigurerade:
1. Java Development Kit (JDK): Se till att du har Java Development Kit installerat på ditt system. Du kan ladda ner och installera den senaste versionen av JDK från Oracles webbplats.
2.  Aspose.Tasks for Java: Ladda ner och installera Aspose.Tasks for Java-biblioteket från[nedladdningssida](https://releases.aspose.com/tasks/java/).

## Importera paket
Först måste du importera de nödvändiga paketen till ditt Java-projekt:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Steg 1: Läs källprojektet
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
// Läs källan Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
I det här steget anger vi sökvägen till källprojektfilen (`ResourceUsageView.mpp` ) och använd`Project` klass att läsa den.
## Steg 2: Definiera SaveOptions med nödvändiga tidsskalainställningar
```java
// Definiera Sparaalternativen med nödvändiga tidsskalainställningar som dagar
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Här definierar vi`SaveOptions` med det erforderliga`TimeScale` inställningar. I det här exemplet ställer vi in`TimeScale` till dagar.
## Steg 3: Ställ in presentationsformatet till ResourceUsage
```java
// Ställ in presentationsformatet till ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Vi ställer in presentationsformatet till`ResourceUsage`, vilket indikerar att vi vill återge vyn Resursanvändning.
## Steg 4: Spara projektet
```java
// Spara projektet
project.save(dataDir + days, options);
```
Slutligen sparar vi projektet med de angivna alternativen. I det här exemplet kommer utdatafilen att sparas som`result_days.pdf`.
## Steg 5: Återge vyer för andra tidsskalainställningar
Upprepa steg 2 till 4 för att återge vyer med olika tidsskalainställningar (ThirdsOfMonths och Months).
```java
// Ställ in inställningarna för tidsskala till ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Spara projektet
project.save(thirds, options);
// Ställ in inställningarna för tidsskala till månader
options.setTimescale(Timescale.Months);
// Spara projektet
project.save(dataDir + months, options);
```
 Se till att ändra`Timescale` inställningar för varje vy.

## Slutsats
I den här handledningen har vi utforskat hur man använder Aspose.Tasks för Java för att återge MS Project Resource Usage och Sheet-vyer. Genom att följa stegen som beskrivs ovan kan du effektivt generera dessa vyer i PDF-format, vilket underlättar bättre visualisering och analys av dina projektdata.
## FAQ's
### Kan Aspose.Tasks återge andra vyer förutom resursanvändning och ark?
Aspose.Tasks stöder rendering av olika vyer såsom Gantt-diagram, uppgiftsanvändning och kalendervyer, bland annat.
### Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project-filer?
Ja, Aspose.Tasks stöder ett brett utbud av Microsoft Project-filformat, inklusive MPP-, MPT- och XML-format.
### Kan jag anpassa utseendet på renderade vyer med Aspose.Tasks?
Absolut! Aspose.Tasks erbjuder omfattande alternativ för att anpassa utseendet och layouten för renderade vyer för att passa dina specifika krav.
### Kräver Aspose.Tasks att Microsoft Project är installerat på systemet?
Nej, Aspose.Tasks är ett fristående bibliotek och kräver inte att Microsoft Project är installerat för att det ska fungera.
### Finns teknisk support tillgänglig för Aspose.Tasks-användare?
 Ja, Aspose.Tasks-användare kan ta del av teknisk support via[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).