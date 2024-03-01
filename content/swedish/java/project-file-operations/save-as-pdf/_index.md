---
title: Spara som PDF i Aspose.Tasks
linktitle: Spara som PDF i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du konverterar projektfiler till PDF med Aspose.Tasks för Java. Enkla steg för effektiv konvertering.
type: docs
weight: 17
url: /sv/java/project-file-operations/save-as-pdf/
---
## Introduktion
den här handledningen guidar vi dig genom processen att spara ett projekt som en PDF med Aspose.Tasks för Java. Med Aspose.Tasks kan du effektivt konvertera dina projektfiler till PDF-format, vilket säkerställer kompatibilitet och enkel delning. Låt oss dyka ner i stegen:
## Förutsättningar
Innan du börjar, se till att du har följande:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Tasks för Java Library: Ladda ner och installera Aspose.Tasks-biblioteket. Du hittar nedladdningslänken[här](https://releases.aspose.com/tasks/java/).
3. En projektfil: Ha en projektfil (t.ex. HomeMovePlan.mpp) redo som du vill konvertera till PDF.

## Importera paket
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Steg 1: Läs Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Se till att du byter ut`"Your Data Directory"` med sökvägen till din datakatalog som innehåller projektfilen.
## Steg 2: Spara projektet som PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Detta kodavsnitt sparar projektet som en PDF-fil med namnet "Project5.pdf".
## Steg 3: Anpassa innehållet till cellstorlek
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Här ställer vi in alternativ för att spara PDF-filen, inklusive passande innehåll, tidsskala och presentationsformat.
## Steg 4: Dölj legender
```java
o.setLegendOnEachPage(false);
```
Detta steg döljer förklaringar på varje sida i PDF-filen.
## Steg 5: Spara projektet med tillämpade alternativ
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Slutligen sparar den här koden projektet med tillämpade alternativ till en PDF-fil.

## Slutsats
I den här handledningen lärde vi oss hur man använder Aspose.Tasks för Java för att spara ett projekt som en PDF. Genom att följa dessa enkla steg kan du effektivt konvertera dina projektfiler för enkel delning och distribution.
## FAQ's
### F: Är Aspose.Tasks kompatibel med alla versioner av Java?
S: Ja, Aspose.Tasks stöder Java-versioner från JDK 6 och senare.
### F: Kan jag anpassa utseendet på PDF-utdata?
A: Absolut! Aspose.Tasks erbjuder olika alternativ för att anpassa PDF-utdata enligt dina krav.
### F: Stöder Aspose.Tasks andra filformat för konvertering?
S: Ja, Aspose.Tasks stöder ett brett utbud av filformat, inklusive MPP, XML, XLSX och mer.
### F: Finns det en testversion tillgänglig för Aspose.Tasks?
 S: Ja, du kan få en gratis provversion av Aspose.Tasks från[här](https://releases.aspose.com/).
### F: Var kan jag få support för Aspose.Tasks?
 S: För support och hjälp kan du besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).