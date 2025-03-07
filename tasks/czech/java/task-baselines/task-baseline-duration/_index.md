---
title: Správa doby trvání základního úkolu v Aspose.Tasks
linktitle: Správa doby trvání základního úkolu v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně spravovat základní linie úkolů v MS Project pomocí Aspose.Tasks for Java. Tento tutoriál vás krok za krokem provede celým procesem.
weight: 12
url: /cs/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa doby trvání základního úkolu v Aspose.Tasks

## Úvod
Správa směrných plánů úkolů v MS Project je zásadní pro plánování a sledování projektů. V tomto tutoriálu prozkoumáme, jak efektivně spravovat dobu trvání základního úkolu pomocí Aspose.Tasks for Java.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK).
2.  Knihovna Aspose.Tasks: Stáhněte a nainstalujte knihovnu Aspose.Tasks for Java z[tady](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Nejprve importujte potřebné balíčky pro váš projekt Java:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Krok 1: Vytvořte instanci projektu
Inicializujte novou instanci projektu pomocí následujícího kódu:
```java
Project project = new Project();
```
## Krok 2: Vytvořte základní plán úkolu
Vytvořte nový úkol a nastavte jeho směrný plán pomocí následujícího kódu:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Krok 3: Zobrazte základní informace o úkolu
Načtěte a zobrazte základní informace o úkolu, jako je trvání, datum zahájení, datum ukončení a další:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Krok 4: Zkontrolujte Interim Baseline a Fixní náklady
Zkontrolujte, zda je základní linie prozatímní základní hodnotou, a zjistěte případné fixní náklady s tím spojené:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Krok 5: Tisk časově uspořádaných dat
Vytiskněte časově uspořádaná data spojená se základním plánem úkolu:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Podle těchto kroků můžete efektivně spravovat dobu trvání základního plánu úkolů v MS Project pomocí Aspose.Tasks for Java.

## Závěr
Správa směrných plánů úkolů je nezbytná pro řízení projektu, umožňuje vám sledovat odchylky od plánovaného plánu. S Aspose.Tasks for Java se tento proces zjednoduší a zefektivní, což umožňuje lepší kontrolu a realizaci projektu.
## FAQ
### Co je základní linie úkolů v MS Project?
Směrný plán úkolu v MS Project je snímek počátečního plánovaného plánu úkolu, včetně jeho data zahájení, data dokončení a trvání.
### Proč je důležité řídit základní úkoly?
Správa směrných plánů úkolů pomáhá při porovnávání plánovaného harmonogramu se skutečným postupem projektu, což usnadňuje sledování a rozhodování.
### Mohu upravit směrný plán úkolu, jakmile je nastaven?
Ano, v MS Project můžete upravit směrné plány úkolů tak, aby odrážely změny v plánu projektu. Je však nezbytné zdokumentovat jakékoli odchylky od původní základní linie.
### Podporuje Aspose.Tasks další funkce projektového řízení?
Ano, Aspose.Tasks nabízí širokou škálu funkcí pro řízení projektů, včetně plánování úkolů, alokace zdrojů a generování Ganttových diagramů.
### Kde najdu podporu pro Aspose.Tasks?
 Podporu pro Aspose.Tasks najdete na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete klást otázky a komunikovat s ostatními uživateli.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
