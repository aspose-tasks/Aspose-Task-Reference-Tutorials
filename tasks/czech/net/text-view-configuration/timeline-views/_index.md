---
title: Zvládnutí zobrazení časové osy projektu v Aspose.Tasks
linktitle: Přizpůsobení zobrazení časové osy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master Aspose.Tasks for .NET v přizpůsobení zobrazení časové osy. Vylepšete své projektové řízení pomocí vizuálně přitažlivých časových plánů přizpůsobených potřebám vašeho projektu.
weight: 13
url: /cs/net/text-view-configuration/timeline-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí zobrazení časové osy projektu v Aspose.Tasks

## Úvod
Vytváření vizuálně přitažlivých a informativních zobrazení časové osy je zásadní pro efektivní řízení projektu. Aspose.Tasks for .NET poskytuje robustní řešení pro přizpůsobení zobrazení časové osy, což vám umožňuje přizpůsobit zobrazení úkolů podle konkrétních potřeb vašeho projektu. V tomto podrobném průvodci prozkoumáme, jak používat Aspose.Tasks k snadnému vytváření a přizpůsobení zobrazení časové osy.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
- Základní znalost programování v C# a .NET.
-  Nainstalovaná knihovna Aspose.Tasks for .NET. Pokud ne, stáhněte si jej[tady](https://releases.aspose.com/tasks/net/).
- Integrované vývojové prostředí (IDE), jako je Visual Studio.
## Importovat jmenné prostory
Ujistěte se, že importujete potřebné jmenné prostory do kódu C#:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Krok 1: Inicializujte zobrazení projektu a časové osy
Začněte inicializací nového projektu a zobrazením časové osy:
```csharp
var project = new Project();
var view = new TimelineView();
```
## Krok 2: Nastavte vlastnosti zobrazení časové osy
Přizpůsobte zobrazení časové osy nastavením různých vlastností:
```csharp
view.DateFormat = DateFormat.DateDddDd;
view.DisplayOverlapped = true;
view.ShowPanZoom = true;
view.ShowTimescale = true;
view.ShowToday = true;
view.TextLinesCount = 2;
```
## Krok 3: Zobrazení podrobností zobrazení časové osy
Načtení informací o zobrazení časové osy:
```csharp
Console.WriteLine("Show Dates: " + view.ShowDates);
```
## Krok 4: Přidejte pohled do projektu
Přidejte do projektu přizpůsobené zobrazení časové osy:
```csharp
project.Views.Add(view);
```
## Krok 5: Přidejte testovací data do projektu
Naplňte projekt ukázkovými úkoly:
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task1.Set(Tsk.Duration, task1.ParentProject.GetDuration(24, TimeUnitType.Hour));
var task2 = project.RootTask.Children.Add("Task 2");
task2.Set(Tsk.Start, new DateTime(2020, 4, 29, 8, 0, 0));
task2.Set(Tsk.Duration, task1.ParentProject.GetDuration(40, TimeUnitType.Hour));
```
## Krok 6: Uložte projekt jako PDF
Uložte projekt s přizpůsobeným zobrazením časové osy jako soubor PDF:
```csharp
project.Save("Your Document Directory/SetTimeScaleCount_out.pdf", SaveFileFormat.Pdf);
```
## Závěr
Gratulujeme! Úspěšně jste přizpůsobili zobrazení časové osy pomocí Aspose.Tasks pro .NET. Tato výkonná knihovna zjednodušuje proces vytváření vizuálně přitažlivých časových os projektů a rozšiřuje možnosti řízení projektů.
## Nejčastější dotazy
### Je Aspose.Tasks kompatibilní s jinými frameworky .NET?
Ano, Aspose.Tasks podporuje různé .NET frameworky, což zajišťuje kompatibilitu s vaším vývojovým prostředím.
### Mohu upravit vzhled jednotlivých úkolů v zobrazení časové osy?
Absolutně! Aspose.Tasks poskytuje flexibilitu pro přizpůsobení vzhledu každého úkolu v zobrazení časové osy.
### Kde najdu další zdroje a podporu pro Aspose.Tasks?
 Navštivte[Dokumentace Aspose.Tasks](https://reference.aspose.com/tasks/net/)pro komplexní průvodce a[Fórum podpory](https://forum.aspose.com/c/tasks/15) pro pomoc.
### Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?
 Ano, můžete vyzkoušet bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Jak získám dočasnou licenci pro Aspose.Tasks?
 Získejte dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
