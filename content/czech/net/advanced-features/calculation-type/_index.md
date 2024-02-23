---
title: Typ výpočtu v Aspose.Tasks
linktitle: Typ výpočtu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak přizpůsobit výpočty hodnot v projektech .NET pomocí Typu výpočtu v knihovně Aspose.Tasks.
type: docs
weight: 30
url: /cs/net/advanced-features/calculation-type/
---
## Úvod

V tomto tutoriálu prozkoumáme funkci Typ výpočtu v Aspose.Tasks pro .NET. Aspose.Tasks je výkonná knihovna, která umožňuje vývojářům .NET pracovat se soubory aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project na jejich systémy. Typ výpočtu nám umožňuje definovat, jak se počítají hodnoty pro úkoly a souhrnné úkoly v rámci projektu.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

1. Základní znalost C# a .NET frameworku.
2. Visual Studio nainstalované ve vašem systému.
3.  Nainstalovaná knihovna Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
4.  Přístup k dokumentaci Aspose.Tasks pro .NET pro referenci, k dispozici[tady](https://reference.aspose.com/tasks/net/).

## Importovat jmenné prostory

Než se ponoříte do příkladu, nezapomeňte importovat potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;


```

## Krok 1: Vytvořte nový projekt

Nejprve vytvořte nový objekt projektu:

```csharp
var project = new Project();
```

## Krok 2: Přidejte úkol

Nyní přidáme úkol do našeho projektu:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Krok 3: Definujte typ výpočtu pro rozšířený atribut

Vytvoříme definici rozšířeného atributu s typem výpočtu nastaveným na Vzorec:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Krok 4: Definujte typ výpočtu pro řádky souhrnu

Dále vytvoříme další definici rozšířeného atributu, kde se hodnoty pro souhrnné úkoly počítají pomocí typu souhrnu Průměr:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak pracovat s typem výpočtu v Aspose.Tasks pro .NET. Definováním typů výpočtů pro rozšířené atributy můžeme přizpůsobit způsob výpočtu hodnot pro úkoly a souhrnné úkoly v rámci projektu, což poskytuje větší flexibilitu a kontrolu.

## FAQ

### Q1: Co je typ výpočtu v Aspose.Tasks?

A1: Typ výpočtu v Aspose.Tasks určuje, jak se počítají hodnoty pro úkoly a souhrnné úkoly v rámci projektu, a nabízí možnosti, jako je vzorec a souhrn.

### Q2: Jak nastavím typ výpočtu pro rozšířený atribut?

A2: Typ výpočtu pro rozšířený atribut můžete nastavit odpovídajícím definováním jeho vlastnosti CalculationType.

### Q3: Mohu přizpůsobit typ výpočtu pro souhrnné řádky v projektu?

Odpověď 3: Ano, Aspose.Tasks vám umožňuje určit typ výpočtu pro souhrnné řádky, což vám umožní přizpůsobit výpočty hodnot na základě vašich požadavků.

### Q4: Jsou pro výpočty souhrnných úkolů k dispozici různé typy kumulativních úloh?

Odpověď 4: Ano, Aspose.Tasks poskytuje různé typy souhrnů, jako je průměr, součet a počet pro výpočet hodnot souhrnných úkolů.

### Q5: Kde najdu další zdroje na Aspose.Tasks pro .NET?

 A5: Můžete prozkoumat dokumentaci a fóra podpory komunity dostupná na webu[Aspose.Tasks pro .NET](https://reference.aspose.com/tasks/net/) za komplexní vedení a pomoc.