---
title: Bez námahy opakující se intervaly MS Project v Aspose.Tasks
linktitle: Správa opakujících se intervalů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Objevte, jak bez námahy spravovat opakující se intervaly v MS Project pomocí Aspose.Tasks for .NET.
type: docs
weight: 12
url: /cs/net/rate-recurring-tasks/recurring-intervals/
---
## Úvod
Hledáte efektivní správu opakujících se intervalů v souborech Microsoft Project pomocí Aspose.Tasks for .NET? Tento obsáhlý návod vás provede procesem krok za krokem a zajistí, že bez námahy zvládnete opakující se intervaly ve vašich projektech. Než se pustíme do výukového programu, pojďme si projít některé předpoklady, abyste se ujistili, že jste připraveni začít.
## Předpoklady
Než budete pokračovat v tomto tutoriálu, ujistěte se, že máte následující:
1. Znalost programování v C#: Vyžaduje se základní znalost programovacího jazyka C# a jeho syntaxe.
2. Nainstalované Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio pro kódování a kompilaci aplikací .NET.
3. Knihovna Aspose.Tasks for .NET: Stáhněte a nainstalujte knihovnu Aspose.Tasks for .NET. Můžete to získat od[tady](https://releases.aspose.com/tasks/net/).

## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů pro přístup k funkcím poskytovaným knihovnou Aspose.Tasks for .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Nyní si každý příklad rozdělíme do několika kroků a podrobně je vysvětlíme.
## Krok 1: Inicializujte objekt projektu:
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Zde inicializujeme novou instanci souboru`Project` třídy poskytnutím cesty k souboru aplikace Microsoft Project.
## Krok 2: Nastavte datum stavu:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Tento krok nastaví datum stavu projektu na datum zahájení.
## Krok 3: Přístup k zobrazení Ganttova diagramu:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Přistupujeme k zobrazení projektu Ganttův diagram.
## Krok 4: Přečtěte si řádek průběhu:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Tento krok načte opakující se interval pro čáry průběhu ze zobrazení Ganttova diagramu.
## Krok 5: Zobrazení informací o intervalu:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Zde zobrazujeme informace o intervalu, čísle týdne v týdnu a dnech týdne.
## Krok 6: Předefinujte opakující se interval:
```csharp
var newInterval = new RecurringInterval();
```
 Vytvoříme novou instanci`RecurringInterval` předefinovat opakující se interval.
## Krok 7: Nastavte měsíční čáry pokroku:
```csharp
// Nastavte měsíční průběhy podle dne.
interval.MonthlyDay = true;
// Nastavte počet dní měsíčních linií průběhu.
interval.MonthlyDayDayNumber = 1;
// Nastavte počet měsíčních řádků průběhu za měsíc.
interval.MonthlyDayMonthNumber = 1;
// Nastavte průběhy podle prvního nebo posledního předdefinovaného dne.
interval.MonthlyFirstLast = true;
// Nastavte první nebo poslední typ měsíčního průběhu.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Nastavte počet řádků průběhu měsíce.
interval.MonthlyFirstLastMonthNumber = 1;
```
Tyto kroky konfigurují měsíční průběhy podle zadaných parametrů.
## Krok 8: Aktualizujte řádky průběhu:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Aktualizujeme čáry průběhu v zobrazení Ganttova diagramu s nově definovaným opakujícím se intervalem.
## Krok 9: Uložit projekt jako PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Nakonec projekt uložíme s aktualizovaným intervalem opakování jako soubor PDF.

## Závěr
Závěrem lze říci, že správa opakujících se intervalů v souborech Microsoft Project pomocí Aspose.Tasks for .NET je díky komplexním funkcím poskytovaným knihovnou zjednodušena. Pokud budete postupovat podle podrobného průvodce popsaného v tomto kurzu, můžete efektivně zvládnout opakující se intervaly ve svých projektech a zvýšit produktivitu a organizaci.
### FAQ
### Mohu používat Aspose.Tasks pro .NET s jinými programovacími jazyky?
Ano, Aspose.Tasks for .NET lze použít s jakýmkoli jazykem podporovaným .NET, jako je C# a VB.NET.
### Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Tasks pro .NET?
 Podporu můžete získat na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Mohu si zakoupit dočasnou licenci pro Aspose.Tasks pro .NET?
 Ano, můžete si zakoupit dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu kompletní dokumentaci k Aspose.Tasks pro .NET?
 Kompletní dokumentaci naleznete[tady](https://reference.aspose.com/tasks/net/).