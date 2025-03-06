---
title: MS-projecttarieven verwerken met Aspose.Tasks voor .NET
linktitle: Tarieven verwerken in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Beheers het beheer van MS Project Rates met gemak met Aspose.Tasks voor .NET. Automatiseer taken efficiënt voor soepelere projectworkflows.
weight: 10
url: /nl/net/rate-recurring-tasks/handling-rates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS-projecttarieven verwerken met Aspose.Tasks voor .NET

## Invoering
Welkom bij onze tutorial over het omgaan met MS Project Rates met Aspose.Tasks voor .NET! In deze handleiding leiden we u stap voor stap door het proces, zodat u de tarieven binnen uw MS Project-documenten efficiënt kunt beheren. Aspose.Tasks voor .NET biedt krachtige functies om MS Project-bestanden programmatisch te manipuleren, zodat u uw projectbeheertaken moeiteloos kunt stroomlijnen.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
1. Visual Studio geïnstalleerd: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor .NET-bibliotheek: Download en installeer de Aspose.Tasks voor .NET-bibliotheek. Je kunt de downloadlink vinden[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: maak uzelf vertrouwd met de grondbeginselen van de programmeertaal C#.
## Naamruimten importeren
Ten eerste moet u de benodigde naamruimten in uw C#-project importeren. Deze naamruimten bieden toegang tot de klassen en methoden die nodig zijn voor het verwerken van MS Project Rates.
## Stap 1: Importeer de Aspose.Tasks-naamruimte
```csharp
using Aspose.Tasks;
using System;

```
Laten we nu het gegeven voorbeeld in meerdere stappen opsplitsen en elke stap grondig begrijpen.
## Stap 1: Projectbestand laden
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 In deze stap laden we een bestaand MS Project-bestand met de naam "Project1.mpp" met behulp van de`Project` klasse aangeboden door Aspose.Tasks.
## Stap 2: Resource toevoegen en werk instellen
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Hier voegen we een nieuwe resource met de naam "Bron 1" toe aan het project en stellen we het type in op "Werk". We definiëren ook de werkduur voor deze resource.
## Stap 3: Stel het standaardtarief in
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
In deze stap stellen we het standaardtarief voor de resource in op € 20 per uur.
## Stap 4: Tariefperioden definiëren
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Hier definiëren we de tariefperioden voor de resource. Tarief 1 is vastgesteld van 1 januari 2019 tot 11 november 2019, met gespecificeerde standaard- en overurentarieven.
## Stap 5: Voeg nog een tariefperiode toe
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
In deze laatste stap voegen we nog een tariefperiode toe vanaf 12 november 2019 tot en met 31 december 2019, waarbij een ander standaardtarief en andere kosten per gebruik zijn gedefinieerd.
Gefeliciteerd! U hebt met succes MS Project Rates afgehandeld met Aspose.Tasks voor .NET.
## Conclusie
Het programmatisch beheren van MS-projecttarieven kan uw projectbeheerworkflow aanzienlijk verbeteren. Met Aspose.Tasks voor .NET beschikt u over de mogelijkheid om de tariefafhandelingstaken efficiënt te automatiseren, waardoor u tijd en middelen bespaart.
## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks complexe projectstructuren aan?
A: Ja, Aspose.Tasks biedt robuuste functies om complexe projectstructuren gemakkelijk af te handelen.
### Vraag: Is Aspose.Tasks compatibel met alle versies van MS Project-bestanden?
A: Aspose.Tasks ondersteunt verschillende versies van MS Project-bestanden, waardoor compatibiliteit tussen verschillende platforms wordt gegarandeerd.
### Vraag: Kan ik bestaande tarieven in een MS Project-bestand wijzigen met Aspose.Tasks?
EEN: Absoluut! Met Aspose.Tasks kunt u bestaande tarieven wijzigen, nieuwe tarieven toevoegen en deze dynamisch beheren.
### V: Biedt Aspose.Tasks ondersteuning voor aangepaste tariefberekeningen?
A: Ja, u kunt aangepaste tariefberekeningen implementeren met Aspose.Tasks om aan specifieke projectvereisten te voldoen.
### Vraag: Is er een communityforum of ondersteuning beschikbaar voor Aspose.Tasks-gebruikers?
 A: Ja, u kunt de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15)om hulp te zoeken en met andere gebruikers te communiceren.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
