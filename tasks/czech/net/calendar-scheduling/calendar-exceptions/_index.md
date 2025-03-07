---
title: Zpracování výjimek kalendáře v Aspose.Tasks
linktitle: Zpracování výjimek kalendáře v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak spravovat výjimky kalendáře v Aspose.Tasks pro .NET pomocí podrobných výukových programů a příkladů.
weight: 12
url: /cs/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zpracování výjimek kalendáře v Aspose.Tasks

## Úvod

V tomto tutoriálu prozkoumáme, jak spravovat výjimky kalendáře v Aspose.Tasks pomocí rozhraní .NET. Výjimky kalendáře nám umožňují definovat speciální data nebo období v kalendáři projektu, kde se mění běžný pracovní plán, jako jsou svátky nebo dočasné uzavření. Probereme různé metody zpracování výjimek kalendáře krok za krokem pomocí Aspose.Tasks pro .NET.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka C#.
- Visual Studio nainstalované ve vašem systému.
- Do vašeho projektu byla přidána knihovna Aspose.Tasks for .NET.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory pro náš projekt:

```csharp
using Aspose.Tasks;
using System;


```

## Krok 1: Odstranění výjimky kalendáře

Chcete-li odstranit výjimku kalendáře, postupujte takto:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Zobrazení informací kalendáře
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Odstraňte první výjimku
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Krok 2: Získání pracovní doby výjimky kalendáře

Chcete-li načíst pracovní čas výjimky kalendáře, postupujte takto:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Zobrazit informace o kalendáři a výjimkách
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Získejte pracovní dobu a zobrazte podrobnosti
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Krok 3: Definování výjimek kalendáře

Chcete-li přidat nebo odebrat výjimky kalendáře, postupujte takto:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Vytvořte novou výjimku kalendáře
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Nastavte podrobnosti o výjimce
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Zkontrolujte, zda datum není výjimkou
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Přidejte výjimku do kalendáře
    calendar.Exceptions.Add(exception);

    // Odstraňte výjimku, pokud existuje
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Přidat novou výjimku
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Tisk výjimek
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Závěr

tomto článku jsme se zabývali různými aspekty zpracování výjimek kalendáře v Aspose.Tasks pro .NET. Dodržováním uvedených kroků můžete efektivně spravovat výjimky v plánech projektu a zajistit tak přesnou reprezentaci pracovní doby a zvláštních událostí.

## FAQ

### Q1: Mohu přidat více výjimek do jednoho kalendáře?

Odpověď 1: Ano, do kalendáře můžete přidat více výjimek, aby vyhovovaly různým zvláštním datům nebo obdobím.

### Q2: Jak mohu zkontrolovat, zda je konkrétní datum výjimkou?

 A2: Můžete použít`CheckException()` metoda k ověření, zda určité datum spadá pod výjimku.

### Q3: Je možné odstranit existující výjimku z kalendáře?

 A3: Ano, můžete odebrat výjimky přístupem k`Exceptions` sběr kalendáře a používání`Remove()` metoda.

### Q4: Jaké typy výjimek kalendáře jsou podporovány?

A4: Aspose.Tasks podporuje různé typy výjimek, včetně denních, týdenních, měsíčních a ročních výjimek a poskytuje flexibilitu při definování pravidel výjimek.

### Q5: Mohu přizpůsobit pracovní dobu pro konkrétní výjimečná data?

A5: Ano, můžete definovat vlastní pracovní časy pro jednotlivá data výjimek pomocí příslušných metod poskytovaných Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
