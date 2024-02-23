---
title: Sbírejte statistiky rizikových položek MS Project v Aspose.Tasks
linktitle: Kolekce statistik rizikových položek v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se shromažďovat statistiky rizikových položek ze souborů MS Project pomocí Aspose.Tasks for .NET. Vylepšete své schopnosti projektového řízení.
type: docs
weight: 22
url: /cs/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Úvod
V tomto tutoriálu prozkoumáme, jak sbírat statistiky rizikových položek ze souborů MS Project pomocí Aspose.Tasks for .NET. Tato knihovna poskytuje výkonné funkce pro analýzu projektových dat, včetně hodnocení rizik a statistické analýzy.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Aspose.Tasks for .NET: Stáhněte a nainstalujte knihovnu Aspose.Tasks. Můžete to získat z[stránka ke stažení](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Mějte nastavené vývojové prostředí pro programování .NET.

## Importovat jmenné prostory
Než začnete kódovat, nezapomeňte do projektu importovat potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Krok 1: Načtěte soubor projektu
Nejprve musíte do aplikace načíst soubor MS Project. Můžete toho dosáhnout takto:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Krok 2: Definujte nastavení analýzy rizik
Inicializujte nastavení analýzy rizik, včetně počtu iterací, jak je uvedeno níže:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Krok 3: Inicializujte rizikový vzor
Nastavte vzorec rizika pro analýzu, určete typ distribuce, optimistická a pesimistická procenta a úroveň spolehlivosti:
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
## Krok 4: Proveďte analýzu rizik
 Vytvořte instanci`RiskAnalyzer` třídu a analyzujte projekt:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Krok 5: Načtení statistiky
Získejte statistiku rizikových položek, jako je předčasné dokončení, z výsledku analýzy:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Krok 6: Tisk statistik
Opakujte statistiky a vytiskněte podrobnosti:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Vytisknout další relevantní statistiky...
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak využít Aspose.Tasks pro .NET ke sběru statistik rizikových položek ze souborů MS Project. Dodržením těchto kroků můžete efektivně analyzovat projektová data a vyhodnocovat potenciální rizika, což napomáhá lepšímu rozhodování a řízení projektů.

## FAQ
### Otázka: Dokáže Aspose.Tasks zpracovat velké soubory MS Project?
Odpověď: Ano, Aspose.Tasks je schopen efektivně zpracovávat velké soubory MS Project a nabízí spolehlivý výkon a škálovatelnost.
### Otázka: Podporuje Aspose.Tasks jiné formáty souborů projektu kromě .mpp?
Odpověď: Ano, Aspose.Tasks podporuje různé formáty projektových souborů, včetně XML a MPT.
### Otázka: Je Aspose.Tasks vhodný pro aplikace řízení projektů na podnikové úrovni?
Odpověď: Aspose.Tasks je rozhodně navržen tak, aby splňoval požadavky aplikací pro řízení projektů na podnikové úrovni, poskytuje robustní funkce a rozsáhlou dokumentaci.
### Otázka: Mohu upravit nastavení analýzy rizik v Aspose.Tasks?
Odpověď: Ano, Aspose.Tasks nabízí flexibilitu při konfiguraci nastavení analýzy rizik tak, aby vyhovovala vašim specifickým projektovým požadavkům a scénářům.
### Otázka: Je pro uživatele Aspose.Tasks k dispozici technická podpora?
 Odpověď: Ano, uživatelé Aspose.Tasks mají přístup k technické podpoře prostřednictvím Aspose.[fórech](https://forum.aspose.com/c/tasks/15), kde mohou klást otázky, hlásit problémy a komunikovat s komunitou.