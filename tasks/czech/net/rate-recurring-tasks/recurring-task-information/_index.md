---
title: Extrahování informací o opakované úloze v Aspose.Tasks
linktitle: Extrahování informací o opakované úloze v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se extrahovat informace o opakujících se úkolech ze souborů MS Project pomocí Aspose.Tasks for .NET. Snadná integrace pro vývojáře .NET.
weight: 13
url: /cs/net/rate-recurring-tasks/recurring-task-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahování informací o opakované úloze v Aspose.Tasks

## Úvod
Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům pracovat se soubory Microsoft Project v jejich aplikacích .NET. V tomto tutoriálu prozkoumáme, jak extrahovat informace o opakujících se úkolech ze souborů MS Project pomocí Aspose.Tasks.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Základní znalost programovacího jazyka C#.
2. Visual Studio nainstalované ve vašem systému.
3.  Nainstalovaná knihovna Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
## Importovat jmenné prostory
Chcete-li začít, importujte potřebné jmenné prostory do kódu C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Nyní si příklad rozdělíme do několika kroků:
## Krok 1: Nastavte cestu k souboru projektu
```csharp
String DataDir = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` s cestou k vašemu souboru MS Project.
## Krok 2: Načtěte soubor MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Tento řádek inicializuje nový`Project` objekt načtením souboru MS Project určeného cestou.
## Krok 3: Přečtěte si opakující se informace o úkolech
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Přístup a zobrazení informací o opakujících se úkolech
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Podle potřeby pokračujte v zobrazování dalších informací o opakujících se úkolech
}
```
Tato smyčka prochází všemi úkoly v projektu a kontroluje, zda má každý úkol přidružené opakující se informace. Pokud ano, načte a zobrazí různé vlastnosti opakované úlohy, jako je datum zahájení, trvání, datum ukončení atd.
## Závěr
tomto tutoriálu jsme se naučili, jak extrahovat informace o opakujících se úkolech ze souborů MS Project pomocí Aspose.Tasks for .NET. S těmito znalostmi nyní můžete tuto funkcionalitu integrovat do svých aplikací .NET a pracovat s opakujícími se úkoly efektivněji.
## FAQ
### Otázka: Mohu upravit informace o opakujících se úlohách pomocí Aspose.Tasks for .NET?
Odpověď: Ano, informace o opakujících se úlohách můžete upravit programově pomocí poskytnutých rozhraní API.
### Otázka: Podporuje Aspose.Tasks jiné formáty souborů projektu kromě MS Project?
Odpověď: Ano, Aspose.Tasks podporuje různé formáty projektových souborů, jako je MPP, XML a CSV.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Otázka: Kde najdu dokumentaci k Aspose.Tasks pro .NET?
 Odpověď: Můžete najít dokumentaci[tady](https://reference.aspose.com/tasks/net/).
### Otázka: Jak mohu získat technickou podporu pro Aspose.Tasks pro .NET?
 Odpověď: Technickou podporu můžete získat na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
