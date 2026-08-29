---
date: 2026-08-29
description: Naučte se, jak nastavit baseline duration a sledovat project progress
  pomocí Aspose.Tasks for Java. Tento krok‑za‑krokem průvodce vám pomůže efektivně
  spravovat task baselines.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Jak nastavit baseline duration v Aspose.Tasks for Java
og_description: Naučte se, jak nastavit baseline duration a sledovat project progress
  pomocí Aspose.Tasks for Java. Postupujte podle tohoto podrobného průvodce a efektivně
  spravujte task baselines.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Jak nastavit baseline duration pro sledování project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Jak nastavit baseline duration pro sledování project progress
url: /cs/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit dobu trvání základní linie pro sledování postupu projektu

## Úvod
Sledování postupu projektu začíná pevnou základní linií. V tomto tutoriálu objevíte **jak nastavit dobu trvání základní linie** pro úkoly v souborech Microsoft Project pomocí knihovny Aspose.Tasks pro Javu a pochopíte, proč včasné vytvoření základní linie pomáhá monitorovat odchylky v plánu, rozpočtové odchylky a přetížení zdrojů během celého životního cyklu projektu.

## Rychlé odpovědi
- **Co znamená „set baseline“?** Zaznamenává původní začátek, ukončení a dobu trvání úkolu, abyste mohli porovnávat budoucí změny.  
- **Která třída Aspose.Tasks vytváří projekt?** Třída `Project` – také se naučíte, jak správně **vytvořit instanci projektu**.  
- **Potřebuji licenci pro spuštění kódu?** Bezplatná zkušební licence funguje pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu získat mezilehlé základní linie?** Ano, Aspose.Tasks vám umožňuje dotazovat se na mezilehlé základní linie a jejich fixní náklady.  
- **Jaká verze Javy je požadována?** Doporučuje se Java 8 nebo novější.  
- **Jak mi to pomáhá sledovat postup projektu?** Jakmile je základní linie nastavena, můžete okamžitě porovnávat skutečná data s původním plánem pomocí vestavěných funkcí reportování.

## Co je základní linie úkolu a proč ji nastavit?
Základní linie úkolu zachycuje plánovaný harmonogram (datum zahájení, datum dokončení a dobu trvání) v konkrétním okamžiku. Nastavením základní linie vytvoříte referenční bod, který usnadňuje odhalování odchylek v plánu, překročení nákladů a přetížení zdrojů během vývoje projektu.

## Proč používat Aspose.Tasks pro správu základních linií?
Aspose.Tasks poskytuje **plnou kompatibilitu s .mpp** – můžete číst a zapisovat nativní soubory Microsoft Project bez nutnosti instalace Microsoft Office. API vám poskytuje programový přístup k **více než 50 vstupním a výstupním formátům**, podporuje **mezilehlé základní linie 1‑10** a dokáže zpracovat **projekty o stovkách stránek** bez načítání celého souboru do paměti, což je nezbytné pro vysoce výkonné dávkové zpracování.

## Požadavky
1. **Java vývojové prostředí** – nainstalovaný a nakonfigurovaný JDK 8+.  
2. **Aspose.Tasks pro Javu** – stáhněte knihovnu ze [stránky ke stažení Aspose.Tasks pro Javu](https://releases.aspose.com/tasks/java/).  
3. **IDE nebo nástroj pro sestavení** – Maven, Gradle nebo jakékoli IDE, které preferujete.

## Import balíčků
Následující importy přinášejí základní třídy Aspose.Tasks potřebné pro práci s projekty, úkoly, základními liniemi a časově fázovanými daty.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Krok 1: vytvořit instanci projektu
Třída `Project` představuje soubor Microsoft Project v paměti a je vstupním bodem pro všechny operace.

```java
Project project = new Project();
```

## Krok 2: vytvořit základní linii úkolu
`TaskBaseline` ukládá plánovaný začátek, ukončení a dobu trvání konkrétního úkolu.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Krok 3: zobrazit informace o základní linii úkolu
Metoda `getBaselines()` vrací kolekci základních linií spojených s úkolem.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Krok 4: zkontrolovat mezilehlou základní linii a fixní náklady
`BaselineType` enumeruje primární a mezilehlé základní linie (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Krok 5: vypsat časově fázovaná data
`TimephasedData` představuje část informací o harmonogramu pro konkrétní časový interval.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Dodržením těchto kroků můžete **nastavit dobu trvání základní linie** pro libovolný úkol a získat podrobné informace o základní linii pomocí Aspose.Tasks pro Javu, což vám poskytne spolehlivý způsob, jak **sledovat postup projektu** během celého životního cyklu projektu.

## Časté problémy a řešení
- **Základní linie se nezobrazuje v MS Project:** Ujistěte se, že jste zavolali `project.setBaseline(BaselineType.Baseline)` **po** přidání úkolu.  
- **NullPointerException při `getBaselines()`:** Ověřte, že byl úkol přidán do projektu před nastavením základní linie.  
- **Neshoda časové jednotky:** Použijte `TimeUnitType` pro správné formátování doby trvání, zejména při práci s vlastními kalendáři.

## Často kladené otázky
### Co je základní linie úkolu v MS Project?
Základní linie úkolu v MS Project je snímek počátečního plánovaného harmonogramu úkolu, zahrnujícího datum zahájení, datum dokončení a dobu trvání.

### Proč je důležitá správa základních linií úkolů?
Správa základních linií úkolů pomáhá porovnávat plánovaný harmonogram se skutečným postupem projektu, což usnadňuje lepší sledování a rozhodování.

### Mohu upravit základní linii úkolu po jejím nastavení?
Ano, můžete upravit základní linie úkolů v MS Project, aby odrážely změny v plánu projektu. Je však důležité zdokumentovat veškeré odchylky od původní základní linie.

### Podporuje Aspose.Tasks další funkce řízení projektů?
Ano, Aspose.Tasks nabízí širokou škálu funkcí pro řízení projektů, včetně plánování úkolů, přidělování zdrojů a generování Ganttových diagramů.

### Kde mohu najít podporu pro Aspose.Tasks?
Podporu pro Aspose.Tasks můžete najít na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a komunikovat s ostatními uživateli.

## Další často kladené otázky
**Q: Musím volat `setBaseline` pro každý úkol zvlášť?**  
A: Ne. Volání `project.setBaseline(BaselineType.Baseline)` zaznamená základní linii pro všechny úkoly v projektu najednou.

**Q: Jak mohu nastavit mezilehlou základní linii pro konkrétní úkol?**  
A: Použijte `project.setBaseline(BaselineType.Baseline1)` (nebo Baseline2‑Baseline10) po aktualizaci harmonogramu úkolu.

**Q: Je možné exportovat data základní linie do CSV?**  
A: Ano. Projděte `task.getBaselines()` a zapište požadovaná pole do CSV souboru pomocí standardního Java I/O.

**Q: Mohu načíst existující .mpp soubor, který již obsahuje základní linie?**  
A: Rozhodně. Načtěte soubor pomocí `new Project("myproject.mpp")` a poté přistupujte k základním liniím každého úkolu, jak je uvedeno výše.

**Q: Zvládá Aspose.Tasks soubory s více projekty?**  
A: Aspose.Tasks pracuje s jednoprojkovými .mpp soubory. Pro scénáře s více projekty kombinujte projekty programově.

---

**Poslední aktualizace:** 2026-08-29  
**Testováno s:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit seznam úkolů v Javě – základní linie MS Project pomocí Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Vytvořit MPP projekt v Javě – změna postupu úkolu pomocí Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Základní linie řízení projektu – plánování úkolů pomocí Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}