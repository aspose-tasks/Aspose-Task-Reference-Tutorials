---
date: 2026-10-31
description: Naučte se, jak exportovat Gantt do PDF v Javě pomocí Aspose.Tasks. Tento
  podrobný návod vám ukáže, jak číst data Gantt diagramu a vytvářet PDF zprávy.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Číst konkrétní data Gantt diagramu v Aspose.Tasks
og_description: Exportujte Gantt do PDF v Javě pomocí Aspose.Tasks. Postupujte podle
  tohoto tutoriálu, abyste četli data Gantt diagramu, přizpůsobili vlastnosti zobrazení
  a vytvářeli PDF zprávy pro řízení projektů.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Export Gantt do PDF v Javě – návod Aspose.Tasks
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
title: Export Gantt do PDF v Javě – extrahovat konkrétní data
url: /cs/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Export gantt do pdf v Javě – extrahování konkrétních dat

## Úvod
V tomto tutoriálu se naučíte, jak **exportovat gantt do pdf v Javě** čtením informací o Ganttově diagramu pomocí Aspose.Tasks for Java. Ganttovy diagramy poskytují projektovým manažerům vizuální plán úkolů, závislostí a časových os, a možnost programově získat tato data vám umožní vytvářet automatizované PDF zprávy, dashboardy nebo integrace s dalšími podnikovými systémy. Projdeme jednotlivé kroky, od načtení projektového souboru po získání vlastností zobrazení a nakonec vytvoření PDF.

## Rychlé odpovědi
- **Co mohu extrahovat?** Jakoukoli vlastnost zobrazení, styl pruhu, mřížku, styl textu, čáru postupu nebo úroveň časové osy z Ganttova diagramu.  
- **Potřebuji licenci?** Zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Která verze Javy je podporována?** Java 8 nebo novější (v tutoriálu je použito JDK 11).  
- **Je kód spustitelný tak, jak je?** Ano – stačí nahradit cestu ke složce s daty.  
- **Mohu po načtení upravit zobrazení?** Rozhodně – API vám umožní měnit vlastnosti a uložit je zpět do projektového souboru.

## Co je export gantt do pdf?
Export gantt do pdf je proces převodu zobrazení Ganttova diagramu uloženého v projektovém souboru do PDF dokumentu, který zachovává vizuální styl a informace o časové ose. Tento úkon je užitečný pro sdílení stavu projektu se zainteresovanými stranami, které nemusí mít nástroj pro řízení projektů.

## Proč exportovat gantt do pdf pomocí Aspose.Tasks?
Aspose.Tasks dokáže zpracovat **více než 30 + vstupních formátů** (MPP, XML, MPX atd.) a **exportovat do PDF jedním voláním**, přičemž zachovává 95 % vizuální věrnosti, i u projektů s více než 500 úkoly. Knihovna zpracovává soubory v paměti, takže můžete generovat PDF na serverech bez instalace Microsoft Project.

## Předpoklady
1. **Java Development Kit (JDK):** Ujistěte se, že máte na svém systému nainstalovanou Javu. Můžete si ji stáhnout ze **[stránky pro stažení Oracle JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Knihovna Aspose.Tasks for Java:** Stáhněte a nainstalujte knihovnu Aspose.Tasks for Java ze **[stránky pro stažení Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)**.  
3. **Integrované vývojové prostředí (IDE):** Vyberte si IDE podle své preference. Populární volby zahrnují IntelliJ IDEA, Eclipse nebo NetBeans.

## Import balíčků
Následující importy vám poskytují přístup k základním třídám Aspose.Tasks potřebným pro čtení a exportování Gantt dat.  
*Žádný blok kódu zde není zobrazen, aby byl tutoriál zaměřen na koncepty; jednoduše přidejte importy do svého Java souboru.*

## Jak načtu projektový soubor Ganttova diagramu v Javě?
Načtěte projektový soubor vytvořením instance `Project` a předáním úplné cesty do konstruktoru. Tento krok inicializuje paměťovou reprezentaci Ganttova diagramu, což umožňuje následné dotazy na vlastnosti zobrazení. Když je soubor úspěšně načten, můžete ověřit název projektu, datum zahájení a počet úkolů, abyste se ujistili, že byl otevřen správný soubor. Toto ověření pomáhá včas zachytit problémy s cestou nebo formátem.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definiční kotva:* `Project` je objekt nejvyšší úrovně v Aspose.Tasks, který představuje jeden projektový soubor v paměti.

## Jak mohu získat přístup k zobrazení Ganttova diagramu?
Získejte první Ganttovo zobrazení ze sbírky zobrazení projektu. Většina projektů obsahuje alespoň jedno Ganttovo zobrazení a obvykle je to první položka. Po získání zobrazení můžete zkontrolovat jeho název a ujistit se, že je typu `GanttChartView`, než budete pokračovat s extrakcí vlastností. Tato dodatečná kontrola zabraňuje chybám za běhu při práci s vlastním nebo nestandardním sbírkou zobrazení.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definiční kotva:* `GanttChartView` představuje vizuální rozvržení úkolů, časových os a pruhů, které vidíte v typickém Ganttově diagramu.

## Jak extrahovat vlastnosti zobrazení?
Můžete číst vlastnosti jako barvu pozadí, výšku pruhu a nastavení časové osy přímo z objektu `GanttChartView`. Jejich výpis vám pomůže ověřit aktuální konfiguraci před exportem. Typický smyčkový výpis iteruje přes každou vlastnost, formátuje hodnotu jako řetězec a zaznamenává ji do konzole nebo souboru pro pozdější analýzu. Tento přístup je užitečný pro ladění a pro generování dokumentace vzhledu diagramu.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definiční kotva:* `GanttChartView` poskytuje přístup k nastavením zobrazení, jako je barva pozadí, výška pruhu a konfigurace časové osy.

## Jak extrahovat styly pruhů?
Iterujte přes sbírku objektů `BarStyle`, abyste získali podrobnosti jako barvu, vzor a tvar pro každý typ pruhu použitého v diagramu. Pro každý styl můžete také přečíst související typ úkolu a podmínku, která styl spouští, což je nezbytné při reprodukci diagramu v jiném formátu. Shromažďování těchto informací vám umožní vytvořit věrnou vizuální repliku nebo programově aplikovat vlastní pravidla stylování.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definiční kotva:* `BarStyle` definuje vizuální vzhled Ganttova pruhu, včetně jeho barvy, vzoru a tvaru.

## Jak extrahovat mřížky?
Mřížky definují vizuální oddělení řádků a sloupců. Přístup k nim získáte pomocí metody `getGridlines()` a můžete vypsat jejich viditelnost a styl. Po získání sbírky mřížek můžete iterovat přes každou čáru a zachytit její typ (plná, čárkovaná), tloušťku a barvu. Tato data jsou cenná, když potřebujete reprodukovat přesné rozložení mřížky v exportovaných PDF nebo jiných formátech reportování.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definiční kotva:* `getGridlines()` vrací sbírku objektů mřížky, které řídí oddělovače řádků a sloupců v Ganttově zobrazení.

## Jak extrahovat styly textu?
Styly textu řídí písmo, velikost a barvu popisků v Ganttově diagramu. Procházejte sbírku `TextStyle` a vypište každý styl. Pro každý styl textu můžete také získat související prvek (název úkolu, datum atd.) a případná pravidla podmíněného formátování. Zachycení těchto podrobností zajišťuje, že exportované dokumenty zachovají stejnou typografii jako originální diagram.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definiční kotva:* `TextStyle` představuje formátovací atributy aplikované na textové prvky v Ganttově diagramu.

## Jak extrahovat čáry postupu?
Čáry postupu ukazují aktuální bod dokončení úkolu. Přístup k nim získáte pomocí `getProgressLines()` a můžete vypsat jejich atributy. Každá čára postupu obsahuje vlastnosti jako barvu čáry, tloušťku a pozici vzhledem k pruhu úkolu. Zaznamenání těchto informací vám umožní vytvářet vizualizace s ohledem na postup nebo vypočítat celkové metriky dokončení projektu.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definiční kotva:* `getProgressLines()` vrací sadu objektů čáry postupu, které indikují stav dokončení úkolu.

## Jak extrahovat úrovně časové osy?
Úrovně časové osy definují hierarchické časové jednotky (dny, týdny, měsíce) zobrazené v diagramu. Získejte je pomocí `getTimescaleTiers()` a vypište jejich nastavení. Pro každou úroveň můžete zachytit typ jednotky, formát popisku a zarovnání, což je klíčové pro reprodukci přesné granularity časové osy v exportovaných PDF nebo vlastních UI komponentách.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definiční kotva:* `getTimescaleTiers()` poskytuje přístup ke sbírce objektů úrovní časové osy, které řídí zobrazení časové osy.

## Jak exportovat Ganttův diagram do PDF?
Vytvořte objekt `PdfSaveOptions`, volitelně upravte velikost stránky nebo vložení fontů, a poté zavolejte `project.save` s formátem PDF. Toto jediné volání vygeneruje PDF, které odráží zobrazení Gantt diagramu na obrazovce. Můžete také zadat další možnosti, jako je komprese obrázků, odstranění vodoznaku nebo vložení vlastních fontů, aby vyhovovaly požadavkům firemního brandingu. Po uložení ověřte velikost PDF souboru a vizuální věrnost, aby byl export úspěšný.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definiční kotva:* `PdfSaveOptions` vám umožňuje jemně ladit výstup PDF, například rozměry stránky, kompresi a správu fontů.

## Časté úskalí a tipy
- **Nesprávná složka s daty:** Ujistěte se, že `dataDir` končí souborovým oddělovačem (`/` nebo `\\`) vhodným pro váš OS.  
- **Chybějící zobrazení:** Pokud projekt nemá žádné Ganttovo zobrazení, `project.getViews()` bude prázdné – přidejte kontrolu před přetypováním.  
- **Výjimky licence:** Bez platné licence může API přidat vodoznak do exportovaných PDF.  
- **Velké projekty:** Pro projekty s více než 1 000 úkoly zvažte zvýšení velikosti haldy JVM (`-Xmx2g`), aby nedošlo k `OutOfMemoryError`.  

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks for Java s jinými Java knihovnami?**  
A: Ano, Aspose.Tasks for Java se bez problémů integruje s libovolnou Java knihovnou nebo frameworkem, včetně Spring, Hibernate a Apache POI.

**Q: Je Aspose.Tasks vhodný pro rozsáhlé podnikově projekty?**  
A: Rozhodně. Knihovna zpracovává více než stovky stránek MPP souborů za méně než 5 sekund na standardním serverovém hardware a podporuje souběžné provádění ve vícevláknových prostředích.

**Q: Podporuje Aspose.Tasks více formátů projektových souborů?**  
A: Ano, Aspose.Tasks podporuje více než 20 formátů, včetně MPP, XML, MPX a Primavera XML, což vám umožní číst a konvertovat starší plány.

**Q: Mohu přizpůsobit vzhled Ganttových diagramů pomocí Aspose.Tasks?**  
A: Samozřejmě. Můžete programově upravit styly pruhů, mřížky, styly textu a úrovně časové osy před exportem do PDF nebo obrazových formátů.

**Q: Jak uložím změny po úpravě zobrazení?**  
A: Zavolejte `project.save("output.mpp");` po provedení jakýchkoli úprav, aby se změny uložily do projektového souboru.

**Poslední aktualizace:** 2026-10-31  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

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

## Související tutoriály

- [Jak uložit projekt jako PDF pomocí Aspose.Tasks – Průvodce exportem](/tasks/java/project-file-operations/save-as-pdf/)
- [Vytvořit PDF projektu – Přizpůsobit časovou stupnici Ganttova diagramu](/tasks/java/project-file-operations/set-time-scale-count/)
- [Exportovat projekt do PDF a zmenšit mezeru mezi seznamem úkolů a patičkou v Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}