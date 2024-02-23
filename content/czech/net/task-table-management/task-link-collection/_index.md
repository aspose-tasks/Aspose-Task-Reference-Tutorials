---
title: Manipulace s odkazy na úkoly v Aspose.Tasks
linktitle: Manipulace s odkazy na úkoly v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte sílu Aspose.Tasks pro .NET při efektivní správě odkazů projektových úkolů. Postupujte podle našeho podrobného průvodce, abyste zlepšili své zkušenosti s řízením projektů.
type: docs
weight: 19
url: /cs/net/task-table-management/task-link-collection/
---
## Úvod
Vítejte v podrobném průvodci zpracováním odkazů na úkoly v Aspose.Tasks pro .NET! Odkazy na úkoly hrají klíčovou roli v řízení projektů, umožňují vytvářet vztahy mezi úkoly a vytvářet závislosti. V tomto tutoriálu vás provedeme procesem práce s kolekcemi odkazů úkolů pomocí Aspose.Tasks.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.Tasks for .NET Library: Stáhněte a nainstalujte knihovnu Aspose.Tasks. Knihovnu najdete[tady](https://releases.aspose.com/tasks/net/).
2. Vzorový projektový soubor: Připravte si vzorový projektový soubor (např. "SampleProject.mpp"), který bude následovat spolu s příklady.
Tak pojďme začít!
## Importovat jmenné prostory
Ve svém projektu .NET se ujistěte, že jste importovali potřebné jmenné prostory pro práci s Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Načtěte úlohy projektu a přístupu
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
// Načtěte projekt
var project = new Project(DataDir + "SampleProject.mpp");
// Přístup k úkolům podle ID
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Krok 2: Vytvořte odkazy na úkoly
Propojte úkoly dohromady a vytvořte závislosti:
```csharp
// Propojte úlohy pomocí závislosti FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Krok 3: Tisk odkazů na úkoly
Vytiskněte odkazy na úkoly pro projekt:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
// Iterujte odkazy na úkoly
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Krok 4: Upravte odkaz na úkol
Upravit odkaz na úkol pomocí indexového přístupu:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Krok 5: Odeberte odkazy na úkoly
Odstraňte z projektu všechny odkazy na úkoly:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak zacházet s odkazy na úkoly v Aspose.Tasks pro .NET. Tento obsáhlý průvodce pokryl načítání projektu, vytváření odkazů na úkoly, tisk odkazů, úpravy odkazů a odstraňování odkazů na úkoly.
Neváhejte a prozkoumejte další funkce a funkce nabízené Aspose.Tasks, abyste zlepšili své zkušenosti s řízením projektů.
## Nejčastější dotazy
### Je Aspose.Tasks kompatibilní se všemi verzemi .NET?
Ano, Aspose.Tasks je navržen tak, aby bezproblémově fungoval se všemi verzemi .NET.
### Mohu vytvořit vlastní typy odkazů na úkoly pomocí Aspose.Tasks?
současné době Aspose.Tasks podporuje standardní typy propojení úloh a vlastní typy propojení nejsou k dispozici.
### Jak mohu použít omezení na úkoly v Aspose.Tasks?
 Omezení můžete použít pomocí`ConstraintType` vlastnictvím`Task` třídy v Aspose.Úkoly.
### Existují nějaká omezení velikosti souborů projektu, které Aspose.Tasks zvládne?
Aspose.Tasks dokáže efektivně zpracovávat velké projektové soubory s minimálním dopadem na výkon.
### Existuje komunitní fórum pro podporu Aspose.Tasks?
 Ano, můžete najít podporu a zapojit se do komunity na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).