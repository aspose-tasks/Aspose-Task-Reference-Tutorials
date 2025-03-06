---
title: Přizpůsobte si sloupce Ganttova diagramu pomocí Aspose.Tasks
linktitle: Sloupce Ganttova diagramu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak upravit sloupce Ganttova diagramu v Aspose.Tasks pro .NET, aby se efektivně zobrazovaly konkrétní informace o úkolu.
weight: 21
url: /cs/net/tasks-project-management/gantt-chart-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přizpůsobte si sloupce Ganttova diagramu pomocí Aspose.Tasks

## Úvod
Ganttovy diagramy jsou základním nástrojem řízení projektů, poskytují vizuální reprezentaci úkolů, časových os a zdrojů. Aspose.Tasks for .NET nabízí výkonné možnosti pro manipulaci s Ganttovými diagramy, včetně přizpůsobení sloupců pro zobrazení informací o konkrétních úkolech. V tomto tutoriálu prozkoumáme, jak pracovat se sloupci Ganttova diagramu pomocí Aspose.Tasks for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Instalace: Aspose.Tasks for .NET nainstalované ve vašem systému. Pokud ne, stáhněte si jej a nainstalujte z[tady](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí .NET: Pracovní znalost C# a frameworku .NET.
3. Vzorový soubor projektu: Mějte vzorový soubor Microsoft Project (`.mpp`) vhodné k experimentování. Pokud žádný nemáte, můžete vytvořit jednoduchý projekt v MS Project a uložit jej.

## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory pro práci s Aspose.Tasks for .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Krok 1: Načtěte soubor projektu
 Načtěte soubor projektu pomocí`Project` třídy poskytuje Aspose.Úkoly:
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Krok 2: Definujte sloupce Ganttova diagramu
Definujte sloupce, které chcete zobrazit v Ganttově diagramu. Můžete zadat vestavěná pole nebo vytvořit vlastní:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Krok 3: Iterujte přes sloupce
Iterováním definovaných sloupců získáte přístup k jejich vlastnostem a zobrazíte informace:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Krok 4: Uložte Ganttův diagram do CSV
Uložte Ganttův diagram s definovanými sloupci do souboru CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Pomocí následujících kroků můžete efektivně pracovat se sloupci Ganttova diagramu v Aspose.Tasks for .NET, což vám umožní přizpůsobit a zobrazit informace o úkolech podle potřeby.

## Závěr
Zvládnutí manipulace se sloupci Ganttova diagramu v Aspose.Tasks for .NET otevírá nekonečné možnosti pro přizpůsobení vizuálů projektového řízení vašim konkrétním potřebám. Podle kroků uvedených v tomto kurzu můžete efektivně zpracovávat informace o úkolech a zlepšit přehlednost a organizaci projektu.
## FAQ
### Otázka: Mohu vytvořit vlastní sloupce v Aspose.Tasks pro .NET?
Odpověď: Ano, můžete definovat vlastní sloupce pro zobrazení specifických atributů úkolu podle požadavků vašeho projektu.
### Otázka: Je Aspose.Tasks for .NET kompatibilní se všemi verzemi souborů Microsoft Project?
Odpověď: Aspose.Tasks for .NET podporuje různé verze souborů Microsoft Project, čímž zajišťuje kompatibilitu v různých prostředích projektu.
### Otázka: Jak mohu zvládnout složité struktury projektů pomocí Aspose.Tasks pro .NET?
Odpověď: Aspose.Tasks for .NET poskytuje komplexní rozhraní API a funkce pro správu složitých struktur projektů a nabízí flexibilitu a škálovatelnost.
### Otázka: Existují nějaká omezení počtu sloupců, které mohu přidat do Ganttova diagramu?
Odpověď: Aspose.Tasks for .NET nabízí rozsáhlé možnosti přizpůsobení, které vám umožňují bez omezení přidat značný počet sloupců do Ganttových diagramů.
### Otázka: Kde najdu další podporu a zdroje pro Aspose.Tasks pro .NET?
Odpověď: Můžete prozkoumat dokumentaci, komunitní fóra a kanály podpory poskytované Aspose.Tasks pro .NET, abyste získali přístup ke komplexním zdrojům a pomoci.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
