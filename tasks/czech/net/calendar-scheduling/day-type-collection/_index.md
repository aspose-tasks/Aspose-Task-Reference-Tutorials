---
title: Správa kolekce typů dne v Aspose.Tasks
linktitle: Správa kolekce typů dne v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat kolekce typu dne v Aspose.Tasks pro .NET. Snadno vytvářejte, upravujte a manipulujte s výjimkami kalendáře.
weight: 28
url: /cs/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa kolekce typů dne v Aspose.Tasks

## Úvod

 Aspose.Tasks for .NET poskytuje robustní funkce pro správu kolekcí typu dne, což je zásadní pro definování výjimek týdenního kalendáře v aplikacích pro správu projektů. V tomto tutoriálu prozkoumáme, jak využít`DayTypeCollection` třídy efektivně. 

## Předpoklady

Než budeme pokračovat s výukovým programem, ujistěte se, že máte následující předpoklady:

1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Znalost programovacího jazyka C# a konceptů .NET frameworku.

## Importovat jmenné prostory

Chcete-li začít, musíte do svého projektu C# importovat potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;


```

Nyní rozdělme poskytnutý příklad do několika kroků:

## Krok 1: Načtěte projekt a otevřete kalendář

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Tento krok inicializuje novou instanci projektu a načte kalendář podle jeho UID.

## Krok 2: Projděte si výjimky kalendáře

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Zde iterujeme každou výjimku kalendáře a vytiskneme její název a související typy dnů.

## Krok 3: Upravte výjimky kalendáře

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Tento krok ukazuje, jak upravit výjimky kalendáře přidáním, odebráním nebo aktualizací typů dnů.

## Krok 4: Vytvoření a manipulace s novými výjimkami kalendáře

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

V tomto posledním kroku vytváříme nové výjimky kalendáře a manipulujeme s nimi přidáváním a kopírováním typů dnů.

## Závěr

 Závěrem lze říci, že správa kolekcí typu dne v Aspose.Tasks for .NET je nezbytná pro definování a úpravu výjimek týdenního kalendáře v aplikacích pro řízení projektů. Pokud budete postupovat podle podrobného průvodce v tomto tutoriálu, můžete efektivně využít`DayTypeCollection` třídy pro zpracování různých kalendářových operací.

## FAQ

### Q1: Lze Aspose.Tasks for .NET použít k vytvoření Ganttových diagramů programově?

Odpověď 1: Ano, Aspose.Tasks for .NET poskytuje rozhraní API pro vytváření a manipulaci s Ganttovými diagramy v aplikacích .NET.

### Q2: Je Aspose.Tasks for .NET kompatibilní s .NET Core i .NET Framework?

Odpověď 2: Ano, Aspose.Tasks for .NET podporuje .NET Core i .NET Framework.

### Q3: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

 A3: Podporu můžete získat návštěvou stránky[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) kde můžete klást otázky a komunikovat s ostatními uživateli.

### Q4: Nabízí Aspose.Tasks for .NET bezplatnou zkušební verzi?

 A4: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET od[tady](https://releases.aspose.com/).

### Q5: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks pro .NET?

 A5: Ano, dočasné licence jsou k dispozici pro nákup z[Aspose webové stránky](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
