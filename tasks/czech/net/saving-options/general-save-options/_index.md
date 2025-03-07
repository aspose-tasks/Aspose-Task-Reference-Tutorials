---
title: Zvládnutí MS Project Uložit možnosti pro Aspose.Tasks
linktitle: Obecné možnosti ukládání pro Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se efektivně ukládat soubory MS Project pomocí Aspose.Tasks for .NET. Přizpůsobte si možnosti výstupu bez námahy pro své projekty.
weight: 17
url: /cs/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí MS Project Uložit možnosti pro Aspose.Tasks

## Úvod
Aspose.Tasks for .NET nabízí výkonné funkce pro programovou manipulaci se soubory Microsoft Project. V tomto tutoriálu se ponoříme do složitosti ukládání souborů MS Project pomocí různých možností, které poskytuje Aspose.Tasks. Konkrétně se zaměříme na obecné možnosti ukládání dostupné pro Aspose.Tasks, které vám umožní přizpůsobit výstup vašim konkrétním požadavkům.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Instalace Aspose.Tasks for .NET: Stáhněte a nainstalujte Aspose.Tasks for .NET z[odkaz ke stažení](https://releases.aspose.com/tasks/net/).
2. Základní porozumění .NET Framework: Prospěšná je znalost programovacích konceptů .NET.

## Import jmenných prostorů
Než se ponoříte do kódu, nezapomeňte importovat potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Krok 1: Načtěte soubor projektu
Nejprve musíte načíst soubor MS Project pomocí Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Krok 2: Definujte možnosti uložení
 Definujte možnosti uložení podle svých požadavků. V tomto příkladu používáme`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Krok 3: Přizpůsobte sloupce zobrazení
Můžete přizpůsobit sloupce zobrazení, jako je Ganttův diagram, zobrazení zdrojů a zobrazení přiřazení. Postup přidání sloupců do každého:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Krok 4: Uložte projekt s možnostmi
Nakonec uložte projekt se zadanými možnostmi:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Závěr
Zvládnutí obecných možností ukládání MS Project pomocí Aspose.Tasks for .NET vám umožňuje efektivně přizpůsobit výstupní formát podle potřeb vašeho projektu.
## FAQ
### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi souborů MS Project?
Odpověď: Ano, Aspose.Tasks podporuje různé verze souborů MS Project, což zajišťuje kompatibilitu v různých prostředích.
### Otázka: Mohu vyzkoušet Aspose.Tasks před nákupem?
 Odpověď: Ano, můžete prozkoumat Aspose.Tasks s bezplatnou zkušební verzí[tady](https://releases.aspose.com/).
### Otázka: Kde najdu dokumentaci k Aspose.Tasks?
 Odpověď: Podrobnou dokumentaci lze nalézt[tady](https://reference.aspose.com/tasks/net/), poskytující komplexní návod k používání funkcí Aspose.Tasks.
### Otázka: Jak mohu získat dočasné licence pro Aspose.Tasks?
 Odpověď: Pro účely hodnocení jsou k dispozici dočasné licence[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde mohu hledat podporu pro dotazy související s Aspose.Tasks?
 Odpověď: Můžete se připojit do fóra komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15)získat pomoc od odborníků a kolegů vývojářů.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
