---
title: Nakonfigurujte možnosti MS Project XLSX v Aspose.Tasks pro .NET
linktitle: Nakonfigurujte možnosti XLSX v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se konfigurovat možnosti MS Project XLSX v Aspose.Tasks pro .NET. Přizpůsobte si sloupce, kódování a ještě více bez námahy.
type: docs
weight: 11
url: /cs/net/file-format-options/configuring-xlsx-options/
---
## Úvod
Microsoft Project (MS Project) je výkonný nástroj pro řízení projektů a Aspose.Tasks for .NET poskytuje bezproblémovou integraci pro práci se soubory MS Project programově. V tomto tutoriálu projdeme procesem konfigurace možností MS Project XLSX pomocí Aspose.Tasks for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
### 1. Aspose.Tasks for .NET Installed
 Ujistěte se, že máte ve vývojovém prostředí nainstalovaný Aspose.Tasks for .NET. Pokud ne, můžete si jej stáhnout z[Aspose.Tasks for .NET download page](https://releases.aspose.com/tasks/net/).
### 2. Základní porozumění C# a .NET Framework
Spolu s tímto tutoriálem je vyžadována znalost programovacího jazyka C# a frameworku .NET.
### 3. Soubor Microsoft Project
Připravte si soubor Microsoft Project (MPP), který chcete nakonfigurovat a uložit jako soubor XLSX.

## Import jmenných prostorů
Chcete-li začít, importujte potřebné jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Krok 1: Načtěte projekt
```csharp
var project = new Project("YourProjectFile.mpp");
```
Načtěte soubor Microsoft Project, který chcete konfigurovat.
## Krok 2: Definujte XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Vytvořte instanci`XlsxOptions` pro konfiguraci nastavení pro ukládání jako XLSX.
## Krok 3: Přidejte sloupce Ganttova diagramu
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Přidejte požadované sloupce Ganttova diagramu do možností.
## Krok 4: Přidejte sloupce zobrazení zdrojů
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Do možností zahrňte požadované sloupce pro zobrazení zdrojů.
## Krok 5: Přidejte sloupce zobrazení přiřazení
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Přidejte požadované sloupce pro zobrazení přiřazení v možnostech.
## Krok 6: Nastavte kódování
```csharp
options.Encoding = Encoding.Unicode;
```
Nastavte kódování pro výstupní soubor.
## Krok 7: Uložte projekt jako XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Uložte projekt s nakonfigurovanými možnostmi jako soubor XLSX.

## Závěr
tomto tutoriálu jsme se naučili, jak nakonfigurovat možnosti MS Project XLSX pomocí Aspose.Tasks pro .NET. Pomocí těchto kroků můžete upravit výstupní formát podle svých požadavků a zvýšit tak flexibilitu a použitelnost pracovního postupu řízení projektů.
## FAQ

### Otázka: Mohu samostatně nakonfigurovat různé sloupce pro Ganttův diagram, zobrazení zdrojů a zobrazení přiřazení?

Odpověď: Ano, pomocí Aspose.Tasks for .NET můžete přizpůsobit sloupce nezávisle pro každé zobrazení.

### Otázka: Je před zakoupením Aspose.Tasks pro .NET k dispozici zkušební verze?

 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[Stránka Aspose.Tasks pro vydání .NET](https://releases.aspose.com/).

### Otázka: Jak mohu získat podporu, pokud během implementace narazím na nějaké problémy nebo mám dotazy?

 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za pomoc od komunity a týmu podpory Aspose.

### Otázka: Mohu generovat soubory XLSX pomocí Aspose.Tasks for .NET na platformách jiných než Windows?

Odpověď: Aspose.Tasks for .NET je primárně navržen pro platformy Windows, ale můžete prozkoumat možnosti kompatibility pro jiné platformy.

### Otázka: Jsou k dispozici nějaké dočasné licenční možnosti pro účely testování?

 Odpověď: Ano, můžete získat dočasnou licenci z[Stránka dočasné licence Aspose.Tasks](https://purchase.aspose.com/temporary-license/).