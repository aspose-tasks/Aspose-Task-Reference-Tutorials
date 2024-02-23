---
title: Pokročilé operace AND v Aspose.Tasks
linktitle: Pokročilé operace AND v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se provádět pokročilé operace AND v Aspose.Tasks pro .NET a efektivně filtrovat projektové úkoly na základě více kritérií.
type: docs
weight: 10
url: /cs/net/advanced-features/advanced-and-operation/
---
## Úvod

 V tomto tutoriálu se ponoříme do pokročilé operace AND v Aspose.Tasks for .NET, mocném nástroji pro správu úloh a projektů. Prozkoumáme, jak filtrovat projektové úkoly na základě více podmínek pomocí`Util.And` třída.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Základní znalost programovacího jazyka C#.
2.  Nainstalované Aspose.Tasks pro .NET. Pokud ne, můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
3. Integrované vývojové prostředí (IDE), jako je Visual Studio.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory do našeho projektu C#:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Krok 1: Inicializujte projekt a sbírejte úkoly

Začněte inicializací nového projektu Aspose.Tasks a shromážděním všech úkolů v něm:

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Krok 2: Definujte podmínky filtru

Dále definujte podmínky filtru. Pro tento příklad vytvoříme dvě podmínky: jednu pro filtrování souhrnných úkolů a druhou pro filtrování nenulových úkolů:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Krok 3: Kombinujte podmínky s operací AND

 Nyní zkombinujte podmínky pomocí`Util.And` třídy k vytvoření složené podmínky:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Krok 4: Použití podmínek a úloh filtrování

Použijte kombinovanou podmínku na shromážděné úkoly a podle toho je filtrujte:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Krok 5: Výstup filtrovaných úloh

Nakonec vytiskněte filtrované úkoly:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Zde lze provést další zpracování
}
```

## Závěr

 V tomto tutoriálu jsme se naučili, jak provádět pokročilé operace AND v Aspose.Tasks pro .NET. Kombinací podmínek pomocí`Util.And` třídy, můžeme úkoly efektivně filtrovat na základě více kritérií.

## FAQ

### Q1: Co je Aspose.Tasks pro .NET?

A: Aspose.Tasks for .NET je robustní API, které umožňuje vývojářům manipulovat se soubory Microsoft Project programově v aplikacích .NET.

### Q2: Mohu použít více než dvě podmínky pomocí Util.And?

Odpověď: Ano, Util.And lze použít ke kombinaci libovolného počtu podmínek k vytvoření komplexních kritérií filtrování.

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?

 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).

### Q4: Kde najdu dokumentaci pro Aspose.Tasks pro .NET?

 Odpověď: Můžete najít dokumentaci[tady](https://reference.aspose.com/tasks/net/).

### Q5: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

 Odpověď: Podporu můžete získat na fóru komunity Aspose.Tasks.[tady](https://forum.aspose.com/c/tasks/15).