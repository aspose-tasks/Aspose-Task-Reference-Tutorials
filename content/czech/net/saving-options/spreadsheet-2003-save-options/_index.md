---
title: MS Project s tabulkami 2003 Možnosti pro Aspose.Tasks
linktitle: Možnosti uložení tabulky 2003 pro Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master Spreadsheet 2003 Uložit možnosti MS Project s Aspose.Tasks pro .NET. Bezproblémově přizpůsobujte a ukládejte soubory MS Project programově.
type: docs
weight: 19
url: /cs/net/saving-options/spreadsheet-2003-save-options/
---
## Úvod
V tomto tutoriálu se ponoříme do využití Aspose.Tasks pro .NET k využití možností aplikace Spreadsheet 2003 Save MS Project. Tento výkonný nástroj umožňuje bezproblémovou manipulaci a přizpůsobení souborů MS Project v prostředí .NET. Pojďme si proces rozebrat krok za krokem.
## Předpoklady
Než se pustíme do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
1.  Instalace Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[odkaz ke stažení](https://releases.aspose.com/tasks/net/).
2. Znalost programování v C#: Pro pochopení pojmů probíraných v tomto tutoriálu je nezbytná základní znalost programovacího jazyka C#.

## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů do vašeho projektu C#:
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Tyto jmenné prostory poskytují přístup k funkcím potřebným pro ukládání souborů MS Project pomocí formátu Spreadsheet 2003 a přizpůsobení možností zobrazení.
## Krok 1: Načtěte projekt
Nejprve načtěte soubor MS Project pomocí Aspose.Tasks:
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
 nahradit`"Your Document Directory"`se skutečnou cestou k adresáři, kde se nachází váš soubor MS Project.
## Krok 2: Definujte možnosti uložení
 Definujte možnosti uložení Spreadsheet 2003 vytvořením instance`Spreadsheet2003SaveOptions`,
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Krok 3: Přizpůsobte sloupce zobrazení
Přizpůsobte sloupce zobrazení pro Ganttův diagram, zobrazení zdrojů a zobrazení úkolu:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
Tyto kroky přidávají do příslušných pohledů vlastní sloupce a vylepšují tak možnosti vizualizace a analýzy souboru MS Project.
## Krok 4: Uložte projekt
Nakonec uložte projekt se zadanými možnostmi:
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
Tento příkaz uloží upravený projekt ve formátu Spreadsheet 2003 a přizpůsobených sloupcích zobrazení.

## Závěr
Využití Aspose.Tasks pro .NET, konkrétně Spreadsheet 2003 Save MS Project Options, umožňuje vývojářům efektivně spravovat a programově upravovat soubory MS Project. Podle podrobného průvodce popsaného v tomto kurzu můžete tyto funkce bez problémů integrovat do svých aplikací .NET a zvýšit tak produktivitu a flexibilitu.

## FAQ
### Otázka: Lze Aspose.Tasks for .NET používat ve webových i desktopových aplikacích?
Odpověď: Ano, Aspose.Tasks for .NET lze bez problémů integrovat do webových i desktopových aplikací a poskytovat konzistentní funkce napříč platformami.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi Aspose.Tasks pro .NET z webu[webová stránka](https://releases.aspose.com/), což vám umožní prozkoumat jeho funkce před nákupem.
### Otázka: Existují nějaká omezení pro přizpůsobení sloupců zobrazení pomocí Aspose.Tasks pro .NET?
Odpověď: Aspose.Tasks for .NET nabízí rozsáhlé možnosti přizpůsobení pro sloupce zobrazení s minimálními omezeními. Složité úpravy však mohou vyžadovat pokročilé znalosti knihovny.
### Otázka: Mohu požádat o pomoc, pokud při používání Aspose.Tasks pro .NET narazím na problémy?
 A: Rozhodně! Komplexní podporu a zdroje naleznete na fóru Aspose.Tasks na adrese[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15), kde jsou k dispozici odborníci a členové komunity, kteří vám pomohou vyřešit jakékoli dotazy nebo problémy, se kterými se můžete setkat.
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Tasks pro .NET?
 Odpověď: Můžete získat dočasnou licenci pro Aspose.Tasks for .NET z[nákupní stránku](https://purchase.aspose.com/temporary-license/), což vám umožní vyhodnotit všechny možnosti knihovny.