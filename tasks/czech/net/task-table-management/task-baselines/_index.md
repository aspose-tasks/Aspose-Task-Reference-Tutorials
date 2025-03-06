---
title: Mastering Task Baselines v Aspose.Tasks pro .NET
linktitle: Práce se základními liniemi úkolů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak zacházet se základními liniemi úkolů v Aspose.Tasks pro .NET pomocí tohoto komplexního kurzu. Vylepšete své dovednosti projektového řízení ještě dnes!
weight: 16
url: /cs/net/task-table-management/task-baselines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering Task Baselines v Aspose.Tasks pro .NET

## Úvod
dynamickém světě projektového řízení je zásadní být organizovaný a informovaný. Aspose.Tasks for .NET poskytuje výkonné řešení pro manipulaci se základními liniemi úloh, které vám umožní efektivně přistupovat k cenným základním informacím. Tento průvodce vás krok za krokem provede celým procesem a zajistí, že každý koncept pochopíte srozumitelně.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Nastavení prostředí: Ujistěte se, že máte ve vývojovém prostředí nainstalovaný Aspose.Tasks for .NET. Pokud ne, můžete si jej stáhnout z[Dokumentace Aspose.Tasks](https://reference.aspose.com/tasks/net/).
- Základní znalost C#: Seznamte se se základy programovacího jazyka C#, protože tento tutoriál předpokládá základní porozumění.
- Integrované vývojové prostředí (IDE): Použijte preferované IDE, jako je Visual Studio, abyste mohli hladce pokračovat.
## Importovat jmenné prostory
Chcete-li začít, importujte potřebné jmenné prostory do svého projektu. Tím zajistíte, že budete mít přístup k funkci Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
```
Nyní rozdělíme poskytnutý příklad do několika kroků, které vás provedou zpracováním základních linií úkolů v Aspose.Tasks.
## Krok 1: Vytvořte projekt
```csharp
var project = new Project();
```
 Začněte inicializací nového projektu pomocí`Project` třída.
## Krok 2: Vytvořte úkol a nastavte základní plán
```csharp
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
```
 Přidejte úkol do projektu a nastavte jeho směrný plán pomocí`SetBaseline` metoda.
## Krok 3: Zobrazte základní informace o úkolu
```csharp
var baseline = task.Baselines.ToList()[0];
Console.WriteLine("Baseline Start: {0}", baseline.Start);
Console.WriteLine("Baseline duration: {0}", baseline.Duration);
Console.WriteLine("Baseline duration format: {0}", baseline.Duration.TimeUnit);
Console.WriteLine("Is it estimated duration?: {0}", baseline.EstimatedDuration);
Console.WriteLine("Baseline Finish: {0}", baseline.Finish);
```
Získejte a zobrazte klíčové informace o výchozím plánu úkolu, jako je čas zahájení, trvání a čas dokončení.
## Krok 4: Další podrobnosti základního plánu
```csharp
Console.WriteLine("Interim: {0}", baseline.Interim);
Console.WriteLine("Fixed Cost: {0}", baseline.FixedCost);
```
Prozkoumejte další podrobnosti, včetně toho, zda je výchozí stav prozatímním výchozím stavem a s tím související fixní náklady.
## Krok 5: Tisk časově uspořádaných dat
```csharp
Console.WriteLine("Number of timephased items: " + baseline.TimephasedData.Count);
foreach (var data in baseline.TimephasedData)
{
    Console.WriteLine(" Uid: " + data.Uid);
    Console.WriteLine(" Start: " + data.Start);
    Console.WriteLine(" Finish: " + data.Finish);
}
```
Pochopte časově uspořádaná data spojená se základním plánem úkolu a poskytněte přehled o různých časových osách projektu.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak zacházet se základními liniemi úkolů v Aspose.Tasks pro .NET. Tyto znalosti rozšíří vaše schopnosti projektového řízení a zajistí přesné sledování a plánování.
## Často kladené otázky
### Otázka: Mohu používat Aspose.Tasks s jinými frameworky .NET?
Odpověď: Aspose.Tasks je kompatibilní s více frameworky .NET a poskytuje flexibilitu ve vašem vývojovém prostředí.
### Otázka: Existuje komunitní fórum pro podporu Aspose.Tasks?
 Odpověď: Ano, můžete najít podporu a zapojit se do komunity na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Otázka: Jak mohu získat dočasnou licenci pro Aspose.Tasks?
 Návštěva[tady](https://purchase.aspose.com/temporary-license/)získat dočasnou licenci pro Aspose.Tasks.
### Otázka: Jsou k dispozici nějaké výukové programy mimo základní linie úkolů?
 A: Prozkoumejte[dokumentace](https://reference.aspose.com/tasks/net/) pro širokou škálu výukových programů o funkcích Aspose.Tasks.
### Otázka: Kde mohu zakoupit Aspose.Tasks pro .NET?
 A: Můžete si pohodlně zakoupit Aspose.Tasks[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
