---
title: Práce s Baseline Collection v Aspose.Tasks
linktitle: Práce s Baseline Collection v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat směrné plány v Aspose.Tasks pro .NET. Postupujte podle našeho komplexního návodu, kde najdete podrobné pokyny.
type: docs
weight: 20
url: /cs/net/advanced-features/working-with-baseline-collection/
---
## Úvod

Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům bezproblémově pracovat se soubory Microsoft Project v jejich aplikacích .NET. Mezi svými mnoha funkcemi poskytuje robustní podporu pro správu základních linií v rámci projektů. Základní linie jsou nezbytné pro řízení projektu, protože umožňují porovnat původní plán projektu se současným stavem, což umožňuje lepší sledování a analýzu průběhu projektu.

## Předpoklady

Než se pustíme do práce se základními kolekcemi v Aspose.Tasks, ujistěte se, že máte splněny následující předpoklady:

1. Visual Studio: Nainstalujte Visual Studio IDE do vašeho systému.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[odkaz ke stažení](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Seznamte se s programovacím jazykem C#.
4. Soubor Microsoft Project: Připravte si soubor Microsoft Project (.mpp) pro účely testování.

## Importovat jmenné prostory

Chcete-li začít pracovat se základními kolekcemi v Aspose.Tasks, musíte importovat následující jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Nyní si každý příklad rozdělíme do několika kroků:

## Krok 1: Načtěte soubor projektu

Nejprve načtěte soubor Microsoft Project pomocí Aspose.Tasks:

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Krok 2: Získejte zdroj

Dále načtěte požadovaný zdroj z projektu:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Krok 3: Zobrazte základní informace

Nyní zobrazte informace o směrných plánech spojených se zdrojem:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Krok 4: Iterujte přes základní linie

Procházejte každou základní linii spojenou se zdrojem a vytiskněte příslušné informace:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Krok 5: Odstraňte základní linie

Smazat všechny směrné plány spojené se zdrojem:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak pracovat se základními kolekcemi v Aspose.Tasks pro .NET. Podle podrobného průvodce můžete snadno spravovat základní linie ve svých aplikacích .NET, což umožňuje efektivní sledování a analýzu projektů.

## FAQ

### Q1: Dokáže Aspose.Tasks zpracovat velké soubory projektu?

Odpověď 1: Ano, Aspose.Tasks je optimalizována tak, aby efektivně zpracovávala velké projektové soubory a zajistila hladký výkon.

### Q2: Je Aspose.Tasks kompatibilní se všemi verzemi aplikace Microsoft Project?

A2: Aspose.Tasks podporuje různé verze aplikace Microsoft Project a zajišťuje kompatibilitu v různých prostředích.

### Q3: Mohu upravit směrné linie v Aspose.Tasks?

Odpověď 3: Ano, pomocí Aspose.Tasks for .NET můžete přizpůsobit směrné plány podle požadavků vašeho projektu.

### Q4: Nabízí Aspose.Tasks podporu pro cloudové platformy?

Odpověď 4: Ano, Aspose.Tasks poskytuje podporu pro integraci s oblíbenými cloudovými platformami a nabízí flexibilitu při nasazení.

### Q5: Existuje komunitní fórum pro uživatele Aspose.Tasks, aby hledali pomoc a sdíleli znalosti?

 A5: Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) zapojit se do komunity a získat pomoc od odborníků.