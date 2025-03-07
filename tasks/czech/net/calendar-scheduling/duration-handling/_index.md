---
title: Zpracování doby trvání v Aspose.Tasks
linktitle: Zpracování doby trvání v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně zacházet s trváním v Aspose.Tasks pro .NET pomocí podrobných výukových programů.
weight: 30
url: /cs/net/calendar-scheduling/duration-handling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zpracování doby trvání v Aspose.Tasks

## Úvod

Efektivní zpracování doby trvání je v aplikacích projektového řízení zásadní. Aspose.Tasks for .NET poskytuje robustní funkce pro efektivní správu trvání. V tomto tutoriálu prozkoumáme různé aspekty zpracování doby trvání pomocí Aspose.Tasks pro .NET.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:

1. Základní znalost C#: Pro pochopení a implementaci příkladů je nezbytná znalost programovacího jazyka C#.
2. Visual Studio: Nainstalujte Visual Studio IDE, abyste mohli vytvářet a spouštět aplikace .NET.
3.  Aspose.Tasks for .NET: Stáhněte a nainstalujte knihovnu Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory pro použití funkcí Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Pojďme si každý příklad rozdělit do několika kroků ve formátu průvodce krok za krokem:

## Aktualizace trvání úkolů

### Krok 1: Načtěte soubor projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Získejte úkol a trvání

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Krok 3: Trvání aktualizace

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Krok 4: Zobrazení aktualizované doby trvání

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Odečítání trvání úkolů

### Krok 1: Načtěte soubor projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Získejte úkol a trvání

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Krok 3: Odečtěte dobu trvání

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Krok 4: Zobrazení aktualizované doby trvání

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Převod Duration to TimeSpan

### Krok 1: Načtěte soubor projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Získejte úkol a trvání

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Krok 3: Převeďte Duration na TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Převod trvání na řetězec

### Krok 1: Načtěte soubor projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Získejte úkol a trvání

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Krok 3: Převeďte trvání na řetězec

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Závěr

tomto tutoriálu jsme se zabývali různými aspekty zpracování doby trvání v Aspose.Tasks pro .NET. Pochopení a efektivní řízení doby trvání je zásadní pro úspěšné řízení projektu. Aspose.Tasks poskytuje komplexní funkce pro zjednodušení úkolů správy trvání ve vašich aplikacích .NET.

## FAQ

### Q1: Co je Aspose.Tasks pro .NET?

A1: Aspose.Tasks for .NET je výkonná knihovna pro práci se soubory Microsoft Project v aplikacích .NET.

### Q2: Dokáže Aspose.Tasks zvládnout složité projektové struktury?

Odpověď 2: Ano, Aspose.Tasks si snadno poradí se složitými projektovými strukturami a poskytuje rozsáhlá rozhraní API pro manipulaci.

### Q3: Je Aspose.Tasks for .NET kompatibilní s .NET Core?

Odpověď 3: Ano, Aspose.Tasks for .NET je kompatibilní s .NET Core, což vám umožňuje používat jej v multiplatformních aplikacích.

### Q4: Podporuje Aspose.Tasks čtení a zápis souborů aplikace Microsoft Project?

Odpověď 4: Ano, Aspose.Tasks podporuje čtení a zápis souborů aplikace Microsoft Project v různých formátech, včetně MPP, XML a MPX.

### Q5: Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?

A5: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET od[tady](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
