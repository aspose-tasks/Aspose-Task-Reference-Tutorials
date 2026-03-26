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

## Úvod
Pokud potřebujete **přizpůsobit vizuály Ganttova diagramu** v Microsoft Project, řízení počtu časových měřítek je klíčová technika. S Aspose.Tasks pro Java můžete programově nastavit spodní a střední úroveň časových měřítek, jemně doladit viditelnost značek a poté **uložit projekt jako PDF** pro sdílení se zainteresovanými stranami. Tento tutoriál vás provede celým procesem – od nastavení prostředí až po vytvoření profesionálního PDF, které ocení váš přizpůsobený Ganttův pohled.

## Rychlé odpovědi
- **Co znamená „customize Gantt chart“?** Úprava časovýchtek, barev a rozvržení tak, aby vyhovovaly úrovním vašim potřebám reportování.
- **Která metoda API nastavuje počet spodní úrovně?** `view.getBottomTimescaleTier().setCount(int)`.
- **Mohu generovat PDF přímo z projektu?** Ano – použijte `project.save(..., SaveFileFormat.Pdf)`.
- **Potřebuji licenci pro produkční použití?** Je vyžadována komerční licence; k dispozici je zkušební verze.
- **Která verze Javy je podporována?** Java8nebo vyšší funguje s nejnovější knihovnou Aspose.Tasks.

## Co je „přizpůsobit Ganttův diagram“ v Aspose.Tasks?
Přizpůsobení Ganttova diagramu znamená programově měnit jeho vizuální komponenty – jako jsou intervaly časových měřítek, značky a úkolové pruhy – tak, aby diagram tomu odpovídal, jak chcete **spravovat vizualizaci projektu**. Změnou počtu časových měřítek řídíte, kolik dní, týdnů nebo měsíců každý segment představuje, což představuje diagram přehlednějším pro různé publikum.

## Předpoklady
Než začnete, se, že máte:

1. **Java Development Environment** – nainstalovaný JDK8nebo novější.
2. **Aspose.Tasks for Java Library** – stáhněte si ji z [zde](https://releases.aspose.com/tasks/java/).
3. **Basic Java Knowledge** – znalost syntaxe Javy a objektově orientovaných konceptů.

## Importujte balíčky
Importujte potřebné třídy do svého projektu Java:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Průvodce krok za krokem

### Krok 1: Nastavte Data Directory
Definujte, odkud budou čteny a kam budou zapsány soubory projektu:

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní cestou ve vašem počítači.

### Krok 2: Vytvoření nové instance projektu
Vytvořte novou instanci `Project`, která bude obsahovat všechny úkoly a nastavení zobrazení:

```java
Project project = new Project();
```

### Krok 3: Konfigurace zobrazení Ganttova diagramu
Vytvořte objekt `GanttChartView` – zde budete **generate Gantt view Java** kód pro kontrolu vzhledu diagramu:

```java
GanttChartView view = new GanttChartView();
```

### Krok 4: Nastavení časového měřítka pro spodní úroveň
Upravte spodní úroveň tak, aby zobrazovala dva intervaly a skryla značky:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Krok 5: Nastavení časového měřítka pro střední úroveň
Aplikujte stejnou konfiguraci na střední úroveň:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Krok 6: Přidání přizpůsobeného zobrazení do projektu
Připojte právě nakonfigurovaný pohled k instanci `Project`:

```java
project.getViews().add(view);
```

### Krok 7: Přidání ukázkových úkolů (testovací data)
Vytvořte několik úkolů s konkrétními délkami, aby byl ilustrován přizpůsobený Ganttův diagram:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Krok 8: Uložení projektu jako PDF
Nakonec exportujte projekt – včetně vašeho **customized Gantt chart** – do PDF souboru:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Výsledné PDF ukazuje, jak byly spodní a střední úrovně časových měřítek **customized**, a poskytuje zainteresovaným stranám jasný, tisknutelný pohled na harmonogram.

## Běžné problémy a odstraňování problémů
- **PDF je prázdné** – naleznete, že cesta `dataDir` končí oddělovacím souborem (`/` nebo `\`) a že adresář existuje.
- **Klíšťata se stále objevují** – Ověřte, že je na obou úrovních zavolána metoda `setShowTicks(false)`.
- **Dration not Apply** – Zkontrolujte, že při vytváření délek zapnete `TimeUnitpe.Hour`nebo příslušnou jednotku).

## Často kladené otázky

**Otázka: Dokáže Aspose.Tasks for Java zpracovat rozsáhlé soubory projektů?**
Odpověď: Ano, knihovna je optimalizována pro vysoce výkonné zpracování rozsáhlých projektových dat.

**Otázka: Je Aspose.Tasks pro Javu kompatibilní s různými Java IDE?**
Odpověď: Rozhodně – funguje bez problémů s Eclipse, IntelliJ IDEA, NetBeans a dalšími populárními IDE.

**Otázka: Mohu si přizpůsobit vzhled Ganttových diagramů nad rámec nastavení časového měřítka?**
Odpověď: Ano, Aspose.Tasks nabízí rozsáhlé možnosti stylingu, jako jsou barvy sloupců, písma a čáry mřížky.

**Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro Javu?**
Odpověď: Ano, bezplatnou zkušební verzi si můžete stáhnout [zde](https://releases.aspose.com/).

**Otázka: Kde mohu získat podporu pro Aspose.Tasks pro Javu?**
Odpověď: Podporu a pomoc naleznete na fóru Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Otázka: Jak programově změním barvu pozadí Ganttova diagramu?**
Odpověď: Po importu `java.awt.Color` použijte metodu `view.getGanttChartProperties().setBackgroundColor(Color)`.

## Závěr
Postupným sledováním těchto kroků jste se naučili, jak **tomize Gantt chart** úrovně časových měřítek, zlepšit **project visualization** a **save project as PDF** using Aspose.Tasks pro Java. Tento přístup vám dává plnou kontrolu vizuálního výstupu, což poskytujete nad sdílení jasných, profesionálních plánů s vaším týmem nebo klienty.

---

**Poslední aktualizace:** 21. 12. 2025
**Testováno s:** Aspose.Tasks for Java 24.12 (nejnovější v době psaní tohoto textu)
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}