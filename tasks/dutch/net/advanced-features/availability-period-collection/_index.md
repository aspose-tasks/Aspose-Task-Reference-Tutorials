---
title: Verzameling van beschikbaarheidsperioden in Aspose.Tasks
linktitle: Verzameling van beschikbaarheidsperioden in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u beschikbaarheidsperioden voor bronnen beheert in Aspose.Tasks voor .NET. Deze stapsgewijze zelfstudie begeleidt u bij het toevoegen, bijwerken en verwijderen van beschikbaarheidsperioden, waardoor een effectieve projectresourceplanning wordt gegarandeerd.
type: docs
weight: 18
url: /nl/net/advanced-features/availability-period-collection/
---
## Invoering

In deze zelfstudie onderzoeken we hoe u kunt werken met de verzameling van de beschikbaarheidsperiode van een bron in Aspose.Tasks voor .NET. Het beheren van beschikbaarheidsperioden is cruciaal voor projectmanagement, waardoor we kunnen definiëren wanneer middelen beschikbaar zijn voor taken binnen een project.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis: Bekendheid met C# en .NET framework.

## Naamruimten importeren

Eerst moeten we de benodigde naamruimten in ons project importeren:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Laten we de voorbeeldcode in meerdere stappen opsplitsen en elk onderdeel begrijpen:

## Stap 1: Initialiseer het project en de resource

```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Hier laden we een projectbestand en verkrijgen we een specifieke bron op basis van zijn ID.

## Stap 2: Bestaande beschikbaarheidsperioden wissen

```csharp
resource.AvailabilityPeriods.Clear();
```

We wissen eventuele bestaande beschikbaarheidsperioden die aan de resource zijn gekoppeld.

## Stap 3: Beschikbaarheidsperioden toevoegen

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

We doorlopen een verzameling beschikbaarheidsperioden en voegen deze toe aan de resource.

## Stap 4: Voeg een nieuwe beschikbaarheidsperiode in

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Wij creëren een nieuwe beschikbaarheidsperiode voor het jaar 2013 en voegen deze in de collectie.

## Stap 5: Beschikbaarheidsperioden weergeven

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

We drukken de telling en details af van elke beschikbaarheidsperiode die aan de bron is gekoppeld.

## Stap 6: Kopieer beschikbaarheidsperioden naar een andere resource

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

We kopiëren de beschikbaarheidsperioden van de ene resource naar de andere.

## Stap 7: Beschikbaarheidsperioden bijwerken en verwijderen

```csharp
// Update beschikbare eenheden voor een specifieke periode
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Verwijder een specifieke periode
otherResource.AvailabilityPeriods.Remove(period2013);
```

We updaten de beschikbare eenheden voor een periode en verwijderen specifieke periodes uit de collectie.

## Conclusie

In deze zelfstudie hebben we geleerd hoe u kunt werken met verzamelingen van beschikbaarheidsperioden in Aspose.Tasks voor .NET. Het beheren van de beschikbaarheid van resources is essentieel voor een effectieve projectplanning en -uitvoering.

## Veelgestelde vragen

### V1: Kan ik aangepaste velden toevoegen aan beschikbaarheidsperioden?

A1: Nee, beschikbaarheidsperioden in Aspose.Tasks voor .NET ondersteunen geen aangepaste velden.

### Vraag 2: Zijn beschikbaarheidsperioden gekoppeld aan specifieke taken?

A2: Nee, beschikbaarheidsperioden zijn gekoppeld aan resources en bepalen wanneer deze beschikbaar zijn voor taken in het algemeen.

### V3: Kan ik beschikbaarheidsperioden uit externe bronnen importeren?

A3: Ja, u kunt beschikbaarheidsperioden uit verschillende gegevensbronnen importeren met Aspose.Tasks voor .NET API's.

### V4: Hoe ga ik om met overlappende beschikbaarheidsperioden?

A4: Aspose.Tasks voor .NET biedt geen ingebouwde mechanismen om overlappende perioden af te handelen. Mogelijk moet u aangepaste logica implementeren om dergelijke scenario's te beheren.

### Vraag 5: Is er een limiet aan het aantal beschikbaarheidsperioden dat een resource kan hebben?

A5: Er is geen vooraf gedefinieerde limiet voor het aantal beschikbaarheidsperioden dat een resource kan hebben, maar de prestaties kunnen afnemen bij een groot aantal perioden.