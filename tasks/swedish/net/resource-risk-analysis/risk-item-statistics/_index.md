---
title: Statistik för riskobjekt i Aspose.Tasks
linktitle: Statistik för riskobjekt i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lås upp kraften i riskanalys i MS Project-filer med Aspose.Tasks för .NET. Få insikter, minska osäkerheter och driv projektframgång utan ansträngning.
weight: 21
url: /sv/net/resource-risk-analysis/risk-item-statistics/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Statistik för riskobjekt i Aspose.Tasks

## Introduktion
Vill du förbättra din projektledningsförmåga med Aspose.Tasks för .NET? Fördjupa dig i riskanalysens område med vår steg-för-steg-handledning om att få statistik för riskobjekt i MS Project-filer. Genom att utnyttja de kraftfulla funktionerna hos Aspose.Tasks kan du få ovärderliga insikter i projektets osäkerheter och fatta välgrundade beslut för att minska riskerna effektivt.
## Förutsättningar
Innan vi ger oss ut på denna resa, se till att du har följande förutsättningar på plats:
1.  Aspose.Tasks för .NET Library: Ladda ner och installera biblioteket från[Aspose.Tasks för .NET-dokumentation](https://reference.aspose.com/tasks/net/). Detta bibliotek utrustar dig med robusta verktyg för att manipulera MS Project-filer programmatiskt.
2. .NET-utvecklingsmiljö: Konfigurera din .NET-utvecklingsmiljö, inklusive Visual Studio eller någon annan IDE du väljer, för att underlätta sömlös integrering av Aspose.Tasks i dina projekt.

## Importera namnområden
Inkludera nödvändiga namnutrymmen i ditt projekt för att utnyttja funktionerna i Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Steg 1: Definiera datakatalog
```csharp
String DataDir = "Your Document Directory";
```
 Se till att byta ut`"Your Document Directory"` med sökvägen till din dokumentkatalog där dina MS Project-filer finns.
## Steg 2: Konfigurera inställningar för riskanalys
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Justera`IterationsCount`parameter baserad på dina projektkrav för att kontrollera precisionen i riskanalysen.
## Steg 3: Ladda MS Project File
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Ladda önskad MS Project-fil i`project` objekt för vidare analys.
## Steg 4: Definiera uppgift och initiera riskmönster
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
Specificera uppgiften för riskanalys och konfigurera riskmönstret med lämpliga parametrar som distributionstyp, optimistiska och pessimistiska varaktigheter och konfidensnivå.
## Steg 5: Analysera projektrisker
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Initiera riskanalysprocessen med de definierade inställningarna och projektdata.
## Steg 6: Hämta och visa statistik
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
Hämta och visa olika statistiska mått relaterade till riskposter i MS Project-filen, inklusive förväntat värde, standardavvikelse, percentiler, minimi- och maximivärden.

## Slutsats
Sammanfattningsvis, att bemästra riskanalys i MS Project-filer med Aspose.Tasks för .NET öppnar upp ett rike av möjligheter för projektledare och intressenter. Genom att följa vår omfattande handledning kan du navigera genom osäkerheter med tillförsikt och säkerställa framgångsrika projektresultat.
## FAQ's
### Kan jag integrera Aspose.Tasks med andra .NET-bibliotek för utökad funktionalitet?
Absolut! Aspose.Tasks integreras sömlöst med olika .NET-bibliotek, vilket gör att du kan förstärka dess kapacitet enligt dina projektkrav.
### Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
 Ja, du kan utforska funktionerna i Aspose.Tasks genom att gå till[gratis provperiod](https://releases.aspose.com/) finns på vår hemsida.
### Hur ofta släpps uppdateringar och förbättringar för Aspose.Tasks?
Vi strävar efter att kontinuerligt förbättra Aspose.Tasks genom att släppa uppdateringar och förbättringar med jämna mellanrum, vilket säkerställer att du alltid har tillgång till de senaste funktionerna och optimeringarna.
### Kan jag få teknisk support för Aspose.Tasks?
Säkert! Vårt dedikerade supportteam är lättillgängligt på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för att hjälpa dig med alla frågor eller utmaningar du kan stöta på under din implementeringsresa.
### Erbjuder ni tillfälliga licenser för kortsiktiga projekt?
 Ja, om du behöver Aspose.Tasks för ett kortsiktigt projekt kan du använda vårt bekväma[tillfällig licens](https://purchase.aspose.com/temporary-license/) möjlighet att uppfylla dina licensbehov utan några långsiktiga åtaganden.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
