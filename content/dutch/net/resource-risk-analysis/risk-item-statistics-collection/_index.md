---
title: Verzamel statistieken over MS Project-risico-items in Aspose.Tasks
linktitle: Verzameling van risico-itemstatistieken in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u statistieken over risico-items verzamelt uit MS Project-bestanden met behulp van Aspose.Tasks voor .NET. Verbeter uw projectmanagementmogelijkheden.
type: docs
weight: 22
url: /nl/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u risico-itemstatistieken kunt verzamelen uit MS Project-bestanden met behulp van Aspose.Tasks voor .NET. Deze bibliotheek biedt krachtige functionaliteiten voor het analyseren van projectgegevens, inclusief risicobeoordeling en statistische analyse.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks-bibliotheek. U kunt deze verkrijgen bij de[downloadpagina](https://releases.aspose.com/tasks/net/).
2. Ontwikkelomgeving: Zorg dat er een ontwikkelomgeving is opgezet voor .NET-programmering.

## Naamruimten importeren
Zorg ervoor dat u, voordat u begint met coderen, de benodigde naamruimten in uw project importeert:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Stap 1: Laad het projectbestand
Eerst moet u het MS Project-bestand in uw applicatie laden. Hier ziet u hoe u dit kunt bereiken:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Stap 2: Definieer de risicoanalyse-instellingen
Initialiseer de risicoanalyse-instellingen, inclusief het aantal iteraties, zoals hieronder weergegeven:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Stap 3: Initialiseer een risicopatroon
Stel een risicopatroon op voor de analyse, waarbij u het distributietype, de optimistische en pessimistische percentages en het betrouwbaarheidsniveau specificeert:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Stap 4: Voer een risicoanalyse uit
 Instantieer de`RiskAnalyzer` klasse en analyseer het project:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Stap 5: Statistieken ophalen
Haal de risico-itemstatistieken, zoals vroege afwerking, op uit het analyseresultaat:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Stap 6: Statistieken afdrukken
Herhaal de statistieken en druk de details af:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Andere relevante statistieken afdrukken...
}
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u Aspose.Tasks voor .NET kunt gebruiken om risico-itemstatistieken uit MS Project-bestanden te verzamelen. Door deze stappen te volgen, kunt u projectgegevens effectief analyseren en potentiële risico's beoordelen, wat helpt bij betere besluitvorming en projectbeheer.

## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks grote MS Project-bestanden verwerken?
A: Ja, Aspose.Tasks kan grote MS Project-bestanden efficiënt verwerken en biedt betrouwbare prestaties en schaalbaarheid.
### Vraag: Ondersteunt Aspose.Tasks naast .mpp ook andere projectbestandsformaten?
A: Ja, Aspose.Tasks ondersteunt verschillende projectbestandsformaten, waaronder XML en MPT.
### Vraag: Is Aspose.Tasks geschikt voor projectbeheertoepassingen op ondernemingsniveau?
A: Absoluut, Aspose.Tasks is ontworpen om te voldoen aan de eisen van projectbeheerapplicaties op bedrijfsniveau en biedt robuuste functies en uitgebreide documentatie.
### Vraag: Kan ik de risicoanalyse-instellingen aanpassen in Aspose.Tasks?
A: Ja, Aspose.Tasks biedt flexibiliteit bij het configureren van risicoanalyse-instellingen om aan uw specifieke projectvereisten en scenario's te voldoen.
### Vraag: Is er technische ondersteuning beschikbaar voor Aspose.Tasks-gebruikers?
 A: Ja, Aspose.Tasks-gebruikers hebben toegang tot technische ondersteuning via Aspose[forums](https://forum.aspose.com/c/tasks/15), waar ze vragen kunnen stellen, problemen kunnen melden en met de community kunnen communiceren.