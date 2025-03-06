---
title: Rozdělit úkoly v Aspose.Tasks
linktitle: Rozdělit úkoly v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Ovládněte správu úloh v Javě pomocí Aspose.Tasks! Naučte se, jak efektivně rozdělit úkoly pro optimalizované časové osy projektů. Stáhnout teď!
weight: 29
url: /cs/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rozdělit úkoly v Aspose.Tasks

## Úvod
Potýkáte se se správou úloh ve svém projektu Java? Aspose.Tasks for Java poskytuje výkonné řešení pro efektivní rozdělování úkolů a zlepšuje možnosti řízení projektů. V tomto tutoriálu vás provedeme procesem rozdělování úkolů pomocí Aspose.Tasks for Java, který vám pomůže optimalizovat časové osy vašich projektů a alokace zdrojů.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
-  Knihovna Aspose.Tasks pro Java byla stažena a přidána do vašeho projektu. Můžete si jej stáhnout z[Aspose.Tasks pro dokumentaci Java](https://reference.aspose.com/tasks/java/).
## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java:
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
## Krok 1: Vytvořte nový projekt
Začněte vytvořením nového projektu pomocí knihovny Aspose.Tasks:
```java
// Vytvořte nový projekt
Project splitTaskProject = new Project();
```
## Krok 2: Nastavte kalendář projektu
Nastavením kalendáře projektu vytvořte časovou osu:
```java
// Získejte standardní kalendář
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Nastavit nastavení kalendáře projektu
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (pokračujte v příkladu)
```
## Krok 3: Přidejte kořenovou úlohu
Přidejte do projektu kořenovou úlohu:
```java
// Kořenový úkol
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Krok 4: Přidejte do Splitu nový úkol
Přidejte do projektu nový úkol, který chcete rozdělit:
```java
// Přidat nový úkol
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Krok 5: Vytvořte přiřazení zdrojů
Vytvořte nové přiřazení zdroje pro úkol:
```java
// Vytvořte nové přiřazení zdroje
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Krok 6: Vygenerujte časově uspořádaná data
Vygenerujte časově uspořádaná data přiřazení zdrojů:
```java
// Generujte časově uspořádaná data přiřazení zdrojů
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Krok 7: Rozdělte úkol
Rozdělte úkol na několik částí:
```java
// Rozdělte úkol na 3 části
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (pokračujte v příkladu)
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak rozdělit úkoly pomocí Aspose.Tasks for Java. Tato výkonná knihovna zjednodušuje správu úloh v projektech Java a poskytuje efektivní řešení pro optimalizaci časových plánů projektů a alokace zdrojů.
## Často kladené otázky
### Mohu rozdělit úkoly s různým trváním?
Ano, dobu trvání úkolů můžete upravit podle požadavků vašeho projektu.
### Je Aspose.Tasks for Java kompatibilní se všemi verzemi Java?
Aspose.Tasks for Java je navržen tak, aby bezproblémově fungoval s různými verzemi Java a zajistil kompatibilitu.
### Mohu používat Aspose.Tasks pro Javu zdarma?
Aspose.Tasks for Java nabízí bezplatnou zkušební verzi, která vám umožní prozkoumat její funkce před nákupem.
### Jak mohu získat podporu pro Aspose.Tasks pro Java?
 Navštivte[Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) získat pomoc a spojit se s komunitou.
### Potřebuji dočasnou licenci pro Aspose.Tasks for Java?
 Dočasnou licenci můžete získat od[tento odkaz](https://purchase.aspose.com/temporary-license/) pro účely testování a hodnocení.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
