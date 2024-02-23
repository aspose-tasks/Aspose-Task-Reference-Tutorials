---
title: Boomalgoritme gebruiken in Aspose.Tasks
linktitle: Boomalgoritme gebruiken in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u taakhiërarchieën in uw .NET-projecten effectief kunt manipuleren met behulp van het Tree Algorithm van Aspose.Tasks.
type: docs
weight: 13
url: /nl/net/advanced-concepts/tree-algorithm/
---
## Invoering

Aspose.Tasks voor .NET biedt krachtige functionaliteiten voor het werken met projectmanagementtaken, bronnen en planningen. Eén zo'n functie is het Tree Algorithm, waarmee gebruikers taakhiërarchieën efficiënt kunnen manipuleren. In deze zelfstudie onderzoeken we hoe u het Tree-algoritme in Aspose.Tasks voor .NET kunt gebruiken om algemeen werk te verzamelen en werkwaarden binnen een project bij te werken.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor .NET: Download en installeer Aspose.Tasks voor .NET van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is vereist om de voorbeelden te kunnen volgen.

## Naamruimten importeren

Importeer in uw C#-project de benodigde naamruimten om met Aspose.Tasks-functionaliteiten te werken:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Laten we nu elk voorbeeld in meerdere stappen opsplitsen:

## Stap 1: Projectbestand laden

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Laad het projectbestand in het geheugen met behulp van de`Project` klas.

## Stap 2: De taakhiërarchie definiëren

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definieer de takenhiërarchie door bovenliggende en onderliggende taken toe te voegen.

## Stap 3: Stel taakeigenschappen in

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Stel eigenschappen zoals startdatum, duur en einddatum voor taken in.

## Stap 4: Bron toevoegen

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Voeg resources toe aan het project en wijs ze indien nodig toe aan taken.

## Stap 5: Pas het boomalgoritme toe

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Initialiseer de`WorkAccumulator` klasse en pas het Boomalgoritme toe om gemeenschappelijk werk te verzamelen.

## Stap 6: Taakwerk bijwerken

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Update de werkwaarden voor taken op basis van de verzamelde informatie.

## Conclusie

In deze zelfstudie hebben we geleerd hoe we het Tree-algoritme in Aspose.Tasks voor .NET kunnen gebruiken om taakhiërarchieën effectief te manipuleren. Door de stapsgewijze handleiding te volgen, kunt u taken en middelen binnen uw projecten efficiënt beheren.

## Veelgestelde vragen

### V1: Wat is Aspose.Tasks voor .NET?

A1: Aspose.Tasks voor .NET is een krachtige API waarmee ontwikkelaars Microsoft Project-bestanden programmatisch kunnen manipuleren met behulp van C#.

### V2: Kan ik een gratis proefversie van Aspose.Tasks voor .NET downloaden?

 A2: Ja, u kunt een gratis proefversie van Aspose.Tasks voor .NET downloaden van[hier](https://releases.aspose.com/).

### V3: Waar kan ik documentatie vinden voor Aspose.Tasks voor .NET?

 A3: U kunt de documentatie voor Aspose.Tasks voor .NET vinden[hier](https://reference.aspose.com/tasks/net/).

### V4: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?

 A4: Voor ondersteuning met betrekking tot Aspose.Tasks voor .NET kunt u terecht op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).

### Vraag 5: Is er een tijdelijke licentie beschikbaar voor testdoeleinden?

 A5: Ja, u kunt een tijdelijke licentie voor testdoeleinden verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).