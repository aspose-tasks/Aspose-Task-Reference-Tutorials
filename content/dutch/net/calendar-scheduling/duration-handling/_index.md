---
title: Duurafhandeling in Aspose.Tasks
linktitle: Duurafhandeling in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u effectief met tijdsduur omgaat in Aspose.Tasks voor .NET met stapsgewijze zelfstudies.
type: docs
weight: 30
url: /nl/net/calendar-scheduling/duration-handling/
---
## Invoering

Effectief omgaan met tijdsduur is cruciaal bij projectmanagementtoepassingen. Aspose.Tasks voor .NET biedt robuuste functionaliteit voor het efficiënt beheren van de duur. In deze zelfstudie verkennen we verschillende aspecten van de duurafhandeling met Aspose.Tasks voor .NET.

## Vereisten

Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:

1. Basiskennis van C#: Bekendheid met de programmeertaal C# is essentieel om de voorbeelden te begrijpen en te implementeren.
2. Visual Studio: Installeer Visual Studio IDE om .NET-applicaties te maken en uit te voeren.
3.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren om de Aspose.Tasks-functionaliteiten te gebruiken:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Laten we elk voorbeeld opsplitsen in meerdere stappen in een stapsgewijze handleiding:

## Duur van taken bijwerken

### Stap 1: Projectbestand laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Stap 2: Krijg taak en duur

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Stap 3: Updateduur

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Stap 4: Geef de bijgewerkte duur weer

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Duur van taken aftrekken

### Stap 1: Projectbestand laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Stap 2: Krijg taak en duur

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Stap 3: Trek de duur af

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Stap 4: Geef de bijgewerkte duur weer

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Duur converteren naar TimeSpan

### Stap 1: Projectbestand laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Stap 2: Krijg taak en duur

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Stap 3: Converteer duur naar TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Duur naar tekenreeks converteren

### Stap 1: Projectbestand laden

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Stap 2: Krijg taak en duur

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Stap 3: Converteer duur naar tekenreeks

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Conclusie

In deze zelfstudie hebben we verschillende aspecten van de duurafhandeling in Aspose.Tasks voor .NET besproken. Het begrijpen en effectief beheren van de looptijden is essentieel voor succesvol projectmanagement. Aspose.Tasks biedt uitgebreide functionaliteiten om duurbeheertaken in uw .NET-applicaties te vereenvoudigen.

## Veelgestelde vragen

### V1: Wat is Aspose.Tasks voor .NET?

A1: Aspose.Tasks voor .NET is een krachtige bibliotheek voor het werken met Microsoft Project-bestanden in .NET-toepassingen.

### Vraag 2: Kan Aspose.Tasks complexe projectstructuren aan?

A2: Ja, Aspose.Tasks kan met gemak complexe projectstructuren aan, en biedt uitgebreide API's voor manipulatie.

### V3: Is Aspose.Tasks voor .NET compatibel met .NET Core?

A3: Ja, Aspose.Tasks voor .NET is compatibel met .NET Core, waardoor u het in platformonafhankelijke toepassingen kunt gebruiken.

### V4: Ondersteunt Aspose.Tasks het lezen en schrijven van Microsoft Project-bestanden?

A4: Ja, Aspose.Tasks ondersteunt het lezen en schrijven van Microsoft Project-bestanden in verschillende formaten, waaronder MPP, XML en MPX.

### V5: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?

 A5: Ja, u kunt een gratis proefversie van Aspose.Tasks voor .NET krijgen van[hier](https://releases.aspose.com/).