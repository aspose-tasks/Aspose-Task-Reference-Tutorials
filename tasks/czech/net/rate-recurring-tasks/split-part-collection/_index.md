---
title: Sbírejte MS Project of Split Parts v Aspose.Tasks
linktitle: Kolekce rozdělených částí v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se shromažďovat rozdělené části v MS Project pomocí Aspose.Tasks for .NET. Tento komplexní návod vás provede procesem krok za krokem.
weight: 19
url: /cs/net/rate-recurring-tasks/split-part-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sbírejte MS Project of Split Parts v Aspose.Tasks

## Úvod
V tomto tutoriálu se ponoříme do toho, jak sbírat rozdělené části v MS Project pomocí Aspose.Tasks pro .NET. Rozdělení úkolů na části může být zásadním aspektem řízení projektu a Aspose.Tasks poskytuje pohodlné metody, jak to efektivně zvládnout.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Instalace Aspose.Tasks pro .NET: Ujistěte se, že jste nainstalovali Aspose.Tasks pro .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Základní znalost C#: Prospěšná bude znalost programovacího jazyka C#, protože budeme psát úryvky kódu v C#.

## Importovat jmenné prostory
Ve svém projektu C# zahrňte potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Krok 1: Nastavte svůj projekt
Nejprve vytvořte nový projekt ve vašem preferovaném IDE a ujistěte se, že Aspose.Tasks for .NET je správně odkazován.
## Krok 2: Inicializujte objekt projektu
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Inicializujte nový objekt Project s cestou k vašemu souboru MS Project.
## Krok 3: Načtěte úlohu a iterujte přes rozdělené části
```csharp
var task = project.RootTask.Children.GetById(1);
// Iterujte přes rozdělené části
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Načtěte úkol z projektu a iterujte jeho rozdělené části a vytiskněte si jejich data zahájení a ukončení.
## Krok 4: Získejte rozdělení částí podle indexu
```csharp
// Získejte díl podle indexu
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Získejte konkrétní rozdělenou část podle indexu a vytiskněte její počáteční datum.

## Závěr
Správa rozdělených částí v souborech MS Project může výrazně zvýšit efektivitu řízení projektů. Aspose.Tasks for .NET zjednodušuje tento proces tím, že poskytuje intuitivní rozhraní API pro bezproblémové zpracování rozdělených úloh.
## FAQ
### Otázka: Mohu úlohy dynamicky rozdělit za běhu?
Odpověď: Ano, úkoly můžete rozdělit programově pomocí Aspose.Tasks for .NET.
### Otázka: Podporuje Aspose.Tasks všechny verze souborů MS Project?
Odpověď: Aspose.Tasks podporuje různé verze souborů MS Project a zajišťuje kompatibilitu napříč různými platformami.
### Otázka: Je k dispozici zkušební verze pro testovací účely?
 Odpověď: Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/) pro hodnocení.
### Otázka: Jak mohu získat dočasné licence pro své projekty?
 Odpověď: Dočasné licence lze získat od[tady](https://purchase.aspose.com/temporary-license/) pro krátkodobé použití.
### Otázka: Kde mohu hledat pomoc nebo podporu ohledně Aspose.Tasks?
 Odpověď: Můžete navštívit fórum Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15)požádat o pomoc komunitu nebo tým podpory Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
