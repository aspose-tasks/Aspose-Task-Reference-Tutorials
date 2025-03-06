---
title: Správa kolekcí úkolů v Aspose.Tasks
linktitle: Správa kolekcí úkolů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte efektivní správu kolekce úkolů v Aspose.Tasks pro .NET. Od vytvoření po úpravy, ovládněte snadno správu projektů.
weight: 18
url: /cs/net/task-table-management/task-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa kolekcí úkolů v Aspose.Tasks

## Úvod
Pokud se ponoříte do světa projektového řízení pomocí .NET, Aspose.Tasks je vaším řešením pro bezproblémové zpracování kolekcí úkolů. Tento výukový program vás provede procesem efektivní správy kolekcí úloh a zajistí, že tuto výkonnou knihovnu využijete na maximum.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka C#.
- Visual Studio nainstalované na vašem počítači.
- Knihovna Aspose.Tasks pro .NET stažená a odkazovaná ve vašem projektu.
## Importovat jmenné prostory
Pro začátek importujme potřebné jmenné prostory do vašeho projektu C#:
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Tyto jmenné prostory poskytují přístup k základním třídám a metodám potřebným pro efektivní správu úloh.
Nyní si tutoriál rozdělíme na řadu kroků, abychom zajistili srozumitelnost a jednoduchost.
## Krok 1: Vytvoření instance projektu
```csharp
var project = new Project();
```
 Vytvořte nový projekt pomocí`Project` třída.
## Krok 2: Kontrola připravenosti shromažďování úkolů
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
Ověřte, zda je kolekce úloh pouze pro čtení.
## Krok 3: Vytváření úkolů
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// Nastavte další vlastnosti úkolu, jako je začátek, trvání a konec
// Podobné kroky pro Úkol 2 a Úkol 3
```
Vytvořte úkoly v rámci projektu a nastavte jejich vlastnosti.
## Krok 4: Tisk úloh projektu
```csharp
foreach (var child in project.RootTask.Children)
{
    // Tisk podrobností o úkolu
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
Vytiskněte podrobnosti o každém úkolu v rámci projektu.
## Krok 5: Úprava úkolů
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
Upravte úkoly pomocí jejich ID nebo UID.
## Krok 6: Přidání opakujícího se úkolu
```csharp
var parameters = new RecurringTaskParameters
{
    // Nastavte parametry opakujících se úloh
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
Přidejte do projektu opakovaný úkol.
## Krok 7: Převod kolekce na seznam
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
Převeďte kolekci úloh na seznam a provádějte operace s každou úlohou.
## Závěr
Správa kolekcí úkolů v Aspose.Tasks pro .NET je s tímto podrobným průvodcem hračka. Ať už vytváříte, upravujete nebo odstraňujete úkoly, Aspose.Tasks vám umožní bezproblémově zvládnout správu projektů.
## Často kladené otázky
### Je Aspose.Tasks kompatibilní s .NET Core?
Ano, Aspose.Tasks podporuje .NET Core, což vám umožňuje používat jej v multiplatformních aplikacích.
### Mohu exportovat projektové úkoly do různých formátů souborů?
Absolutně! Aspose.Tasks poskytuje všestranné možnosti exportu, včetně PDF, XLSX a MPP.
### Jak mohu zvládnout závislosti mezi úkoly?
 Závislosti úloh můžete nastavit pomocí`TaskLink` třídy poskytuje Aspose.Tasks.
### Existuje komunitní fórum pro podporu Aspose.Tasks?
 Ano, můžete najít podporu a zapojit se do komunity na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Mohu získat dočasnou licenci pro Aspose.Tasks?
 Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
