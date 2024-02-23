---
title: Manipulace s rozdělenými díly MS Project v Aspose.Tasks
linktitle: Manipulace s rozdělenými díly v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně zacházet s rozdělenými částmi MS Project pomocí Aspose.Tasks pro .NET. Vylepšete svůj pracovní postup projektového řízení.
type: docs
weight: 18
url: /cs/net/rate-recurring-tasks/split-parts/
---

## Úvod
Správa rozdělených částí MS Project může být zásadním aspektem projektového řízení při použití Aspose.Tasks pro .NET. V tomto tutoriálu prozkoumáme, jak efektivně zacházet s rozdělenými částmi pomocí pokynů krok za krokem.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1.  Instalace Aspose.Tasks for .NET: Stáhněte a nainstalujte Aspose.Tasks for .NET z[webová stránka](https://releases.aspose.com/tasks/net/).
   
2. Základní porozumění C#: Výhodou bude znalost programovacího jazyka C#.

## Importovat jmenné prostory
kódu C# nezapomeňte importovat potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Krok 1: Vytvoření instance projektu
```csharp
var project = new Project();
```
 Vytvořte novou instanci souboru`Project` třída.
## Krok 2: Nastavení data zahájení a ukončení projektu
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Nastavte datum zahájení a ukončení projektu.
## Krok 3: Přidání úkolu
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Přidejte do projektu nový úkol.
## Krok 4: Nastavení vlastností úlohy
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Nastavte vlastnosti, jako je ruční stav, datum zahájení a trvání úlohy.
## Krok 5: Přidání přiřazení zdrojů
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Přidejte k úkolu přiřazení zdrojů.
## Krok 6: Nastavení vlastností přiřazení
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Nastavte vlastnosti, jako je datum zahájení, práce a datum dokončení úkolu.
## Krok 7: Generování časově uspořádaných dat
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Vygenerujte časově uspořádaná data pro úkol na základě kalendáře projektu.
## Krok 8: Rozdělení úkolu
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Rozdělte úkol na více částí v určeném časovém rámci.
## Krok 9: Iterace přes rozdělené části
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Iterujte přes rozdělené části úkolu a vytiskněte jejich data zahájení a ukončení.

## Závěr
Efektivní manipulace s rozdělenými částmi MS Project v Aspose.Tasks pro .NET je zásadní pro efektivitu řízení projektu. Podle kroků uvedených v tomto kurzu můžete bez problémů spravovat rozdělené úkoly a vylepšit pracovní postup řízení projektů.
## FAQ
### Otázka: Mohu používat Aspose.Tasks pro .NET s jinými frameworky .NET?
Odpověď: Ano, Aspose.Tasks for .NET je kompatibilní s různými frameworky .NET včetně .NET Core a .NET Standard.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/).
### Otázka: Podporuje Aspose.Tasks pro .NET správu prostředků?
Odpověď: Ano, Aspose.Tasks for .NET vám umožňuje efektivně spravovat zdroje projektu.
### Otázka: Mohu upravit projektové kalendáře pomocí Aspose.Tasks pro .NET?
A: Rozhodně si můžete přizpůsobit projektové kalendáře podle vašich požadavků projektu.
### Otázka: Kde najdu podporu pro Aspose.Tasks pro .NET?
 Odpověď: Podporu a pomoc najdete na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).