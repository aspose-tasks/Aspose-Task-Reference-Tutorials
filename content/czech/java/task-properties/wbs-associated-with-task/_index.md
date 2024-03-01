---
title: WBS spojené s úlohou v Aspose.Tasks
linktitle: WBS spojené s úlohou v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Zvládněte WBS pomocí Aspose.Tasks for Java - Naučte se číst a přečíslovat kódy úkolu WBS. Zvyšte efektivitu řízení projektů!
type: docs
weight: 36
url: /cs/java/task-properties/wbs-associated-with-task/
---
## Úvod
Vítejte ve světě projektového řízení s Aspose.Tasks for Java! V tomto tutoriálu se ponoříme do složitosti Work Breakdown Structure (WBS) spojené s úkoly pomocí Aspose.Tasks for Java. Ať už jste zkušený vývojář nebo teprve začínáte, tato příručka vám pomůže procházet základy efektivní správy kódů WBS.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
-  Knihovna Aspose.Tasks pro Java byla stažena a přidána do vašeho projektu. Můžete to získat od[tady](https://releases.aspose.com/tasks/java/).
## Importujte balíčky
Ujistěte se, že importujete potřebné balíčky pro nastartování vašeho projektu:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Přečtěte si kódy WBS
Začněme čtením kódů WBS spojených s úkoly. Následuj tyto kroky:
## Krok 1: Načtěte projekt
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Krok 2: Sbírejte úkoly
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Krok 3: Analýza a přizpůsobení
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Tento fragment čte a přizpůsobuje kódy WBS spojené s úkoly ve vašem projektu.
## Přečíslovat kódy WBS úkolu
Nyní se podívejme na přečíslování WBS kódů pro úkoly:
## Krok 1: Načtěte projekt
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Krok 2: Vyberte Všechny úkoly
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Krok 3: Výstup počátečních kódů WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Krok 4: Přečíslujte kódy WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Krok 5: Výstup aktualizovaných kódů WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Pomocí těchto kroků účinně přečíslujete kódy WBS pro úkoly ve vašem projektu.
## Závěr
Gratulujeme! Úspěšně jste se naučili pracovat s kódy WBS pomocí Aspose.Tasks for Java. Tyto znalosti vám umožní efektivně spravovat a přizpůsobovat hierarchii úkolů vašeho projektu.
## Nejčastější dotazy
### Otázka: Kde najdu dokumentaci k Aspose.Tasks for Java?
 Odpověď: Dokumentace je k dispozici[tady](https://reference.aspose.com/tasks/java/).
### Otázka: Jak si mohu stáhnout Aspose.Tasks for Java?
 A: Můžete si to stáhnout[tady](https://releases.aspose.com/tasks/java/).
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro Java?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Kde mohu získat podporu pro Aspose.Tasks for Java?
 A: Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro podporu.
### Otázka: Mohu získat dočasnou licenci pro Aspose.Tasks for Java?
 Odpověď: Ano, získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).