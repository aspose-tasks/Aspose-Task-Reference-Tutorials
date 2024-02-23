---
title: Zvládnutí pracovních dnů v Aspose.Tasks pro .NET
linktitle: Definování pracovních dnů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte sílu definování pracovních dnů v Aspose.Tasks .NET. Postupujte podle našeho podrobného výukového programu pro efektivní správu projektových kalendářů, přizpůsobení pracovní doby a další.
type: docs
weight: 10
url: /cs/net/time-recurrence-configuration/defining-weekdays/
---
## Úvod
Pokud se ponoříte do světa projektového řízení pomocí Aspose.Tasks pro .NET, pochopení a manipulace se všedními dny je zásadním aspektem. Efektivní správa a přizpůsobení pracovních dnů v kalendáři projektu může významně ovlivnit harmonogramy projektů. V tomto tutoriálu vás provedeme procesem definování pracovních dnů pomocí Aspose.Tasks, poskytneme vám podrobné pokyny a příklady pro lepší přehlednost.
## Předpoklady
Než se vydáme na tuto cestu, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka C#.
-  Nainstalovaná knihovna Aspose.Tasks for .NET. Pokud ne, stáhněte si jej z[tady](https://releases.aspose.com/tasks/net/).
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Zkontrolujte Rovnost pracovních dnů
```csharp
// Váš adresář dokumentů
String DataDir = "Your Document Directory";
// Načíst soubor projektu
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Přístup ve všední dny
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Zkontrolujte rovnost na základě různých vlastností
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Přidejte podobné výstupní příkazy pro DayWorking, FromDate, ToDate a WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Klonujte pracovní den
```csharp
// Načíst soubor projektu
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Vytvořte hlubokou kopii pracovního dne
var weekDay2 = weekDay1.Clone();
// Výstupní vlastnosti obou pracovních dnů
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Přidejte podobné výstupní příkazy pro DayWorking, FromDate, ToDate a WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Získejte hash kód dne v týdnu
```csharp
// Načíst soubor projektu
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Výstupní vlastnosti obou pracovních dnů
// Přidejte podobné výstupní příkazy pro DayWorking, FromDate, ToDate a WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Vytvořte nový kalendář s definovanými dny v týdnu
```csharp
// Vytvořte nový projekt
var project = new Project();
// Definujte kalendář
var calendar = project.Calendars.Add("Calendar1");
// Přidejte pracovní dny a výjimečné dny
// Přidejte podobné výstupní příkazy pro FromDate a ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Nastavte pracovní dobu na pátek
// Přidejte podobné výstupní příkazy pro DayWorking, FromDate, ToDate a WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Nastavte výchozí pracovní dobu na den
```csharp
// Vytvořte nový projekt
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Přidejte výchozí pracovní dobu pro pondělí až pátek
// Přidejte podobné výstupní příkazy pro DayWorking, FromDate, ToDate a WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Opakujte pro úterý, středu, čtvrtek a pátek
// Nastavte dny pracovního klidu na sobotu a neděli
// Přidejte podobné výstupní příkazy pro DayWorking, FromDate, ToDate a WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Závěr
V tomto tutoriálu jsme se zabývali základními aspekty definování pracovních dnů v Aspose.Tasks pro .NET. Manipulace se všedními dny je klíčovou dovedností pro efektivní řízení projektů. Experimentujte s poskytnutými příklady, přizpůsobte je potřebám svého projektu a odemkněte plný potenciál Aspose.Tasks.
## Nejčastější dotazy
### Mohu definovat vlastní pracovní dobu pro každý den?
Ano, pomocí uvedených příkladů můžete nastavit vlastní pracovní dobu pro konkrétní dny v týdnu.
### Je možné do kalendáře přidat více výjimečných dnů?
Absolutně. Upravte kód ve čtvrtém příkladu tak, aby zahrnoval další výjimečné dny.
### Jak mohu z kalendáře odstranit konkrétní den v týdnu?
Použijte vhodné metody poskytované knihovnou Aspose.Tasks k odstranění pracovních dnů podle potřeby.
### Jsou změny provedené v pracovních dnech v souboru projektu trvalé?
Ano, jakékoli změny pracovních dnů se při uložení projeví v souboru projektu.
### Mohu používat Aspose.Tasks s jinými programovacími jazyky?
Aspose.Tasks podporuje různé programovací jazyky, ale příklady zde jsou specificky pro .NET.