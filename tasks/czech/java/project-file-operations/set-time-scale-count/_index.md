---
date: 2025-12-21
description: Naučte se, jak přizpůsobit zobrazení Ganttova diagramu, spravovat vizualizaci
  projektu a uložit projekt jako PDF pomocí Aspose.Tasks pro Javu. Jednoduše upravte
  počet časových měřítek.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Přizpůsobení Ganttova diagramu – Ovládání počtu časových měřítek v MS Project
  v Aspose.Tasks
url: /cs/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přizpůsobení Ganttova diagramu – Ovládání počtu časových měřítek v MS Project pomocí Aspose.Tasks

## Introduction
Pokud potřebujete **přizpůsobit vizuály Ganttova diagramu** v Microsoft Project, řízení počtu časových měřítek je klíčová technika. S Aspose.Tasks pro Java můžete programově nastavit spodní a střední úroveň časových měřítek, jemně doladit viditelnost značek a poté **uložit projekt jako PDF** pro sdílení se zainteresovanými stranami. Tento tutoriál vás provede celým procesem – od nastavení prostředí až po vytvoření profesionálního PDF, které odráží váš přizpůsobený Ganttův pohled.

## Quick Answers
- **Co znamená „customize Gantt chart“?** Úprava úrovní časových měřítek, barev a rozvržení tak, aby vyhovovaly vašim potřebám reportování.  
- **Která metoda API nastavuje počet spodní úrovně?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Mohu generovat PDF přímo z projektu?** Ano – použijte `project.save(..., SaveFileFormat.Pdf)`.  
- **Potřebuji licenci pro produkční použití?** Je vyžadována komerční licence; k dispozici je bezplatná zkušební verze.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší funguje s nejnovější knihovnou Aspose.Tasks.

## What is “customize Gantt chart” in Aspose.Tasks?
Přizpůsobení Ganttova diagramu znamená programově měnit jeho vizuální komponenty – jako jsou intervaly časových měřítek, značky a úkolové pruhy – tak, aby diagram odpovídal tomu, jak chcete **spravovat vizualizaci projektu**. Změnou počtu časových měřítek řídíte, kolik dní, týdnů nebo měsíců každý segment představuje, což činí diagram přehlednějším pro různé publikum.

## Prerequisites
Než začnete, ujistěte se, že máte:

1. **Java Development Environment** – nainstalovaný JDK 8 nebo novější.  
2. **Aspose.Tasks for Java Library** – stáhněte ji z [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – znalost syntaxe Javy a objektově orientovaných konceptů.

## Import Packages
Importujte potřebné třídy do svého Java projektu:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step‑by‑Step Guide

### Step 1: Set Data Directory
Definujte, odkud budou čteny a kam budou zapisovány soubory projektu:

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní cestou ve vašem počítači.

### Step 2: Create a New Project Instance
Vytvořte novou instanci `Project`, která bude obsahovat všechny úkoly a nastavení zobrazení:

```java
Project project = new Project();
```

### Step 3: Configure the Gantt Chart View
Vytvořte objekt `GanttChartView` – zde budete **generate Gantt view Java** kód pro kontrolu vzhledu diagramu:

```java
GanttChartView view = new GanttChartView();
```

### Step 4: Set Time Scale Count for the Bottom Tier
Upravte spodní úroveň tak, aby zobrazovala dva intervaly a skryla značky:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Step 5: Set Time Scale Count for the Middle Tier
Aplikujte stejnou konfiguraci na střední úroveň:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Step 6: Add the Customized View to the Project
Připojte právě nakonfigurovaný pohled k instanci `Project`:

```java
project.getViews().add(view);
```

### Step 7: Add Sample Tasks (Test Data)
Vytvořte několik úkolů s konkrétními délkami, aby byl ilustrován přizpůsobený Ganttův diagram:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Step 8: Save the Project as a PDF
Nakonec exportujte projekt – včetně vašeho **customized Gantt chart** – do PDF souboru:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Výsledné PDF ukazuje, jak byly spodní a střední úrovně časových měřítek **customized**, a poskytuje zainteresovaným stranám jasný, tisknutelný pohled na harmonogram.

## Common Issues & Troubleshooting
- **PDF is blank** – Ujistěte se, že cesta `dataDir` končí oddělovačem souborů (`/` nebo `\`) a že adresář existuje.  
- **Ticks still appear** – Ověřte, že je na obou úrovních zavolána metoda `setShowTicks(false)`.  
- **Duration not applied** – Zkontrolujte, že při vytváření délek používáte `TimeUnitType.Hour` (nebo příslušnou jednotku).

## Frequently Asked Questions

**Q: Can Aspose.Tasks for Java handle large‑scale project files?**  
A: Yes, the library is optimized for high‑performance processing of extensive project data.

**Q: Is Aspose.Tasks for Java compatible with different Java IDEs?**  
A: Absolutely – it works seamlessly with Eclipse, IntelliJ IDEA, NetBeans, and other popular IDEs.

**Q: Can I customize the appearance of Gantt charts beyond time‑scale settings?**  
A: Yes, Aspose.Tasks provides extensive styling options such as bar colors, fonts, and grid lines.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can get a free trial version from [here](https://releases.aspose.com/).

**Q: Where can I get support for Aspose.Tasks for Java?**  
A: You can find support and assistance on the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).

**Q: How do I programmatically change the Gantt chart’s background color?**  
A: Use the `view.getGanttChartProperties().setBackgroundColor(Color)` method after importing `java.awt.Color`.

## Conclusion
Postupným sledováním těchto kroků jste se naučili, jak **customize Gantt chart** úrovně časových měřítek, zlepšit **project visualization** a **save project as PDF** pomocí Aspose.Tasks pro Java. Tento přístup vám dává plnou kontrolu nad vizuálním výstupem, což usnadňuje sdílení jasných, profesionálních plánů s vaším týmem nebo klienty.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}