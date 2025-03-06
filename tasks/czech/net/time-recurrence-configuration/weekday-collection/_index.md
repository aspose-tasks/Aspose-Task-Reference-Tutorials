---
title: Zvládnutí všedních dnů v Aspose.Tasks
linktitle: Kolekce pracovních dnů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Objevte sílu Aspose.Tasks pro .NET při řízení pracovních dnů bez námahy. Snadno si přizpůsobte pracovní dny, odstraňte víkendy a vytvořte specializované kalendáře.
weight: 11
url: /cs/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí všedních dnů v Aspose.Tasks

## Úvod
Aspose.Tasks for .NET je výkonná knihovna, která usnadňuje efektivní manipulaci s daty projektového řízení. V tomto tutoriálu prozkoumáme sbírku pracovních dnů v Aspose.Tasks, což vám umožní přizpůsobit pracovní dny, odstranit víkendy a vytvořit specializované kalendáře, aby splňovaly požadavky vašeho projektu. Ať už jste ostřílený vývojář nebo nováček, tento podrobný průvodce vás provede procesem práce se všedními dny v Aspose.Tasks pro .NET.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Nainstalujte knihovnu Aspose.Tasks for .NET. Můžete si jej stáhnout z[Aspose.Tasks for .NET download page](https://releases.aspose.com/tasks/net/).
- Znalost programovacího jazyka C#.
- Integrované vývojové prostředí (IDE), jako je Visual Studio.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Vytvořte instanci projektu
Inicializujte nový projekt Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Krok 2: Otevřete Kalendář
Získejte kalendář projektu:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Krok 3: Přizpůsobte si pracovní dny
Vymazat stávající pracovní dny a nastavit výchozí pracovní dny:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Podobně přidejte další dny v týdnu...
```
## Krok 4: Přidejte pracovní dobu
Přidejte pracovní dobu pro konkrétní dny v týdnu:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Krok 5: Zobrazení informací kalendáře
Výstup podrobností kalendáře do konzole:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Zobrazit každý všední den a pracovní dobu...
```
## Krok 6: Odstraňte víkendy
Odebrat sobotu a neděli z pracovních dnů:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Krok 7: Zobrazení aktualizované pracovní doby
Výstup aktualizované pracovní doby po odstranění víkendů:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Zobrazit každý aktualizovaný den v týdnu a pracovní dobu...
```
## Krok 8: Vytvořte 24hodinový kalendář
Vytvořte 24hodinový kalendář a zkopírujte pracovní dny:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Závěr
V tomto tutoriálu jsme prozkoumali výkonné možnosti Aspose.Tasks pro .NET při správě pracovních dnů v rámci projektových kalendářů. Od přizpůsobení pracovních dnů po vytváření specializovaných 24hodinových kalendářů, Aspose.Tasks zjednodušuje proces a nabízí flexibilitu a kontrolu při řízení projektů.
## Často kladené otázky
### Otázka: Mohu používat Aspose.Tasks pro .NET s jinými programovacími jazyky?
A: Aspose.Tasks primárně podporuje jazyky .NET, ale nabízí i verze pro Javu.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[Stránka vydání Aspose.Tasks](https://releases.aspose.com/).
### Otázka: Jak mohu získat podporu pro Aspose.Tasks pro .NET?
 A: Navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro podporu komunity nebo zvažte nákup plánu podpory.
### Otázka: Kde najdu komplexní dokumentaci k Aspose.Tasks pro .NET?
 A: Viz[Aspose.Tasks pro dokumentaci .NET](https://reference.aspose.com/tasks/net/) pro podrobné informace.
### Otázka: Jak získám dočasnou licenci pro Aspose.Tasks pro .NET?
 Odpověď: Můžete získat dočasnou licenci z[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
