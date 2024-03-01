---
title: Konfigurace pracovní doby v Aspose.Tasks
linktitle: Konfigurace pracovní doby v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Vylepšete plánování projektů v .NET pomocí Aspose.Tasks. Bez námahy konfigurujte pracovní dobu pro přesné řízení zdrojů. Stáhněte si knihovnu nyní!
type: docs
weight: 13
url: /cs/net/time-recurrence-configuration/working-times/
---
## Úvod
projektovém řízení je přesná kontrola nad pracovní dobou zásadní pro přesné plánování a alokaci zdrojů. Aspose.Tasks for .NET poskytuje výkonné řešení pro manipulaci s informacemi o pracovní době v rámci vašich projektů. Tento tutoriál vás provede procesem konfigurace pracovní doby pomocí Aspose.Tasks v prostředí .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující:
- Základní znalost programovacího jazyka C#.
-  Nainstalovaná knihovna Aspose.Tasks for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
- Nastavení sady Visual Studio nebo jakéhokoli preferovaného vývojového prostředí C#.
## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů pro přístup k funkcím Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## Krok 1: Vytvořte kalendář
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Zde zahájíme nový projekt a vytvoříme kalendář s názvem „MyCalendar“ založený na standardním kalendáři. Tento kalendář bude použit k definování konkrétní pracovní doby.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Krok 2: Zobrazte informace o pracovním týdnu
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
Tento krok vytiskne celkový počet pracovních dnů v zadaném kalendáři.
## Krok 3: Podrobnosti o pracovní době
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
této části iterujeme každý den v týdnu, vytiskneme typ dne a související pracovní doby. Pracovní dobu pro každý všední den si můžete přizpůsobit podle požadavků vašeho projektu.
## Závěr
Efektivní konfigurace pracovní doby v Aspose.Tasks pro .NET zajišťuje přesné plánování projektů a správu zdrojů. Podle tohoto podrobného průvodce můžete bez problémů integrovat úpravy pracovní doby do pracovních postupů projektu.
## Často kladené otázky
### Je Aspose.Tasks vhodný pro řízení rozsáhlých projektů?
Ano, Aspose.Tasks je navržen pro zpracování projektů různých velikostí a nabízí robustní funkce pro efektivní řízení projektů.
### Mohu nastavit různé pracovní doby pro různé členy týmu?
Absolutně. Pracovní dobu si můžete přizpůsobit na základě jednotlivých zdrojů, což umožňuje individuální plány.
### Podporuje Aspose.Tasks integraci s jinými nástroji pro řízení projektů?
Ano, Aspose.Tasks usnadňuje integraci s různými nástroji pro řízení projektů a zvyšuje interoperabilitu.
### Je možné importovat/exportovat data projektu v různých formátech?
Aspose.Tasks podporuje více formátů souborů, což umožňuje bezproblémový import/export dat projektu.
### Jak často jsou vydávány aktualizace Aspose.Tasks?
Aktualizace jsou pravidelně vydávány, aby byla zajištěna kompatibilita s nejnovějšími technologiemi a reagovaly na zpětnou vazbu uživatelů.