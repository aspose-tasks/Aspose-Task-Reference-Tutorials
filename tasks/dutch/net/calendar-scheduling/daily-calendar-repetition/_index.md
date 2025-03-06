---
title: Dagelijkse kalenderherhaling in Aspose.Tasks
linktitle: Dagelijkse kalenderherhaling in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u terugkerende taken kunt maken met dagelijkse agendaherhalingen in Aspose.Tasks voor .NET. Verbeter moeiteloos de efficiëntie van projectbeheer.
weight: 25
url: /nl/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dagelijkse kalenderherhaling in Aspose.Tasks

## Invoering

 Aspose.Tasks voor .NET biedt een krachtige set tools voor het programmatisch beheren van taken en projecten. Een van de opvallende kenmerken is de mogelijkheid om dagelijkse agendaherhalingen efficiënt af te handelen. In deze zelfstudie onderzoeken we hoe u de`DailyCalendarRepetition` klas samen met andere relevante klassen om terugkerende taken te creëren met dagelijkse herhalingen op basis van een gespecificeerde kalender.

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende hebt ingesteld:

1.  Installatie: Zorg ervoor dat Aspose.Tasks voor .NET is geïnstalleerd. Als dit niet het geval is, kunt u deze downloaden van[hier](https://releases.aspose.com/tasks/net/).

2. Naamruimte importeren: importeer de benodigde naamruimten in uw project:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Stap 1: Initialiseer het project

Ten eerste moeten we een bestaand project laden of een nieuw project maken om mee te werken:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Stap 2: Definieer de kalender

Vervolgens maken we een kalender met een duur van 24 uur en koppelen deze aan het project:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Stap 3: Stel parameters voor terugkerende taken in

Laten we nu de parameters voor onze terugkerende taak instellen. We definiëren de naam, duur, herhalingspatroon en bereik:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Stap 4: Stel de kalender in voor taken

Koppel de gedefinieerde kalender aan de taak:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Stap 5: Taak toevoegen aan project

Voeg de taak met gedefinieerde parameters toe aan het project:

```csharp
project.RootTask.Children.Add(parameters);
```

## Stap 6: Sla het project op

Sla ten slotte het project op met de toegevoegde terugkerende taak:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Nu hebt u met succes een project gemaakt met een terugkerende taak die dagelijks moet worden herhaald op basis van een 24-uurskalender met behulp van Aspose.Tasks voor .NET!

## Conclusie

In deze zelfstudie hebben we gedemonstreerd hoe u Aspose.Tasks voor .NET kunt gebruiken om dagelijkse agendaherhalingen efficiënt af te handelen. Door deze stappen te volgen, kunt u terugkerende taken naadloos in uw projecten integreren, waardoor de productiviteit en organisatie worden verbeterd.

## Veelgestelde vragen

### Vraag 1: Kan ik de duur van elke herhaling aanpassen?

A1: Ja, u kunt de duur van elke herhaling aanpassen aan uw wensen door de parameters in de code te wijzigen.

### Vraag 2: Is het mogelijk om verschillende kalenders in te stellen voor verschillende taken binnen hetzelfde project?

A2: Absoluut, met Aspose.Tasks kunt u specifieke agenda's aan individuele taken toewijzen, wat flexibiliteit bij de planning biedt.

### Vraag 3: Ondersteunt Aspose.Tasks andere herhalingspatronen dan dagelijks?

A3: Ja, Aspose.Tasks biedt een breed scala aan herhalingspatronen, zoals wekelijks, maandelijks, jaarlijks, enz., om tegemoet te komen aan diverse projectbehoeften.

### V4: Kan ik de terugkerende taken visualiseren die zijn gemaakt met Aspose.Tasks?

A4: Zeker, Aspose.Tasks biedt visualisatie-opties waarmee u terugkerende taken effectief kunt analyseren en volgen.

### V5: Is er een proefversie beschikbaar voor Aspose.Tasks?

 A5: Ja, u kunt profiteren van een gratis proefperiode van Aspose.Tasks vanaf[hier](https://releases.aspose.com/) om de functies ervan te verkennen voordat u een aankoop doet.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
