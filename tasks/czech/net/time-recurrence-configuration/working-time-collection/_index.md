---
title: Zvládnutí pracovní doby v Aspose.Tasks
linktitle: Sbírka pracovních dob v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte sílu Aspose.Tasks pro .NET při efektivní správě časových os projektů. Snadno si přizpůsobte kalendáře, nastavte pracovní dobu a zefektivněte své projekty.
weight: 14
url: /cs/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí pracovní doby v Aspose.Tasks

## Úvod
Chcete zvládnout umění řízení pracovní doby v Aspose.Tasks pro .NET? Už nehledejte! V tomto podrobném průvodci se ponoříme do složitosti sběru pracovní doby pomocí Aspose.Tasks, což vám umožní efektivně pracovat s vlastními kalendáři a zefektivnit časové osy vašich projektů.
## Předpoklady
Než se vydáme na tuto cestu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Tasks for .NET Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[Stránka vydání Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Pracovní prostředí: Nastavte vhodné vývojové prostředí, nejlépe pomocí IDE kompatibilního s .NET.
## Importovat jmenné prostory
Ve svém projektu importujte potřebné jmenné prostory pro přístup k funkcím Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Nyní si výukový program rozdělíme do několika kroků, abychom zajistili plynulé učení.
## Krok 1: Vytvořte si vlastní kalendář
Začněte vytvořením nového projektu a přidáním vlastního kalendáře:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Krok 2: Definujte pracovní dny
Nastavte výchozí pracovní dny od pondělí do pátku:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Krok 3: Nakonfigurujte sobotní pracovní dobu
Upřesněte pracovní dobu na sobotu:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Krok 4: Tisk sobotních pracovních období
Vytiskněte si nakonfigurovanou pracovní dobu pro sobotu:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Krok 5: Nakonfigurujte nedělní pracovní dobu
Definujte pracovní dobu pro neděli:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Krok 6: Tisk nedělních pracovních období
Vytiskněte si nakonfigurovanou pracovní dobu pro neděli:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Krok 7: Přidejte do kalendáře vlastní dny
Zahrnout nakonfigurovanou sobotu a neděli do kalendáře:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Krok 8: Projděte pracovní dobu
Procházejte pracovní časy a zobrazte je pro každý den v kalendáři:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Nyní, když jste úspěšně prošli jednotlivými kroky, jste připraveni využít sílu Aspose.Tasks pro .NET při efektivním řízení pracovní doby.
## Závěr
Zvládnutí shromažďování pracovních časů v Aspose.Tasks vám umožňuje přizpůsobit kalendáře projektů, zajistit přesné plánování a efektivní využití zdrojů. Ponořte se do svých projektů s důvěrou, vyzbrojeni znalostmi získanými z tohoto komplexního průvodce.
## Často kladené otázky
### Je Aspose.Tasks vhodný pro řízení rozsáhlých projektů?
Ano, Aspose.Tasks je navržen pro zpracování projektů různých velikostí a poskytuje robustní funkce pro efektivní řízení projektů.
### Mohu integrovat Aspose.Tasks s jinými knihovnami .NET?
Rozhodně! Aspose.Tasks se hladce integruje s ostatními knihovnami .NET, čímž se zvyšuje jeho všestrannost a kompatibilita.
### Jak často se Aspose.Tasks aktualizuje?
 Aspose.Tasks je pravidelně aktualizován, aby zahrnoval nové funkce, vylepšení a vylepšení kompatibility. Zkontrolovat[stránka vydání](https://releases.aspose.com/tasks/net/) pro nejnovější aktualizace.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Ano, můžete navštívit Aspose.Tasks s bezplatnou zkušební verzí[tento odkaz](https://releases.aspose.com/).
### Kde mohu hledat podporu pro Aspose.Tasks?
 V případě jakýchkoli dotazů nebo pomoci navštivte stránku[Fórum podpory Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
