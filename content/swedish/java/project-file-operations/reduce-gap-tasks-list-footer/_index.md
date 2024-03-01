---
title: Minska klyftan mellan uppgiftslistan och sidfoten i Aspose.Tasks
linktitle: Minska klyftan mellan uppgiftslistan och sidfoten i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du minskar klyftan mellan MS Projects uppgiftslistor och sidfötter med Aspose.Tasks för Java. Optimera projektdokumentlayout utan ansträngning.
type: docs
weight: 10
url: /sv/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## Introduktion
I den här handledningen kommer vi att fördjupa oss i att minska klyftan mellan uppgiftslistan och sidfoten i Microsoft Project-filer med Aspose.Tasks för Java. Genom att följa dessa steg kommer du att kunna optimera layouten för dina projektdokument utan ansträngning.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Tasks for Java Library: Ladda ner och inkludera Aspose.Tasks for Java-biblioteket i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).

## Importera paket
Innan vi dyker in i kodningsdelen, låt oss importera de nödvändiga paketen:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Steg 1: Ange sökvägen till din datakatalog
```java
String dataDir = "Your Data Directory";
```
 Se till att byta ut`"Your Data Directory"` med sökvägen till din faktiska datakatalog där din Microsoft Project-fil (`HomeMovePlan.mpp` i detta exempel) finns.
## Steg 2: Läs MPP-filen
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Denna kodrad läser den namngivna Microsoft Project-filen`HomeMovePlan.mpp`.
## Steg 3: Ställ in ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Konfigurera bildsparalternativen, inställning`ReduceFooterGap` till`true` för att minska klyftan mellan uppgiftslistan och sidfoten.
## Steg 4: Spara som bild
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Spara projektet som en bild med de konfigurerade alternativen.
## Steg 5: Ställ in PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Definiera PDF-sparalternativ, se till att ställa in`ReduceFooterGap` till`true`.
## Steg 6: Spara som PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Spara projektet som en PDF med de konfigurerade alternativen.
## Steg 7: Ställ in HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // satt till sant
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Ange HTML-sparalternativ, inställning`ReduceFooterGap` till`true`.
## Steg 8: Spara som HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Spara projektet som en HTML-fil med de konfigurerade alternativen.

## Slutsats
Sammanfattningsvis, att minska klyftan mellan uppgiftslistan och sidfoten i Microsoft Project-filer är en enkel process med Aspose.Tasks för Java. Genom att följa stegen som beskrivs i denna handledning kan du effektivt optimera layouten för dina projektdokument.

## FAQ's

### F: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?

S: Aspose.Tasks stöder Microsoft Project 2003-2019-format, vilket säkerställer kompatibilitet mellan olika versioner.

### F: Kan jag anpassa utseendet på sidfoten i mina projektdokument?

S: Ja, Aspose.Tasks erbjuder omfattande alternativ för att anpassa utseendet på sidfötter, inklusive att minska luckor och justera innehållsplacering.

### F: Stöder Aspose.Tasks att spara projekt i andra format än PNG, PDF och HTML?

S: Ja, Aspose.Tasks stöder ett brett utbud av format, inklusive XLSX, XML och MPP, bland andra.

### F: Finns det en testversion tillgänglig för Aspose.Tasks?

 S: Ja, du kan ladda ner en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).

### F: Var kan jag få support om jag stöter på några problem när jag använder Aspose.Tasks?

 S: Du kan få hjälp från Aspose.Tasks communityforum[här](https://forum.aspose.com/c/tasks/15).