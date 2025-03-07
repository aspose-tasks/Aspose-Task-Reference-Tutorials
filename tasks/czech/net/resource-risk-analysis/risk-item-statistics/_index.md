---
title: Statistiky pro rizikové položky v Aspose.Tasks
linktitle: Statistiky pro rizikové položky v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Odemkněte sílu analýzy rizik v souborech MS Project pomocí Aspose.Tasks for .NET. Získejte přehled, zmírněte nejistoty a řiďte úspěch projektu bez námahy.
weight: 21
url: /cs/net/resource-risk-analysis/risk-item-statistics/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Statistiky pro rizikové položky v Aspose.Tasks

## Úvod
Hledáte vylepšit své schopnosti projektového řízení pomocí Aspose.Tasks pro .NET? Ponořte se do oblasti analýzy rizik s naším podrobným návodem na získávání statistik pro rizikové položky v souborech MS Project. Využitím výkonných schopností Aspose.Tasks můžete získat neocenitelný přehled o nejistotách projektu a činit informovaná rozhodnutí pro účinné zmírnění rizik.
## Předpoklady
Než se vydáme na tuto cestu, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.Tasks for .NET Library: Stáhněte a nainstalujte knihovnu z[Aspose.Tasks pro dokumentaci .NET](https://reference.aspose.com/tasks/net/). Tato knihovna vás vybaví robustními nástroji pro programovou manipulaci se soubory MS Project.
2. Vývojové prostředí .NET: Nastavte své vývojové prostředí .NET, včetně Visual Studia nebo jakéhokoli jiného IDE dle vašeho výběru, abyste usnadnili bezproblémovou integraci Aspose.Tasks do vašich projektů.

## Importovat jmenné prostory
Zahrňte do svého projektu potřebné jmenné prostory, abyste mohli využít funkce Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Krok 1: Definujte datový adresář
```csharp
String DataDir = "Your Document Directory";
```
 Zajistěte výměnu`"Your Document Directory"` s cestou k adresáři dokumentů, kde jsou umístěny soubory MS Project.
## Krok 2: Konfigurace nastavení analýzy rizik
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Upravte`IterationsCount`parametr založený na požadavcích vašeho projektu pro kontrolu přesnosti analýzy rizik.
## Krok 3: Načtěte soubor MS Project
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Nahrajte požadovaný soubor MS Project do`project` objekt pro další analýzu.
## Krok 4: Definujte úlohu a inicializujte vzor rizika
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
Zadejte úlohu pro analýzu rizik a nakonfigurujte vzorec rizik s vhodnými parametry, jako je typ distribuce, optimistická a pesimistická doba trvání a úroveň spolehlivosti.
## Krok 5: Analyzujte rizika projektu
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Spusťte proces analýzy rizik pomocí definovaných nastavení a dat projektu.
## Krok 6: Načtení a zobrazení statistik
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
Získejte a zobrazte různé statistické metriky související s rizikovými položkami v souboru MS Project, včetně očekávané hodnoty, směrodatné odchylky, percentilů, minimálních a maximálních hodnot.

## Závěr
Závěrem lze říci, že zvládnutí analýzy rizik v souborech MS Project pomocí Aspose.Tasks for .NET otevírá oblast možností pro projektové manažery a zúčastněné strany. Sledováním našeho komplexního tutoriálu můžete s jistotou procházet nejistotami a zajistit úspěšné výsledky projektu.
## FAQ
### Mohu integrovat Aspose.Tasks s jinými knihovnami .NET pro rozšířenou funkčnost?
Absolutně! Aspose.Tasks se hladce integruje s různými knihovnami .NET, což vám umožní rozšířit jeho schopnosti podle požadavků vašeho projektu.
### Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Ano, funkce Aspose.Tasks můžete prozkoumat přístupem na[zkušební verze zdarma](https://releases.aspose.com/) k dispozici na našich webových stránkách.
### Jak často jsou pro Aspose.Tasks vydávány aktualizace a vylepšení?
Snažíme se neustále vylepšovat Aspose.Tasks pravidelným vydáváním aktualizací a vylepšení, abychom zajistili, že budete mít vždy přístup k nejnovějším funkcím a optimalizacím.
### Mohu získat technickou podporu pro Aspose.Tasks?
Rozhodně! Náš specializovaný tým podpory je snadno dostupný na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) abychom vám pomohli s jakýmikoli dotazy nebo problémy, se kterými se můžete během své implementace setkat.
### Nabízíte dočasné licence pro krátkodobé projekty?
 Ano, pokud požadujete Aspose.Tasks pro krátkodobý projekt, můžete využít našich výhod[dočasná licence](https://purchase.aspose.com/temporary-license/) možnost splnit vaše licenční potřeby bez jakýchkoliv dlouhodobých závazků.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
