---
date: 2026-08-29
description: Naučte se, jak číst data základní linie a plánovat úkoly pomocí Aspose.Tasks
  pro Java, abyste mohli efektivně porovnat plánovaný a skutečný průběh.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Plánování úkolů podle základní linie v Aspose.Tasks
og_description: Naučte se, jak číst data základní linie a plánovat úkoly pomocí Aspose.Tasks
  pro Java, což umožňuje přesné porovnání plánovaného a skutečného průběhu.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Jak číst základní linii a plánovat úkoly pomocí Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Jak číst základní linii a plánovat úkoly pomocí Aspose.Tasks
url: /cs/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst baseline a plánovat úkoly pomocí Aspose.Tasks

V tomto průvodci se dozvíte **jak číst baseline** informace a programově plánovat úkoly pomocí Aspose.Tasks pro Java. Na konci tutoriálu budete schopni zachytit původní plán projektu, porovnat jej se skutečným průběhem a vytvořit zprávy o odchylkách – vše bez nutnosti instalace Microsoft Project.

## Úvod do baseline projektového řízení
Správa **project management baseline** je základním kamenem efektivního řízení projektů. Umožňuje vám zachytit původní plán a později porovnat **planned vs actual progress**, abyste mohli včas odhalit odchylky. V tomto tutoriálu vás provedeme, jak naplánovat baseline úkolů pomocí Aspose.Tasks pro Java, a poskytneme vám nástroje k **manage project baselines** s jistotou a udržení vašich projektů na správné cestě.

## Rychlé odpovědi
- **Co představuje project management baseline?**  
  Zaznamenává schválený harmonogram, náklady a rozsah na začátku projektu a poskytuje referenci pro analýzu odchylek.  
- **Která knihovna zajišťuje plánování baseline v Javě?**  
  Aspose.Tasks pro Java nabízí čisté Java API, které podporuje více než 45 vstupních a výstupních formátů a projekty až do 100 000 úkolů.  
- **Potřebuji licenci pro spuštění kódu?**  
  Bezplatná zkušební verze funguje pro testování; pro produkční použití je vyžadována komerční licence.  
- **Jaké jsou hlavní předpoklady?**  
  Java Development Kit (JDK) 11+ a knihovna Aspose.Tasks pro Java.  
- **Mohu zobrazit data baseline po jejich nastavení?**  
  Ano — použijte objekt `TaskBaseline` k načtení hodnot start, finish a duration.

## Co je project management baseline?
Project management baseline zaznamenává schválený harmonogram, rozpočet a rozsah na začátku realizace. Slouží jako referenční bod pro měření výkonnosti a identifikaci odchylek během celého životního cyklu projektu. Obsahuje plánované data zahájení a ukončení, celkové náklady a podrobnosti o rozsahu, poskytující komplexní přehled pro budoucí srovnání.

## Proč použít Aspose.Tasks pro plánování baseline?
Aspose.Tasks poskytuje čisté Java API, které funguje bez instalace Microsoft Project. Podporuje **45+ vstupních a výstupních formátů**, dokáže zpracovat projekty s **až 100 000 úkoly** v paměťově úsporném režimu a nabízí vestavěné metody pro čtení a zápis dat baseline — což usnadňuje automatizované reportování a integraci.

## Předpoklady
- **Java Development Kit (JDK)** – nainstalujte JDK 11 nebo novější. Můžete jej stáhnout z [webu](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – stáhněte nejnovější verzi ze [stránky ke stažení](https://releases.aspose.com/tasks/java/) a přidejte JAR do classpath vašeho projektu.

## Import balíčků
Třídy `Project`, `Task` a `TaskBaseline` se nacházejí v jmenném prostoru `com.aspose.tasks`. Importujte je na začátku vašeho zdrojového souboru:

Třída `Project` je hlavní objekt Aspose.Tasks, který v paměti představuje jeden soubor projektu. Poskytuje přístup k úkolům, zdrojům a kolekcím baseline.

## Jak číst baseline?
Načtěte projekt a poté dotazujte kolekci `TaskBaseline` pro každý úkol. Objekt `TaskBaseline` vrací start, finish a duration baseline, které byly zachyceny při volání `setBaseline`. Tento přímý přístup vám umožní číst hodnoty baseline bez parsování XML nebo binárních souborů.

## Krok 1: vytvořit novou instanci projektu
Třída `Project` představuje celý soubor projektu v paměti.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Krok 2: definovat úkol a nastavit baseline
`Task` představuje jednotlivou pracovní položku a `setBaseline` zachytí její aktuální plán jako baseline.
```java
Project project = new Project();
```

## Krok 3: přístup k informacím o baseline
`TaskBaseline` uchovává uložené hodnoty start, finish a duration pro baseline.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Krok 4: zobrazit duration baseline
`Duration` představuje délku času pro úkol nebo baseline.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Krok 5: zobrazit datum startu baseline
`Start` je naplánované počáteční datum baseline.
```java
System.out.println(baseline.getDuration().toString());
```

## Krok 6: zobrazit datum ukončení baseline
`Finish` je naplánované datum dokončení baseline.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Časté problémy a řešení
- **Baseline není nastaven:** Ujistěte se, že voláte `project.setBaseline(BaselineType.Baseline)` **po** přidání úkolů; jinak bude kolekce baseline prázdná.  
- **Null hodnoty:** Pokud `task.getBaselines()` vrací prázdný seznam, ověřte, že úkol byl přidán do hierarchie projektu před nastavením baseline.  
- **Formát data:** Metody `getStart()` a `getFinish()` vrací objekty `java.util.Date`. Použijte `SimpleDateFormat`, pokud potřebujete vlastní formát zobrazení.

## Často kladené otázky

**Q: Jak vytvořit novou instanci projektu v Aspose.Tasks?**  
A: Vytvořte instanci třídy `Project` (`Project project = new Project();`). Tím vytvoříte nový soubor projektu připravený pro úkoly a baseline.

**Q: Jaký je rozdíl mezi `BaselineType.Baseline` a ostatními typy baseline?**  
A: `BaselineType.Baseline` odkazuje na primární baseline (Baseline 1). Aspose.Tasks také podporuje Baseline 2‑10 pro další snímky.

**Q: Mohu exportovat data baseline do Excelu nebo CSV?**  
A: Ano, můžete iterovat přes objekty `TaskBaseline` a zapisovat hodnoty do CSV souboru pomocí standardního Java I/O.

**Q: Ovlivňuje nastavení baseline existující data úkolů?**  
A: Nastavení baseline zachytí aktuální data, ale nemění aktivní plán úkolu. Stále můžete upravit data start/finish po nastavení baseline.

**Q: Je možné programově porovnat více baseline?**  
A: Rozhodně. Získejte každou baseline pomocí `task.getBaselines().get(index)` a porovnejte jejich vlastnosti `Start`, `Finish` a `Duration`.

---

**Poslední aktualizace:** 2026-08-29  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Související tutoriály

- [Vytvořit seznam úkolů Java – MS Project Baseline pomocí Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Jak nastavit dobu trvání baseline v Aspose.Tasks pro Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Vytvořit MPP projekt Java – změnit průběh úkolu pomocí Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}