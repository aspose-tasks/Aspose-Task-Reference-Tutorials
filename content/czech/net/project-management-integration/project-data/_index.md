---
title: Zvládnutí projektových dat pomocí Aspose.Tasks
linktitle: Práce s daty projektu v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se manipulovat s daty Microsoft Project pomocí Aspose.Tasks v .NET. Snadno vytvářejte úkoly, přidávejte zdroje a ukládejte projekty.
type: docs
weight: 16
url: /cs/net/project-management-integration/project-data/
---
## Úvod
tomto tutoriálu prozkoumáme, jak pracovat s daty Microsoft Project pomocí knihovny Aspose.Tasks pro .NET. Aspose.Tasks poskytuje výkonné funkce pro manipulaci se soubory projektu, včetně vytváření úkolů, přidávání zdrojů, nastavení vlastností a ukládání projektů v různých formátech.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1.  Instalace knihovny Aspose.Tasks: Stáhněte a nainstalujte knihovnu Aspose.Tasks z[tady](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí .NET.
3. Základní znalost C#: Výhodou bude znalost programovacího jazyka C#.

## Importovat jmenné prostory
Než začnete pracovat s Aspose.Tasks, importujte do projektu potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Inicializujte objekt projektu
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Tento řádek inicializuje novou instanci souboru`Project` class, která představuje soubor Microsoft Project.
## Krok 2: Nastavte vlastnosti projektu
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Tyto řádky ukazují, jak nastavit vlastnosti projektu, jako je formát práce a režim vytváření úkolů.
## Krok 3: Přidání úkolů
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Zde je ke kořenové úloze projektu přidán nový úkol s názvem "Task 1".
## Krok 4: Nastavení vlastností úlohy
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Tyto řádky nastavují datum zahájení, trvání a datum ukončení pro „Úkol 1“.
## Krok 5: Přidání zdrojů
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Tato část ukazuje, jak přidat pracovní zdroj do projektu.
## Krok 6: Přiřazení zdrojů k úkolům
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Tyto řádky ukazují, jak přiřadit dříve přidaný pracovní zdroj k "Úkolu 1" s konkrétními daty zahájení, práce a ukončení.
## Krok 7: Uložení projektu
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Nakonec je projekt uložen ve formátu souboru Microsoft Project XML.

## Závěr
V tomto tutoriálu jsme se naučili pracovat s daty Microsoft Project pomocí knihovny Aspose.Tasks v .NET. Podle podrobného průvodce můžete manipulovat se soubory projektu, přidávat úkoly, zdroje, přiřazovat zdroje k úkolům a ukládat projekty v různých formátech.
## FAQ
### Otázka: Dokáže Aspose.Tasks zvládnout složité projektové struktury?
Odpověď: Ano, Aspose.Tasks poskytuje komplexní podporu pro složité projektové struktury, což vám umožňuje efektivně spravovat úkoly, zdroje a přiřazení.
### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi Microsoft Project?
Odpověď: Aspose.Tasks podporuje širokou škálu verzí Microsoft Project, což zajišťuje kompatibilitu v různých prostředích.
### Otázka: Mohu integrovat Aspose.Tasks s jinými knihovnami .NET?
Odpověď: Aspose.Tasks se bez problémů integruje s ostatními knihovnami .NET a poskytuje flexibilitu ve vašich vývojových projektech.
### Otázka: Nabízí Aspose.Tasks podporu pro algoritmy plánování projektů?
Odpověď: Ano, Aspose.Tasks obsahuje pokročilé plánovací algoritmy, které vám pomohou optimalizovat časové osy projektů a využití zdrojů.
### Otázka: Existuje komunitní fórum pro uživatele Aspose.Tasks?
 Odpověď: Ano, můžete najít užitečné zdroje a komunikovat s ostatními uživateli Aspose.Tasks na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).