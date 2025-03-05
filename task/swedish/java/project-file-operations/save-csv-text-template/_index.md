---
title: Spara som CSV, text och mall i Aspose.Tasks
linktitle: Spara som CSV, text och mall i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du sparar Microsoft Project-filer i CSV-, text- och mallformat med Aspose.Tasks för Java.
type: docs
weight: 16
url: /sv/java/project-file-operations/save-csv-text-template/
---
## Introduktion
den här handledningen kommer vi att utforska hur man sparar projektfiler i olika format som CSV, text och mall med Aspose.Tasks för Java. Aspose.Tasks är ett kraftfullt Java-bibliotek som låter utvecklare arbeta med Microsoft Project-filer utan att Microsoft Project behöver installeras.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Tasks för Java-bibliotek nedladdade och konfigurerade i ditt Java-projekt. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
3. Grundläggande kunskaper i programmeringsspråket Java.

## Importera paket
Först måste du importera de nödvändiga paketen i din Java-fil:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Spara projekt som CSV
Låt oss dela upp stegen för att spara ett projekt som CSV:
### Steg 1: Ladda projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Steg 2: Spara som CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Spara projekt som text
Så här kan du spara ett projekt som text:
### Steg 1: Ladda projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Steg 2: Spara som text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Spara projekt som mall
Att spara ett projekt som en mall innebär följande steg:
### Steg 1: Ladda projektet
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Steg 2: Ställ in mallalternativ
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Steg 3: Spara som mall
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Slutsats
den här handledningen har vi lärt oss hur man sparar Microsoft Project-filer som CSV, text och mall med Aspose.Tasks för Java. Med dessa enkla steg kan du effektivt hantera dina projektfiler i olika format, vilket ökar din produktivitet som Java-utvecklare.
## FAQ's
### F: Kan Aspose.Tasks för Java hantera komplexa projektfiler?
A: Absolut! Aspose.Tasks för Java kan hantera projekt av varierande komplexitet med lätthet, vilket ger omfattande stöd för Microsoft Project-filformat.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan få en gratis provversion av Aspose.Tasks för Java från[här](https://releases.aspose.com/).
### F: Var kan jag hitta support för Aspose.Tasks för Java?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för all hjälp eller frågor angående Aspose.Tasks för Java.
### F: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?
 S: Ja, du kan köpa en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/), så att du kan utvärdera bibliotekets fulla potential.
### F: Är Aspose.Tasks för Java kompatibelt med olika operativsystem?
S: Ja, Aspose.Tasks för Java är kompatibelt med olika operativsystem, inklusive Windows, macOS och Linux.