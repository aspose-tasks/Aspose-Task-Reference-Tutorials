---
title: Práce s obdobími dostupnosti v Aspose.Tasks
linktitle: Práce s obdobími dostupnosti v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat období dostupnosti zdrojů pomocí Aspose.Tasks for .NET. Tento kurz poskytuje podrobného průvodce pro práci s obdobími dostupnosti ve vašich projektech .NET.
type: docs
weight: 17
url: /cs/net/advanced-features/working-with-availability-periods/
---
## Úvod

tomto tutoriálu prozkoumáme, jak pracovat s obdobími dostupnosti v Aspose.Tasks pro .NET. Období dostupnosti jsou zásadní pro efektivní řízení zdrojů ve scénářích projektového řízení. Provedeme vás procesem krok za krokem.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

1. Visual Studio: Nainstalujte Visual Studio nebo jakékoli jiné preferované IDE pro vývoj .NET.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost programování v C#: Užitečná bude znalost základů programovacího jazyka C#.

## Importovat jmenné prostory

Než se ponoříte do kódu, nezapomeňte importovat potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Rozdělme ukázkový kód do několika kroků:

## Krok 1: Vytvořte novou instanci projektu

```csharp
var project = new Project();
```

Tento řádek inicializuje novou instanci třídy Project, která představuje projekt v Aspose.Tasks.

## Krok 2: Přidejte zdroj

```csharp
var resource = project.Resources.Add("Work Resource");
```

Zde přidáme do projektu nový zdroj s názvem „Work Resource“.

## Krok 3: Definujte období dostupnosti

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Zavoláme na`GetPeriods()` metoda pro načtení kolekce období dostupnosti.

## Krok 4: Přidejte do zdroje období dostupnosti

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Procházíme sbírkou období dostupnosti získaných v předchozím kroku a přidáváme je do zdroje.

## Krok 5: Zobrazte podrobnosti o období dostupnosti

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Nakonec projdeme období dostupnosti související se zdrojem a vytiskneme jejich podrobnosti, včetně data zahájení, data ukončení a dostupných jednotek.

## Závěr

V tomto tutoriálu jsme se naučili pracovat s obdobími dostupnosti v Aspose.Tasks pro .NET. Dodržováním tohoto podrobného průvodce můžete efektivně spravovat dostupnost zdrojů v aplikacích pro řízení projektů.

## FAQ

### Q1: Mohu použít Aspose.Tasks pro .NET v komerčních projektech?

 A1: Ano, Aspose.Tasks for .NET lze použít v komerčních projektech. Můžete si zakoupit licenci[tady](https://purchase.aspose.com/buy).

### Q2: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?

 A2: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET[tady](https://releases.aspose.com/).

### Q3: Kde najdu dokumentaci pro Aspose.Tasks pro .NET?

 A3: Můžete najít dokumentaci[tady](https://reference.aspose.com/tasks/net/).

### Q4: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

 Odpověď 4: Podporu můžete získat na fóru komunity.[tady](https://forum.aspose.com/c/tasks/15).

### Q5: Nabízíte dočasné licence pro Aspose.Tasks pro .NET?

 A5: Ano, dočasné licence jsou k dispozici[tady](https://purchase.aspose.com/temporary-license/).