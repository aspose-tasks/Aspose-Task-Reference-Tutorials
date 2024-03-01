---
title: Att skriva och läsa MS-projektformler i Aspose.Tasks
linktitle: Skriv och läs formler i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig att skriva och läsa MS Project-formler effektivt med Aspose.Tasks för Java. Förbättra dina färdigheter i projektledning.
type: docs
weight: 12
url: /sv/java/formulas/write-read-formulas/
---
## Introduktion
Inom projektledningssfären är effektiv datahantering av största vikt. Aspose.Tasks för Java är en robust lösning som underlättar manipulering och extrahering av data från Microsoft Project-filer. En kraftfull funktion den erbjuder är möjligheten att skriva och läsa MS Project-formler. Den här handledningen guidar dig genom processen att utnyttja den här funktionen för att förbättra dina projektledningsuppgifter.
## Förutsättningar
Innan du dyker in i den här handledningen, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har Java installerat på ditt system.
2.  Aspose.Tasks for Java: Ladda ner och installera Aspose.Tasks for Java från[här](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Välj din föredragna IDE för Java-utveckling.

## Importera paket
För att börja, importera de nödvändiga paketen till ditt Java-projekt:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Steg 1: Ställ in datakatalog
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
```
I det här steget definierar du katalogen där dina MS Project-filer finns.
## Steg 2: Ladda projektfilen
```java
Project project = new Project(dataDir + "project.mpp");
```
Här laddar du MS Project-filen i en`Project` föremål för manipulation.
## Steg 3: Definiera anpassad formel
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
Detta steg innebär att skapa ett anpassat fält med en formel som fördubblar uppgiftskostnaden.
## Steg 4: Lägg till uppgift och ställ in kostnad
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Här läggs en ny uppgift till och kostnaden är satt till 100.
## Steg 5: Spara projektfil
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Slutligen, spara den ändrade projektfilen.

## Slutsats
I den här handledningen har vi utforskat hur man skriver och läser MS Project-formler med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt manipulera projektdata för att uppfylla dina specifika krav.
## FAQ's
### Är Aspose.Tasks kompatibel med alla versioner av MS Project?
Aspose.Tasks erbjuder kompatibilitet med olika versioner av MS Project, vilket säkerställer flexibilitet för användarna.
### Kan jag integrera Aspose.Tasks i mitt befintliga Java-projekt?
Absolut! Aspose.Tasks ger sömlös integration med Java-projekt genom enkel API-användning.
### Finns det några begränsningar för vilka typer av formler jag kan skapa?
Med Aspose.Tasks har du stor flexibilitet när det gäller att skapa skräddarsydda formler som är skräddarsydda för dina projektbehov.
### Stöder Aspose.Tasks distribution av flera plattformar?
Ja, Aspose.Tasks stöder distribution över flera plattformar, vilket förbättrar dess mångsidighet.
### Hur kan jag få teknisk support för Aspose.Tasks?
 För teknisk assistans och gemenskapsstöd, besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).