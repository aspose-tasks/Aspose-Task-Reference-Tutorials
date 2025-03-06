---
title: Správa úkolů v Aspose.Tasks
linktitle: Správa úkolů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte komplexního průvodce pro správu úloh pomocí Aspose.Tasks for .NET. Naučte se přidávat, zobrazovat rozdělené části, přesouvat, získávat/nastavovat vlastnosti a další.
weight: 15
url: /cs/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa úkolů v Aspose.Tasks

## Úvod
Pokud jste vývojář .NET a chcete efektivně spravovat úkoly ve svých projektech, Aspose.Tasks for .NET poskytuje robustní řešení. Tento tutoriál vás provede různými aspekty správy úloh pomocí Aspose.Tasks a nabídne vám podrobné pokyny a příklady kódu. Ať už přidáváte úkoly, zobrazujete rozdělené části, přesouváte úkoly pod stejného rodiče, získáváte/nastavujete vlastnosti úkolu, iterujete přes přiřazení úkolů, čtete osnovy úkolů nebo odstraňujete úkoly, tato příručka vám pomůže.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1. Aspose.Tasks for .NET Library: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Tasks for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
2. Adresář dokumentů: Nastavte adresář, kde budou uloženy vaše projektové dokumenty.
## Importovat jmenné prostory
Ve svém projektu .NET zahrňte potřebné jmenné prostory pro práci s Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Přidání úkolu do projektu
```csharp
// Vytvořte nový projekt
var project = new Project();
// Přidejte úkol
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Uložte projekt
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Zobrazení rozdělených částí úlohy
```csharp
// Načtěte projekt s rozdělenými úkoly
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Přístup k úkolu
var task = project.RootTask.Children.GetById(4);
// Zobrazit rozdělené části
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Přesunutí úkolu pod stejného rodiče
```csharp
try
{
    // Načíst projekt
    var project = new Project(DataDir + "MoveTask.mpp");
    // Přesuň úkoly s ID 5 před úkol s ID 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Uložte upravený projekt
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Získání/nastavení vlastností úlohy
```csharp
// Vytvořte nový projekt
var project = new Project();
// Přidejte úkol a nastavte vlastnosti
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Shromáždit a zobrazit vlastnosti úlohy
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Iterace přes přiřazení úkolu
```csharp
// Načtěte projekt s úkoly
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Sbírejte a zobrazujte přiřazení úkolů
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Čtení základních linií úkolu
```csharp
// Vytvořte nový projekt
var project = new Project();
// Přidejte úkol a nastavte základní linii
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Zobrazit dobu základního plánu úkolu
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Odstranění úkolu
```csharp
// Vytvořte nový projekt
var project = new Project();
// Přidejte úkol
var task = project.RootTask.Children.Add("Task");
//Zobrazení počtu úkolů před a po smazání
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Smazat úkol
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Závěr
Správa úloh v Aspose.Tasks for .NET je bezproblémový proces s poskytnutými příklady. Ať už jste zkušený vývojář nebo teprve začínáte, začlenění těchto technik zlepší vaše schopnosti projektového řízení.
## Často kladené otázky
### Otázka: Je Aspose.Tasks kompatibilní se všemi .NET frameworky?
Odpověď: Ano, Aspose.Tasks podporuje různé .NET frameworky, což zajišťuje kompatibilitu s vaším vývojovým prostředím.
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Tasks?
 Odpověď: Můžete získat 30denní dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Existují nějaká omezení při práci s rozdělenými úkoly v Aspose.Tasks?
 Odpověď: Rozdělení úloh je výkonná funkce a lze k ní nalézt podrobnou dokumentaci[tady](https://reference.aspose.com/tasks/net/).
### Otázka: Mohu upravit vlastnosti úlohy nad rámec toho, co je uvedeno v příkladech?
A: Rozhodně! Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení vlastností úloh. Další podrobnosti naleznete v dokumentaci.
### Otázka: Jak získám podporu pro Aspose.Tasks?
 A: Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity a diskuze.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
