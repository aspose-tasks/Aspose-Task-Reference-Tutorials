---
title: Berekeningsmodus in Aspose.Tasks
linktitle: Berekeningsmodus in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u berekeningsmodi effectief kunt beheren in Aspose.Tasks voor .NET om projectplanning en taakafhankelijkheden te stroomlijnen.
type: docs
weight: 29
url: /nl/net/advanced-features/calculation-mode/
---
## Invoering

Aspose.Tasks voor .NET is een krachtige API waarmee ontwikkelaars programmatisch met Microsoft Project-bestanden kunnen werken in hun .NET-toepassingen. Een cruciaal aspect van het werken met projectbestanden is het beheren van berekeningsmodi, die bepalen hoe taken en projectplanningen worden berekend en bijgewerkt. In deze zelfstudie verdiepen we ons in de verschillende berekeningsmodi die worden ondersteund door Aspose.Tasks voor .NET en laten we zien hoe u deze effectief kunt gebruiken.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#-programmeren: maak uzelf vertrouwd met C#-programmeerconcepten.

## Naamruimten importeren

Voordat we met Aspose.Tasks voor .NET gaan werken, importeren we de benodigde naamruimten:

```csharp
using Aspose.Tasks;
using System;


```

## Automatische berekeningsmodus toepassen

### Stap 1: Maak een nieuw Project-exemplaar

 Initialiseer een nieuwe`Project` object en stel het in`CalculationMode` eigendom aan`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Stap 2: Stel de startdatum van het project in en voeg taken toe

Definieer de startdatum van het project en voeg er taken aan toe.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Stap 3: Taken koppelen

Breng afhankelijkheden tussen taken tot stand.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Stap 4: Controleer de herberekende datums

Controleer of de data automatisch opnieuw zijn berekend.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Voeg indien nodig meer verificaties toe
```

## Handmatige berekeningsmodus toepassen

### Stap 1: Maak een nieuw Project-exemplaar

 Initialiseer een nieuwe`Project` object en stel het in`CalculationMode` eigendom aan`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Stap 2: Stel de startdatum van het project in en voeg taken toe

Definieer de startdatum van het project en voeg er taken aan toe.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Stap 3: Controleer de taakeigenschappen

Controleer of de taakeigenschappen correct zijn ingesteld in de handmatige modus.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Voeg indien nodig meer verificaties toe
```

### Stap 4: Taken koppelen en datums verifiëren

Koppel taken aan elkaar en controleer of hun datums niet opnieuw worden berekend.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Geen berekeningsmodus toepassen

### Stap 1: Maak een nieuw Project-exemplaar

 Initialiseer een nieuwe`Project` object en stel het in`CalculationMode` eigendom aan`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Stap 2: Voeg een nieuwe taak toe

Voeg een nieuwe taak toe aan het project.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Stap 3: Controleer de taakeigenschappen

Controleer of taakeigenschappen niet automatisch worden berekend.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Voeg indien nodig meer verificaties toe
```

## Conclusie

In deze zelfstudie hebben we de beschikbare berekeningsmodi in Aspose.Tasks voor .NET onderzocht en geleerd hoe we deze in praktische scenario's kunnen toepassen. Of u nu een automatische, handmatige of geen berekeningsmodus nodig heeft, Aspose.Tasks biedt de flexibiliteit om aan de vereisten van uw project te voldoen.

## Veelgestelde vragen

### V1: Kan ik de berekeningsmodus dynamisch wijzigen tijdens runtime?

A1: Ja, u kunt de berekeningsmodus van een project op elk moment tijdens de runtime wijzigen door de`CalculationMode` eigendom.

### V2: Ondersteunt Aspose.Tasks naast Microsoft Project ook andere bestandsindelingen voor projectbeheer?

A2: Aspose.Tasks richt zich primair op Microsoft Project-bestandsformaten, maar ondersteunt ook andere formaten zoals Primavera P6 XML, Primavera DB en Asta Powerproject XML.

### Vraag 3: Is Aspose.Tasks geschikt voor zowel kleinschalige als ondernemingsprojecten?

A3: Absoluut! Aspose.Tasks is ontworpen om tegemoet te komen aan de behoeften van zowel kleinschalige als ondernemingsprojecten met zijn uitgebreide functies en robuuste API's.

### V4: Kan ik Aspose.Tasks integreren met andere .NET-bibliotheken en -frameworks?

A4: Ja, u kunt Aspose.Tasks naadloos integreren met andere .NET-bibliotheken en -frameworks om de functionaliteit van uw applicaties te verbeteren.

### V5: Is er een communityforum of ondersteuningskanaal beschikbaar voor Aspose.Tasks-gebruikers?

 A5: Ja, u kunt de bezoeken[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapsondersteuning en discussies.