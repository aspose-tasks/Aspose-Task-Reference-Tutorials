---
title: Verzameling van dagtypes beheren in Aspose.Tasks
linktitle: Verzameling van dagtypes beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u dagtypecollecties efficiënt beheert in Aspose.Tasks voor .NET. Creëer, wijzig en manipuleer eenvoudig agenda-uitzonderingen.
type: docs
weight: 28
url: /nl/net/calendar-scheduling/day-type-collection/
---
## Invoering

 Aspose.Tasks voor .NET biedt robuuste functionaliteit voor het beheren van dagtypeverzamelingen, cruciaal voor het definiëren van wekelijkse kalenderuitzonderingen in projectbeheertoepassingen. In deze zelfstudie onderzoeken we hoe u de`DayTypeCollection` klas efficiënt. 

## Vereisten

Voordat we verder gaan met de zelfstudie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: Bekendheid met de programmeertaal C# en .NET framework-concepten.

## Naamruimten importeren

Om aan de slag te gaan, moet u de benodigde naamruimten in uw C#-project importeren:

```csharp
using Aspose.Tasks;
using System;


```

Laten we het gegeven voorbeeld nu in meerdere stappen opsplitsen:

## Stap 1: Project laden en toegang krijgen tot de agenda

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Met deze stap wordt een nieuw projectexemplaar geïnitialiseerd en wordt de kalender opgehaald op basis van de UID.

## Stap 2: Herhaal de agenda-uitzonderingen

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Hier doorlopen we elke kalenderuitzondering en drukken de naam en de bijbehorende dagtypen af.

## Stap 3: Wijzig agenda-uitzonderingen

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Deze stap laat zien hoe u agenda-uitzonderingen kunt wijzigen door dagtypen toe te voegen, te verwijderen of bij te werken.

## Stap 4: Nieuwe agenda-uitzonderingen maken en manipuleren

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

In deze laatste stap maken we nieuwe kalenderuitzonderingen en manipuleren deze door dagtypen toe te voegen en te kopiëren.

## Conclusie

 Kortom, het beheren van dagtypeverzamelingen in Aspose.Tasks voor .NET is essentieel voor het definiëren en wijzigen van wekelijkse kalenderuitzonderingen in projectbeheertoepassingen. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u effectief gebruik maken van de`DayTypeCollection` klasse om verschillende agendabewerkingen af te handelen.

## Veelgestelde vragen

### Vraag 1: Kan Aspose.Tasks voor .NET worden gebruikt om programmatisch Gantt-diagrammen te maken?

A1: Ja, Aspose.Tasks voor .NET biedt API's voor het maken en manipuleren van Gantt-diagrammen in .NET-toepassingen.

### V2: Is Aspose.Tasks voor .NET compatibel met zowel .NET Core als .NET Framework?

A2: Ja, Aspose.Tasks voor .NET ondersteunt zowel .NET Core als .NET Framework.

### V3: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?

 A3: U kunt ondersteuning krijgen door naar de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) waar u vragen kunt stellen en kunt communiceren met andere gebruikers.

### V4: Biedt Aspose.Tasks voor .NET een gratis proefperiode?

 A4: Ja, u kunt een gratis proefversie van Aspose.Tasks voor .NET krijgen van[hier](https://releases.aspose.com/).

### V5: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks voor .NET?

 A5: Ja, tijdelijke licenties zijn te koop bij de[Aspose-website](https://purchase.aspose.com/temporary-license/).