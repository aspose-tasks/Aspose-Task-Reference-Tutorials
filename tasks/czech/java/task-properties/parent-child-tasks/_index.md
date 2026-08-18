---
date: 2026-02-23
description: Naučte se, jak nastavit datum zahájení projektu, nastavit dobu trvání
  úkolu a uložit projekt jako MPP pomocí Aspose.Tasks pro Javu. Efektivně spravujte
  nadřazené a podřízené úkoly.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Nastavte počáteční datum projektu a spravujte nadřazené a podřízené úkoly v
  Aspose.Tasks
url: /cs/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavte datum zahájení projektu a spravujte nadřazené a podřazené úkoly v Aspose.Tasks

## Úvod
Efektivní organizace úkolů je základem úspěšného řízení projektů a **nastavení data zahájení projektu** správně je prvním krokem k dobře strukturovanému plánu. V tomto tutoriálu uvidíte, jak **nastavit datum zahájení projektu**, konfigurovat trvání úkolů a spravovat vztahy nadřazený‑podřazený pomocí Aspose.Tasks pro Java. Na konci budete připraveni **uložit projekt jako MPP**, aktualizovat procenta dokončení úkolů a přizpůsobit vlastnosti úkolů tak, aby vyhovovaly jakémukoli reálnému scénáři.

## Rychlé odpovědi
- **Jak nastavit datum zahájení projektu?** Použijte `proj.set(Prj.START_DATE, startDate);` po inicializaci objektu `Project`.  
- **Mohu přidat podřízené úkoly pod nadřazený úkol?** Ano – zavolejte `parentTask.getChildren().add("Child Task")`.  
- **V jakém formátu Aspose.Tasks ukládá soubor?** Použijte `SaveFileFormat.Mpp` k **uložení projektu jako MPP**.  
- **Jak aktualizovat dokončení úkolu?** Nastavte `Tsk.PERCENT_COMPLETE` na objektu úkolu.  
- **Kde mohu získat dočasnou licenci?** Navštivte stránku dočasné licence odkazovanou v FAQ.

## Předpoklady
Než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v jazyce Java.  
- Knihovna Aspose.Tasks pro Java nainstalována. Můžete si ji stáhnout [zde](https://releases.aspose.com/tasks/java/).  
- Integrované vývojové prostředí (IDE) pro Javu nastavené ve vašem systému.

## Import balíčků
Na začátek importujte potřebné balíčky do svého Java projektu. Tyto balíčky usnadňují bezproblémovou integraci s funkcionalitou Aspose.Tasks pro Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Krok 1: Nastavte datum zahájení projektu
Začněte nastavením data zahájení projektu a dalších relevantních parametrů.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Krok 2: Přidejte nadřazený úkol (Úkol 1)
Vytvořte nadřazený úkol s názvem "Task 1" a nakonfigurujte jeho vlastnosti, včetně **nastavení trvání úkolu**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Krok 3: Přidejte nadřazený úkol (Úkol 2) s podřízenými úkoly
Nyní přidejte další nadřazený úkol s názvem "Task 2" a zahrňte podřízené úkoly (Úkol 3 a Úkol 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Krok 4: Konfigurujte podřízené úkoly
Zadejte data zahájení, trvání a omezení pro Úkol 3 a Úkol 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Krok 5: Aktualizujte procento dokončení úkolu
Upravte procento dokončení pro Úkol 3 a Úkol 4 – takto **aktualizujete dokončení úkolu**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Krok 6: Uložte projekt
Nakonec **uložte projekt jako MPP** s aplikovanými změnami.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Tento krok‑za‑krokem průvodce ukazuje, jak efektivně spravovat nadřazené a podřazené úkoly pomocí Aspose.Tasks pro Java. Experimentujte s různými konfiguracemi, aby vyhovovaly požadavkům vašeho projektu.

## Proč přizpůsobovat vlastnosti úkolů?
Přizpůsobení vlastností úkolů, jako jsou data zahájení, trvání, omezení a procenta dokončení, vám poskytuje detailní kontrolu nad chováním plánu. Ať už potřebujete sladit úkoly s dostupností zdrojů nebo vynutit obchodní pravidla, Aspose.Tasks vám umožní **programově přizpůsobit vlastnosti úkolů**.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Datum zahájení nebylo použito** | Ujistěte se, že voláte `proj.set(Prj.START_DATE, …)` **po** vytvoření objektu `Project` a před přidáním úkolů. |
| **Podřízené úkoly dědí nesprávná omezení** | Nastavte explicitně `ConstraintType` a `ConstraintDate` pro každý podřízený úkol, jak je ukázáno v Kroku 4. |
| **Uložený soubor nelze otevřít v MS Project** | Ověřte, že používáte nejnovější verzi Aspose.Tasks a ukládáte pomocí `SaveFileFormat.Mpp`. |
| **Procento se neprojevuje v UI** | Po nastavení `Tsk.PERCENT_COMPLETE` zavolejte `proj.calculateTaskSchedule()`, pokud potřebujete přepočítané data. |

## Často kladené otázky
### Je Aspose.Tasks pro Java kompatibilní s různými formáty souborů projektu?
Ano, Aspose.Tasks pro Java podporuje různé formáty souborů projektu, včetně MPP a XML.

### Mohu přizpůsobit vlastnosti úkolů nad rámec toho, co je v tomto tutoriálu?
Rozhodně! Aspose.Tasks pro Java poskytuje rozsáhlé možnosti přizpůsobení vlastností úkolů.

### Existuje komunitní fórum pro Aspose.Tasks, kde mohu získat podporu?
Ano, můžete navštívit [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pro komunitní podporu.

### Jak mohu získat dočasnou licenci pro Aspose.Tasks pro Java?
Můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

### Kde najdu komplexní dokumentaci pro Aspose.Tasks pro Java?
Dokumentace je dostupná [zde](https://reference.aspose.com/tasks/java/).

**Další otázky a odpovědi**

**Q: Jak programově získat dočasnou licenci?**  
A: Načtěte soubor dočasné licence pomocí `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Mohu změnit výchozí jednotku trvání úkolu?**  
A: Ano – upravte argument `TimeUnitType` v `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: Jaká verze Aspose.Tasks je vyžadována pro použití `SaveFileFormat.Mpp`?**  
A: Všechny recentní verze (2022‑2026) podporují ukládání jako MPP; zkontrolujte poznámky k vydání pro případné breaking changes.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}