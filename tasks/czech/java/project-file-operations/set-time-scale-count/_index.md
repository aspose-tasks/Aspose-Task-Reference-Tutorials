---
date: 2026-03-29
description: Naučte se, jak vytvářet PDF soubory projektů a přizpůsobovat počet časových
  jednotek Ganttova diagramu pomocí Aspose.Tasks pro Javu. Tento průvodce vám krok
  za krokem ukáže, jak exportovat Gantt do PDF s plnou kontrolou.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Vytvořit PDF projektu – Přizpůsobit časovou osu Ganttova diagramu
url: /cs/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit PDF projektu – Přizpůsobit časovou stupnici Ganttova diagramu

## Úvod
Pokud potřebujete **vytvořit PDF projektu** soubory, které odrážejí dokonale nastavený Ganttův diagram, klíčové je řízení počtu časových stupnic. S Aspose.Tasks pro Java můžete programově nastavit spodní a střední úroveň časové stupnice, skrýt značky a poté **uložit projekt jako PDF** pro snadné šíření. V tomto tutoriálu vás provedeme vším, co potřebujete – od nastavení vývojového prostředí až po generování vylepšeného PDF, které představí váš přizpůsobený Ganttův pohled.

## Rychlé odpovědi
- **Co znamená „přizpůsobit Ganttův diagram“?** Úprava úrovní časové stupnice, barev a rozvržení tak, aby odpovídaly vašim požadavkům na reportování.  
- **Která metoda API nastavuje počet pro spodní úroveň?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Mohu generovat PDF přímo z projektu?** Ano – použijte `project.save(..., SaveFileFormat.Pdf)`.  
- **Potřebuji licenci pro produkční použití?** Je vyžadována komerční licence; je k dispozici bezplatná zkušební verze.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší funguje s nejnovější knihovnou Aspose.Tasks.

## Co znamená „přizpůsobit Ganttův diagram“ v Aspose.Tasks?
Přizpůsobení Ganttova diagramu znamená programově měnit jeho vizuální komponenty – jako jsou intervaly časové stupnice, značky a úkolové pruhy – tak, aby diagram odpovídal tomu, jak chcete **spravovat vizualizaci projektu**. Změnou počtu časových stupnic řídíte, kolik dní, týdnů nebo měsíců každý segment představuje, což činí diagram přehlednějším pro různé publikum.

## Proč vytvořit PDF projektu s přizpůsobeným Ganttovým diagramem?
- **Výstup připravený pro stakeholdery:** PDF je univerzálně zobrazitelné, zajišťuje, že všichni vidí stejný rozvrh.  
- **Přátelské k tisku:** Přesná kontrola nad úrovněmi časové stupnice zabraňuje přeplněným nebo nejasným výtiskům.  
- **Automatizace:** Integrujte generování PDF do CI pipeline nebo reportovacích služeb pro nulovou manuální práci.  

## Požadavky
1. **Vývojové prostředí Java** – nainstalovaný JDK 8 nebo novější.  
2. **Knihovna Aspose.Tasks pro Java** – Stáhněte ji z [zde](https://releases.aspose.com/tasks/java/).  
3. **Základní znalost Javy** – Znalost syntaxe Javy a objektově orientovaných konceptů.

## Importovat balíčky
Importujte potřebné třídy do svého Java projektu:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Průvodce krok za krokem

### Krok 1: Nastavit adresář dat
Definujte, odkud budou soubory projektu čteny a kam budou zapisovány:

```java
String dataDir = "Your Data Directory";
```

Nahraďte `"Your Data Directory"` absolutní cestou na vašem počítači.

### Krok 2: Vytvořit novou instanci projektu
Vytvořte novou instanci objektu `Project`, která bude obsahovat všechny úkoly a nastavení zobrazení:

```java
Project project = new Project();
```

### Krok 3: Nakonfigurovat zobrazení Ganttova diagramu
Vytvořte objekt `GanttChartView` – zde budete **generovat Java kód pro Gantt view** k ovládání vzhledu diagramu:

```java
GanttChartView view = new GanttChartView();
```

### Krok 4: Nastavit počet časových stupnic pro spodní úroveň
Upravte spodní úroveň tak, aby zobrazovala dva intervaly a skryla značky:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Krok 5: Nastavit počet časových stupnic pro střední úroveň
Použijte stejnou konfiguraci pro střední úroveň:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Krok 6: Přidat přizpůsobené zobrazení do projektu
Připojte právě nakonfigurované zobrazení k instanci `Project`:

```java
project.getViews().add(view);
```

### Krok 7: Přidat ukázkové úkoly (testovací data)
Vytvořte několik úkolů s konkrétními délkami pro ilustraci přizpůsobeného Ganttova diagramu:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Krok 8: Uložit projekt jako PDF
Nakonec exportujte projekt – včetně vašeho **přizpůsobeného Ganttova diagramu** – do PDF souboru:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Výsledné PDF ukazuje, jak byly spodní a střední úrovně časové stupnice **přizpůsobeny**, což poskytuje stakeholderům jasný, tisknutelný pohled na harmonogram.

## Časté problémy a řešení
- **PDF je prázdný** – Ujistěte se, že cesta `dataDir` končí souborovým oddělovačem (`/` nebo `\`) a že adresář existuje.  
- **Značky se stále zobrazují** – Ověřte, že `setShowTicks(false)` je voláno na obou úrovních.  
- **Délka není aplikována** – Potvrďte, že při vytváření délek používáte `TimeUnitType.Hour` (nebo příslušnou jednotku).

## Často kladené otázky

**Q: Může Aspose.Tasks pro Java zpracovávat velké projektové soubory?**  
A: Ano, knihovna je optimalizována pro vysokovýkonné zpracování rozsáhlých projektových dat.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými Java IDE?**  
A: Ano – funguje bez problémů s Eclipse, IntelliJ IDEA, NetBeans a dalšími populárními IDE.

**Q: Mohu přizpůsobit vzhled Ganttových diagramů mimo nastavení časové stupnice?**  
A: Ano, Aspose.Tasks poskytuje rozsáhlé možnosti stylování, jako jsou barvy pruhů, písma a mřížkové čáry.

**Q: Je k dispozici zkušební verze Aspose.Tasks pro Java?**  
A: Ano, můžete získat bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

**Q: Kde mohu získat podporu pro Aspose.Tasks pro Java?**  
A: Podporu a pomoc najdete na fóru Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Jak programově změnit barvu pozadí Ganttova diagramu?**  
A: Použijte metodu `view.getGanttChartProperties().setBackgroundColor(Color)` po importu `java.awt.Color`.

## Závěr
Po provedení těchto kroků jste se naučili, jak **vytvořit PDF projektu** soubory s plně přizpůsobenou časovou stupnicí Ganttova diagramu, zlepšit **vizualizaci projektu** a **uložit projekt jako PDF** pomocí Aspose.Tasks pro Java. Tento přístup vám dává plnou kontrolu nad vizuálním výstupem, což usnadňuje sdílení jasných, profesionálních harmonogramů s vaším týmem nebo klienty.

---

**Poslední aktualizace:** 2026-03-29  
**Testováno s:** Aspose.Tasks for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}