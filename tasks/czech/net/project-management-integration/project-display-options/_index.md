---
title: Konfigurace možností zobrazení MS Project v Aspose.Tasks
linktitle: Konfigurace možností zobrazení projektu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se konfigurovat možnosti zobrazení MS Project programově pomocí Aspose.Tasks pro .NET. Přizpůsobte si vzhled svého projektu bez námahy.
weight: 17
url: /cs/net/project-management-integration/project-display-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurace možností zobrazení MS Project v Aspose.Tasks

## Úvod
Microsoft Project nabízí nepřeberné množství možností zobrazení pro přizpůsobení vzhledu vašeho projektu. Aspose.Tasks for .NET poskytuje robustní rámec pro programovou manipulaci s těmito možnostmi. V tomto tutoriálu prozkoumáme, jak nakonfigurovat možnosti zobrazení MS Project pomocí Aspose.Tasks.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující:
1.  Aspose.Tasks for .NET: Stáhněte a nainstalujte knihovnu z[tady](https://releases.aspose.com/tasks/net/).
2. Soubor Microsoft Project: Připravte si platný soubor MS Project (.mpp) pro použití možností zobrazení.
3. Základní znalost C#: Vyžaduje se znalost programovacího jazyka C#.

## Import jmenných prostorů
Nejprve se ujistěte, že jste do kódu C# importovali potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Krok 1: Načtěte soubor projektu
 Načtěte soubor MS Project pomocí`Project` třídy poskytuje Aspose.Úkoly:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Krok 2: Nakonfigurujte možnosti zobrazení
Nyní nakonfigurujme různé možnosti zobrazení dostupné v MS Project:
### Zakázat varování plánu úloh
Chcete-li zakázat upozornění na konflikty plánování s ručně naplánovanými úlohami (k dispozici pro Project 2010 a novější):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Přidejte mezeru před štítkem
Nastavte přidání mezery před číselnou hodnotu a časovou zkratku:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Konfigurace zobrazení štítků pro časové jednotky
Přizpůsobte, jak se zobrazují různé časové jednotky:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Zobrazit souhrnný úkol projektu
Zobrazení souhrnných informací o celém projektu na jednom řádku:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Povolit návrhy plánu úloh
Povolit zobrazování návrhů pro konflikty plánování s ručně naplánovanými úlohami:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Podtrhnout hypertextové odkazy
Nastavit podtržení hypertextových odkazů v rámci projektu:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Krok 3: Uložte projekt
Nakonec uložte projekt s použitými možnostmi zobrazení:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak nakonfigurovat možnosti zobrazení MS Project pomocí Aspose.Tasks pro .NET. Díky těmto možnostem můžete efektivně programově přizpůsobit vzhled souborů projektu.
## FAQ
### Otázka: Mohu použít tyto možnosti zobrazení pouze na konkrétní úlohy?
Odpověď: Ano, můžete selektivně aplikovat možnosti zobrazení na jednotlivé úlohy pomocí Aspose.Tasks API.
### Otázka: Mají tyto možnosti zobrazení vliv na podkladová data projektu?
Odpověď: Ne, tyto možnosti pouze upravují vizuální reprezentaci projektu a nemění podkladová data.
### Otázka: Jsou tyto možnosti zobrazení kompatibilní se všemi verzemi aplikace Microsoft Project?
Odpověď: Ne, některé možnosti mohou být specifické pro určité verze MS Project. Podrobnosti o kompatibilitě naleznete v dokumentaci.
### Otázka: Mohu vrátit možnosti zobrazení zpět na výchozí nastavení?
Odpověď: Ano, můžete resetovat možnosti zobrazení na jejich výchozí hodnoty pomocí Aspose.Tasks API.
### Otázka: Existují nějaká omezení programového přizpůsobení možností zobrazení?
Odpověď: Přestože Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení, určité možnosti zobrazení nemusí být programově dostupné kvůli omezením ve formátu souboru MS Project.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
