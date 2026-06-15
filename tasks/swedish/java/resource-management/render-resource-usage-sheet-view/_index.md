---
date: 2026-06-15
description: Lär dig hur du konverterar mpp till pdf och renderar Resource Usage och
  Sheet vyer med Aspose.Tasks för Java. Följ vår steg‑för‑steg‑guide för att ställa
  in timescale och skapa detaljerade PDF‑rapporter utan ansträngning.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Konvertera MPP till PDF och rendera Resource Usage View – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Konvertera MPP till PDF och rendera Resource Usage View – Aspose.Tasks
url: /sv/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera MPP till PDF och rendera resursanvändningsvy – Aspose.Tasks

I den här handledningen kommer du att lära dig **hur man konverterar mpp till pdf** samtidigt som du renderar resursanvändnings- och bladvyerna i en Microsoft Project‑fil. Att använda Aspose.Tasks för Java eliminerar behovet av Microsoft Project på servern och ger dig ett snabbt, pålitligt sätt att skapa PDF‑rapporter från MPP‑filer. Vi visar också **hur man ställer in tidslinjen** så att resultatet matchar dina rapporteringskrav.

## Snabba svar
- **Vad gör Aspose.Tasks?** Den läser, modifierar och konverterar Microsoft Project (MPP)-filer utan att behöva MS Project installerat.  
- **Kan jag konvertera MPP till PDF med en enda kodrad?** Ja – ladda projektet, sätt SaveOptions och anropa `save`.  
- **Vilka tidslinjer stöds?** Days, ThirdsOfMonths och Months.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för icke‑testdistributioner.  
- **Är biblioteket kompatibelt med Java 8+?** Absolut – det stödjer Java 8 och senare versioner.

## Vad är konvertering av mpp till pdf?
*Convert mpp to pdf* avser processen att ta en Microsoft Project‑fil (.mpp) och generera en Portable Document Format (PDF)-version som troget återger projektets tabeller, scheman, diagram och resursallokeringar. Den resulterande PDF‑filen kan enkelt delas, skrivas ut och arkiveras utan att Microsoft Project måste vara installerat på mottagarens dator.

## Varför konvertera projekt till PDF med Aspose.Tasks?
Aspose.Tasks stödjer **50+ in‑ och utdataformat** och kan rendera projekt med flera hundra sidor utan att ladda hela filen i minnet, vilket minskar RAM‑användningen med upp till 70 %. PDF‑utdata behåller tabeller, diagram och resursallokeringar, vilket gör det idealiskt för distribution till intressenter och arkivering.

## Förutsättningar
1. **Java Development Kit (JDK)** – Java 8 eller nyare installerat på din maskin.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från [download page](https://releases.aspose.com/tasks/java/).  

## Hur man konverterar mpp till pdf med Aspose.Tasks för Java?
Läs in din käll‑MPP‑fil, konfigurera önskad tidslinje, sätt presentationsformatet till **ResourceUsage** och spara resultatet som en PDF. Detta end‑to‑end‑flöde kräver bara några få API‑anrop och körs på under en sekund för typiska projektstorlekar.

### Steg 1: Läs in källprojektet
`Project`‑klassen representerar en Microsoft Project‑fil som laddats in i minnet och ger åtkomst till dess data och struktur.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Steg 2: Definiera SaveOptions med nödvändiga TimeScale‑inställningar
`SaveOptions` konfigurerar hur projektet sparas och låter dig ange format‑specifika inställningar såsom tidslinje.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Steg 3: Ställ in presentationsformatet till ResourceUsage
`PresentationFormat` bestämmer vilken projektvy (t.ex. ResourceUsage) som renderas i utdata‑dokumentet.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Steg 4: Spara projektet som PDF
`project.save` skriver projektet till en fil med de angivna `SaveOptions` och skapar den slutgiltiga PDF‑filen.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Steg 5: Rendera vyer för andra TimeScale‑inställningar
Upprepa de föregående stegen och ändra `TimeScale`‑värdet för att rendera ytterligare tidslinje‑vyer.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Steg 6: Valfritt – Konvertera flera projekt i batch
Om du behöver **konvertera projekt till pdf** för många filer, placera ovanstående logik i en loop som itererar över en katalog med *.mpp*-filer. Detta tillvägagångssätt **sparar ms project pdf**‑filer i bulk med minimala kodändringar.  
Följande kod demonstrerar ett komplett exempel på hur man konverterar en MPP‑fil till PDF med de önskade inställningarna.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Vanliga problem och lösningar
- **Saknade teckensnitt i PDF** – Se till att de nödvändiga teckensnitten är installerade på servern eller bädda in dem via `PdfSaveOptions`.  
- **Stora projektfiler orsakar OutOfMemoryError** – Använd `LoadOptions.setLoadAllResources(false)` för att ladda resurser vid behov.  
- **Felaktig tidslinjerendering** – Verifiera att `options.setTimeScale(TimeScale.Days)` (eller annan enum) matchar den önskade granulariteten.

## Vanliga frågor

**Q: Kan Aspose.Tasks rendera andra vyer än Resursanvändning och Blad?**  
A: Ja, det stödjer även Gantt‑diagram, Task Usage, Calendar och många ytterligare vyer.

**Q: Är Aspose.Tasks kompatibelt med olika versioner av Microsoft Project‑filer?**  
A: Absolut – det hanterar MPP-, MPT- och XML‑format från Project 2000 till Project 2021.

**Q: Kan jag anpassa utseendet på renderade vyer?**  
A: Ja, du kan ändra färger, teckensnitt och kolumnlayouter via `PdfSaveOptions` och `PresentationOptions`.

**Q: Kräver Aspose.Tasks att Microsoft Project är installerat?**  
A: Nej, det är ett fristående bibliotek och fungerar i alla Java‑kompatibla miljöer.

**Q: Var kan jag få teknisk support?**  
A: Support finns via [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).

---

**Senast uppdaterad:** 2026-06-15  
**Testat med:** Aspose.Tasks 24.12 for Java  
**Författare:** Aspose

## Relaterade handledningar

- [Rendera resursanvändnings- och bladvy i Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Hur man exporterar PDF i Aspose.Tasks – Spara som PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Hur man skapar MPP‑filer med Aspose.Tasks för Java](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}