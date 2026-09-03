---
date: 2026-05-20
description: Naučte se, jak exportovat projekt do PDF, snížit mezeru v zápatí a uložit
  projekt jako obrázek pomocí Aspose.Tasks pro Java. Optimalizujte rozložení svého
  MS Project bez námahy.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Exportujte projekt do PDF a snižte mezeru mezi seznamem úkolů a zápatím
  v Aspose.Tasks
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
title: Exportujte projekt do PDF a snižte mezeru mezi seznamem úkolů a zápatím v Aspose.Tasks
url: /cs/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exportovat projekt do PDF a zmenšit mezeru mezi seznamem úkolů a zápatím v Aspose.Tasks

## Úvod  
V tomto tutoriálu objevíte **jak exportovat projekt do PDF**, a zároveň snížíte nechtěný prostor mezi seznamem úkolů a zápatím v souborech Microsoft Project. Na konci průvodce budete schopni generovat čisté PDF, PNG obrázky a HTML stránky s kompaktním rozvržením pomocí Aspose.Tasks pro Java. Projděte si proces krok za krokem a uvidíte, proč je to důležité pro profesionální reportování.

## Rychlé odpovědi  
- **Co znamená „exportovat projekt do PDF“?** Převádí soubor MPP do PDF dokumentu zachovávajícího úkoly, časové osy a formátování.  
- **Proč zmenšit mezeru v zápatí?** Menší mezera vytváří těsnější, profesionálněji vypadající zprávy, zejména pro tištěné nebo webové dokumenty.  
- **Mohu také projekt uložit jako obrázek?** Ano – Aspose.Tasks podporuje PNG, JPEG a další formáty obrázků.  
- **Potřebuji speciální licenci?** K dispozici je bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo vyšší funguje s aktuální knihovnou Aspose.Tasks.  

## Co je „exportovat projekt do PDF“?  
Exportování projektu do PDF převádí interní strukturu MPP do přenosného dokumentu, který lze otevřít na jakémkoli zařízení bez potřeby Microsoft Project. To je ideální pro sdílení stavových zpráv, aktualizací pro zúčastněné strany nebo archivaci projektových plánů. Zachovává původní rozvržení, barvy a hierarchii úkolů, což zajišťuje, že PDF vypadá identicky jako zdrojový soubor.

## Proč zmenšit mezeru v zápatí?  
Výchozí mezera v zápatí může přidávat zbytečný bílý prostor, způsobovat problémy s stránkováním a nevyvážený vzhled. Zmenšením mezery zajistíte, že váš obsah efektivně využije stránku, což učiní finální PDF nebo obrázek čitelnějším. Těsnější rozvržení také snižuje celkový počet stránek, což může snížit náklady na tisk a zlepšit navigaci na obrazovce.

## Jak zmenšit mezeru mezi seznamem úkolů a zápatím?  
`setReduceFooterGap` je Boolean vlastnost, která řídí mezery v zápatí během exportu.  
Aspose.Tasks poskytuje možnost `setReduceFooterGap(true)` pro operace ukládání obrázku, PDF a HTML. Povolením tohoto příznaku řeknete enginu, aby zkomprimoval prostor mezi posledním řádkem úkolu a zápatím stránky. Když je nastaveno na true, vykreslovač automaticky ořízne okraj, aniž by ořezal jakákoli data úkolu, což vede k čistějšímu rozvržení stránky.

## Uložit projekt jako obrázek pomocí Aspose.Tasks  
`ImageSaveOptions` konfiguruje, jak je projekt vykreslen do souboru obrázku.  
Třída `ImageSaveOptions` vám umožní exportovat snímek plánu jako PNG, JPEG nebo BMP. Když také povolíte `setReduceFooterGap(true)`, vygenerovaný obrázek odráží kompaktní rozvržení PDF, což vám poskytne čistý vizuál pro prezentace nebo dashboardy.

## Export Java projektu do PDF  
Následující sekce provádějí kompletní workflow **exportu java projektu**, od načtení souboru MPP po jeho uložení ve třech různých formátech.

## Požadavky
Než začneme, ujistěte se, že máte následující požadavky:
1. Java Development Kit (JDK) – verze 8 nebo novější.  
2. Knihovna Aspose.Tasks pro Java – stáhněte ji z [zde](https://releases.aspose.com/tasks/java/).  

## Importovat balíčky  
Než se ponoříme do kódu, importujme potřebné balíčky:

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

## Krok 1: Zadejte cestu k vašemu datovému adresáři  
```java
String dataDir = "Your Data Directory";
```  
Ujistěte se, že nahradíte `"Your Data Directory"` cestou k vašemu skutečnému datovému adresáři, kde se nachází váš soubor Microsoft Project (`HomeMovePlan.mpp` v tomto příkladu).

## Krok 2: Načíst soubor MPP  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Tento řádek kódu načte soubor Microsoft Project s názvem `HomeMovePlan.mpp`.

## Krok 3: Nastavit ImageSaveOptions (Uložit projekt jako obrázek)  
`ImageSaveOptions` konfiguruje, jak je projekt vykreslen do souboru obrázku.  
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```  
Nastavte možnosti ukládání obrázku, nastavte `ReduceFooterGap` na `true`, aby se zmenšila mezera mezi seznamem úkolů a zápatím.

## Krok 4: Uložit jako obrázek  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```  
Uložte projekt jako obrázek s nastavenými možnostmi.

## Krok 5: Nastavit PdfSaveOptions (Exportovat projekt do PDF)  
`PdfSaveOptions` určuje nastavení pro export projektu do formátu PDF.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Definujte možnosti ukládání PDF a ujistěte se, že `ReduceFooterGap` je nastaven na `true`.

## Krok 6: Uložit jako PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Uložte projekt jako PDF s nastavenými možnostmi.

## Krok 7: Nastavit HtmlSaveOptions  
`HtmlSaveOptions` řídí konverzi projektu do HTML, včetně stylování a možností rozvržení.  
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```  
Zadejte možnosti ukládání HTML a nastavte `ReduceFooterGap` na `true`.

## Krok 8: Uložit jako HTML  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```  
Uložte projekt jako HTML soubor s nastavenými možnostmi.

## Běžné případy použití a tipy  
- **Reportování pro zúčastněné strany:** Export do PDF se zmenšenou mezerou v zápatí, aby byly zprávy stručné a vhodné pro tisk.  
- **Snímky dashboardu:** Použijte export obrázku, když potřebujete rychlou vizualizaci pro Power BI nebo Confluence.  
- **Webové publikování:** Export do HTML zachovává interaktivitu a může být vložen přímo do intranetových portálů.  
- **Profesionální tip:** Pro velmi velké projekty zvyšte `Resolution` v `ImageSaveOptions` na 300 dpi, aby byla zachována ostrost, zatímco stále těžíte ze zmenšené mezery.

## Často kladené otázky (další)

**Q: Jak zmenšení mezery v zápatí ovlivňuje stránkování?**  
A: Minimalizuje prázdný prostor na spodní části každé stránky, což umožňuje umístit více úkolů na jednu stránku a snížit celkový počet stránek.

**Q: Můžu použít stejné nastavení zmenšení mezery pouze na jednu stránku?**  
A: Ano, nastavením `setRenderToSinglePage(true)` v `ImageSaveOptions` můžete řídit stránkování a zároveň zmenšit mezeru.

**Q: Je volba `setReduceFooterGap` dostupná pro jiné výstupní formáty?**  
A: V současné době je podporována pro exporty PNG, PDF a HTML. Pro jiné formáty může být nutné ručně upravit rozvržení.

**Q: Co když můj projekt obsahuje vlastní pole—jsou zachována?**  
A: Všechna vlastní pole jsou při exportu zachována; úpravy rozvržení ovlivňují pouze mezery, ne data.

**Q: Zvládá knihovna efektivně velké projekty?**  
A: Aspose.Tasks streamuje data a může zpracovat MPP soubory s několika stovkami stránek, aniž by načítala celý soubor do paměti; přesto je třeba při exportu vysoce rozlišených obrázků alokovat dostatečnou haldu.

---

**Poslední aktualizace:** 2026-05-20  
**Testováno s:** Aspose.Tasks 24.11 pro Java  
**Autor:** Aspose

## Související tutoriály

- [Uložit projekt jako obrázek – formát 24bppRgb s Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Uložit projekt jako šablonu, CSV a Text s Aspose.Tasks pro Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Jak vytvořit MPP soubor – vytvořit a uložit prázdný projekt ve formátu MPP s Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}