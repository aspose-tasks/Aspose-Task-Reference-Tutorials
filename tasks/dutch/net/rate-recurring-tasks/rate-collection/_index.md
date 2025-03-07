---
title: Beheer MS-projecttarieven met Aspose.Tasks
linktitle: Verzameling van tarieven in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u tarieven in MS Project-bestanden beheert met Aspose.Tasks voor .NET. Stapsgewijze handleiding voor effectief resourcebeheer.
weight: 11
url: /nl/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheer MS-projecttarieven met Aspose.Tasks

## Invoering
Welkom bij onze tutorial over het beheren van tarieven in MS Project met Aspose.Tasks voor .NET! In deze handleiding leiden we u door het proces van het werken met tarieven in uw MS Project-bestanden met behulp van Aspose.Tasks. Of u nu een doorgewinterde ontwikkelaar bent of net begint met .NET-ontwikkeling, deze tutorial biedt u stapsgewijze instructies om effectief met tarieven binnen uw projecten om te gaan.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
### 1. Visual Studio geïnstalleerd
Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd. Je kunt het downloaden van de website als je dat nog niet hebt gedaan.
### 2. Aspose.Tasks voor .NET
 Download en installeer de Aspose.Tasks voor .NET-bibliotheek vanuit de[website](https://releases.aspose.com/tasks/net/).
### 3. Basiskennis van C# en .NET
Maak uzelf vertrouwd met de programmeertaal C# en de basisbeginselen van het .NET-framework om de codevoorbeelden in deze zelfstudie beter te begrijpen.
## Naamruimten importeren
Importeer in uw C#-project de benodigde naamruimten om de Aspose.Tasks-functionaliteiten te gebruiken:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Laten we nu elk voorbeeld in meerdere stappen opsplitsen:
## Stap 1: Laad een MS-projectbestand
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Hier maken we een nieuwe`Project` object door een bestaand MS Project-bestand te laden.
## Stap 2: Voeg een resource toe en stel het werk en de tarieven in
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
We voegen een nieuwe resource toe aan het project en stellen het type in als werk, werkhoeveelheid en standaardtarief.
## Stap 3: Voeg tarieven toe aan de resource
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
We voegen tarieven toe aan de resource en specificeren de begin- en einddatum, het standaardtarief en het tariefformaat.
## Stap 4: Tariefinformatie afdrukken
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Met deze stap wordt informatie afgedrukt over de tarieven die aan de resource zijn gekoppeld.
## Stap 5: Update een tarief
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
We werken de einddatum van een specifiek tarief bij.
## Stap 6: Tarieven verwijderen
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Met deze stap worden alle tarieven van een specifiek type verwijderd.
## Stap 7: Herhaal de resterende tarieven
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Ten slotte herhalen we de resterende tarieven na verwijdering.
## Conclusie
Kortom, deze tutorial heeft u een uitgebreide handleiding gegeven over het beheren van tarieven in MS Project-bestanden met behulp van Aspose.Tasks voor .NET. Door de stapsgewijze instructies in deze zelfstudie te volgen, kunt u de tarieven binnen uw projecten efficiënt verwerken, waardoor u verzekerd bent van nauwkeurig resourcebeheer.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor .NET gebruiken met andere projectbeheersoftware?
A: Ja, Aspose.Tasks voor .NET ondersteunt integratie met verschillende projectbeheersoftware, waaronder MS Project, Primavera en meer.
### Vraag: Is Aspose.Tasks voor .NET compatibel met verschillende versies van MS Project-bestanden?
A: Absoluut, Aspose.Tasks voor .NET ondersteunt het werken met MS Project-bestanden van verschillende versies, waardoor flexibiliteit en compatibiliteit wordt gegarandeerd.
### Vraag: Biedt Aspose.Tasks voor .NET documentatie en ondersteuning?
 A: Ja, u kunt uitgebreide documentatie en toegang tot ondersteuningsforums vinden op Aspose.Tasks[website](https://reference.aspose.com/tasks/net/).
### Vraag: Kan ik Aspose.Tasks voor .NET uitproberen voordat ik het aanschaf?
A: Ja, u kunt gebruikmaken van een gratis proefversie van Aspose.Tasks voor .NET om de functies en compatibiliteit ervan met uw vereisten te evalueren.
### Vraag: Hoe kan ik een licentie kopen voor Aspose.Tasks voor .NET?
 A: U kunt een licentie voor Aspose.Tasks voor .NET kopen bij de[website](https://purchase.aspose.com/temporary-license/)dat flexibele licentieopties biedt die aan uw behoeften voldoen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
