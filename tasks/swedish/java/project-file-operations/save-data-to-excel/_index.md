---
title: Spara MS Project Data till Excel i Aspose.Tasks
linktitle: Spara data till Excel i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du sparar Microsoft Project-data till Excel-filer med Aspose.Tasks för Java. Enkel integration för Java-utvecklare.
weight: 19
url: /sv/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara MS Project Data till Excel i Aspose.Tasks

## Introduktion
Aspose.Tasks för Java är ett kraftfullt bibliotek som låter utvecklare arbeta med Microsoft Project-filer programmatiskt. I den här handledningen guidar vi dig genom processen att spara data från en projektfil till en Excel-fil steg för steg.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har Java installerat på ditt system. Du kan ladda ner och installera den senaste versionen av JDK från Oracles webbplats.
2.  Aspose.Tasks for Java Library: Ladda ner Aspose.Tasks for Java-biblioteket från[nedladdningslänk](https://releases.aspose.com/tasks/java/) och inkludera det i ditt Java-projekt.

## Importera paket
Först måste du importera de nödvändiga paketen i din Java-kod för att fungera med Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Låt oss dela upp exemplet i flera steg:
## Steg 1: Definiera sökvägen för datakatalogen
```java
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"`med sökvägen till din datakatalog där projektfilen finns.
## Steg 2: Ladda projektfilen
```java
Project project = new Project(dataDir + "project5.mpp");
```
Denna kodrad laddar projektfilen med namnet "project5.mpp" från den angivna datakatalogen.
## Steg 3: Spara projektet som XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Här, den`save` metod används för att spara den laddade projektfilen som en Excel-fil med namnet "project1.xlsx" i samma datakatalog. Vi specificerar`SaveFileFormat.Xlsx` parameter för att spara den i XLSX-format.

## Slutsats
I den här handledningen har vi lärt oss hur man sparar data från en Microsoft Project-fil till en Excel-fil med Aspose.Tasks för Java. Genom att följa de medföljande stegen kan du sömlöst integrera denna funktion i dina Java-applikationer.
## FAQ's
### Kan jag använda Aspose.Tasks för Java för att manipulera projektdata programmatiskt?
Ja, Aspose.Tasks för Java tillhandahåller omfattande funktioner för att manipulera projektdata, inklusive att läsa, skriva och ändra projektfiler.
### Finns det en gratis testversion tillgänglig för Aspose.Tasks för Java?
 Ja, du kan ladda ner en gratis testversion av Aspose.Tasks för Java från[här](https://releases.aspose.com/).
### Var kan jag hitta dokumentation för Aspose.Tasks för Java?
Du kan hitta dokumentationen för Aspose.Tasks för Java[här](https://reference.aspose.com/tasks/java/).
### Hur kan jag få support för eventuella problem eller frågor relaterade till Aspose.Tasks för Java?
 Du kan få support genom att besöka Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).
### Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?
 Ja, du kan köpa en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
