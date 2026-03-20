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

## Introduktion
I den här handledningen kommer du att upptäcka **hur man exporterar projekt till PDF** samtidigt som du minskar det oönskade utrymmet mellan uppgiftslistan och sidfoten i Microsoft Project‑filer. I slutet av guiden kommer du att kunna generera rena PDF‑filer, PNG‑bilder och HTML‑sidor med en kompakt layout med hjälp av Aspose.Tasks för Java. Låt oss gå igenom processen steg‑för‑steg.

## Snabba svar
- **Vad betyder "exportera projekt till PDF"?** Det konverterar en MPP-fil till ett PDF‑dokument som innehåller uppgifter, tidslinjer och formatering.
- **Varför minska avståndet till sidfoten?** Ett mindre avstånd skapar tätare, mer professionella rapporter, särskilt för utskrivna eller webblästa dokument.
- **Kan jag också spara projektet som en bild?** Ja – Aspose.Tasks stöder PNG, JPEG och andra bildformat.
- **Behöver jag en speciell licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktionsbruk.
- **Vilken Java‑version krävs?** Java8 eller högre fungerar med det aktuella Aspose.Tasks‑biblioteket.

## Vad är "exportera projekt till PDF"?
Att exportera ett projekt till PDF omvandlar den interna MPP‑strukturen till ett portabelt dokument som kan öppnas på vilken enhet som helst utan att behöva Microsoft Project. Detta är idealiskt för att dela statusrapporter, intressentuppdateringar eller arkivera projektplaner.

## Varför minska sidfotsgapet?
Standardavståndet till sidfoten kan lägga till onödigt vitt utrymme, vilket orsakar sidbrytningar och ett obalanserat utseende. Att minska avståndet säkerställer att ditt innehåll utnyttjar sidan effektivt, vilket gör den slutgiltiga PDF‑ eller bildfilen mer läsbar.

## Hur kan man minska klyftan mellan uppgiftslistan och sidfoten?
Aspose.Tasks erbjuder ett `setReduceFooterGap(true)`‑alternativ för bild-, PDF‑ och HTML‑sparoperationer. Att aktivera detta flagga instruerar motorn att komprimera utrymmet mellan den sista uppgiftsraden och sidfoten.

## Spara projekt som bild med Aspose.Tasks
Om du behöver ett visuellt ögonblick av ditt schema kan du **spara projekt som bild** (PNG) samtidigt som du använder samma inställningar för att minska avståndet.

## Java Project Export till PDF
Följande avsnitt går igenom ett komplett **java project export**‑arbetsflöde, från att läsa i MPP-filen till att spara den i tre olika format.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK) – version8 eller senare.
2. Aspose.Tasks for Java Library – ladda ner den [här](https://releases.aspose.com/tasks/java/).

## Importera paket
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

## Steg 1: Ange sökvägen till din datakatalog
```java
String dataDir = "Your Data Directory";
```
Se till att ersätta `"Your Data Directory"` med sökvägen till din faktiska datamapp där din Microsoft Project‑fil (`HomeMovePlan.mpp` i detta exempel) finns.

## Steg 2: Läs MPP-filen
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Denna kodrad läser Microsoft Project‑filen med namnet `HomeMovePlan.mpp`.

## Steg 3: Ställ in ImageSaveOptions (Spara projekt som bild)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Konfigurera bildsparalternativen och sätt `ReduceFooterGap` till `true` för att minska avståndet mellan uppgiftslistan och sidfoten.

## Steg 4: Spara som bild
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Spara projektet som en bild med de konfigurerade alternativen.

## Steg 5: Ställ in PdfSaveOptions (Exportera projekt till PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Definiera PDF‑sparalternativen och se till att `ReduceFooterGap` är satt till `true`.

## Steg 6: Spara som PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Spara projektet som en PDF med de konfigurerade alternativen.

## Steg 7: Ställ in HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Ange HTML‑sparalternativen och sätt `ReduceFooterGap` till `true`.

## Steg 8: Spara som HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Spara projektet som en HTML‑fil med de konfigurerade alternativen.

## Slutsats
Sammanfattningsvis är det enkla processen att minska avståndet mellan uppgiftslistan och sidfoten i Microsoft Project-filer med Aspose.Tasks för Java. Genom att följa stegen i denna handledning kan du effektivt **exportera projekt till PDF**, spara det som en bild eller generera HTML samtidigt som layouten är kompakt och professionell.

## Vanliga frågor (ytterligare)

**F: Hur påverkar minskning av sidfoten avstånd sidnumreringen?**
A: Det minskar det tomma utrymmet längst ner på varje sida, så att fler uppgifter får plats på en sida och det totala sidantalet minskar.

**F: Kan jag tillämpa samma avståndsreducering endast på en enskild sida?**
A: Ja, genom att sätta `setRenderToSinglePage(true)` i `ImageSaveOptions` kan du kontrollera sidbrytning samtidigt som du minskar avståndet.

**F: Är `setReduceFooterGap`-alternativet tillgängligt för andra exportformat?**
A: För närvarande stöds det för PNG, PDF och HTML. För andra format kan du behöva justera layouten manuellt.

**F: Vad händer om mitt projekt innehåller anpassat fält – bevaras de?**
A: Alla anpassade fält behålls vid export; layoutjusteringarna påverkar endast avstånd, inte data.

**F: Hanterar biblioteket stora projekt effektivt?**
A: Aspose.Tasks strömmar data och kan bearbeta stora MPP-filer; se dock till att ha allt med minne vid export till högupplösta bilder.

---

**Senast uppdaterad:** 2025-12-17
**Testad med:** Aspose.Tasks 24.11 för Java
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}