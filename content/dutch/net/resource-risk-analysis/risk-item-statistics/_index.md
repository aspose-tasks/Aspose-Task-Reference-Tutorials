---
title: Statistieken voor risico-items in Aspose.Tasks
linktitle: Statistieken voor risico-items in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontgrendel de kracht van risicoanalyse in MS Project-bestanden met Aspose.Tasks voor .NET. Krijg inzichten, verminder onzekerheden en zorg moeiteloos voor projectsucces.
type: docs
weight: 21
url: /nl/net/resource-risk-analysis/risk-item-statistics/
---
## Invoering
Wilt u uw projectmanagementvaardigheden verbeteren met Aspose.Tasks voor .NET? Duik in de wereld van risicoanalyse met onze stapsgewijze zelfstudie over het verkrijgen van statistieken voor risico-items in MS Project-bestanden. Door gebruik te maken van de krachtige mogelijkheden van Aspose.Tasks kunt u waardevolle inzichten verkrijgen in projectonzekerheden en weloverwogen beslissingen nemen om risico's effectief te beperken.
## Vereisten
Voordat we aan deze reis beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET-bibliotheek: Download en installeer de bibliotheek van de .NET-bibliotheek[Aspose.Tasks voor .NET-documentatie](https://reference.aspose.com/tasks/net/). Deze bibliotheek voorziet u van robuuste tools voor het programmatisch manipuleren van MS Project-bestanden.
2. .NET-ontwikkelomgeving: Stel uw .NET-ontwikkelomgeving in, inclusief Visual Studio of een andere IDE van uw keuze, om een naadloze integratie van Aspose.Tasks in uw projecten te vergemakkelijken.

## Naamruimten importeren
Neem de nodige naamruimten op in uw project om de functionaliteiten van Aspose te benutten. Taken:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Stap 1: Definieer de gegevensdirectory
```csharp
String DataDir = "Your Document Directory";
```
 Zorg ervoor dat u deze vervangt`"Your Document Directory"` met het pad naar uw documentmap waar uw MS Project-bestanden zich bevinden.
## Stap 2: Configureer de risicoanalyse-instellingen
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Pas de .... aan`IterationsCount`parameter gebaseerd op uw projectvereisten om de nauwkeurigheid van de risicoanalyse te controleren.
## Stap 3: MS-projectbestand laden
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Laad het gewenste MS Project-bestand in het`project` object voor verdere analyse.
## Stap 4: Definieer de taak en initialiseer het risicopatroon
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Specificeer de taak voor risicoanalyse en configureer het risicopatroon met de juiste parameters, zoals het distributietype, de optimistische en pessimistische duur en het betrouwbaarheidsniveau.
## Stap 5: Analyseer projectrisico's
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Start het risicoanalyseproces met behulp van de gedefinieerde instellingen en projectgegevens.
## Stap 6: Statistieken ophalen en weergeven
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Haal verschillende statistische gegevens met betrekking tot risico-items op in het MS Project-bestand en geef deze weer, inclusief verwachte waarde, standaardafwijking, percentielen, minimum- en maximumwaarden.

## Conclusie
Kortom, het beheersen van de risicoanalyse in MS Project-bestanden met behulp van Aspose.Tasks voor .NET opent een scala aan mogelijkheden voor projectmanagers en belanghebbenden. Door onze uitgebreide tutorial te volgen, kunt u met vertrouwen door onzekerheden navigeren en succesvolle projectresultaten garanderen.
## Veelgestelde vragen
### Kan ik Aspose.Tasks integreren met andere .NET-bibliotheken voor uitgebreide functionaliteit?
Absoluut! Aspose.Tasks kan naadloos worden geïntegreerd met verschillende .NET-bibliotheken, waardoor u de mogelijkheden ervan kunt uitbreiden op basis van uw projectvereisten.
### Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?
 Ja, u kunt de functies van Aspose.Tasks verkennen door naar de[gratis proefperiode](https://releases.aspose.com/) beschikbaar op onze website.
### Hoe vaak worden er updates en verbeteringen uitgebracht voor Aspose.Tasks?
We streven ernaar Aspose.Tasks voortdurend te verbeteren door regelmatig updates en verbeteringen uit te brengen, zodat u altijd toegang heeft tot de nieuwste functies en optimalisaties.
### Kan ik technische ondersteuning krijgen voor Aspose.Tasks?
Zeker! Ons toegewijde ondersteuningsteam is direct beschikbaar op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) om u te helpen met eventuele vragen of uitdagingen die u tijdens uw implementatietraject tegenkomt.
### Bieden jullie tijdelijke licenties aan voor kortlopende projecten?
 Ja, als u Aspose.Tasks nodig heeft voor een kortlopend project, kunt u gebruik maken van onze handige[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) optie om aan uw licentiebehoeften te voldoen zonder enige langetermijnverplichtingen.