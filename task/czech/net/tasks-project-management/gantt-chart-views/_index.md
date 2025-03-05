---
title: Zvládnutí zobrazení Ganttova diagramu v Aspose.Tasks
linktitle: Zobrazení Ganttova diagramu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak přizpůsobit zobrazení Ganttova diagramu v souborech Microsoft Project pomocí Aspose.Tasks for .NET. Průvodce krok za krokem pro efektivní řízení projektů.
type: docs
weight: 22
url: /cs/net/tasks-project-management/gantt-chart-views/
---
## Úvod
Ganttovy diagramy jsou výkonné nástroje používané při řízení projektů k vizualizaci úkolů, časových os a závislostí. Aspose.Tasks for .NET poskytuje robustní možnosti pro práci s Ganttovým diagramem v souborech aplikace Microsoft Project. V tomto tutoriálu prozkoumáme, jak využít Aspose.Tasks k manipulaci se zobrazeními Ganttova diagramu, přizpůsobení jejich vzhledu a jejich uložení jako soubory PDF.
## Předpoklady
Než budete pokračovat, ujistěte se, že máte splněny následující předpoklady:
### 1. Instalace Aspose.Tasks pro .NET
 Ujistěte se, že jste nainstalovali Aspose.Tasks for .NET. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/tasks/net/) a postupujte podle pokynů k instalaci uvedených v dokumentaci[tady](https://reference.aspose.com/tasks/net/).
### 2. Soubor Microsoft Project
Připravte soubor Microsoft Project (`Project2.mpp`), který budete používat pro práci se zobrazeními Ganttova diagramu.
### 3. Základní znalost C# a .NET Framework
Tento tutoriál předpokládá, že máte základní znalosti programovacího jazyka C# a frameworku .NET.
## Importovat jmenné prostory
Než začnete pracovat se zobrazeními Ganttova diagramu v Aspose.Tasks, musíte do kódu C# importovat potřebné jmenné prostory. Můžete to udělat takto:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Rozdělme poskytnutý příklad kódu do několika kroků a každý krok podrobně vysvětlíme:
## Krok 1: Načtěte soubor projektu
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Tento krok zahrnuje načtení souboru Microsoft Project (`Project2.mpp` ) do instance the`Project` třída.
## Krok 2: Nastavte datum stavu
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Zde nastavíme datum stavu projektu na datum zahájení.
## Krok 3: Přístup k zobrazení Ganttova diagramu
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Z projektu přistupujeme k zobrazení Ganttova diagramu. Aspose.Tasks umožňuje přístup k zobrazením, jako je Ganttův diagram, síťový diagram a využití úloh.
## Krok 4: Přizpůsobte zobrazení Ganttova diagramu
Nyní přizpůsobíme různé aspekty zobrazení Ganttova diagramu:
### Nastavte zaokrouhlení tyče
```csharp
view.BarRounding = false;
```
Tím se nastaví, zda se pruhy v Ganttově diagramu zaokrouhlí na nejbližší den.
### Nastavte velikost pruhu
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
To určuje výšku Ganttových pruhů v grafu.
### Skrýt Rollup Bary
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Určuje, zda budou při rozbalování souhrnných úkolů skryté kumulativní panely.
### Nastavte barvu nepracovního času
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Definuje barvu pro nepracovní dobu v Ganttově diagramu.
### Roll Up Ganttovy tyče
```csharp
view.RollUpGanttBars = true;
```
Určuje, zda musí být pruhy v Ganttově diagramu srolovány.
### Zobrazit rozdělení pruhů
```csharp
view.ShowBarSplits = true;
```
Určuje, zda se musí zobrazit rozdělení úkolů v Ganttově diagramu.
### Zobrazit výkresy
```csharp
view.ShowDrawings = true;
```
Určuje, zda musí být zobrazeny výkresy v Ganttově diagramu.
### Procento velikosti časové osy
```csharp
view.TimescaleSizePercentage = 10;
```
Nastaví procento pro úpravu mezery mezi jednotkami na úrovni časové osy.
## Krok 5: Uložte zobrazení Ganttova diagramu jako PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Nakonec uložíme přizpůsobené zobrazení Ganttova diagramu jako soubor PDF.
## Závěr
V tomto tutoriálu jsme se naučili, jak pracovat se zobrazeními Ganttova diagramu v Aspose.Tasks pro .NET. Dodržováním uvedených kroků můžete efektivně manipulovat a přizpůsobovat Ganttovy diagramy podle požadavků vašeho projektu.
## FAQ
### Otázka: Mohu dále upravit vzhled pruhů Ganttova diagramu?
Odpověď: Ano, Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení vzhledu pruhů Ganttova diagramu, včetně barev, tvarů a velikostí.
### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?
Odpověď: Ano, Aspose.Tasks podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.
### Otázka: Mohu exportovat zobrazení Ganttova diagramu do jiných formátů než PDF?
Odpověď: Aspose.Tasks rozhodně podporuje export zobrazení Ganttova diagramu do různých formátů, včetně PNG, JPEG a XPS.
### Otázka: Nabízí Aspose.Tasks podporu pro složité algoritmy plánování projektů?
Odpověď: Ano, Aspose.Tasks poskytuje pokročilé plánovací algoritmy pro efektivní zpracování složitých projektových plánů.
### Otázka: Existuje komunitní fórum, kde mohu hledat pomoc nebo sdílet své zkušenosti s Aspose.Tasks?
 Odpověď: Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) komunikovat s ostatními uživateli, klást otázky a hledat řešení vašich dotazů.