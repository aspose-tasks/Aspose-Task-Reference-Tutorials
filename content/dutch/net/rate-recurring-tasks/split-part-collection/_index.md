---
title: Verzamel MS-project van gesplitste onderdelen in Aspose.Tasks
linktitle: Verzameling van gesplitste onderdelen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u gesplitste onderdelen verzamelt in MS Project met behulp van Aspose.Tasks voor .NET. Deze uitgebreide tutorial begeleidt u stap voor stap door het proces.
type: docs
weight: 19
url: /nl/net/rate-recurring-tasks/split-part-collection/
---
## Invoering
In deze zelfstudie gaan we dieper in op het verzamelen van gesplitste onderdelen in MS Project met behulp van Aspose.Tasks voor .NET. Het opsplitsen van taken in delen kan een cruciaal aspect van projectmanagement zijn, en Aspose.Tasks biedt handige methoden om dit efficiënt af te handelen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Installatie van Aspose.Tasks voor .NET: Zorg ervoor dat u Aspose.Tasks voor .NET hebt geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).
2. Basiskennis van C#: Bekendheid met de programmeertaal C# is nuttig, aangezien we codefragmenten in C# gaan schrijven.

## Naamruimten importeren
Neem in uw C#-project de benodigde naamruimten op:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Stap 1: Stel uw project in
Maak eerst een nieuw project in de IDE van uw voorkeur en zorg ervoor dat er correct naar Aspose.Tasks voor .NET wordt verwezen.
## Stap 2: Initialiseer het projectobject
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Initialiseer een nieuw Project-object met het pad naar uw MS Project-bestand.
## Stap 3: Haal de taak op en herhaal de gesplitste delen
```csharp
var task = project.RootTask.Children.GetById(1);
// Herhaal over gesplitste delen
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Haal de taak uit het project op en herhaal de gesplitste delen, waarbij u de begin- en einddatum afdrukt.
## Stap 4: Verkrijg een gesplitst onderdeel per index
```csharp
// Haal het onderdeel op via index
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Haal een specifiek opgesplitst onderdeel op per index en print de startdatum ervan.

## Conclusie
Het beheren van gesplitste onderdelen in MS Project-bestanden kan de efficiëntie van het projectbeheer aanzienlijk verbeteren. Aspose.Tasks voor .NET vereenvoudigt dit proces door intuïtieve API's te bieden om gesplitste taken naadloos af te handelen.
## Veelgestelde vragen
### Vraag: Kan ik taken dynamisch splitsen tijdens runtime?
A: Ja, u kunt taken programmatisch splitsen met Aspose.Tasks voor .NET.
### Vraag: Ondersteunt Aspose.Tasks alle versies van MS Project-bestanden?
A: Aspose.Tasks ondersteunt verschillende versies van MS Project-bestanden, waardoor compatibiliteit tussen verschillende platforms wordt gegarandeerd.
### Vraag: Is er een proefversie beschikbaar voor testdoeleinden?
 A: Ja, u kunt een gratis proefversie verkrijgen via[hier](https://releases.aspose.com/) voor evaluatie.
### Vraag: Hoe kan ik tijdelijke licenties krijgen voor mijn projecten?
 A: Tijdelijke licenties kunnen worden verkregen via[hier](https://purchase.aspose.com/temporary-license/) voor kortdurend gebruik.
### Vraag: Waar kan ik hulp of ondersteuning zoeken met betrekking tot Aspose.Tasks?
 A: U kunt het Aspose.Tasks-forum bezoeken[hier](https://forum.aspose.com/c/tasks/15) om hulp te zoeken bij de gemeenschap of het Aspose-ondersteuningsteam.