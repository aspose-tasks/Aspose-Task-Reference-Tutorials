---
title: Agenda-uitzonderingen afhandelen in Aspose.Tasks
linktitle: Agenda-uitzonderingen afhandelen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u agenda-uitzonderingen beheert in Aspose.Tasks voor .NET met stapsgewijze zelfstudies en voorbeelden.
type: docs
weight: 12
url: /nl/net/calendar-scheduling/calendar-exceptions/
---
## Invoering

In deze zelfstudie onderzoeken we hoe u agenda-uitzonderingen in Aspose.Tasks kunt beheren met behulp van het .NET-framework. Kalenderuitzonderingen stellen ons in staat speciale datums of perioden in een projectkalender te definiëren waarin het reguliere werkschema wordt gewijzigd, zoals vakanties of tijdelijke sluitingen. We bespreken stap voor stap verschillende methoden om agenda-uitzonderingen af te handelen, met behulp van Aspose.Tasks voor .NET.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal C#.
- Visual Studio is op uw systeem geïnstalleerd.
- Aspose.Tasks voor .NET-bibliotheek toegevoegd aan uw project.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten voor ons project importeren:

```csharp
using Aspose.Tasks;
using System;


```

## Stap 1: Een agenda-uitzondering verwijderen

Volg deze stappen om een agenda-uitzondering te verwijderen:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Agenda-informatie weergeven
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Verwijder de eerste uitzondering
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Stap 2: Werktijd verkrijgen van een kalenderuitzondering

Volg deze stappen om de werktijd van een kalenderuitzondering op te halen:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Agenda- en uitzonderingsinformatie weergeven
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Krijg werktijd en geef details weer
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Stap 3: Agenda-uitzonderingen definiëren

Volg deze stappen om agenda-uitzonderingen toe te voegen of te verwijderen:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Maak een nieuwe agenda-uitzondering
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Uitzonderingsdetails instellen
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Controleer of een datum een uitzondering is
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Voeg de uitzondering toe aan de kalender
    calendar.Exceptions.Add(exception);

    // Verwijder een uitzondering als deze bestaat
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Voeg een nieuwe uitzondering toe
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Uitzonderingen bij het afdrukken
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Conclusie

In dit artikel hebben we verschillende aspecten van het omgaan met agenda-uitzonderingen in Aspose.Tasks voor .NET besproken. Door de aangegeven stappen te volgen, kunt u uitzonderingen in uw projectplanningen effectief beheren, waardoor u verzekerd bent van een nauwkeurige weergave van werktijden en speciale gebeurtenissen.

## Veelgestelde vragen

### V1: Kan ik meerdere uitzonderingen toevoegen aan één kalender?

A1: Ja, u kunt meerdere uitzonderingen aan een kalender toevoegen om verschillende speciale datums of periodes mogelijk te maken.

### Vraag 2: Hoe kan ik controleren of een specifieke datum een uitzondering is?

 A2: U kunt de`CheckException()` methode om te verifiëren of een bepaalde datum onder een uitzondering valt.

### Vraag 3: Is het mogelijk om een bestaande uitzondering uit een kalender te verwijderen?

 A3: Ja, u kunt uitzonderingen verwijderen door naar het bestand te gaan`Exceptions` verzameling van de kalender en het gebruik van de`Remove()` methode.

### V4: Welke typen agenda-uitzonderingen worden ondersteund?

A4: Aspose.Tasks ondersteunt verschillende soorten uitzonderingen, waaronder dagelijkse, wekelijkse, maandelijkse en jaarlijkse uitzonderingen, waardoor flexibiliteit wordt geboden bij het definiëren van uitzonderingsregels.

### V5: Kan ik de werktijden aanpassen voor specifieke uitzonderingsdata?

A5: Ja, u kunt aangepaste werktijden definiëren voor individuele uitzonderingsdata met behulp van de juiste methoden van Aspose.Tasks.