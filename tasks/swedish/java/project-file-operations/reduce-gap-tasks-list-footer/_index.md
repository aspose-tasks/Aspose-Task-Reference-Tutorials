---
date: 2026-05-20
description: Lär dig hur du exporterar projekt till PDF, minskar avståndet i sidfoten
  och sparar projektet som bild med Aspose.Tasks för Java. Optimera din MS Project‑layout
  utan ansträngning.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Exportera projekt till PDF och minska avståndet mellan uppgiftslistan och
  sidfoten i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
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
I den här handledningen kommer du att upptäcka **hur man exporterar projekt till PDF** samtidigt som du minskar det oönskade utrymmet mellan uppgiftslistan och sidfoten i Microsoft Project-filer. I slutet av guiden kommer du att kunna generera rena PDF-filer, PNG-bilder och HTML-sidor med en kompakt layout med hjälp av Aspose.Tasks för Java. Låt oss gå igenom processen steg för steg, och du kommer att se varför detta är viktigt för professionell rapportering.

## Snabba svar  
- **Vad betyder “export project to PDF”?** Det konverterar en MPP-fil till ett PDF-dokument och bevarar uppgifter, tidslinjer och formatering.  
- **Varför minska avståndet till sidfoten?** Ett mindre avstånd skapar tätare, mer professionellt utseende rapporter, särskilt för utskrivna eller webblästa dokument.  
- **Kan jag också spara projektet som en bild?** Ja – Aspose.Tasks stödjer PNG, JPEG och andra bildformat.  
- **Behöver jag en speciell licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktionsanvändning.  
- **Vilken Java-version krävs?** Java 8 eller högre fungerar med det aktuella Aspose.Tasks-biblioteket.  

## Vad är “export project to PDF”?  
Att exportera ett projekt till PDF omvandlar den interna MPP-strukturen till ett portabelt dokument som kan öppnas på vilken enhet som helst utan att behöva Microsoft Project. Detta är idealiskt för att dela statusrapporter, intressentuppdateringar eller arkivera projektplaner. Det bevarar den ursprungliga layouten, färgerna och uppgiftshierarkin, vilket säkerställer att PDF-filen ser identisk ut med källfilen.

## Varför minska avståndet till sidfoten?  
Det standardavståndet till sidfoten kan lägga till onödigt vitt utrymme, vilket orsakar sidnumreringsproblem och ett obalanserat utseende. Att minska avståndet säkerställer att ditt innehåll utnyttjar sidan effektivt, vilket gör den slutliga PDF‑filen eller bilden mer läsbar. En tätare layout minskar också det totala antalet sidor, vilket kan sänka utskriftskostnaderna och förbättra navigeringen på skärmen.

## Hur man minskar avståndet mellan uppgiftslistan och sidfoten?  
`setReduceFooterGap` är en boolesk egenskap som styr avståndet till sidfoten under export.  
Aspose.Tasks tillhandahåller ett `setReduceFooterGap(true)`‑alternativ för bild-, PDF- och HTML‑sparoperationer. Att aktivera detta flagga instruerar motorn att komprimera utrymmet mellan den sista uppgiftsraden och sidfoten. När den är satt till true trimmar renderaren automatiskt marginalen utan att klippa bort någon uppgiftsdata, vilket resulterar i en renare sidlayout.

## Spara projekt som bild med Aspose.Tasks  
`ImageSaveOptions` konfigurerar hur ett projekt renderas till en bildfil.  
Klassen `ImageSaveOptions` låter dig exportera en schemaundersökning som PNG, JPEG eller BMP. När du också aktiverar `setReduceFooterGap(true)` speglar den genererade bilden den kompakta PDF‑layouten, vilket ger dig en ren visuell för presentationer eller instrumentpaneler.

## Java-projektexport till PDF  
Följande avsnitt går igenom ett komplett **java project export**‑arbetsflöde, från att läsa in MPP‑filen till att spara den i tre olika format.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK) – version 8 eller senare.  
2. Aspose.Tasks för Java‑bibliotek – ladda ner det från [here](https://releases.aspose.com/tasks/java/).  

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
Se till att ersätta `"Your Data Directory"` med sökvägen till din faktiska datakatalog där din Microsoft Project‑fil (`HomeMovePlan.mpp` i detta exempel) finns.

## Steg 2: Läs MPP‑filen  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Denna kodrad läser Microsoft Project‑filen med namnet `HomeMovePlan.mpp`.

## Steg 3: Ställ in ImageSaveOptions (Spara projekt som bild)  
`ImageSaveOptions` konfigurerar hur ett projekt renderas till en bildfil.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Konfigurera bildsparalternativen genom att sätta `ReduceFooterGap` till `true` för att minska avståndet mellan uppgiftslistan och sidfoten.

## Steg 4: Spara som bild  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Spara projektet som en bild med de konfigurerade alternativen.

## Steg 5: Ställ in PdfSaveOptions (Exportera projekt till PDF)  
`PdfSaveOptions` specificerar inställningar för att exportera ett projekt till PDF‑format.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Definiera PDF‑sparalternativen och se till att sätta `ReduceFooterGap` till `true`.

## Steg 6: Spara som PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Spara projektet som en PDF med de konfigurerade alternativen.

## Steg 7: Ställ in HtmlSaveOptions  
`HtmlSaveOptions` styr konverteringen av ett projekt till HTML, inklusive stil- och layoutalternativ.  
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

## Vanliga användningsområden och tips  
- **Intressentrapportering:** Exportera till PDF med minskat sidfotavstånd för att hålla rapporterna koncisa och utskriftsvänliga.  
- **Dashboard‑ögonblicksbilder:** Använd bildexport när du behöver en snabb visuell för Power BI eller Confluence.  
- **Webbpublicering:** HTML‑export behåller interaktivitet och kan bäddas in direkt i intranätportaler.  
- **Pro tip:** För mycket stora projekt, öka `Resolution` i `ImageSaveOptions` till 300 dpi för att behålla klarhet samtidigt som du drar nytta av det minskade avståndet.

## Vanliga frågor (ytterligare)

**Q: Hur påverkar minskning av sidfotavståndet sidnumreringen?**  
A: Det minimerar tomt utrymme längst ner på varje sida, vilket gör att fler uppgifter får plats på en enda sida och minskar det totala antalet sidor.

**Q: Kan jag tillämpa samma avståndsminskningsinställning endast på en enda sida?**  
A: Ja, genom att sätta `setRenderToSinglePage(true)` i `ImageSaveOptions` kan du kontrollera sidnumreringen samtidigt som du fortfarande minskar avståndet.

**Q: Är alternativet `setReduceFooterGap` tillgängligt för andra utdataformat?**  
A: För närvarande stöds det för PNG-, PDF- och HTML‑export. För andra format kan du behöva justera layouten manuellt.

**Q: Vad händer om mitt projekt innehåller anpassade fält—bevaras de?**  
A: Alla anpassade fält behålls under export; layoutjusteringarna påverkar endast avståndet, inte data.

**Q: Hanterar biblioteket stora projekt effektivt?**  
A: Aspose.Tasks strömmar data och kan bearbeta MPP‑filer med flera hundra sidor utan att ladda hela filen i minnet; dock bör du allokera tillräckligt med heap‑utrymme när du exporterar högupplösta bilder.

**Senast uppdaterad:** 2026-05-20  
**Testad med:** Aspose.Tasks 24.11 för Java  
**Författare:** Aspose

## Relaterade handledningar

- [Spara projekt som bild – 24bppRgb-format med Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Spara projekt som mall, CSV och text med Aspose.Tasks för Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Hur man skapar MPP‑fil – Skapa och spara tomt projekt i MPP‑format med Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}