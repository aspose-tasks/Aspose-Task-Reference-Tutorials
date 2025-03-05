---
title: Konvertera MS Project till SVG i Java
linktitle: Spara som SVG i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du sparar Microsoft Project-filer som SVG i Java med Aspose.Tasks-biblioteket. Steg-för-steg guide med kodexempel.
type: docs
weight: 18
url: /sv/java/project-file-operations/save-as-svg/
---
## Introduktion
Aspose.Tasks för Java är ett kraftfullt bibliotek för att arbeta med projektledningsfiler, vilket gör det möjligt för utvecklare att manipulera projektdata, utföra olika operationer och generera rapporter effektivt. I den här handledningen kommer vi att utforska hur man sparar ett projekt som SVG med Aspose.Tasks för Java. SVG (Scalable Vector Graphics) är ett allmänt använt format för att visa vektorgrafik på webben, vilket ger skalbarhet och högkvalitativ rendering.
## Förutsättningar
Innan vi börjar, se till att du har följande:
### Java utvecklingsmiljö
Se till att du har Java Development Kit (JDK) installerat på ditt system. Du kan ladda ner och installera JDK från Oracles webbplats.
### Aspose.Tasks för Java Library
 Ladda ner och installera Aspose.Tasks for Java-biblioteket från webbplatsen. Du hittar nedladdningslänken i den medföljande dokumentationen[här](https://releases.aspose.com/tasks/java/).

## Importera paket
Först måste du importera de nödvändiga paketen i ditt Java-program för att fungera med Aspose.Tasks-funktioner.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Låt oss nu dela upp exemplet i flera steg:
## Steg 2: Definiera datakatalog
```java
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"`med sökvägen till katalogen där din projektfil finns.
## Steg 3: Ladda projektfilen
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Detta steg laddar projektfilen med namnet "HomeMovePlan.mpp" från den angivna datakatalogen.
## Steg 4: Spara som SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Detta steg sparar det inlästa projektet som SVG-format med namnet "project5.svg" i den angivna datakatalogen.

## Slutsats
I den här handledningen har vi lärt oss hur man sparar ett projekt som SVG med Aspose.Tasks för Java. Genom att följa de medföljande stegen kan du effektivt konvertera projektfiler till SVG-format, vilket möjliggör sömlös integration med webbaserade applikationer eller visualiseringsverktyg.
## FAQ's
### Är Aspose.Tasks för Java kompatibelt med alla versioner av Microsoft Project-filer?
Ja, Aspose.Tasks för Java stöder olika versioner av Microsoft Project-filer, inklusive MPP-, MPT- och XML-format.
### Kan jag anpassa utseendet på SVG-utdata?
Ja, du kan anpassa utseendet på SVG-utdata genom att justera parametrar som typsnitt, färger och layoutkonfigurationer.
### Kräver Aspose.Tasks för Java en licens för kommersiellt bruk?
 Ja, en giltig licens krävs för kommersiell användning av Aspose.Tasks för Java. Du kan få en licens från webbplatsen[här](https://purchase.aspose.com/temporary-license/).
### Kan jag prova Aspose.Tasks för Java innan jag köper?
 Ja, du kan begära en gratis testversion av Aspose.Tasks för Java från webbplatsen[här](https://purchase.aspose.com/buy) för att utvärdera dess egenskaper och möjligheter.
### Var kan jag få support för Aspose.Tasks för Java?
 Du kan få support för Aspose.Tasks för Java genom att besöka forumet[här](https://forum.aspose.com/c/tasks/15), där du kan ställa frågor och interagera med samhället.