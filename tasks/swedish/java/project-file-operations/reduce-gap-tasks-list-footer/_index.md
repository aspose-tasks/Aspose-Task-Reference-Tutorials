---
date: 2025-12-17
description: Lär dig hur du exporterar projektet till PDF, minskar fotnotens avstånd
  och sparar projektet som bild med Aspose.Tasks för Java. Optimera din MS Project‑layout
  utan ansträngning.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Exportera projekt till PDF och minska avståndet mellan uppgiftslistan och sidfoten
  i Aspose.Tasks
url: /sv/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exportera projekt till PDF och minska avståndet mellan uppgiftslistan och sidfoten i Aspose.Tasks

## Introduction  
I den här handledningen kommer du att upptäcka **hur man exporterar projekt till PDF** samtidigt som du minskar det oönskade utrymmet mellan uppgiftslistan och sidfoten i Microsoft Project‑filer. I slutet av guiden kommer du att kunna generera rena PDF‑filer, PNG‑bilder och HTML‑sidor med en kompakt layout med hjälp av Aspose.Tasks för Java. Låt oss gå igenom processen steg‑för‑steg.

## Quick Answers  
- **Vad betyder “export project to PDF”?** Det konverterar en MPP‑fil till ett PDF‑dokument som bevarar uppgifter, tidslinjer och formatering.  
- **Varför minska avståndet till sidfoten?** Ett mindre avstånd skapar tätare, mer professionella rapporter, särskilt för utskrivna eller webblästa dokument.  
- **Kan jag också spara projektet som en bild?** Ja – Aspose.Tasks stöder PNG, JPEG och andra bildformat.  
- **Behöver jag en speciell licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktionsbruk.  
- **Vilken Java‑version krävs?** Java 8 eller högre fungerar med det aktuella Aspose.Tasks‑biblioteket.

## What is “export project to PDF”?  
Att exportera ett projekt till PDF omvandlar den interna MPP‑strukturen till ett portabelt dokument som kan öppnas på vilken enhet som helst utan att behöva Microsoft Project. Detta är idealiskt för att dela statusrapporter, intressentuppdateringar eller arkivera projektplaner.

## Why Reduce Footer Gap?  
Standardavståndet till sidfoten kan lägga till onödigt vitt utrymme, vilket orsakar sidbrytningar och ett obalanserat utseende. Att minska avståndet säkerställer att ditt innehåll utnyttjar sidan effektivt, vilket gör den slutgiltiga PDF‑ eller bildfilen mer läsbar.

## How to Reduce Gap Between Tasks List and Footer?  
Aspose.Tasks erbjuder ett `setReduceFooterGap(true)`‑alternativ för bild-, PDF‑ och HTML‑sparoperationer. Att aktivera detta flagga instruerar motorn att komprimera utrymmet mellan den sista uppgiftsraden och sidfoten.

## Save Project as Image with Aspose.Tasks  
Om du behöver ett visuellt ögonblick av ditt schema kan du **spara projekt som bild** (PNG) samtidigt som du använder samma inställningar för att minska avståndet.

## Java Project Export to PDF  
Följande avsnitt går igenom ett komplett **java project export**‑arbetsflöde, från att läsa in MPP‑filen till att spara den i tre olika format.

## Prerequisites
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK) – version 8 eller senare.  
2. Aspose.Tasks for Java Library – ladda ner den [här](https://releases.aspose.com/tasks/java/).  

## Import Packages
Innan du dyker ner i koddelen, låt oss importera de nödvändiga paketen:
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

## Step 1: Provide the Path to Your Data Directory
```java
String dataDir = "Your Data Directory";
```
Se till att ersätta `"Your Data Directory"` med sökvägen till din faktiska datamapp där din Microsoft Project‑fil (`HomeMovePlan.mpp` i detta exempel) finns.

## Step 2: Read the MPP File
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Denna kodrad läser Microsoft Project‑filen med namnet `HomeMovePlan.mpp`.

## Step 3: Set ImageSaveOptions (Save Project as Image)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Konfigurera bildsparalternativen och sätt `ReduceFooterGap` till `true` för att minska avståndet mellan uppgiftslistan och sidfoten.

## Step 4: Save as Image
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Spara projektet som en bild med de konfigurerade alternativen.

## Step 5: Set PdfSaveOptions (Export Project to PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Definiera PDF‑sparalternativen och se till att `ReduceFooterGap` är satt till `true`.

## Step 6: Save as PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Spara projektet som en PDF med de konfigurerade alternativen.

## Step 7: Set HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Ange HTML‑sparalternativen och sätt `ReduceFooterGap` till `true`.

## Step 8: Save as HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Spara projektet som en HTML‑fil med de konfigurerade alternativen.

## Conclusion  
Sammanfattningsvis är det en enkel process att minska avståndet mellan uppgiftslistan och sidfoten i Microsoft Project‑filer med Aspose.Tasks för Java. Genom att följa stegen i denna handledning kan du effektivt **exportera projekt till PDF**, spara det som en bild eller generera HTML samtidigt som layouten hålls kompakt och professionell.

## FAQ's

### Q: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?

A: Aspose.Tasks stöder Microsoft Project 2003‑2019‑format, vilket säkerställer kompatibilitet över olika versioner.

### Q: Kan jag anpassa utseendet på sidfoten i mina projektdokument?

A: Ja, Aspose.Tasks erbjuder omfattande alternativ för att anpassa sidfotens utseende, inklusive att minska avstånd och justera innehållsplacering.

### Q: Stöder Aspose.Tasks att spara projekt i andra format än PNG, PDF och HTML?

A: Ja, Aspose.Tasks stöder ett brett spektrum av format, inklusive XLSX, XML och MPP, bland andra.

### Q: Finns det en provversion av Aspose.Tasks?

A: Ja, du kan ladda ner en gratis provversion av Aspose.Tasks [här](https://releases.aspose.com/).

### Q: Var kan jag få support om jag stöter på problem när jag använder Aspose.Tasks?

A: Du kan få hjälp i Aspose.Tasks‑community‑forum [här](https://forum.aspose.com/c/tasks/15).

## Frequently Asked Questions (Additional)

**Q: Hur påverkar minskning av sidfotens avstånd sidnumreringen?**  
A: Det minskar det tomma utrymmet längst ner på varje sida, så att fler uppgifter får plats på en sida och det totala sidantalet minskar.

**Q: Kan jag tillämpa samma avståndsreducering endast på en enskild sida?**  
A: Ja, genom att sätta `setRenderToSinglePage(true)` i `ImageSaveOptions` kan du kontrollera sidbrytning samtidigt som du minskar avståndet.

**Q: Är `setReduceFooterGap`‑alternativet tillgängligt för andra exportformat?**  
A: För närvarande stöds det för PNG, PDF och HTML. För andra format kan du behöva justera layouten manuellt.

**Q: Vad händer om mitt projekt innehåller anpassade fält – bevaras de?**  
A: Alla anpassade fält behålls vid export; layoutjusteringarna påverkar endast avstånd, inte data.

**Q: Hanterar biblioteket stora projekt effektivt?**  
A: Aspose.Tasks strömmar data och kan bearbeta stora MPP‑filer; se dock till att ha tillräckligt med minne vid export till högupplösta bilder.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}