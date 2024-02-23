---
title: Dagelijkse werkherhaling in Aspose.Tasks
linktitle: Dagelijkse werkherhaling in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u dagelijks terugkerende taken in Microsoft Project-bestanden kunt maken met Aspose.Tasks voor .NET. Verhoog moeiteloos de productiviteit en organisatie.
type: docs
weight: 26
url: /nl/net/calendar-scheduling/daily-work-repetition/
---
## Invoering

Aspose.Tasks voor .NET is een krachtige bibliotheek waarmee ontwikkelaars Microsoft Project-bestanden gemakkelijk kunnen manipuleren. Een van de talloze functies is de mogelijkheid om terugkerende taken efficiënt af te handelen. In deze zelfstudie gaan we dieper in op de functionaliteit Dagelijkse werkherhaling, waarmee taken kunnen worden gemaakt die dagelijks binnen een project worden herhaald.

## Vereisten

Voordat u in deze zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:

- Basiskennis van C# en .NET framework.
- Visual Studio is op uw systeem geïnstalleerd.
-  Aspose.Tasks voor .NET-bibliotheek. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/net/).
- Bekendheid met Microsoft Project-bestanden (.mpp).

## Naamruimten importeren

Voordat we beginnen, zorg ervoor dat u de benodigde naamruimten importeert:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Laten we het gegeven voorbeeld in meerdere stappen opsplitsen:

## Stap 1: Laad het projectbestand

 Laad eerst het projectbestand met behulp van de`Project` klas:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Stap 2: Definieer terugkerende taakparameters

Definieer de parameters voor de terugkerende taak:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Stap 3: Stel de startdatum van de kalender en de taak in

Stel de kalender en startdatum voor de taak in:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u Aspose.Tasks voor .NET kunt gebruiken om terugkerende taken te maken met dagelijkse werkherhaling. Door deze stappen te volgen, kunt u de taken binnen uw projecten efficiënt beheren, waardoor een soepele workflow en organisatie wordt gegarandeerd.

## Veelgestelde vragen

### V1: Kan ik het herhalingspatroon verder aanpassen?

A1: Ja, u kunt parameters zoals de startdatum, het aantal voorvallen en het herhalingsinterval aanpassen om het herhalingspatroon aan uw vereisten aan te passen.

### V2: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project?

A2: Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project, waardoor compatibiliteit en naadloze integratie worden gegarandeerd.

### Vraag 3: Hoe kan ik omgaan met uitzonderingen of wijzigingen in terugkerende taken?

A3: Aspose.Tasks biedt robuuste functionaliteit voor het beheren van uitzonderingen en wijzigingen binnen terugkerende taken, waardoor flexibiliteit en maatwerk mogelijk zijn.

### Vraag 4: Kan ik het project naar verschillende formaten exporteren?

A4: Absoluut, Aspose.Tasks biedt ondersteuning voor het exporteren van projecten naar verschillende formaten, waaronder PDF, HTML, XML en meer, waardoor delen en samenwerken gemakkelijk wordt gemaakt.

### V5: Biedt Aspose.Tasks technische ondersteuning?

A5: Ja, Aspose.Tasks biedt uitgebreide technische ondersteuning via het forum, waar u hulp kunt zoeken, ervaringen kunt delen en met medegebruikers kunt communiceren.