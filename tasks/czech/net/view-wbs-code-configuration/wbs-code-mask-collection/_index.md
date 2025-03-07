---
title: Zvládnutí kódových masek WBS pomocí Aspose.Tasks pro .NET
linktitle: Kolekce kódových masek WBS v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Vylepšete řízení projektů pomocí Aspose.Tasks pro .NET. Naučte se snadno vytvářet, spravovat a přenášet masky kódu WBS v tomto komplexním kurzu.
weight: 15
url: /cs/net/view-wbs-code-configuration/wbs-code-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí kódových masek WBS pomocí Aspose.Tasks pro .NET

## Úvod
V dynamickém světě projektového řízení je efektivní organizace úkolů zásadní. Aspose.Tasks for .NET poskytuje výkonné řešení pro snadnou správu kódů struktury členění projektové práce (WBS). V tomto tutoriálu se ponoříme do kolekce WBS kódových masek a prozkoumáme, jak je implementovat a manipulovat s nimi pomocí Aspose.Tasks for .NET.
## Předpoklady
Než se pustíme do této kódovací cesty, ujistěte se, že máte splněny následující předpoklady:
- Pracovní znalost programovacího jazyka C#.
-  Aspose.Tasks for .NET nainstalované ve vašem vývojovém prostředí. Pokud ne, stáhněte si ji[tady](https://releases.aspose.com/tasks/net/).
- Editor kódu jako Visual Studio pro bezproblémové kódování.
## Importovat jmenné prostory
Chcete-li začít, importujme potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Inicializujte projekt a definici kódu WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Definujte masky kódu WBS
Vymažte všechny existující masky kódu a přidejte nové:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Zobrazte informace o maskách kódu
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Přidejte úkoly do projektu
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Získejte informace o úkolu
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipulujte s maskami kódu
Odstraňte masku kódu a ujistěte se, že je odstraněna:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Zkopírujte masky kódu do jiného projektu
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Zobrazte masky kódu v jiném projektu
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Přidejte úkoly do jiného projektu
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Zobrazte kódy WBS v jiném projektu
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Závěr
S Aspose.Tasks for .NET se správa kódů WBS stává snadným úkolem. Tento výukový program se zabýval tvorbou, manipulací a přenosem kódových masek WBS a poskytl vám komplexního průvodce, který vám pomůže zlepšit vaše zkušenosti s řízením projektů.
## Nejčastější dotazy
### Otázka: Mohu používat Aspose.Tasks pro .NET s jinými programovacími jazyky?
Odpověď: Aspose.Tasks primárně podporuje jazyky .NET, ale můžete prozkoumat možnosti interoperability s jinými jazyky.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, můžete si stáhnout zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Jak mohu vyhledat pomoc nebo nahlásit problémy s Aspose.Tasks for .NET?
 A: Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu a diskuze.
### Otázka: Jaký je účel kódů WBS v řízení projektů?
Odpověď: Kódy WBS pomáhají hierarchicky organizovat a strukturovat projektové úkoly a poskytují systematický přístup k plánování projektu.
### Otázka: Mohu upravit formát kódů WBS v Aspose.Tasks pro .NET?
Odpověď: Rozhodně máte plnou kontrolu nad formátem a strukturou kódů WBS pomocí Aspose.Tasks for .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
