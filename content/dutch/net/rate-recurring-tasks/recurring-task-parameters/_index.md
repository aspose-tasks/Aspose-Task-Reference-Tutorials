---
title: Parameters voor terugkerende taken instellen in Aspose.Tasks
linktitle: Parameters voor terugkerende taken instellen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u terugkerende taakparameters instelt in Microsoft Project met behulp van Aspose.Tasks voor .NET. Uitgebreide tutorial met stapsgewijze handleiding.
type: docs
weight: 14
url: /nl/net/rate-recurring-tasks/recurring-task-parameters/
---
## Invoering
In deze zelfstudie begeleiden we u bij het instellen van terugkerende taakparameters van Microsoft Project met behulp van Aspose.Tasks voor .NET.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1. Basiskennis van de programmeertaal C#.
2. Visual Studio of een andere C# IDE geïnstalleerd.
3. Aspose.Tasks voor de .NET-bibliotheek geïnstalleerd en waarnaar wordt verwezen in uw project.

## Naamruimten importeren
Ten eerste moet u de benodigde naamruimten in uw C#-code importeren:
```csharp
using Aspose.Tasks;
using System;

```
## Stap 1: Definieer de documentmap
```csharp
String DataDir = "Your Document Directory";
```
 vervangen`"Your Document Directory"` met het pad naar uw documentmap.
## Stap 2: Laad het projectbestand
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Deze coderegel laadt het Microsoft Project-bestand in het`project` variabelen.
## Stap 3: Definieer terugkerende taakparameters
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Hier definieert u de parameters voor de terugkerende taak, zoals taaknaam, duur, herhalingspatroon, herhalingsbereik en of de resourcekalender moet worden genegeerd.
## Stap 4: Stel de kalender in voor terugkerende taken
```csharp
parameters.SetCalendar(project, "Standard");
```
Met deze stap wordt de kalender voor de terugkerende taak ingesteld. In dit voorbeeld wordt de kalender ingesteld op "Standaard".
## Stap 5: parameters toevoegen aan project
```csharp
project.RootTask.Children.Add(parameters);
```
Voeg ten slotte de parameters toe aan de hoofdtaak van het project.

## Conclusie
In deze zelfstudie hebben we gedemonstreerd hoe u terugkerende taakparameters van Microsoft Project kunt instellen met behulp van Aspose.Tasks voor .NET. Door deze stappen te volgen, kunt u terugkerende taken in uw projecten efficiënt beheren.
## Veelgestelde vragen
### Kan ik het herhalingspatroon verder aanpassen?
Ja, Aspose.Tasks biedt verschillende herhalingspatronen en opties die u kunt aanpassen aan uw projectvereisten.
### Is er een proefversie beschikbaar voordat u deze aanschaft?
 Ja, u kunt een gratis proefversie downloaden via Aspose.Tasks[website](https://purchase.aspose.com/buy) om de kenmerken van de bibliotheek te evalueren.
### Ondersteunt Aspose.Tasks andere projectbestandsindelingen?
Ja, Aspose.Tasks ondersteunt verschillende projectbestandsindelingen, waaronder MPP, XML, XLSX en meer.
### Kan ik ondersteuning krijgen als ik problemen ondervind tijdens de implementatie?
Ja, u kunt het Aspose.Tasks-forum bezoeken voor hulp van de community of contact opnemen met de ondersteuning voor directe hulp.
### Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?
 Een tijdelijke licentie kunt u verkrijgen bij de[website](https://purchase.aspose.com/temporary-license/) voor testdoeleinden.