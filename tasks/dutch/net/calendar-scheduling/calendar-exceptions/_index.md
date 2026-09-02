---
date: 2026-04-13
description: Leer hoe u een kalenderuitzondering kunt verwijderen in Aspose.Tasks
  voor .NET en controleer de uitzonderingsdatum bij het beheren van ASP.NET‑kalenderplanning.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Verwijder kalenderuitzondering met Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Kalenderuitzondering verwijderen met Aspose.Tasks
url: /nl/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalenderuitzondering verwijderen met Aspose.Tasks

## Inleiding

In deze tutorial leer je hoe je **kalenderuitzondering verwijderen** en andere kalenderuitzonderingen beheert in Aspose.Tasks met behulp van het .NET-framework. Kalenderuitzonderingen stellen je in staat om feestdagen, tijdelijke sluitingen of andere speciale perioden te modelleren waarin het normale werkschema wijzigt. Het begrijpen van het toevoegen, opvragen en verwijderen van deze uitzonderingen is essentieel voor nauwkeurige projectplanning, vooral bij **ASP.NET calendar scheduling** scenario's.

## Snelle antwoorden
- **Wat is de primaire methode om een uitzondering te verwijderen?** Use the `Delete()` method on the `CalendarException` object.  
- **Welke klasse controleert een datum tegen een uitzondering?** `CalendarException.CheckException()`—useful to **check exception date**.  
- **Heb ik een licentie nodig om de code uit te voeren?** Yes, a valid Aspose.Tasks license is required for production use.  
- **Kan ik meerdere uitzonderingen aan één kalender toevoegen?** Absolutely; the `Exceptions` collection supports many entries.  
- **Ondersteunde .NET-versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is een kalenderuitzondering?

Een **kalenderuitzondering** vertegenwoordigt een afwijking van de reguliere werkagenda—beschouw het als een regel die zegt “op deze data zijn de werktijden anders of er zijn geen werktijden”. In Aspose.Tasks kan elke uitzondering eigen werktijden, herhalingspatroon en vlaggen hebben die aangeven of de dag een werkdag is.

## Waarom kalenderuitzonderingen beheren in ASP.NET Calendar Scheduling?

- **Nauwkeurige tijdlijnen:** Projects automatically respect holidays and special closures, preventing unrealistic deadlines.
- **Flexibiliteit:** You can define daily, weekly, monthly, or yearly patterns, matching real‑world business calendars.
- **Automatisering:** Programmatically checking an exception date lets you build dynamic scheduling logic in ASP.NET applications.

## Vereisten

- Basiskennis van C# programmeren.  
- Visual Studio (een recente versie).  
- Aspose.Tasks for .NET bibliotheek toegevoegd aan je project (via NuGet of handmatige referentie).  

## Namespaces importeren

Eerst importeer je de namespaces die je nodig hebt:

```csharp
using Aspose.Tasks;
using System;
```

## Stap 1: Kalenderuitzondering verwijderen

Het verwijderen van een ongewenste uitzondering is eenvoudig. De volgende code laadt een project, selecteert de eerste kalender, toont basisinformatie, verwijdert de eerste uitzondering, en toont vervolgens het bijgewerkte aantal.

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

> **Pro tip:** Controleer altijd of de uitzonderingsindex bestaat voordat je `Delete()` aanroept om `IndexOutOfRangeException` te voorkomen.

## Stap 2: Werkuren van een kalenderuitzondering ophalen

Als je de werkuren die voor een uitzondering zijn gedefinieerd wilt inspecteren, gebruik dan `GetWorkingTime()`. Dit voorbeeld toont ook hoe je **check exception date** kunt gebruiken met `CheckException`.

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

## Stap 3: Kalenderuitzonderingen definiëren

Hieronder staat een volledige walkthrough die laat zien hoe je kalenderuitzonderingen **toevoegt**, **controleert**, en **verwijdert**. Let op het gebruik van `CheckException` om **check exception date** voor een specifiek moment te controleren.

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

## Veelvoorkomende problemen & tips

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`IndexOutOfRangeException` when deleting** | Proberen een uitzondering te verwijderen die niet bestaat. | Controleer `calendar.Exceptions.Count` > index voordat je `Delete()` aanroept. |
| **Incorrect working times** | `DayWorking` of `WorkingTimes` niet correct instellen. | Gebruik `exception.WorkingTimes.Add(new WorkingTime(...))` om expliciete periodes te definiëren. |
| **Exception not recognized** | `CheckException` retourneert `false` omdat de datum buiten het gedefinieerde bereik valt. | Controleer `FromDate`/`ToDate` en het `Type` (Daily, Weekly, etc.) dubbel. |

## Veelgestelde vragen

**Q: Kan ik meerdere uitzonderingen aan één kalender toevoegen?**  
A: Ja, je kunt zoveel uitzonderingen toevoegen als nodig is om feestdagen, onderhoudsvensters of andere speciale planningsregels te vertegenwoordigen.

**Q: Hoe kan ik **check exception date** voor een specifieke dag?**  
A: Gebruik de `CheckException(DateTime date)`-methode op een `CalendarException`-instance. Deze retourneert `true` als de opgegeven datum binnen het uitzonderingsbereik valt.

**Q: Is het mogelijk om een bestaande uitzondering uit een kalender te verwijderen?**  
A: Absoluut. Toegang tot de `Exceptions`-collectie en roep `Remove()` aan of gebruik `Delete()` op het specifieke `CalendarException`-object.

**Q: Welke soorten kalenderuitzonderingen worden ondersteund?**  
A: Aspose.Tasks ondersteunt Daily, Weekly, Monthly en Yearly uitzonderingssoorten, waardoor je flexibiliteit hebt om bijna elk herhalingspatroon te modelleren.

**Q: Kan ik werkuren aanpassen voor specifieke uitzonderingsdatums?**  
A: Ja. Na het aanmaken van een uitzondering vul je de `WorkingTimes`-collectie met `WorkingTime`-objecten die de start- en eindtijden voor die dag definiëren.

## Conclusie

We hebben de volledige levenscyclus van **delete calendar exception**-operaties doorlopen, van het inspecteren van bestaande uitzonderingen tot het toevoegen van nieuwe en het controleren van datums. Het beheersen van deze technieken zorgt ervoor dat je projectschema's rekening houden met de echte wereld kalenders, waardoor je ASP.NET calendar scheduling-implementaties robuust en betrouwbaar zijn.

---

**Laatst bijgewerkt:** 2026-04-13  
**Getest met:** Aspose.Tasks for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}