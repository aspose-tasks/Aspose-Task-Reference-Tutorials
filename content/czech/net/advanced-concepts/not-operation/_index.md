---
title: Práce s operací NOT v Aspose.Tasks
linktitle: Práce s operací NOT v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se používat operaci NOT v Aspose.Tasks pro .NET k efektivnímu filtrování úkolů. Vylepšete své schopnosti projektového řízení již nyní.
type: docs
weight: 20
url: /cs/net/advanced-concepts/not-operation/
---
## Úvod

tomto tutoriálu prozkoumáme, jak využít operaci NOT v Aspose.Tasks pro .NET. Operace NOT nám umožňuje obrátit podmínku filtru, což nám umožňuje vybrat prvky, které nesplňují zadaná kritéria.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Visual Studio: Potřebujete funkční instalaci sady Visual Studio, abyste mohli postupovat spolu s příklady kódu.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[webová stránka](https://releases.aspose.com/tasks/net/).
3. Základní porozumění C#: Pro pochopení příkladů kódu vám pomůže znalost programovacího jazyka C#.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory pro náš kód:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Nastavte projekt a úkoly

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Začneme načtením souboru projektu s názvem "Project2.mpp" pomocí`Project` třídy poskytuje Aspose.Tasks. Ujistěte se, že soubor projektu existuje v zadaném adresáři.

## Krok 2: Sbírejte úkoly projektu

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Zde vytvoříme a`ChildTasksCollector` objekt shromáždit všechny úkoly v rámci projektu. Poté používáme`TaskUtils.Apply`procházet hierarchií úkolů projektu a shromažďovat všechny podřízené úkoly.

## Krok 3: Definujte podmínku filtru

```csharp
var filter = new NullCondition();
```

 Definujeme podmínku filtru pomocí vlastní třídy s názvem`NullCondition`, Tato podmínka vybere úlohy, které mají hodnotu null.

## Krok 4: Použijte operaci NOT

```csharp
var condition = new Not<Task>(filter);
```

 Operaci NOT aplikujeme na podmínku filtru pomocí`Not<T>` třídy poskytuje Aspose.Tasks. Tím se obrátí podmínka filtru a vyberou se úlohy, které nemají hodnotu null.

## Krok 5: Filtrování úkolů

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Shromážděné úkoly filtrujeme na základě použité podmínky pomocí vlastního`Filter` metoda. Tato metoda bere jako vstupní parametry vyčíslitelný soubor úkolů a podmínku filtru a vrací seznam úkolů, které splňují podmínku.

## Krok 6: Zpracujte filtrované úkoly

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Práce s jinými nemovitostmi...
}
```

Nakonec projdeme filtrované úkoly a provedeme libovolné požadované operace. V tomto příkladu jednoduše vytiskneme názvy úloh do konzole.

## Závěr

tomto tutoriálu jsme se naučili pracovat s operací NOT v Aspose.Tasks pro .NET. Obrácením podmínek filtru můžeme selektivně vybrat prvky, které nesplňují zadaná kritéria, což zvyšuje naši flexibilitu při manipulaci s úkoly v rámci projektů.

## FAQ

### Q1: Mohu používat Aspose.Tasks s jinými frameworky .NET?

Odpověď: Ano, Aspose.Tasks podporuje různé .NET frameworky včetně .NET Core, .NET Standard a .NET Framework.

### Q2: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?

 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[webová stránka](https://releases.aspose.com/).

### Q3: Jak mohu získat podporu pro Aspose.Tasks?

 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakékoli dotazy na podporu nebo technickou pomoc.

### Q4: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks?

 Odpověď: Ano, můžete si zakoupit dočasnou licenci z[nákupní stránku](https://purchase.aspose.com/temporary-license/).

### Q5: Kde najdu komplexní dokumentaci pro Aspose.Tasks?

 Odpověď: Kompletní dokumentaci najdete na[Stránka dokumentace Aspose.Tasks](https://reference.aspose.com/tasks/net/).