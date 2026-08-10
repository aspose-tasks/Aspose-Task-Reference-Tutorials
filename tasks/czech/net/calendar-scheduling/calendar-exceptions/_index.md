---
date: 2026-04-13
description: Naučte se, jak odstranit výjimku kalendáře v Aspose.Tasks pro .NET a
  zkontrolovat datum výjimky při správě plánování kalendáře v ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Smazat výjimku kalendáře pomocí Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Smazat výjimku kalendáře pomocí Aspose.Tasks
url: /cs/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odstranění výjimky kalendáře pomocí Aspose.Tasks

## Úvod

V tomto tutoriálu se naučíte, jak **odstranit výjimku kalendáře** a spravovat další výjimky kalendáře v Aspose.Tasks pomocí .NET frameworku. Výjimky kalendáře vám umožňují modelovat svátky, dočasné uzavírky nebo jakékoli speciální období, kdy se mění běžný pracovní rozvrh. Porozumění tomu, jak přidávat, dotazovat a odstraňovat tyto výjimky, je nezbytné pro přesné plánování projektů, zejména při práci se scénáři **plánování kalendáře v ASP.NET**.

## Rychlé odpovědi
- **Jaká je hlavní metoda pro odstranění výjimky?** Použijte metodu `Delete()` na objektu `CalendarException`.  
- **Která třída kontroluje datum vůči výjimce?** `CalendarException.CheckException()` — užitečné pro **kontrolu data výjimky**.  
- **Potřebuji licenci pro spuštění kódu?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu přidat více výjimek do jednoho kalendáře?** Ano; kolekce `Exceptions` podporuje mnoho položek.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je výjimka kalendáře?

**Výjimka kalendáře** představuje odchylku od běžného pracovního kalendáře — představte si ji jako pravidlo, které říká „v těchto dnech jsou pracovní hodiny jiné nebo vůbec žádné“. V Aspose.Tasks může mít každá výjimka své vlastní pracovní časy, vzor opakování a příznaky, které určují, zda je den pracovním.

## Proč spravovat výjimky kalendáře v plánování kalendáře ASP.NET?

- **Přesné časové osy:** Projekty automaticky respektují svátky a speciální uzavírky, čímž zabraňují nerealistickým termínům.  
- **Flexibilita:** Můžete definovat denní, týdenní, měsíční nebo roční vzory, které odpovídají reálným obchodním kalendářům.  
- **Automatizace:** Programová kontrola data výjimky vám umožní vytvořit dynamickou logiku plánování v aplikacích ASP.NET.

## Požadavky

- Základní znalost programování v C#.  
- Visual Studio (jakákoli aktuální verze).  
- Knihovna Aspose.Tasks pro .NET přidaná do vašeho projektu (prostřednictvím NuGet nebo ruční reference).  

## Importovat jmenné prostory

Nejprve importujte potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
```

## Krok 1: Odstranit výjimku kalendáře

Odstranění nechtěné výjimky je jednoduché. Následující kód načte projekt, vybere první kalendář, zobrazí základní informace, odstraní první výjimku a poté zobrazí aktualizovaný počet.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Tip:** Vždy ověřte, že index výjimky existuje, než zavoláte `Delete()`, abyste se vyhnuli `IndexOutOfRangeException`.

## Krok 2: Získat pracovní čas výjimky kalendáře

Pokud potřebujete zkontrolovat pracovní hodiny definované pro výjimku, použijte `GetWorkingTime()`. Tento příklad také ukazuje, jak **zkontrolovat datum výjimky** pomocí `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Krok 3: Definovat výjimky kalendáře

Níže je kompletní průvodce, který ukazuje, jak **přidat**, **zkontrolovat** a **odstranit** výjimky kalendáře. Všimněte si použití `CheckException` k **kontrole data výjimky** pro konkrétní okamžik.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Časté problémy a tipy

| Problém | Důvod | Řešení |
|-------|--------|----------|
| **`IndexOutOfRangeException` při mazání** | Pokus o smazání výjimky, která neexistuje. | Ověřte, že `calendar.Exceptions.Count` > index před voláním `Delete()`. |
| **Nesprávné pracovní časy** | Nesprávné nastavení `DayWorking` nebo `WorkingTimes`. | Použijte `exception.WorkingTimes.Add(new WorkingTime(...))` k definování explicitních období. |
| **Výjimka není rozpoznána** | `CheckException` vrací `false`, protože datum spadá mimo definovaný rozsah. | Zkontrolujte `FromDate`/`ToDate` a `Type` (Daily, Weekly, atd.). |

## Často kladené otázky

**Q:** *Mohu přidat více výjimek do jednoho kalendáře?*  
**A:** Ano, můžete přidat libovolný počet výjimek potřebných k reprezentaci svátků, údržbových oken nebo jakýchkoli speciálních pravidel plánování.

**Q:** *Jak **zkontrolovat datum výjimky** pro konkrétní den?*  
**A:** Použijte metodu `CheckException(DateTime date)` na instanci `CalendarException`. Vrátí `true`, pokud zadané datum spadá do rozsahu výjimky.

**Q:** *Je možné odstranit existující výjimku z kalendáře?*  
**A:** Ano. Přistupte ke kolekci `Exceptions` a zavolejte `Remove()` nebo použijte `Delete()` na konkrétním objektu `CalendarException`.

**Q:** *Jaké typy výjimek kalendáře jsou podporovány?*  
**A:** Aspose.Tasks podporuje typy výjimek Daily, Weekly, Monthly a Yearly, což vám poskytuje flexibilitu modelovat téměř jakýkoli vzor opakování.

**Q:** *Mohu přizpůsobit pracovní hodiny pro konkrétní data výjimek?*  
**A:** Ano. Po vytvoření výjimky naplňte její kolekci `WorkingTimes` objekty `WorkingTime`, které definují začátek a konec pracovní doby pro daný den.

## Závěr

Prošli jsme kompletním životním cyklem operací **odstranění výjimky kalendáře**, od kontroly existujících výjimek po přidání nových a kontrolu dat. Ovládnutí těchto technik zajišťuje, že vaše projektové plány respektují reálné kalendáře, což činí vaše implementace plánování kalendáře v ASP.NET robustní a spolehlivé.

---

**Poslední aktualizace:** 2026-04-13  
**Testováno s:** Aspose.Tasks for .NET (nejnovější verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}