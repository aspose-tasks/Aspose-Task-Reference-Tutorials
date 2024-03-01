---
title: Práce s přiřazením v Aspose.Tasks
linktitle: Práce s přiřazením v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak spravovat přiřazení projektů v .NET pomocí Aspose.Tasks. Prozkoumejte různé obrysy pro plánování zdrojů.
type: docs
weight: 13
url: /cs/net/advanced-features/working-with-assignment/
---
## Úvod

V tomto tutoriálu prozkoumáme, jak pracovat s úkoly v Aspose.Tasks pro .NET. Úkoly jsou klíčové v projektovém řízení, protože přidělují zdroje úkolům, pomáhají při plánování a sledování pokroku. Zaměříme se na generování časově uspořádaných dat přiřazení zdrojů s různými obrysy pomocí Aspose.Tasks.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

1.  Instalace Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[odkaz ke stažení](https://releases.aspose.com/tasks/net/).
2. Základní porozumění C# a .NET Framework: Je nezbytné, abyste se seznámili s programovacím jazykem C# a koncepty .NET frameworku.

## Importovat jmenné prostory

Ujistěte se, že jste do svého projektu C# importovali potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Krok 1: Vytvořte projekt a úkol

Začněme vytvořením nového projektu a přidáním úkolu. Nastavte datum zahájení, trvání a datum dokončení úkolu:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Krok 2: Přidejte zdroj a přiřaďte k úloze

Dále přidejte do projektu zdroj a přiřaďte jej k dříve vytvořenému úkolu:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Krok 3: Generujte časově uspořádaná data s různými obrysy

Nyní vygenerujme časově uspořádaná data s různými obrysy pro přiřazení zdrojů:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Krok 4: Změňte obrysy a generujte data

Můžeme změnit typ obrysu a podle toho generovat časově uspořádaná data. Zde jsou nějaké příklady:

```csharp
// Změňte obrys
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Generujte časově uspořádaná data a tiskněte
// Opakujte tento krok pro další typy obrysů
```

## Závěr

tomto tutoriálu jsme se naučili pracovat s úkoly v Aspose.Tasks pro .NET. Zkoumali jsme generování časově uspořádaných dat přiřazení zdrojů s různými konturami. Tyto znalosti mohou být nesmírně užitečné ve scénářích projektového řízení.

## FAQ

### Q1: Mohu použít Aspose.Tasks pro plánování úloh v mé aplikaci .NET?

Odpověď 1: Ano, Aspose.Tasks poskytuje komplexní rozhraní API pro plánování a správu úloh v aplikacích .NET.

### Q2: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?

 A2: Ano, můžete využít bezplatnou zkušební verzi[tady](https://releases.aspose.com/).

### Q3: Existují nějaká omezení počtu úkolů nebo zdrojů v Aspose.Tasks?

A3: Aspose.Tasks neklade žádná omezení na počet úkolů nebo zdrojů, které můžete ve svých projektech spravovat.

### Q4: Mohu upravit obrysy pro přiřazení zdrojů v Aspose.Tasks?

A4: Ano, jak je ukázáno v tomto tutoriálu, můžete nastavit různé obrysy, jako je želva, zvonek, vrchol atd., podle požadavků vašeho projektu.

### Q5: Kde najdu podporu pro dotazy související s Aspose.Tasks?

A5: Podporu najdete na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) kde se odborníci a členové komunity aktivně zapojují do diskusí.