---
title: Přizpůsobte si pracovní týdny v Aspose.Tasks
linktitle: Kolekce pracovních týdnů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak přizpůsobit pracovní týdny v Aspose.Tasks pro .NET. Podrobný průvodce vytvářením personalizovaných projektových kalendářů. Stáhnout teď!
type: docs
weight: 17
url: /cs/net/time-recurrence-configuration/workweek-collection/
---
## Úvod
Vítejte v našem tutoriálu o vytvoření vlastního pracovního týdne pomocí Aspose.Tasks pro .NET! V tomto podrobném průvodci vás provedeme procesem definování personalizovaného pracovního týdne pro kalendář ve vašem projektu. Aspose.Tasks je výkonná knihovna, která umožňuje vývojářům efektivně pracovat s dokumenty Microsoft Project v jejich aplikacích .NET.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio.
2.  Aspose.Tasks for .NET: Stáhněte a nainstalujte knihovnu Aspose.Tasks. Odkaz ke stažení najdete[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Seznamte se se základy programovacího jazyka C#.
## Importovat jmenné prostory
Ve svém projektu C# nezapomeňte importovat potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Vytvořte projekt a kalendář
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Krok 2: Definujte vlastní pracovní týden
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Krok 3: Nastavte pracovní dny
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Krok 4: Zobrazení informací o pracovních týdnech
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Tento komplexní průvodce vám umožňuje efektivně vytvářet a spravovat vlastní pracovní týdny pomocí Aspose.Tasks for .NET.
## Závěr
Na závěr, Aspose.Tasks for .NET poskytuje robustní řešení pro práci s projektovými kalendáři s vlastními pracovními týdny. Sledováním tohoto kurzu jste se naučili, jak vytvářet a zobrazovat informace o vlastních pracovních týdnech ve vašem projektu.
## Nejčastější dotazy
### Mohu mít více vlastních pracovních týdnů v jednom projektu?
Ano, do kalendáře projektu můžete přidat více vlastních pracovních týdnů.
### Jak mohu upravit stávající pracovní týdny?
 Použijte poskytnuté`WorkWeek` vlastnosti a metody pro úpravu stávajících pracovních týdnů.
### Je Aspose.Tasks kompatibilní s .NET Core?
Ano, Aspose.Tasks podporuje .NET Core.
### Mohu exportovat projekt s vlastními pracovními týdny do formátu souboru Microsoft Project?
Rozhodně vám Aspose.Tasks umožňuje uložit váš projekt v různých formátech, včetně Microsoft Project.
### Kde mohu hledat podporu pro dotazy související s Aspose.Tasks?
 navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za jakoukoli podporu nebo pomoc.