---
title: Zvládnutí časového měřítka projektu MS Project v Aspose.Tasks
linktitle: Nastavte počet časového měřítka v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně spravovat počet časových řad v MS Project pomocí Aspose.Tasks for Java. Optimalizujte vizualizaci a správu projektu bez námahy.
weight: 22
url: /cs/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí časového měřítka projektu MS Project v Aspose.Tasks

## Úvod
Správa počtu časového měřítka v MS Project může významně ovlivnit vizualizaci a správu projektu. S Aspose.Tasks for Java, výkonným rozhraním API pro programové zpracování úkolů projektového řízení, můžete efektivně manipulovat s počtem časového měřítka a přizpůsobit zobrazení projektu vašim konkrétním potřebám.
## Předpoklady
Než začnete, ujistěte se, že máte na svém místě následující:
1. Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK).
2.  Aspose.Tasks for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for Java. Můžete to získat od[tady](https://releases.aspose.com/tasks/java/).
3. Základní znalost programování v Javě: Výhodou bude znalost programovacího jazyka Java.

## Importujte balíčky
Importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Krok 1: Nastavte Data Directory
Definujte cestu k datovému adresáři, kde budou uloženy soubory vašeho projektu:
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` s cestou k vašemu datovému adresáři.
## Krok 2: Vytvořte instanci projektu
 Vytvořte nový`Project` objekt:
```java
Project project = new Project();
```
Tím se vytvoří nový objekt projektu.
## Krok 3: Konfigurace zobrazení Ganttova diagramu
 Vytvořit`GanttChartView` objekt pro konfiguraci zobrazení Ganttova diagramu:
```java
GanttChartView view = new GanttChartView();
```
## Krok 4: Nastavte počet časového měřítka pro spodní úroveň
Nastavte počet a viditelnost tiků pro spodní vrstvu časové osy:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
To určuje počet intervalů a zda se mají zobrazovat ticks pro spodní vrstvu.
## Krok 5: Nastavte počet časového měřítka pro střední úroveň
Podobně nakonfigurujte střední časovou vrstvu:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Krok 6: Přidejte pohled do projektu
Přidejte do projektu nakonfigurovaný pohled:
```java
project.getViews().add(view);
```
Tím se do projektu přidá přizpůsobený pohled.
## Krok 7: Přidejte testovací data do projektu
Přidejte do projektu některá testovací data pro demonstraci:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Vzniknou tak dva úkoly se zadanou dobou trvání.
## Krok 8: Uložte projekt jako PDF
Uložte projekt jako soubor PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Tím se projekt s použitými konfiguracemi uloží do souboru PDF.

## Závěr
Efektivní správa časového měřítka v MS Project pomocí Aspose.Tasks pro Java vám umožňuje přizpůsobit zobrazení projektu pro lepší vizualizaci a správu.
## FAQ
### Otázka: Dokáže Aspose.Tasks for Java zpracovat rozsáhlé soubory projektů?
Odpověď: Ano, Aspose.Tasks for Java je schopen efektivně zpracovávat rozsáhlé soubory projektů.
### Otázka: Je Aspose.Tasks for Java kompatibilní s různými Java IDE?
Odpověď: Ano, Aspose.Tasks for Java bezproblémově funguje s populárními Java Integrated Development Environment (IDE), jako jsou Eclipse a IntelliJ IDEA.
### Otázka: Mohu upravit vzhled Ganttových diagramů pomocí Aspose.Tasks for Java?
Odpověď: Rozhodně, Aspose.Tasks for Java poskytuje rozsáhlé možnosti přizpůsobení vzhledu Ganttových diagramů podle vašich požadavků.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro Javu?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/).
### Otázka: Kde mohu získat podporu pro Aspose.Tasks for Java?
 Odpověď: Podporu a pomoc můžete najít na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
