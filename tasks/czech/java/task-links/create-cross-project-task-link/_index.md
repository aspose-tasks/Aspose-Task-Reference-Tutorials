---
title: Vytvořte propojení úloh mezi projekty v Aspose.Tasks
linktitle: Vytvořte propojení úloh mezi projekty v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Vylepšete spolupráci na projektech s Aspose.Tasks for Java. Naučte se krok za krokem vytvářet odkazy na úkoly napříč projekty. Zvyšte efektivitu nyní!
weight: 10
url: /cs/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte propojení úloh mezi projekty v Aspose.Tasks

## Úvod
dynamickém světě projektového řízení jsou efektivita a spolupráce prvořadé. Aspose.Tasks for Java poskytuje robustní řešení pro rozšíření možností řízení projektů. V tomto tutoriálu se ponoříme do procesu vytváření propojení úloh mezi projekty pomocí Aspose.Tasks for Java. Tento podrobný průvodce vás vybaví dovednostmi pro bezproblémové propojování úkolů napříč různými projekty, čímž podpoří lepší koordinaci a zefektivní pracovní postupy.
## Předpoklady
Než se pustíme do tohoto tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost programování v Javě.
-  Aspose.Tasks for Java nainstalován. Můžete si jej stáhnout z[Aspose.Tasks for Java release page](https://releases.aspose.com/tasks/java/).
- Základní pochopení projektového řízení a závislostí úkolů.
## Importujte balíčky
Chcete-li proces nastartovat, naimportujte potřebné balíčky do vašeho prostředí Java. To zajistí, že budete mít přístup k funkcím Aspose.Tasks for Java. Použijte následující fragment kódu:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Nyní rozeberme výše uvedený kód do srozumitelných kroků:
## Krok 1: Nastavte své prostředí
Než se ponoříte do kódu, ujistěte se, že máte nainstalovanou Javu a že je knihovna Aspose.Tasks for Java správně přidána do vašeho projektu.
## Krok 2: Vytvořte instanci projektu
Inicializujte nový projekt pomocí knihovny Aspose.Tasks:
```java
Project project = new Project();
```
## Krok 3: Přidejte souhrnný úkol
Vytvořte souhrnný úkol pro uspořádání a správu propojených úkolů:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## Krok 4: Přidejte externí úlohu
Chcete-li vytvořit odkaz na úkol z jiného projektu, přidejte k souhrnnému úkolu externí úkol:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## Krok 5: Přidejte místní úlohu
Přidejte místní úkol do souhrnného úkolu. Toto bude úkol spojený s externím úkolem:
```java
Task t = summary.getChildren().add("Task");
```
## Krok 6: Vytvořte odkaz na úkol
Vytvořte propojení úlohy mezi externí úlohou a místní úlohou:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Krok 7: Zobrazení výsledků
Nakonec zobrazte výsledek převodu:
```java
System.out.println("Process completed Successfully");
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vytvořit propojení úloh napříč projekty pomocí Aspose.Tasks for Java. Tato funkce zlepšuje spolupráci a koordinaci při řízení projektů a zajišťuje bezproblémovou integraci mezi úkoly v různých projektech.
## Nejčastější dotazy
### Mohu propojit úkoly z více externích projektů ve stejném souhrnném úkolu?
Ano, můžete propojit úkoly z různých externích projektů v rámci stejného souhrnného úkolu podle podobného procesu.
### Co se stane, když se změní externí úkol v propojeném projektu?
Jakékoli úpravy externího úkolu se projeví v propojeném úkolu ve vašem aktuálním projektu.
### Je možné vytvářet vazby mezi úkoly v různých formátech souborů?
Ano, Aspose.Tasks for Java podporuje propojení úkolů mezi projekty v různých formátech souborů.
### Mohu zrušit propojení úkolů, jakmile jsou propojeny napříč projekty?
Ano, můžete odpojit úkoly odstraněním odkazu na úkol pomocí příslušných metod Aspose.Tasks.
### Existují nějaká omezení ohledně počtu úkolů, které lze propojit napříč projekty?
Počet úloh, které lze propojit, závisí na možnostech a omezeních vaší licence Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
