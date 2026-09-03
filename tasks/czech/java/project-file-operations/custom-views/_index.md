---
date: 2026-05-26
description: Naučte se, jak přidat zobrazení do projektu pomocí Aspose.Tasks pro Java,
  uložit vlastní zobrazení a nastavit vlastnosti zobrazení pro robustní reportování
  v MS Project.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: Vlastní zobrazení v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak přidat zobrazení do projektu pomocí Aspose.Tasks
url: /cs/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat pohled do projektu s Aspose.Tasks

## Úvod
Pokud hledáte **jak přidat pohled do projektu**, aby vaše zprávy přesně odpovídaly potřebám zúčastněných stran, jste na správném místě. Přizpůsobení pohledů v MS Project vám umožní zobrazit nejrelevantnější data, odstranit přebytečné informace a urychlit rozhodování. **Aspose.Tasks for Java** poskytuje výkonné, typově bezpečné API, které vám umožní vytvářet, konfigurovat a ukládat vlastní pohledy přímo v souboru MPP. V tomto průvodci projdeme každý krok – od přípravy prostředí až po uložení pohledu – abyste mohli dodat vylepšené, opakovatelné řešení.

## Rychlé odpovědi
- **Jaký je hlavní účel?** Přidat pohled do projektu a uložit jej uvnitř souboru MPP pomocí Aspose.Tasks for Java.  
- **Která třída vytváří pohled?** `GanttChartView` (nebo jiné typy pohledů, jako `TaskSheetView`).  
- **Jak zajistit, aby se pohled zobrazil v nabídce?** Zavolejte `view.setShowInMenu(true)` před uložením.  
- **Jak mohu uložit pohled spolu s projektem?** Použijte `MPPSaveOptions` s `setWriteViewData(true)`.  
- **Potřebuji licenci?** Ano – pro produkční nasazení je vyžadována platná licence Aspose.Tasks.

## Co je „přidat pohled do projektu“?
*Přidání pohledu do projektu* znamená vytvoření nové vizuální reprezentace (např. Ganttův diagram, list úkolů) a vložení její definice do souboru MPP, aby ji Microsoft Project mohl později zobrazit. Tato operace je s Aspose.Tasks zcela programová, čímž se eliminuje potřeba ručních kroků v uživatelském rozhraní.

## Proč používat vlastní pohledy?
Aspose.Tasks podporuje **více než 50 vlastností souvisejících s pohledy** a dokáže zpracovat projekty s **statisíci úkolů** bez načítání celého souboru do paměti. Definováním pohledu jednou a jeho uložením zajistíte konzistentní reportování pro všechny členy týmu a snížíte riziko chyb při ruční konfiguraci.

## Požadavky
- **Java Development Kit** (JDK 8 nebo novější) nainstalovaný a nakonfigurovaný na vašem počítači.  
- **Aspose.Tasks for Java** knihovna – stáhněte ji z [zde](https://releases.aspose.com/tasks/java/).  
- Platný soubor licence **Aspose.Tasks** pro produkční použití (bezplatná zkušební verze funguje pro hodnocení).

## Import balíčků
Třídy `GanttChartView`, `MPPSaveOptions` a související třídy se nacházejí v jmenném prostoru `com.aspose.tasks`. Importujte je na začátku vašeho zdrojového souboru:

`GanttChartView` představuje definici Ganttova diagramu.  
`MPPSaveOptions` řídí, jak je projekt uložen, včetně dat pohledu.  
`Project` je hlavní třída představující soubor MS Project.  
`View` je základní třída pro všechny typy pohledů.

```text
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```
```

## Krok 1: Nastavení projektu
Vytvořte novou instanci `Project` nebo načtěte existující soubor. Tento objekt obsahuje všechna data projektu, včetně úkolů, zdrojů a pohledů. `Prj` poskytuje konstantní klíče pro vlastnosti projektu, jako je název projektu.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## Krok 2: Vytvoření pohledu
`GanttChartView` je reprezentací klasického Ganttova diagramu v Aspose.Tasks. Umožňuje vám řídit sloupce, styly pruhů, časové měřítka a další.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## Krok 3: Přizpůsobení vlastností pohledu *(nastavit vlastnosti pohledu)*
Zde můžete jemně doladit vzhled pohledu: nastavit první viditelný sloupec, definovat barvy pruhů a upravit granularitu časového měřítka. `setShowInMenu(boolean)` určuje, zda se pohled zobrazí v nabídce MS Project. `setHighlightFilter(boolean)` udává, zda je filtr pro pohled zvýrazněn.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### Jak zobrazit nabídku pohledu
Volání `view.setShowInMenu(true)` zajistí, že nově vytvořený pohled se objeví v nabídce **View** v MS Project, což koncovým uživatelům poskytne okamžitý přístup bez další konfigurace.

## Krok 4: Ladění nastavení pohledu
V tomto kroku se nastavují pokročilé možnosti, jako je rozvržení stránky, tiskové volby a šířky sloupců. Správné ladění zajišťuje, že tištěné zprávy odpovídají zobrazení na obrazovce.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## Krok 5: Přidání pohledu do projektu *(přidat vlastní pohled java)*
Po nakonfigurování pohledu jej přidejte do kolekce `Views` projektu. `getViews()` vrací kolekci pohledů v projektu. Tento krok skutečně **přidává pohled do projektu**, aby se stal součástí vnitřní struktury souboru.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## Krok 6: Uložení projektu *(uložit pohled projektu)*
Při ukládání projektu musíte Aspose.Tasks sdělit, aby zapsal data pohledu. Třída `MPPSaveOptions` řídí toto chování. `setWriteViewData(boolean)` instruuje ukladač, aby vložil definice pohledu.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### Proč je důležité uložit pohled projektu
Nastavení `options.setWriteViewData(true)` instruuje Aspose.Tasks, aby vložil definici vlastního pohledu do souboru MPP. Bez tohoto příznaku by pohled existoval jen v paměti a po uzavření souboru by zmizel.

## Krok 7: Kontrola vlastností pohledu
Po uložení můžete projekt znovu načíst a ověřit, že se pohled správně zobrazuje v uživatelském rozhraní a že všechny vlastnosti (sloupce, styly pruhů atd.) jsou zachovány.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## Běžné případy použití
- **Reportování pro zúčastněné strany:** Zobrazit pouze milníky a úkoly kritické cesty pro vrcholové vedení.  
- **Alokace zdrojů:** Zobrazit zdroje vedle jejich přiřazených úkolů pro plánování kapacity.  
- **Tiskové snímky:** Nakonfigurovat velikost stránky, orientaci a viditelnost sloupců pro vytvoření čistých PDF pro offline revizi.

## Tipy pro řešení problémů
- **Pohled se nezobrazuje v nabídce:** Ujistěte se, že `view.setShowInMenu(true)` je zavoláno *před* uložením a že je povoleno `MPPSaveOptions.setWriteViewData(true)`.  
- **Chybějící sloupce v tisku:** Ověřte, že `setFirstColumnsCount` odpovídá počtu sloupců, které jste definovali, a povolte `setPrintFirstColumnsCountOnAllPages(true)`.  
- **Výjimky licence:** Načtěte soubor licence pomocí `License license = new License(); license.setLicense("Aspose.Tasks.lic");` před vytvořením jakýchkoli objektů `Project`.

## Často kladené otázky

**Q: Mohu přizpůsobit pohledy i mimo Ganttovy diagramy?**  
A: Ano – Aspose.Tasks vám umožní vytvořit vlastní listy úkolů, listy zdrojů a dokonce vlastní tabulky, což vám dává plnou kontrolu nad každým vizuálním aspektem.

**Q: Je Aspose.Tasks for Java vhodný pro rozsáhlé projekty?**  
A: Rozhodně. Knihovna zpracovává projekty s **500 000+ úkoly** pomocí streamovacího API, které udržuje využití paměti pod 200 MB.

**Q: Podporuje Aspose.Tasks for Java export pohledů do různých formátů?**  
A: Ano – můžete exportovat pohled do PDF, XLSX, HTML a několika formátů obrázků přímo z API.

**Q: Mohu automatizovat vytváření vlastních pohledů pomocí Aspose.Tasks for Java?**  
A: Samozřejmě. API je plně skriptovatelné, což vám umožní generovat, upravovat a ukládat pohledy v dávkových úlohách nebo CI pipelinech.

**Q: Existuje komunitní fórum pro podporu Aspose.Tasks for Java?**  
A: Ano, můžete získat pomoc od ostatních vývojářů a zaměstnanců Aspose na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2026-05-26  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit soubor MPP – Vytvořit a uložit prázdný projekt ve formátu MPP s Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Nastavení adresáře dat pro Gantt Chart View v Aspose.Tasks](/tasks/java/project-configuration/configure-gantt-chart/)
- [Načtení souboru MPP v Javě – Správa vlastností projektu s Aspose.Tasks](/tasks/java/project-management/default-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}