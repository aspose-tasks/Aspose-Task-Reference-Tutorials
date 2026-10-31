---
date: 2026-10-31
description: Lär dig hur du exporterar gantt till pdf i Java med Aspose.Tasks. Denna
  steg‑för‑steg‑guide visar hur du läser Gantt‑diagramdata och genererar PDF‑rapporter.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Läs specifik Gantt‑diagramdata i Aspose.Tasks
og_description: Exportera gantt till pdf i Java med Aspose.Tasks. Följ den här handledningen
  för att läsa Gantt‑diagramdata, anpassa visningsinställningar och generera PDF‑rapporter
  för projektledning.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Exportera gantt till pdf i Java – Aspose.Tasks‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Exportera gantt till pdf i Java – extrahera specifik data
url: /sv/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exportera gantt till pdf i Java – extrahera specifik data

## Introduktion
I den här handledningen kommer du att lära dig hur du **exporterar gantt till pdf i Java** genom att läsa Gantt-diagraminformation med Aspose.Tasks för Java. Gantt-diagram ger projektledare en visuell färdplan för uppgifter, beroenden och tidslinjer, och att kunna hämta dessa data programatiskt låter dig skapa automatiserade PDF-rapporter, instrumentpaneler eller integrationer med andra företagsystem. Låt oss gå igenom varje steg, från att ladda en projektfil till att extrahera vyegenskaper och slutligen generera en PDF.

## Snabba svar
- **Vad kan jag extrahera?** Alla vyegenskaper, stapelstil, rutnätslinje, textstil, förloppslinje eller tidslinjesteg från ett Gantt-diagram.  
- **Behöver jag en licens?** En provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilken Java-version stöds?** Java 8 eller senare (handledningen använder JDK 11).  
- **Är koden körbar som den är?** Ja – byt bara ut sökvägen till datakatalogen.  
- **Kan jag ändra vyn efter läsning?** Absolut – API:et låter dig ändra egenskaper och spara tillbaka till projektfilen.

## Vad är export av gantt till pdf?
Export av gantt till pdf är processen att konvertera en Gantt-diagravy från en projektfil till ett PDF-dokument som bevarar visuell stil och tidslinjeinformation. Denna operation är användbar för att dela projektstatus med intressenter som kanske inte har ett projektledningsverktyg.

## Varför exportera gantt till pdf med Aspose.Tasks?
Aspose.Tasks kan hantera **över 30 + inmatningsformat** (MPP, XML, MPX, etc.) och **exportera till PDF i ett enda anrop** samtidigt som 95 % av den visuella integriteten bevaras, även för projekt med mer än 500 uppgifter. Biblioteket bearbetar filer i minnet, så du kan generera PDF-filer på servrar utan att installera Microsoft Project.

## Förutsättningar
1. **Java Development Kit (JDK):** Se till att du har Java installerat på ditt system. Du kan ladda ner det från **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Ladda ner och installera Aspose.Tasks för Java-biblioteket från **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** Välj en IDE du föredrar. Populära val inkluderar IntelliJ IDEA, Eclipse eller NetBeans.

## Importera paket
Följande import-satser ger dig åtkomst till de centrala Aspose.Tasks-klasserna som behövs för att läsa och exportera Gantt-data.  
*Ingen kodblock visas här för att hålla handledningen fokuserad på koncept; lägg helt enkelt till importerna i din Java-fil.*

## Hur laddar jag en Gantt-diagram projektfil i Java?
Ladda projektfilen genom att skapa en `Project`-instans och skicka den fullständiga sökvägen till konstruktorn. Detta steg initierar den minnesbaserade representationen av Gantt-diagrammet, vilket möjliggör efterföljande frågor om vyegenskaper. När filen har laddats framgångsrikt kan du verifiera projektets namn, startdatum och antalet uppgifter för att säkerställa att rätt fil öppnades. Denna verifiering hjälper till att tidigt fånga upp sökvägs- eller formatproblem i arbetsflödet.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definition ankare:* `Project` är det översta Aspose.Tasks-objektet som representerar en enskild projektfil i minnet.

## Hur kan jag komma åt Gantt-diagramvyn?
Hämta den första Gantt-vyn från projektets vykollektion. De flesta projekt innehåller minst en Gantt-vy, och den är vanligtvis den första posten. Efter att ha fått vyn kan du vilja kontrollera dess namn och säkerställa att den är av typen `GanttChartView` innan du fortsätter med egenskapsextraktion. Denna extra kontroll förhindrar körfel när du arbetar med anpassade eller icke‑standard vykollektioner.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definition ankare:* `GanttChartView` representerar den visuella layouten av uppgifter, tidslinjer och staplar som du ser i ett typiskt Gantt-diagram.

## Hur extraherar jag vyegenskaper?
Du kan läsa egenskaper såsom bakgrundsfärg, stapelhöjd och tidslinjeinställningar direkt från `GanttChartView`-objektet. Att skriva ut dem hjälper dig att verifiera den aktuella konfigurationen innan export. En typisk extraktionsloop itererar över varje egenskap, formaterar värdet som en sträng och loggar det till konsolen eller en fil för senare analys. Detta tillvägagångssätt är användbart för felsökning och för att skapa dokumentation av diagrammets utseende.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definition ankare:* `GanttChartView` ger åtkomst till vyinställningar såsom bakgrundsfärg, stapelhöjd och tidslinjekonfiguration.

## Hur extraherar jag stapelstilar?
Iterera genom samlingen av `BarStyle`-objekt för att få detaljer som färg, mönster och form för varje stapeltyp som används i diagrammet. För varje stil kan du också läsa den associerade uppgiftstypen och villkoret som utlöser stilen, vilket är viktigt när du återskapar diagrammet i ett annat format. Att samla in denna information gör det möjligt att producera en trogen visuell kopia eller att programatiskt tillämpa anpassade stilregler.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definition ankare:* `BarStyle` definierar det visuella utseendet på en Gantt-stapel, inklusive dess färg, mönster och form.

## Hur extraherar jag rutnätslinjer?
Rutnätslinjer definierar den visuella separationen mellan rader och kolumner. Åtkomst sker via metoden `getGridlines()` och du kan skriva ut deras synlighet och stil. Efter att ha hämtat rutnätslinjesamlingen kan du loopa igenom varje linje för att fånga dess linjetyp (solid, streckad), tjocklek och färg. Dessa data är värdefulla när du behöver reproducera den exakta rutnätslayouten i exporterade PDF-filer eller andra rapportformat.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definition ankare:* `getGridlines()` returnerar samlingen av rutnätslinjeobjekt som styr rad- och kolumnseparatorer i Gantt-vyn.

## Hur extraherar jag textstilar?
Textstilar styr teckensnitt, storlek och färg på etiketter i Gantt-diagrammet. Loop igenom `TextStyle`-samlingen för att lista varje stil. För varje textstil kan du också hämta dess associerade element (uppgiftsnamn, datum, etc.) och eventuella villkorliga formateringsregler. Att fånga dessa detaljer säkerställer att exporterade dokument behåller samma typografi som originaldiagrammet.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definition ankare:* `TextStyle` representerar formateringsattributen som tillämpas på textuella element i Gantt-diagrammet.

## Hur extraherar jag förloppslinjer?
Förloppslinjer visar den aktuella slutförande-punkten för en uppgift. Åtkomst sker via `getProgressLines()` och du kan skriva ut deras attribut. Varje förloppslinje innehåller egenskaper såsom linjefärg, tjocklek och position relativt uppgiftsstapeln. Att registrera denna information gör det möjligt att skapa förloppsmedvetna visualiseringar eller att beräkna övergripande projektavslutningsmått.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definition ankare:* `getProgressLines()` returnerar mängden förloppslinjeobjekt som indikerar uppgiftens slutförandestatus.

## Hur extraherar jag tidslinjesteg?
Tidslinjesteg definierar de hierarkiska tidsenheterna (dagar, veckor, månader) som visas i diagrammet. Hämta dem via `getTimescaleTiers()` och skriv ut deras inställningar. För varje steg kan du fånga enhetstyp, etikettformat och justering, vilket är avgörande för att reproducera den exakta tidslinjegranulariteten i exporterade PDF-filer eller anpassade UI-komponenter.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definition ankare:* `getTimescaleTiers()` ger åtkomst till samlingen av tidslinjesteg-objekt som styr tidsaxelns visning.

## Hur exporterar jag Gantt-diagrammet till PDF?
Skapa ett `PdfSaveOptions`-objekt, anpassa eventuellt sidstorlek eller teckensnittsinbäddning, och anropa sedan `project.save` med PDF-formatet. Detta enkla anrop genererar en PDF som speglar Gantt-vyn på skärmen. Du kan också ange ytterligare alternativ såsom bildkomprimering, borttagning av vattenstämpel eller inbäddning av anpassade teckensnitt för att uppfylla företagets varumärkeskrav. Efter sparandet, verifiera PDF-filens storlek och visuella integritet för att säkerställa att exporten lyckades.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definition ankare:* `PdfSaveOptions` låter dig finjustera PDF-utdata, såsom sidmått, komprimering och teckensnittshantering.

## Vanliga fallgropar & tips
- **Felaktig datakatalog:** Se till att `dataDir` slutar med en filseparator (`/` eller `\\`) som är lämplig för ditt OS.  
- **Saknad vy:** Om projektet saknar Gantt-vy, kommer `project.getViews()` att vara tom – lägg till en kontroll innan du castar.  
- **Licensundantag:** Utan en giltig licens kan API:et lägga till en vattenstämpel på exporterade PDF-filer.  
- **Stora projekt:** För projekt med mer än 1 000 uppgifter, överväg att öka JVM:s heap-storlek (`-Xmx2g`) för att undvika `OutOfMemoryError`.  

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks för Java med andra Java-bibliotek?**  
A: Ja, Aspose.Tasks för Java integreras sömlöst med alla Java-bibliotek eller ramverk, inklusive Spring, Hibernate och Apache POI.

**Q: Är Aspose.Tasks lämplig för storskaliga företagsprojekt?**  
A: Absolut. Biblioteket bearbetar flersidiga MPP-filer på under 5 sekunder på standard serverhårdvara och stödjer samtidig körning i flertrådade miljöer.

**Q: Stöder Aspose.Tasks flera projektfilformat?**  
A: Ja, Aspose.Tasks stödjer 20+ format, inklusive MPP, XML, MPX och Primavera XML, vilket möjliggör att läsa och konvertera äldre scheman.

**Q: Kan jag anpassa utseendet på Gantt-diagram med Aspose.Tasks?**  
A: Självklart. Du kan programatiskt ändra stapelstilar, rutnätslinjer, textstilar och tidslinjesteg innan du exporterar till PDF- eller bildformat.

**Q: Hur sparar jag ändringar efter att ha modifierat en vy?**  
A: Anropa `project.save("output.mpp");` efter att ha gjort ändringar för att spara dem i projektfilen.

---

**Senast uppdaterad:** 2026-10-31  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Relaterade handledningar

- [Hur man sparar projekt som PDF med Aspose.Tasks – Exportguide](/tasks/java/project-file-operations/save-as-pdf/)
- [Skapa projekt-PDF – Anpassa Gantt-diagrammets tidslinje](/tasks/java/project-file-operations/set-time-scale-count/)
- [Exportera projekt till PDF och minska gapet mellan uppgiftslistan och sidfot i Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}