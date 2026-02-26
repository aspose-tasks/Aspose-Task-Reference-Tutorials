---
date: 2026-02-26
description: Naučte se, jak rozdělit úkoly pomocí Aspose.Tasks pro Javu – definitní
  průvodce, jak rozdělit úkoly, nastavit kalendář projektu a vytvořit přiřazení zdrojů.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak rozdělit úkoly v Aspose.Tasks
url: /cs/java/task-properties/split-tasks/
weight: 29
---

 close.

We must keep them unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak rozdělit úkoly v Aspose.Tasks

## Úvod
Pokud hledáte **jak rozdělit úkoly** v projektu založeném na Javě, jste na správném místě. Aspose.Tasks for Java vám poskytuje čistý, programový způsob, jak rozdělit dlouhodobý úkol na menší, zvládnutelné části, což pomáhá s vyrovnáváním zdrojů, přesným reportováním a těsnějšími termíny projektu. V tomto tutoriálu projdeme celý proces – od nastavení kalendáře projektu po vytvoření přiřazení zdroje a nakonec rozdělení úkolu na více segmentů.

## Rychlé odpovědi
- **Co je rozdělení úkolu?** Rozdělení jednoho úkolu na několik menších intervalů při zachování celkové délky.  
- **Proč rozdělovat úkoly v Javě?** Umožňuje přesné přidělování zdrojů a lepší sledování postupu.  
- **Která knihovna pomáhá?** Aspose.Tasks for Java poskytuje vestavěné metody pro rozdělení a časové fáze.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; licence je vyžadována pro produkci.  
- **Jaká verze Javy je podporována?** Knihovna funguje s Javou 8 a novějšími.

## Předpoklady
Než se ponoříte do tutoriálu, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovna Aspose.Tasks for Java stažená a přidaná do vašeho projektu. Můžete ji stáhnout z [dokumentace Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## Import balíčků
Začněte importováním potřebných balíčků do vašeho Java projektu:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Krok 1: Vytvořit nový projekt
Začněte vytvořením nového projektu pomocí knihovny Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Krok 2: Nastavit kalendář projektu
Nastavení **project calendar** definuje pracovní dny, svátky a celkový časový rámec vašeho plánu. Tento krok je nezbytný pro přesné výpočty časově fázovaných dat.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Krok 3: Přidat kořenový úkol
Každý projekt potřebuje kořenový kontejner. Přidání kořenového úkolu vám poskytne místo, kam můžete připojit všechny následné úkoly.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Krok 4: Přidat nový úkol k rozdělení
Vytvořte úkol, který chcete rozdělit. Zde jako příklad nastavíme dobu trvání na tři dny.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Krok 5: Vytvořit přiřazení zdroje
**Resource assignment** spojuje zdroj (nebo zástupný znak) s úkolem. Toto je vyžadováno před generováním časově fázovaných dat.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Krok 6: Vygenerovat časově fázovaná data
Časově fázovaná data představují, jak je práce rozložena během doby trvání úkolu. Jejich generování připraví úkol na rozdělení.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Krok 7: Rozdělit úkol
Nyní **split the task into parts**. V tomto příkladu rozdělíme třídenní úkol na tři jednodenní segmenty.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Proč rozdělovat úkoly?
Rozdělení úkolů vám poskytuje jemnější kontrolu nad:
- **Vyrovnání zdrojů:** Přiřadit různé zdroje k jednotlivým segmentům.
- **Sledování postupu:** Aktualizovat stav po jednotlivých segmentech.
- **Reportování:** Vytvářet podrobnější Ganttovy diagramy a zprávy.

## Časté problémy a řešení
- **Chybějící data kalendáře:** Ujistěte se, že před rozdělením zavoláte `timephasedDataFromTaskDuration`.  
- **Segmenty s nulovou délkou:** Ověřte, že každý rozdělený interval má nenulovou dobu trvání; jinak jej knihovna ignoruje.  
- **Licence výjimky:** Spuštění bez platné licence může přidat vodoznak do exportovaných souborů.

## Často kladené otázky
### Můžu rozdělit úkoly s různými délkami?
Ano, můžete upravit délku každé části tak, aby odpovídala požadavkům vašeho projektu.

### Je Aspose.Tasks for Java kompatibilní se všemi verzemi Javy?
Aspose.Tasks for Java je navrženo tak, aby bez problémů fungovalo s Javou 8 a novějšími, což zajišťuje širokou kompatibilitu.

### Můžu používat Aspose.Tasks for Java zdarma?
Aspose.Tasks for Java nabízí bezplatnou zkušební verzi, která vám umožní prozkoumat jeho funkce před zakoupením.

### Jak mohu získat podporu pro Aspose.Tasks for Java?
Navštivte [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15), kde získáte pomoc a spojíte se s komunitou.

### Potřebuji dočasnou licenci pro Aspose.Tasks for Java?
Dočasnou licenci můžete získat na [this link](https://purchase.aspose.com/temporary-license/) pro testovací a evaluační účely.

---

**Poslední aktualizace:** 2026-02-26  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}