---
title: Správa nadřazených a podřízených úkolů v Aspose.Tasks
linktitle: Správa nadřazených a podřízených úkolů v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Zvyšte efektivitu řízení projektů pomocí Aspose.Tasks for Java. Naučte se krok za krokem spravovat rodičovské a dětské úkoly. Začněte hned!
weight: 24
url: /cs/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa nadřazených a podřízených úkolů v Aspose.Tasks

## Úvod
V oblasti projektového řízení je efektivní organizace úkolů zásadní. Aspose.Tasks for Java poskytuje robustní řešení pro efektivní správu nadřazených a podřízených úloh. V tomto tutoriálu vás provedeme procesem používání Aspose.Tasks for Java ke zefektivnění vašich projektových úkolů.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
-  Nainstalovaná knihovna Aspose.Tasks pro Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/java/).
- Java Integrated Development Environment (IDE) nastavené na vašem systému.
## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java. Tyto balíčky usnadňují bezproblémovou integraci s funkcemi Aspose.Tasks for Java.
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
## Krok 1: Nastavte datum zahájení projektu
Začněte nastavením data zahájení projektu a dalších relevantních parametrů.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Zde lze přidat další kód pro import balíků
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Krok 2: Přidejte nadřazený úkol (úloha 1)
Vytvořte nadřazenou úlohu s názvem "Task 1" a nakonfigurujte její vlastnosti.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Krok 3: Přidejte nadřazený úkol (úkol 2) s podřízenými úkoly
Nyní přidejte další nadřazený úkol s názvem „Úkol 2“ a zahrňte podřízené úkoly (Úkol 3 a Úkol 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Přidejte podřízené úkoly do úkolu 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Zde lze přidat další konfiguraci pro Task 3 a Task 4
```
## Krok 4: Konfigurace podřízených úloh
Zadejte data zahájení, trvání a omezení pro Úkol 3 a Úkol 4.
```java
// Konfigurace úkolu 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Konfigurace úkolu 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Krok 5: Aktualizujte procento dokončení úlohy
Upravte procento dokončení pro úkol 3 a úkol 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Krok 6: Uložte projekt
Nakonec uložte projekt s aplikovanými změnami.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Tento podrobný průvodce ukazuje, jak efektivně spravovat rodičovské a podřízené úlohy pomocí Aspose.Tasks for Java. Experimentujte s různými konfiguracemi, aby vyhovovaly požadavkům vašeho projektu.
## Závěr
Závěrem lze říci, že Aspose.Tasks for Java umožňuje vývojářům efektivně zpracovávat projektové úkoly a zajišťuje bezproblémovou organizaci a sledování. Implementujte nastíněné kroky ke zlepšení schopností řízení projektů.
## Nejčastější dotazy
### Je Aspose.Tasks for Java kompatibilní s různými formáty souborů projektu?
Ano, Aspose.Tasks for Java podporuje různé formáty projektových souborů, včetně MPP a XML.
### Mohu přizpůsobit vlastnosti úlohy nad rámec toho, co je popsáno v tomto kurzu?
Absolutně! Aspose.Tasks for Java poskytuje rozsáhlé možnosti přizpůsobení vlastností úloh.
### Existuje komunitní fórum pro Aspose.Tasks, kde mohu hledat podporu?
 Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity.
### Jak mohu získat dočasnou licenci pro Aspose.Tasks for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu komplexní dokumentaci k Aspose.Tasks for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
