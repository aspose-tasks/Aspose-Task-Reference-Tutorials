---
title: Herhaling per maand weekdag in Aspose.Tasks
linktitle: Herhaling per maand weekdag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u herhalingen per maand, week en dag in Aspose.Tasks voor .NET instelt om terugkerende taken efficiënt te automatiseren.
type: docs
weight: 26
url: /nl/net/advanced-features/repetition-by-month-week-day/
---
## Invoering

Op het gebied van softwareontwikkeling, vooral bij projectmanagementtoepassingen, is het vermogen om terugkerende taken efficiënt af te handelen van het allergrootste belang. Aspose.Tasks voor .NET is een krachtige bibliotheek die is ontworpen om het maken en beheren van projecttaken, inclusief terugkerende taken, te stroomlijnen. Eén van deze functionaliteiten van Aspose.Tasks is de mogelijkheid om herhalingen per maand, week en dag in te stellen, zodat taken volgens schema worden uitgevoerd zonder handmatige tussenkomst.

## Vereisten

Voordat u zich verdiept in de fijne kneepjes van het instellen van herhalingen per maand, week en dag met behulp van Aspose.Tasks voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Basiskennis van C#: Bekendheid met de programmeertaal C# is essentieel om de gegeven codevoorbeelden te begrijpen en te implementeren.
   
2.  Installatie van Aspose.Tasks voor .NET: Zorg ervoor dat u de Aspose.Tasks voor .NET-bibliotheek hebt gedownload en geïnstalleerd. U kunt de bibliotheek verkrijgen bij de[downloadpagina](https://releases.aspose.com/tasks/net/).

3. Toegang tot een .mpp-projectbestand: Zorg ervoor dat u een Microsoft Project-bestand (.mpp) bij de hand hebt, aangezien we dit zullen gebruiken om de implementatie van herhalingen per maand, week en dag te demonstreren.

## Naamruimten importeren

Om aan de slag te gaan met het gebruik van Aspose.Tasks voor .NET in uw C#-toepassing, moet u de benodigde naamruimten importeren. Hier ziet u hoe u het kunt doen:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Laten we het meegeleverde codefragment opsplitsen in meerdere stappen om elk onderdeel grondig te begrijpen.

## Stap 1: Projectbestand laden

```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Deze stap omvat het maken van een nieuw exemplaar van de`Project` class en het laden van een bestaand Microsoft Project-bestand (`Project1.mpp`) uit de opgegeven map.

## Stap 2: Definieer terugkerende taakparameters

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

In deze stap definiëren we de parameters voor een terugkerende taak. We specificeren de taaknaam, de duur, het herhalingspatroon (maandelijks) en het herhalingsbereik (eindigt op een specifieke datum).

## Stap 3: Terugkerende taak toevoegen aan project

```csharp
project.RootTask.Children.Add(parameters);
```

Hier voegen we de gedefinieerde terugkerende taakparameters toe aan de hoofdtaak van het project.

## Stap 4: Projectbestand opslaan

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Ten slotte slaan we het gewijzigde projectbestand op met de toegevoegde terugkerende taak.

## Conclusie

Kortom, het instellen van herhalingen per maand, week en dag in Aspose.Tasks voor .NET is een eenvoudig proces waarmee ontwikkelaars het beheer van terugkerende taken binnen hun projecten efficiënt kunnen automatiseren. Door de stappen in deze tutorial te volgen, kunt u deze functionaliteit naadloos integreren in uw C#-applicaties, waardoor u tijd en moeite bespaart bij projectbeheer.

## Veelgestelde vragen

###Q1: Kan ik het herhalingspatroon aanpassen naast de gegeven voorbeelden?

A1: Ja, Aspose.Tasks voor .NET biedt uitgebreide aanpassingsopties voor herhalingspatronen, zodat u deze kunt afstemmen op uw specifieke vereisten.

###Q2: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?

 A2: Ja, u kunt een gratis proefversie van Aspose.Tasks voor .NET verkrijgen via de[releases pagina](https://releases.aspose.com/).

###Q3: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?

 A3: U kunt hulp zoeken en in contact komen met de gemeenschap op de site[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).

###Q4: Zijn er tijdelijke licenties beschikbaar voor Aspose.Tasks voor .NET?

 A4: Ja, u kunt tijdelijke licenties verkrijgen bij de[aankooppagina](https://purchase.aspose.com/temporary-license/) voor test- en evaluatiedoeleinden.

###V5: Waar kan ik uitgebreide documentatie vinden voor Aspose.Tasks voor .NET?

 A5: U kunt naar de details verwijzen[documentatie](https://reference.aspose.com/tasks/net/) beschikbaar op de Aspose-website voor uitgebreide richtlijnen over het gebruik van de bibliotheek.