---
title: Kolekce období dostupnosti v Aspose.Tasks
linktitle: Kolekce období dostupnosti v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Zjistěte, jak spravovat období dostupnosti prostředků v Aspose.Tasks for .NET. Tento podrobný návod vás provede přidáváním, aktualizací a odebíráním období dostupnosti a zajišťuje efektivní plánování zdrojů projektu.
type: docs
weight: 18
url: /cs/net/advanced-features/availability-period-collection/
---
## Úvod

V tomto tutoriálu prozkoumáme, jak pracovat s kolekcí období dostupnosti zdroje v Aspose.Tasks for .NET. Správa období dostupnosti je pro projektové řízení zásadní a umožňuje nám definovat, kdy jsou k dispozici zdroje pro úkoly v rámci projektu.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní porozumění: Znalost C# a .NET frameworku.

## Importovat jmenné prostory

Nejprve musíme do našeho projektu importovat potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Pojďme si ukázkový kód rozdělit do několika kroků a porozumět každé části:

## Krok 1: Inicializujte projekt a zdroj

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Zde načítáme soubor projektu a získáváme konkrétní zdroj podle jeho ID.

## Krok 2: Vymažte existující období dostupnosti

```csharp
resource.AvailabilityPeriods.Clear();
```

Vymažeme všechna existující období dostupnosti spojená se zdrojem.

## Krok 3: Přidejte období dostupnosti

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Procházíme sbírkou období dostupnosti a přidáváme je do zdroje.

## Krok 4: Vložte nové období dostupnosti

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Vytvoříme nové období dostupnosti pro rok 2013 a vložíme ho do kolekce.

## Krok 5: Zobrazte období dostupnosti

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Vytiskneme počet a podrobnosti každého období dostupnosti spojeného se zdrojem.

## Krok 6: Zkopírujte období dostupnosti do jiného zdroje

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Zkopírujeme období dostupnosti z jednoho zdroje do druhého.

## Krok 7: Aktualizujte a odeberte období dostupnosti

```csharp
// Aktualizujte dostupné jednotky pro konkrétní období
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Odebrat konkrétní období
otherResource.AvailabilityPeriods.Remove(period2013);
```

Aktualizujeme dostupné jednotky pro určité období a konkrétní období odstraníme z kolekce.

## Závěr

tomto tutoriálu jsme se naučili, jak pracovat s kolekcemi období dostupnosti v Aspose.Tasks pro .NET. Řízení dostupnosti zdrojů je zásadní pro efektivní plánování a realizaci projektu.

## FAQ

### Q1: Mohu přidat vlastní pole do období dostupnosti?

A1: Ne, období dostupnosti v Aspose.Tasks pro .NET nepodporují vlastní pole.

### Q2: Jsou období dostupnosti spojena s konkrétními úkoly?

Odpověď 2: Ne, období dostupnosti jsou spojena se zdroji a obecně definují, kdy jsou k dispozici pro úkoly.

### Q3: Mohu importovat období dostupnosti z externích zdrojů?

A3: Ano, můžete importovat období dostupnosti z různých zdrojů dat pomocí Aspose.Tasks for .NET API.

### Q4: Jak zvládnu překrývající se období dostupnosti?

A4: Aspose.Tasks for .NET neposkytuje vestavěné mechanismy pro zpracování překrývajících se období. Možná budete muset implementovat vlastní logiku ke správě takových scénářů.

### Otázka 5: Existuje omezení počtu období dostupnosti zdroje?

Odpověď 5: Neexistuje žádné předem definované omezení počtu období dostupnosti, které může mít prostředek, ale s velkým počtem období může dojít ke snížení výkonu.