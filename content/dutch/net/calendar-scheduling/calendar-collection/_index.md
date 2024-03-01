---
title: Agendaverzameling beheren in Aspose.Tasks
linktitle: Agendaverzameling beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u agendaverzamelingen efficiënt beheert in Aspose.Tasks voor .NET. Creëer, wijzig en manipuleer kalenders met gemak.
type: docs
weight: 11
url: /nl/net/calendar-scheduling/calendar-collection/
---
## Invoering

In deze zelfstudie onderzoeken we hoe u agendaverzamelingen beheert in Aspose.Tasks voor .NET. Kalenders spelen een cruciale rol bij projectbeheer, waarbij werkdagen, feestdagen en uitzonderingen worden gedefinieerd. Aspose.Tasks biedt robuuste functionaliteit om kalenders binnen uw projecten te manipuleren.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1. Visual Studio: Installeer Visual Studio of een andere compatibele IDE voor .NET-ontwikkeling.
2.  Aspose.Tasks voor .NET: Download en installeer Aspose.Tasks voor .NET van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is een voordeel.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren om met Aspose.Tasks te werken:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Een nieuwe kalender maken

###  Stap 1: Initialiseer een nieuw`Project` object.
```csharp
var project = new Project();
```

### Stap 2: Voeg kalenders toe aan de kalendercollectie van het project.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Stap 3: Blader door de kalenders en geef hun namen weer.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Een kalender vervangen door een nieuwe kalender

### Stap 1: Laad een bestaand project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Stap 2: Verwijder de bestaande agenda (indien aanwezig).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Stap 3: Voeg een nieuwe kalender toe.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Agenda ophalen op naam of ID

### Stap 1: Laad het project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Stap 2: Agenda's ophalen op naam of UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Stap 3: Geef agendagegevens weer.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Itereren over kalenders

### Stap 1: Laad het project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Stap 2: Haal het aantal kalenders op.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Stap 3: Herhaal de agendaverzameling en geef namen weer.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Een standaardkalender maken

### Stap 1: Initialiseer een nieuw project.
```csharp
var project = new Project();
```

### Stap 2: Definieer een nieuwe kalender en maak deze standaard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Stap 3: Sla het project op.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Conclusie

Het beheren van agendaverzamelingen in Aspose.Tasks voor .NET is essentieel voor effectief projectbeheer. Met de meegeleverde functionaliteiten kunt u efficiënt kalenders maken, wijzigen en manipuleren volgens uw projectvereisten.

## Veelgestelde vragen

### V1: Kan ik aangepaste werkdagen aanmaken in Aspose.Tasks?

A1: Ja, u kunt aangepaste werkdagen maken door uitzonderingen aan kalenders toe te voegen.

### Vraag 2: Is het mogelijk om kalenders uit Microsoft Project-bestanden te importeren?

A2: Absoluut, Aspose.Tasks ondersteunt het importeren van agenda's uit Microsoft Project-bestanden.

### Q3: Hoe kan ik een specifieke kalender uit een project verwijderen?

 A3: U kunt een kalender verwijderen door deze uit de collectie te halen en vervolgens te bellen naar de`Remove` methode.

### V4: Ondersteunt Aspose.Tasks het exporteren van agenda's naar verschillende formaten?

A4: Ja, Aspose.Tasks maakt het exporteren van kalenders naar verschillende formaten mogelijk, zoals XML, MPP, enz.

### Vraag 5: Kan ik de werktijden voor specifieke dagen in een kalender aanpassen?

A5: Natuurlijk kunt u werktijden voor afzonderlijke dagen definiëren met behulp van uitzonderingen in de kalender.