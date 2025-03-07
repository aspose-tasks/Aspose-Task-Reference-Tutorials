---
title: Skriv ut sidor för att separera bild i Aspose.Tasks
linktitle: Skriv ut sidor för att separera bild i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du skriver ut sidor för att separera bilder i Aspose.Tasks för Java. Förbättra projektvisualiseringen med denna steg-för-steg-guide.
weight: 22
url: /sv/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skriv ut sidor för att separera bild i Aspose.Tasks

## Introduktion
I den här handledningen guidar vi dig genom processen att skriva ut sidor för att separera bilder med Aspose.Tasks för Java. Denna funktion kan vara särskilt användbar när du behöver visualisera projektlayouter eller kritiska uppgifter separat.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner den från[här](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Ladda ner och inkludera Aspose.Tasks for Java-biblioteket i ditt projekt. Du kan få det från[här](https://releases.aspose.com/tasks/java/).

## Importera paket
Se till att importera de nödvändiga paketen i början av din Java-fil:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Steg 1: Ladda projektdata
Ladda först projektdata från din MPP-fil:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Steg 2: Ställ in alternativ för bildspar
Definiera alternativen för att spara bilden, inklusive startdatum, slutdatum, viktiga uppgifter, förklaring och rutnät:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Steg 3: Anpassa rutnät
Anpassa rutnät för bilden, ange typ, färg och mönster:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Steg 4: Spara bilder
Spara projektlayouten som bilder, både som en enskild fil och separata filer:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Slutsats
I den här handledningen har vi demonstrerat hur man skriver ut sidor för att separera bilder med Aspose.Tasks för Java. Genom att följa stegen som beskrivs ovan kan du effektivt visualisera projektlayouter och kritiska uppgifter enligt dina krav.
## FAQ's
### F: Kan jag anpassa bildformatet när jag sparar projektlayouter?
 S: Ja, Aspose.Tasks för Java stöder olika bildformat som PNG, JPEG, BMP, etc. Du kan ange önskat format i`ImageSaveOptions` klass.
### F: Är Aspose.Tasks för Java kompatibelt med olika Java-utvecklingsmiljöer?
S: Ja, Aspose.Tasks för Java är kompatibel med de flesta Java-utvecklingsmiljöer, inklusive Eclipse, IntelliJ IDEA och NetBeans.
### F: Kan jag integrera Aspose.Tasks för Java i mitt Maven- eller Gradle-projekt?
S: Ja, du kan enkelt integrera Aspose.Tasks för Java i ditt Maven- eller Gradle-projekt genom att lägga till lämpligt beroende i din`pom.xml` eller`build.gradle` fil.
### F: Stöder Aspose.Tasks för Java export av projektdata till andra format än bilder?
S: Ja, Aspose.Tasks för Java stöder export av projektdata till olika format som PDF, HTML, XLSX, etc., vilket ger flexibilitet i datavisualisering och rapportering.
### F: Finns det något community-stöd tillgängligt för Aspose.Tasks för Java?
 S: Ja, du kan hitta communitysupport, ställa frågor och engagera dig med andra användare på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
