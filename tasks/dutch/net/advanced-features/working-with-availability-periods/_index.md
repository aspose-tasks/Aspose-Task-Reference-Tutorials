---
title: Werken met beschikbaarheidsperioden in Aspose.Tasks
linktitle: Werken met beschikbaarheidsperioden in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u de beschikbaarheidsperioden van bronnen efficiënt kunt beheren met Aspose.Tasks voor .NET. Deze tutorial biedt een stapsgewijze handleiding voor het werken met beschikbaarheidsperioden in uw .NET-projecten.
weight: 17
url: /nl/net/advanced-features/working-with-availability-periods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Werken met beschikbaarheidsperioden in Aspose.Tasks

## Invoering

In deze zelfstudie onderzoeken we hoe u kunt werken met beschikbaarheidsperioden in Aspose.Tasks voor .NET. Beschikbaarheidsperioden zijn cruciaal voor het efficiënt beheren van resources in projectmanagementscenario's. Wij begeleiden u stap voor stap door het proces.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1. Visual Studio: Installeer Visual Studio of een andere gewenste IDE voor .NET-ontwikkeling.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#-programmeren: Bekendheid met de basisprincipes van de C#-programmeertaal zal nuttig zijn.

## Naamruimten importeren

Voordat je in de code duikt, zorg ervoor dat je de benodigde naamruimten importeert:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Laten we de voorbeeldcode in meerdere stappen opsplitsen:

## Stap 1: Maak een nieuw Project-exemplaar

```csharp
var project = new Project();
```

Deze regel initialiseert een nieuw exemplaar van de klasse Project, die een project in Aspose.Tasks vertegenwoordigt.

## Stap 2: Voeg een bron toe

```csharp
var resource = project.Resources.Add("Work Resource");
```

Hier voegen we een nieuwe resource toe aan het project met de naam "Werkresource".

## Stap 3: Definieer beschikbaarheidsperioden

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Wij noemen de`GetPeriods()` methode om een verzameling beschikbaarheidsperioden op te halen.

## Stap 4: Voeg beschikbaarheidsperioden toe aan de resource

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

We doorlopen de verzameling beschikbaarheidsperioden die we in de vorige stap hebben verkregen en voegen deze toe aan de resource.

## Stap 5: Details van de beschikbaarheidsperiode weergeven

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Ten slotte doorlopen we de beschikbaarheidsperioden die aan de resource zijn gekoppeld en drukken we de details ervan af, inclusief de startdatum, einddatum en beschikbare eenheden.

## Conclusie

In deze tutorial hebben we geleerd hoe we met beschikbaarheidsperioden kunnen werken in Aspose.Tasks voor .NET. Door de stapsgewijze handleiding te volgen, kunt u de beschikbaarheid van resources in uw projectbeheertoepassingen efficiënt beheren.

## Veelgestelde vragen

### V1: Kan ik Aspose.Tasks voor .NET gebruiken in commerciële projecten?

 A1: Ja, Aspose.Tasks voor .NET kan worden gebruikt in commerciële projecten. U kunt een licentie kopen[hier](https://purchase.aspose.com/buy).

### V2: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor .NET?

A2: Ja, u kunt een gratis proefversie van Aspose.Tasks voor .NET verkrijgen[hier](https://releases.aspose.com/).

### V3: Waar kan ik documentatie vinden voor Aspose.Tasks voor .NET?

 A3: U kunt de documentatie vinden[hier](https://reference.aspose.com/tasks/net/).

### V4: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?

 A4: U kunt ondersteuning krijgen van het communityforum[hier](https://forum.aspose.com/c/tasks/15).

### V5: Bieden jullie tijdelijke licenties aan voor Aspose.Tasks voor .NET?

 A5: Ja, er zijn tijdelijke licenties beschikbaar[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
