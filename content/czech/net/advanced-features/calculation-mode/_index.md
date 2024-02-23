---
title: Režim výpočtu v Aspose.Tasks
linktitle: Režim výpočtu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat režimy výpočtu v Aspose.Tasks for .NET, abyste zefektivnili plánování projektů a závislosti na úkolech.
type: docs
weight: 29
url: /cs/net/advanced-features/calculation-mode/
---
## Úvod

Aspose.Tasks for .NET je výkonné API, které umožňuje vývojářům pracovat se soubory Microsoft Project programově v jejich aplikacích .NET. Jedním z klíčových aspektů práce s projektovými soubory je správa režimů výpočtu, které určují, jak se úkoly a harmonogramy projektů počítají a aktualizují. V tomto tutoriálu se ponoříme do různých režimů výpočtu podporovaných Aspose.Tasks pro .NET a předvedeme, jak je efektivně používat.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní porozumění programování v C#: Seznamte se s koncepty programování v C#.

## Importovat jmenné prostory

Než začneme pracovat s Aspose.Tasks pro .NET, importujme potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;


```

## Použití režimu automatického výpočtu

### Krok 1: Vytvořte novou instanci projektu

 Inicializujte nový`Project` objekt a nastavte jej`CalculationMode` majetek do`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Krok 2: Nastavte datum zahájení projektu a přidejte úkoly

Definujte datum zahájení projektu a přidejte k němu úkoly.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Krok 3: Propojte úkoly

Vytvořte závislosti mezi úkoly.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Krok 4: Ověřte přepočítaná data

Zkontrolujte, zda byla data přepočítána automaticky.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Podle potřeby přidejte další ověření
```

## Použití režimu ručního výpočtu

### Krok 1: Vytvořte novou instanci projektu

 Inicializujte nový`Project` objekt a nastavte jej`CalculationMode` majetek do`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Krok 2: Nastavte datum zahájení projektu a přidejte úkoly

Definujte datum zahájení projektu a přidejte k němu úkoly.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Krok 3: Ověřte vlastnosti úlohy

Zkontrolujte, zda jsou vlastnosti úlohy správně nastaveny v ručním režimu.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Podle potřeby přidejte další ověření
```

### Krok 4: Propojte úkoly a ověřte data

Propojte úkoly dohromady a zkontrolujte, zda se jejich data nepřepočítají.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Použití žádného režimu výpočtu

### Krok 1: Vytvořte novou instanci projektu

 Inicializujte nový`Project` objekt a nastavte jej`CalculationMode` majetek do`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Krok 2: Přidejte nový úkol

Přidejte do projektu nový úkol.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Krok 3: Ověřte vlastnosti úlohy

Zkontrolujte, zda se vlastnosti úlohy nevypočítávají automaticky.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Podle potřeby přidejte další ověření
```

## Závěr

V tomto tutoriálu jsme prozkoumali režimy výpočtu dostupné v Aspose.Tasks pro .NET a naučili jsme se, jak je aplikovat v praktických scénářích. Ať už potřebujete automatický, manuální nebo žádný režim výpočtu, Aspose.Tasks poskytuje flexibilitu, aby vyhovovala požadavkům vašeho projektu.

## FAQ

### Q1: Mohu během běhu dynamicky změnit režim výpočtu?

A1: Ano, režim výpočtu projektu můžete změnit kdykoli během běhu úpravou`CalculationMode` vlastnictví.

### Q2: Podporuje Aspose.Tasks jiné formáty souborů správy projektů kromě Microsoft Project?

Odpověď 2: Aspose.Tasks se primárně zaměřuje na formáty souborů Microsoft Project, ale podporuje také další formáty, jako je Primavera P6 XML, Primavera DB a Asta Powerproject XML.

### Q3: Je Aspose.Tasks vhodný jak pro malé, tak pro podnikové projekty?

A3: Rozhodně! Aspose.Tasks je navržen tak, aby uspokojil potřeby malých i podnikových projektů se svými komplexními funkcemi a robustními API.

### Q4: Mohu integrovat Aspose.Tasks s jinými knihovnami a frameworky .NET?

Odpověď 4: Ano, můžete bezproblémově integrovat Aspose.Tasks s dalšími knihovnami a frameworky .NET a zlepšit tak funkčnost vašich aplikací.

### Q5: Je pro uživatele Aspose.Tasks k dispozici komunitní fórum nebo kanál podpory?

 A5: Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity a diskuze.