---
title: Zvládněte vlastnosti zpoždění vyrovnání v Aspose.Tasks
linktitle: Zvládněte vlastnosti zpoždění vyrovnání pro přiřazení prostředků v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak zacházet s vlastnostmi zpoždění vyrovnání pro přiřazení zdrojů v Aspose.Tasks for Java, pomocí tohoto komplexního kurzu.
type: docs
weight: 17
url: /cs/java/resource-assignments/leveling-delay-properties/
---
## Úvod
V tomto tutoriálu projdeme procesem zpracování vlastností zpoždění vyrovnání pro přiřazení zdrojů v Aspose.Tasks for Java. Aspose.Tasks je výkonná Java knihovna, která vám umožňuje pracovat se soubory aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project do vašeho systému.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Java JDK. Můžete si jej stáhnout a nainstalovat z[webová stránka](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Stáhněte si knihovnu Aspose.Tasks for Java z[stránka ke stažení](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Nejprve importujte potřebné balíčky do svého projektu Java, abyste mohli používat funkce Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Krok 1: Vytvořte objekt projektu
 Instantovat a`Project` objekt:
```java
Project prj = new Project();
```
## Krok 2: Vytvořte úkol
Přidejte úkol do projektu:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Krok 3: Nastavte datum zahájení úlohy a dobu trvání
Nastavte datum zahájení a dobu trvání úkolu:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Krok 4: Přidejte zdroj
Přidejte do projektu zdroj:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Krok 5: Vytvořte přiřazení zdrojů
Vytvořte přiřazení zdroje pro úkol a zdroj:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Krok 6: Nastavte zpoždění vyrovnání
Nastavte zpoždění vyrovnání pro úkol:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Krok 7: Zobrazení výsledků
Vytiskněte zpoždění vyrovnání a další relevantní informace:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak zacházet s vlastnostmi zpoždění vyrovnání pro přiřazení zdrojů v Aspose.Tasks for Java. Pomocí těchto kroků můžete efektivně spravovat přiřazení prostředků ve svých projektech Java.
## FAQ
### Otázka: Mohu používat Aspose.Tasks s jinými knihovnami Java?

Odpověď: Ano, Aspose.Tasks lze integrovat s jinými knihovnami Java, aby se zlepšily možnosti řízení projektů.

### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?

Odpověď: Ano, Aspose.Tasks podporuje různé verze souborů Microsoft Project a zajišťuje kompatibilitu v různých prostředích.

### Otázka: Kde najdu další podporu pro Aspose.Tasks?

 Odpověď: Podporu a zdroje najdete na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Otázka: Mohu vyzkoušet Aspose.Tasks před nákupem?

 Odpověď: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks z[stránka vydání](https://releases.aspose.com/).

### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Tasks?

 Odpověď: Můžete požádat o dočasnou licenci z[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/) pro účely hodnocení.