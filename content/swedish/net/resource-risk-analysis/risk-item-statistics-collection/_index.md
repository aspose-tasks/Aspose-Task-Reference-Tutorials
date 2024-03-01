---
title: Samla MS Project Risk Item Statistics i Aspose.Tasks
linktitle: Samling av riskpoststatistik i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du samlar in riskpoststatistik från MS Project-filer med Aspose.Tasks för .NET. Förbättra dina projektledningsmöjligheter.
type: docs
weight: 22
url: /sv/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Introduktion
I den här handledningen kommer vi att utforska hur man samlar in riskpoststatistik från MS Project-filer med Aspose.Tasks för .NET. Detta bibliotek tillhandahåller kraftfulla funktioner för att analysera projektdata, inklusive riskbedömning och statistisk analys.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks-biblioteket. Du kan få det från[nedladdningssida](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Ha en utvecklingsmiljö inrättad för .NET-programmering.

## Importera namnområden
Innan du börjar koda, se till att importera de nödvändiga namnrymden i ditt projekt:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Steg 1: Ladda projektfilen
Först måste du ladda MS Project-filen i din ansökan. Så här kan du uppnå det:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Steg 2: Definiera inställningar för riskanalys
Initiera inställningarna för riskanalys, inklusive antalet iterationer, som visas nedan:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Steg 3: Initiera ett riskmönster
Sätt upp ett riskmönster för analysen, ange distributionstyp, optimistiska och pessimistiska procentsatser och konfidensnivå:
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
## Steg 4: Utför riskanalys
 Instantiera`RiskAnalyzer` klass och analysera projektet:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Steg 5: Hämta statistik
Hämta riskpoststatistiken, såsom tidig finish, från analysresultatet:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Steg 6: Skriv ut statistik
Iterera över statistiken och skriv ut detaljerna:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Skriv ut annan relevant statistik...
}
```

## Slutsats
I den här handledningen har vi lärt oss hur man använder Aspose.Tasks för .NET för att samla in riskpoststatistik från MS Project-filer. Genom att följa dessa steg kan du effektivt analysera projektdata och bedöma potentiella risker, vilket hjälper till med bättre beslutsfattande och projektledning.

## FAQ's
### F: Kan Aspose.Tasks hantera stora MS Project-filer?
S: Ja, Aspose.Tasks kan hantera stora MS Project-filer effektivt och erbjuder pålitlig prestanda och skalbarhet.
### F: Stöder Aspose.Tasks andra projektfilformat förutom .mpp?
S: Ja, Aspose.Tasks stöder olika projektfilformat, inklusive XML och MPT.
### F: Är Aspose.Tasks lämpligt för projektledningsapplikationer på företagsnivå?
S: Absolut, Aspose.Tasks är designat för att möta kraven från projektledningsapplikationer på företagsnivå, med robusta funktioner och omfattande dokumentation.
### F: Kan jag anpassa riskanalysinställningarna i Aspose.Tasks?
S: Ja, Aspose.Tasks erbjuder flexibilitet när det gäller att konfigurera riskanalysinställningar för att passa dina specifika projektkrav och scenarier.
### F: Finns teknisk support tillgänglig för Aspose.Tasks-användare?
 S: Ja, Aspose.Tasks-användare kan få tillgång till teknisk support via Aspose[forum](https://forum.aspose.com/c/tasks/15), där de kan ställa frågor, rapportera problem och interagera med samhället.