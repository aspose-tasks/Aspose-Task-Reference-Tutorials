---
title: Kolekce kalendářních výjimek v Aspose.Tasks
linktitle: Kolekce kalendářních výjimek v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně zpracovávat výjimky kalendáře ve vašich projektech .NET pomocí Aspose.Tasks, což zajišťuje přesné plánování a správu zdrojů.
weight: 13
url: /cs/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kolekce kalendářních výjimek v Aspose.Tasks

## Úvod

projektovém řízení je přesné plánování zásadní pro úspěch. Scénáře reálného světa však často vyžadují odchylky od standardních plánů kvůli svátkům, zvláštním událostem nebo jiným faktorům. Aspose.Tasks for .NET poskytuje robustní řešení pro správu takových výjimek prostřednictvím funkce Calendar Exception Collection. Tento tutoriál vás krok za krokem provede procesem využití této funkce.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:

1.  Aspose.Tasks for .NET: Ujistěte se, že máte nainstalovanou knihovnu. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
2. Základní znalost C#: Pro pochopení příkladů pomůže znalost programovacího jazyka C#.
3. Vývojové prostředí: Nastavte si preferované vývojové prostředí, jako je Visual Studio nebo JetBrains Rider.

## Importovat jmenné prostory

Než začnete pracovat s Aspose.Tasks for .NET, musíte do svého projektu importovat požadované jmenné prostory. Tento krok vám umožní přístup ke třídám a metodám nezbytným pro správu výjimek kalendáře.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Nyní si uvedený příklad rozdělíme do několika kroků:

## Krok 1: Načtěte projekt a načtěte kalendář

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

V tomto kroku načteme soubor projektu a načteme požadovaný kalendář podle jeho UID.

## Krok 2: Vymažte existující výjimky a nastavte standardní kalendář

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Tento krok vymaže všechny existující výjimky z kalendáře a nastaví jej na standardní konfiguraci.

## Krok 3: Definujte a přidejte výjimku pracovní doby

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Tento krok definuje výjimku pracovní doby s konkrétními daty začátku a konce spolu s pracovní dobou v rámci těchto dat a přidá ji do kalendáře.

## Krok 4: Definujte a přidejte výjimky nepracovní doby

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// V případě potřeby přidejte další výjimky

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Tento krok definuje výjimky mimo pracovní dobu, jako jsou svátky, a přidá je do kalendáře.

## Krok 5: Zobrazení výjimek kalendáře

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Tento krok zobrazí přidané výjimky kalendáře spolu s jejich podrobnostmi.

## Krok 6: Odstraňte všechny výjimky

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Nakonec tento krok odstraní všechny výjimky z kalendáře.

## Závěr

Správa výjimek kalendáře je zásadní pro přesné plánování projektu. Aspose.Tasks for .NET tento úkol zjednodušuje poskytováním komplexní sady funkcí, včetně kolekce výjimek kalendáře. Podle kroků uvedených v tomto kurzu můžete efektivně zpracovat různé scénáře plánování v rámci svých projektů.

## FAQ

### Q1: Mohu přidat více výjimek do jednoho kalendáře?

 A1: Ano, můžete přidat více výjimek do kalendáře pomocí`AddRange` metoda.

### Q2: Jak zpracuji opakující se výjimky, jako jsou týdenní svátky?

A2: Můžete programově vypočítat opakované výjimky a přidat je do kalendáře pomocí vlastní logiky.

### Q3: Je možné importovat výjimky kalendáře z externích zdrojů?

A3: Ano, můžete číst výjimky kalendáře z externích zdrojů, jako jsou databáze nebo soubory CSV, a integrovat je do svého projektu.

### Q4: Co se stane, pokud se v kalendáři překrývají výjimky?

A4: Aspose.Tasks for .NET umožňuje zpracovat překrývající se výjimky definováním priorit nebo řešením konfliktů na základě požadavků projektu.

### Q5: Mohu upravit pracovní dobu pro každý den v rámci výjimky?

A5: Ano, můžete zadat vlastní pracovní dobu pro jednotlivé dny v rámci výjimky, aby vyhovovala konkrétním potřebám plánování.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
