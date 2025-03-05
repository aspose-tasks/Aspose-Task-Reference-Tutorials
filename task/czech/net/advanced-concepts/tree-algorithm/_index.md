---
title: Použití stromového algoritmu v Aspose.Tasks
linktitle: Použití stromového algoritmu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně manipulovat s hierarchiemi úkolů ve vašich projektech .NET pomocí stromového algoritmu Aspose.Tasks.
type: docs
weight: 13
url: /cs/net/advanced-concepts/tree-algorithm/
---
## Úvod

Aspose.Tasks for .NET poskytuje výkonné funkce pro práci s úkoly, zdroji a plány projektového řízení. Jednou z takových funkcí je stromový algoritmus, který uživatelům umožňuje efektivně manipulovat s hierarchiemi úkolů. V tomto tutoriálu prozkoumáme, jak využít stromový algoritmus v Aspose.Tasks pro .NET ke shromažďování společné práce a aktualizaci pracovních hodnot v rámci projektu.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Spolu s příklady je vyžadována znalost programovacího jazyka C#.

## Importovat jmenné prostory

Ve svém projektu C# importujte potřebné jmenné prostory pro práci s funkcemi Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Nyní si každý příklad rozdělíme do několika kroků:

## Krok 1: Načtěte soubor projektu

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Nahrajte soubor projektu do paměti pomocí`Project` třída.

## Krok 2: Definujte hierarchii úkolů

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definujte hierarchii úkolů přidáním nadřazených a podřízených úkolů.

## Krok 3: Nastavte vlastnosti úlohy

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Nastavte vlastnosti, jako je datum zahájení, trvání a datum ukončení úkolů.

## Krok 4: Přidejte zdroj

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Přidejte do projektu zdroje a podle potřeby je přiřaďte k úkolům.

## Krok 5: Použijte stromový algoritmus

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Inicializujte`WorkAccumulator` třídy a aplikujte stromový algoritmus ke shromažďování společné práce.

## Krok 6: Aktualizujte práci úkolu

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Aktualizujte pracovní hodnoty pro úkoly na základě shromážděných informací.

## Závěr

V tomto tutoriálu jsme se naučili, jak využít stromový algoritmus v Aspose.Tasks pro .NET k efektivní manipulaci s hierarchiemi úloh. Podle podrobného průvodce můžete efektivně spravovat úkoly a zdroje v rámci svých projektů.

## FAQ

### Q1: Co je Aspose.Tasks pro .NET?

A1: Aspose.Tasks for .NET je výkonné rozhraní API, které umožňuje vývojářům manipulovat se soubory aplikace Microsoft Project programově pomocí jazyka C#.

### Q2: Mohu si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro .NET?

 A2: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks for .NET z[tady](https://releases.aspose.com/).

### Q3: Kde najdu dokumentaci pro Aspose.Tasks pro .NET?

 A3: Můžete najít dokumentaci pro Aspose.Tasks pro .NET[tady](https://reference.aspose.com/tasks/net/).

### Q4: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

 A4: Pro podporu související s Aspose.Tasks pro .NET můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Je k dispozici dočasná licence pro testovací účely?

 A5: Ano, můžete získat dočasnou licenci pro testovací účely od[tady](https://purchase.aspose.com/temporary-license/).