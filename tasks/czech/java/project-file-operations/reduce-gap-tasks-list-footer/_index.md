---
date: 2025-12-17
description: Naučte se, jak exportovat projekt do PDF, zmenšit mezeru v zápatí a uložit
  projekt jako obrázek pomocí Aspose.Tasks pro Java. Optimalizujte rozvržení svého
  MS Projectu bez námahy.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Exportovat projekt do PDF a zmenšit mezeru mezi seznamem úkolů a zápatím v
  Aspose.Tasks
url: /cs/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Export projektu do PDF a snížení mezery mezi seznamem úkolů a zápatím v Aspose.Tasks

## Úvod  
V tomto tutoriálu objevíte **jak exportovat projekt do PDF** a zároveň snížit nežádoucí mezeru mezi seznamem úkolů a zápatím v souborech Microsoft Project. Na konci průvodce budete schopni generovat čisté PDF, PNG obrázky a HTML stránky s kompaktním rozvržením pomocí Aspose.Tasks pro Java. Projděme si proces krok za krokem.

## Rychlé odpovědi  
- **Co znamená „export projektu do PDF“?** Převádí soubor MPP do PDF dokumentu a zachovává úkoly, časové osy a formátování.  
- **Proč snížit mezeru v zápatí?** Menší mezera vytváří těsnější, profesionálněji vypadající zprávy, zejména pro tištěné nebo webové dokumenty.  
- **Mohu také projekt uložit jako obrázek?** Ano – Aspose.Tasks podporuje PNG, JPEG a další formáty obrázků.  
- **Potřebuji speciální licenci?** K dispozici je bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Která verze Javy je vyžadována?** Java 8 nebo vyšší funguje s aktuální knihovnou Aspose.Tasks.

## Co je „export projektu do PDF“?  
Export projektu do PDF převádí interní strukturu MPP do přenosného dokumentu, který lze otevřít na jakémkoli zařízení bez potřeby Microsoft Project. To je ideální pro sdílení stavových zpráv, aktualizací pro zainteresované strany nebo archivaci projektových plánů.

## Proč snížit mezeru v zápatí?  
Výchozí mezera v zápatí může přidávat zbytečný bílý prostor, způsobovat problémy s stránkováním a nevyvážený vzhled. Snížením mezery zajistíte, že váš obsah bude stránku využívat efektivně, což učiní finální PDF nebo obrázek čitelnějším.

## Jak snížit mezeru mezi seznamem úkolů a zápatím?  
Aspose.Tasks poskytuje možnost `setReduceFooterGap(true)` pro operace ukládání do obrázku, PDF a HTML. Aktivace tohoto příznaku řekne enginu, aby zkomprimoval prostor mezi posledním řádkem úkolu a zápatím stránky.

## Uložení projektu jako obrázek pomocí Aspose.Tasks  
Pokud potřebujete vizuální snímek svého plánu, můžete **uložit projekt jako obrázek** (PNG) a zároveň použít stejné nastavení pro snížení mezery.

## Export Java projektu do PDF  
Následující sekce vás provedou kompletním pracovním postupem **exportu java projektu**, od načtení souboru MPP až po jeho uložení ve třech různých formátech.

## Požadavky
Než začneme, ujistěte se, že máte následující požadavky:
1. Java Development Kit (JDK) – verze 8 nebo novější.  
2. Aspose.Tasks for Java Library – stáhněte ji z [zde](https://releases.aspose.com/tasks/java/).  

## Import balíčků
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
Ujistěte se, že nahradíte `"Your Data Directory"` cestou k vašemu skutečnému datovému adresáři, kde se nachází váš soubor Microsoft Project (`HomeMove.mpp` v tomto příkladu).

## Krok 2: Načtěte soubor MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Tento řádek kódu načte soubor Microsoft Project s názvem `HomeMovePlan.mpp`.

## Krok 3: Nastavte ImageSaveOptions (Uložení projektu jako obrázek)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Nakonfigurujte možnosti ukládání obrázku a nastavte `ReduceFooterGap` na `true`, aby se snížila mezera mezi seznamem úkolů a zápatím.

## Krok 4: Uložení jako obrázek
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Uložte projekt jako obrázek s nakonfigurovanými možnostmi.

## Krok 5: Nastavte PdfSaveOptions (Export projektu do PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Definujte možnosti ukládání PDF a ujistěte se, že `ReduceFooterGap` je nastaveno na `true`.

## Krok 6: Uložení jako PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Uložte projekt jako PDF s nakonfigurovanými možnostmi.

## Krok 7: Nastavte HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Určete možnosti ukládání HTML a nastavte `ReduceFooterGap` na `true`.

## Krok 8: Uložení jako HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Uložte projekt jako HTML soubor s nakonfigurovanými možnostmi.

## Závěr  
Závěrem, snížení mezery mezi seznamem úkolů a zápatím v souborech Microsoft Project je jednoduchý proces s Aspose.Tasks pro Java. Dodržením kroků popsaných v tomto tutoriálu můžete efektivně **exportovat projekt do PDF**, uložit jej jako obrázek nebo vygenerovat HTML při zachování těsného a profesionálního rozvržení.

## Často kladené otázky

### Q: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?
A: Aspose.Tasks podporuje formáty Microsoft Project 2003‑2019, což zajišťuje kompatibilitu napříč různými verzemi.

### Q: Mohu přizpůsobit vzhled zápatí v mých projektových dokumentech?
A: Ano, Aspose.Tasks nabízí rozsáhlé možnosti přizpůsobení vzhledu zápatí, včetně snížení mezer a úpravy umístění obsahu.

### Q: Podporuje Aspose.Tasks ukládání projektů v jiných formátech než PNG, PDF a HTML?
A: Ano, Aspose.Tasks podporuje širokou škálu formátů, včetně XLSX, XML a MPP a dalších.

### Q: Je k dispozici zkušební verze Aspose.Tasks?
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks z [zde](https://releases.aspose.com/).

### Q: Kde mohu získat podporu, pokud narazím na problémy při používání Aspose.Tasks?
A: Pomoc můžete získat na komunitním fóru Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

## Často kladené otázky (další)

**Q: Jak snížení mezery v zápatí ovlivňuje stránkování?**  
A: Minimalizuje prázdný prostor na konci každé stránky, což umožňuje umístit více úkolů na jednu stránku a snižuje celkový počet stránek.

**Q: Mohu použít stejné nastavení snížení mezery pouze na jednu stránku?**  
A: Ano, nastavením `setRenderToSinglePage(true)` v `ImageSaveOptions` můžete řídit stránkování a zároveň snížit mezeru.

**Q: Je možnost `setReduceFooterGap` dostupná pro jiné výstupní formáty?**  
A: V současné době je podporována pro exporty PNG, PDF a HTML. Pro jiné formáty může být nutné upravit rozvržení ručně.

**Q: Co když můj projekt obsahuje vlastní pole – jsou zachována?**  
A: Všechna vlastní pole jsou během exportu zachována; úpravy rozvržení ovlivňují pouze mezery, ne data.

**Q: Zvládá knihovna velké projekty efektivně?**  
A: Aspose.Tasks streamuje data a může zpracovávat velké soubory MPP; však zajistěte dostatek paměti při exportu do vysoce rozlišených obrázků.

---

**Poslední aktualizace:** 2025-12-17  
**Testováno s:** Aspose.Tasks 24.11 pro Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}