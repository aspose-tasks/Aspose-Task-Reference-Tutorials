---
date: 2026-09-30
description: Spravujte kritické úkoly v Java projektech pomocí Aspose.Tasks. Naučte
  se řešit kritické a na úsilí založené úkoly, stáhněte knihovnu a zrychlete svůj
  workflow projektového řízení.
keywords:
- manage critical tasks java
- effort‑driven tasks Aspose.Tasks
- Java project management
lastmod: 2026-09-30
linktitle: Správa kritických a na úsilí založených úkolů v Aspose.Tasks
og_description: Spravujte kritické úkoly, se kterými se setkávají vývojáři Java, pomocí
  Aspose.Tasks. Tento průvodce ukazuje krok za krokem, jak řešit kritické a na úsilí
  založené úkoly v Java projektech.
og_image_alt: Screenshot of Aspose.Tasks Java API managing critical and effort‑driven
  tasks
og_title: Jak spravovat kritické úkoly v Javě pomocí Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Manage critical tasks Java projects with Aspose.Tasks. Learn to handle
    critical and effort‑driven tasks, download the library and boost your project
    management workflow.
  headline: How to manage critical tasks in Java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is platform‑independent and runs on Windows,
      Linux, and macOS.
    question: Can I use Aspose.Tasks for Java in both Windows and Linux environments?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java on the [Aspose.Tasks
      free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find support for Aspose.Tasks for Java?
  - answer: You can acquire a temporary license on the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: You can purchase Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- critical tasks
- effort‑driven tasks
- Aspose.Tasks
- Java
- project management
title: Jak spravovat kritické úkoly v Javě pomocí Aspose.Tasks
url: /cs/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spravujte kritické a na úsilí řízené úkoly v Javě s Aspose.Tasks

V moderním řízení projektů je **manage critical tasks java** každodenní výzvou pro vývojáře, kteří potřebují udržet harmonogramy v pořádku a zároveň pracovat s úkoly řízenými úsilím. Aspose.Tasks pro Java vám poskytuje čistý programový způsob, jak identifikovat, kontrolovat a aktualizovat kritické a na úsilí řízené úkoly bez ručního manipulování s tabulkami.

## Rychlé odpovědi
- **Jaký je hlavní přínos?** Automaticky označuje kritické úkoly a upravuje plánování řízené úsilím jedním voláním API.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaké verze Javy jsou podporovány?** Java 8 až 17, jak OpenJDK, tak Oracle distribuce.  
- **Mohu zpracovávat velké projekty?** Ano – Aspose.Tasks zvládne projekty až s 10 000 úkoly efektivně.  
- **Je knihovna multiplatformní?** Knihovna běží na Windows, Linuxu i macOS bez nativních závislostí.

## Jak spravovat kritické a na úsilí řízené úkoly v Aspose.Tasks pro Java?
Načtěte svůj projektový soubor pomocí třídy `Project`, použijte `ChildTasksCollector` k sesbírání všech úkolů a poté prozkoumejte vlastnosti `Critical` a `EffortDriven` u každého úkolu. Iterací přes sesbíraný seznam můžete vytvořit stavovou zprávu nebo automaticky upravit pravidla plánování, vše jen s několika řádky Java kódu, který se vykoná během několika sekund.

Aspose.Tasks pro Java podporuje **30+ vstupních a výstupních formátů projektů** (včetně Microsoft Project 2019, 2022 a Primavera P6) a může zpracovávat soubory s **až 10 000 úkoly**, přičemž spotřeba paměti zůstává pod 200 MB na typickém serveru. Tyto kvantifikované schopnosti jej činí vhodným pro podnikovou úroveň plánování.

## Předpoklady
Než začnete, ujistěte se, že máte:

- **Aspose.Tasks pro Java** knihovnu – stáhněte ji z [dokumentace Aspose.Tasks pro Java](https://reference.aspose.com/tasks/java/).  
- **Java Development Kit (JDK)** – verze 8 nebo novější nainstalovanou ve vašem systému.  
- **IDE** dle vašeho výběru (IntelliJ IDEA, Eclipse, VS Code, atd.).  
- Ukázkový projektový soubor ve formátu XML (nebo .mpp), který použijete pro demonstraci.

## Import balíčků
Přidejte požadované jmenné prostory do svého Java zdrojového souboru:

```java
import com.aspose.tasks.*;
import java.util.*;
```

Tyto importy vám poskytují přístup k základním třídám pro správu úkolů, jako jsou `Project`, `Task` a pomocné utility.

## Co je kritický úkol?
**Kritický úkol** je jakákoli činnost, jejíž zpoždění přímo prodlužuje datum dokončení projektu, což znamená, že leží na kritické cestě harmonogramu. V Aspose.Tasks můžete zjistit, zda je úkol kritický, voláním metody `Task.isCritical()`, která vrací `true`, když úkol ovlivňuje celkový čas dokončení projektu.

## Co je úkol řízený úsilím?
**Úkol řízený úsilím** automaticky přerozděluje svou zbývající práci vždy, když se změní jeho trvání, což zajišťuje, že celkové množství úsilí zůstává během celého harmonogramu konstantní. Toto chování je užitečné pro zdroje pracující pevnou rychlostí. V Aspose.Tasks vlastnost `Task.isEffortDriven()` vrací `true` pro úkoly, které tuto charakteristiku vykazují.

## Krok 1: sběr úkolů pomocí ChildTasksCollector
Třída `ChildTasksCollector` sbírá každý úkol pod daným nadřazeným úkolem.  

`ChildTasksCollector` je pomocník, který prochází hierarchii úkolů a vrací plochý seznam objektů `Task`.

```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector);
List<Task> allTasks = collector.getTasks();
```

## Krok 2: iterace přes sesbírané úkoly
Procházejte seznam a vypište kritický a na úsilí řízený stav každého úkolu.

```java
for (Task t : allTasks) {
    boolean isCritical = t.get(Tsk.Critical);
    boolean isEffortDriven = t.get(Tsk.EffortDriven);
    System.out.println("Task ID " + t.get(Tsk.Id) + 
        ": critical=" + isCritical + ", effortDriven=" + isEffortDriven);
}
```

Tento jednoduchý dvoustupňový vzor vám poskytne kompletní přehled o zdraví plánování projektu.

## Časté problémy a řešení
- **NullPointerException při přístupu k vlastnostem úkolu** – Ujistěte se, že je projektový soubor plně načten před přístupem k úkolům (`project = new Project("file.mpp")`).  
- **Nesprávná značka kritického úkolu** – Ověřte, že režim výpočtu projektu je nastaven na `CalculationMode.Automatic`, aby Aspose.Tasks mohl po úpravách přepočítat kritickou cestu.  
- **Velké soubory zpomalují** – Použijte `Project.set(Prj.ReadOnly, true)` k otevření souboru v režimu jen pro čtení, což snižuje paměťovou zátěž při analýzách jen pro čtení.

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks pro Java jak ve Windows, tak v Linuxu?**  
A: Ano, Aspose.Tasks pro Java je platformně nezávislý a běží na Windows, Linuxu i macOS.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro Java na [stránce ke stažení bezplatné zkušební verze Aspose.Tasks](https://releases.aspose.com/).

**Q: Kde najdu podporu pro Aspose.Tasks pro Java?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro komunitní podporu a diskuze.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks pro Java?**  
A: Dočasnou licenci můžete získat na [stránce žádosti o dočasnou licenci](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu zakoupit Aspose.Tasks pro Java?**  
A: Aspose.Tasks pro Java můžete zakoupit na [stránce nákupu](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-09-30  
**Testováno s:** Aspose.Tasks pro Java 24.11  
**Autor:** Aspose  

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

## Související tutoriály

- [Critical Path MS Project – Aspose.Tasks Java Tutorial](/tasks/java/project-management/critical-path/)
- [Create Project Management Task Dependencies in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Project Management Java: Task % Complete using Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}