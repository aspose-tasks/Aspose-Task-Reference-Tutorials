---
title: Manipulace s MS Project Progress Lines pomocí Aspose.Tasks
linktitle: Manipulace s čárami průběhu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak manipulovat s řádky průběhu v souborech MS Project pomocí Aspose.Tasks pro .NET, což zlepšuje vizualizaci a správu projektů.
type: docs
weight: 15
url: /cs/net/project-management-integration/progress-lines/
---
## Úvod
Microsoft Project (MS Project) je výkonný nástroj pro řízení projektů, který uživatelům umožňuje sledovat různé aspekty jejich projektů. Jedním z klíčových rysů MS Project je schopnost vizualizovat průběhové linie, které pomáhají zúčastněným stranám porozumět stavu a trajektorii projektu. V tomto tutoriálu prozkoumáme, jak zacházet s řádky průběhu v MS Project pomocí knihovny Aspose.Tasks pro .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Visual Studio: Nainstalujte Visual Studio nebo jakékoli jiné preferované vývojové prostředí .NET.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Výhodou bude znalost programovacího jazyka C#.

## Import jmenných prostorů
Chcete-li začít, importujme potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Nyní si rozeberme jednotlivé kroky při zpracování řádků postupu:
## Krok 1: Načtěte soubor projektu
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Zde načteme soubor MS Project`Project2.mpp` a nastavte datum jeho stavu.
## Krok 2: Definujte zobrazení Ganttova diagramu
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Pohled projektu jsme přenesli do zobrazení Ganttova diagramu pro další manipulaci.
## Krok 3: Definujte čáry průběhu
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Inicializujeme čáry průběhu pro zobrazení Ganttova diagramu.
## Krok 4: Nakonfigurujte nastavení Progress Line
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Zde nastavujeme různé vlastnosti pro čáry průběhu, jako je barva čáry, vzor, písmo atd.
## Krok 5: Zkontrolujte konfiguraci Progress Lines
```csharp
// Nastavení výstupních řádků průběhu
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Výstup dalších nastavení...
```
Vydáváme nakonfigurovaná nastavení průběhových čar pro ověření.
## Krok 6: Uložte soubor projektu
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Nakonec upravený soubor projektu s průběhem uložíme.

## Závěr
V tomto tutoriálu jsme se naučili, jak zacházet s řádky průběhu MS Project pomocí Aspose.Tasks for .NET. Pomocí těchto kroků můžete efektivně přizpůsobit a zobrazit řádky průběhu v souborech MS Project programově.
## FAQ
### Otázka: Mohu dále upravit vzhled čar postupu?
Odpověď: Ano, můžete upravit různé vlastnosti, jako je barva čáry, vzor a písmo, aby vyhovovaly vašim požadavkům.
### Otázka: Podporuje Aspose.Tasks další funkce projektového řízení?
Odpověď: Ano, Aspose.Tasks poskytuje rozsáhlou podporu pro manipulaci s různými aspekty souborů MS Project, včetně úkolů, zdrojů a kalendářů.
### Otázka: Mohu integrovat Aspose.Tasks s jinými knihovnami .NET?
Odpověď: Rozhodně, Aspose.Tasks je navržen tak, aby se hladce integroval s ostatními knihovnami .NET, což vám umožní dále vylepšit vaše aplikace pro řízení projektů.
### Otázka: Existuje komunitní fórum pro podporu Aspose.Tasks?
 Odpověď: Ano, užitečné zdroje a pomoc můžete vyhledat na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Nabízí Aspose.Tasks dočasné licence pro účely hodnocení?
 Odpověď: Ano, můžete získat dočasnou licenci pro vyzkoušení od[tady](https://purchase.aspose.com/temporary-license/).