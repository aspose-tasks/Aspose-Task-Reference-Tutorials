---
title: Herhaling per maanddag in Aspose.Tasks
linktitle: Herhaling per maanddag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u terugkerende taken in .NET-projecten beheert met Aspose.Tasks. Stapsgewijze handleiding voor het verwerken van herhalingen per maanddag.
weight: 25
url: /nl/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Herhaling per maanddag in Aspose.Tasks

## Invoering

Op het gebied van .NET-ontwikkeling is Aspose.Tasks een krachtig hulpmiddel voor het beheren van projecttaken en planningen. Het biedt een overvloed aan functionaliteiten om de workflows voor projectbeheer te stroomlijnen, inclusief het afhandelen van terugkerende taken. Herhaling per dag van de maand is een veel voorkomende vereiste bij projectplanning, en Aspose.Tasks biedt robuuste ondersteuning voor dit scenario.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Basiskennis van C#: Bekendheid met de programmeertaal C# is noodzakelijk om de concepten te begrijpen die in deze tutorial worden besproken.
2. Installatie van Aspose.Tasks voor .NET: Zorg ervoor dat u Aspose.Tasks voor .NET hebt geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).
3. Integrated Development Environment (IDE): Zorg ervoor dat een IDE zoals Visual Studio op uw systeem is geïnstalleerd voor codeergemak.

## Naamruimten importeren

Importeer in uw C#-project de benodigde naamruimten om toegang te krijgen tot de Aspose.Tasks-functionaliteiten:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Laten we het meegeleverde codevoorbeeld opsplitsen in een stapsgewijze handleiding:

## Stap 1: Projectbestand laden

```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Deze coderegel initialiseert een nieuw exemplaar van de`Project` class, waarbij het projectbestand met de naam "Project1.mpp" wordt geladen.

## Stap 2: Definieer terugkerende taakparameters

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

In deze sectie worden de parameters voor de terugkerende taak gedefinieerd, inclusief de naam, duur, herhalingspatroon en herhalingsbereik.

## Stap 3: Taak toevoegen aan project

```csharp
project.RootTask.Children.Add(parameters);
```

Hier voegen we de terugkerende taakparameters toe aan het project.

## Stap 4: Projectbestand opslaan

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Tenslotte wordt het gewijzigde project opgeslagen met de toegevoegde terugkerende taak.

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u met herhaling per maanddag kunt omgaan in Aspose.Tasks voor .NET. Door de aangegeven stappen te volgen, kunt u terugkerende taken binnen uw projectplanningen efficiënt beheren.

## Veelgestelde vragen

### V1: Is Aspose.Tasks compatibel met alle versies van .NET?

A1: Aspose.Tasks ondersteunt verschillende versies van het .NET-framework, waardoor compatibiliteit tussen verschillende omgevingen wordt gegarandeerd.

### Vraag 2: Kan ik het herhalingspatroon verder aanpassen?

A2: Ja, Aspose.Tasks biedt uitgebreide aanpassingsopties voor het definiëren van herhalingspatronen op basis van specifieke projectvereisten.

### V3: Biedt Aspose.Tasks ondersteuning voor andere projectbeheerfunctionaliteiten?

A3: Absoluut, Aspose.Tasks biedt een breed scala aan functies voor projectbeheer, waaronder het volgen van taken, het toewijzen van middelen en het genereren van Gantt-diagrammen.

### V4: Is er een proefversie beschikbaar voor Aspose.Tasks?

 A4: Ja, u kunt profiteren van een gratis proefperiode van[hier](https://releases.aspose.com/) om de mogelijkheden van Aspose.Tasks te verkennen voordat u een aankoopbeslissing neemt.

### Vraag 5: Waar kan ik hulp zoeken als ik problemen tegenkom of vragen heb?

 A5: U kunt de bezoeken[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) om steun te zoeken bij de gemeenschap of het Aspose-team.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
