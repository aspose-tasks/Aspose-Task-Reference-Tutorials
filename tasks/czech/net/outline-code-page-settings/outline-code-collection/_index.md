---
title: Kolekce MS Project osnovových kódů v Aspose.Tasks
linktitle: Kolekce kódů osnovy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se shromažďovat kódy osnovy Microsoft Project pomocí Aspose.Tasks for .NET. Tento obsáhlý tutoriál poskytuje pokyny krok za krokem.
weight: 11
url: /cs/net/outline-code-page-settings/outline-code-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kolekce MS Project osnovových kódů v Aspose.Tasks

## Úvod
V tomto tutoriálu prozkoumáme, jak shromáždit obrysové kódy Microsoft Project pomocí Aspose.Tasks for .NET. Abychom zajistili srozumitelnost a porozumění, celý proces rozdělíme na pokyny krok za krokem.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Visual Studio: Nainstalujte Visual Studio do svého systému.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost programování v C#: Prospěšná bude znalost C#.

## Importovat jmenné prostory
Nejprve importujte potřebné jmenné prostory pro přístup k funkci Aspose.Tasks ve vašem projektu C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Krok 1: Načtěte soubor projektu
 Začněte načtením souboru Microsoft Project pomocí`Project` třída.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Krok 2: Sbírejte kódy osnovy
Vytvořte kolektor pro shromažďování kódů osnovy z úkolů projektu.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Krok 3: Projděte úkoly a osnovy kódů
Procházejte shromážděné úkoly a obrysové kódy a vytiskněte jejich podrobnosti.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Krok 4: Přidejte vlastní definici kódu osnovy
Přidejte do projektu vlastní definici kódu osnovy.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Krok 5: Vytvořte a vložte kód osnovy
Vytvořte kód osnovy a vložte jej do úkolu.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Krok 6: Manipulujte s obrysovými kódy
S obrysovými kódy manipulujte podle potřeby, jako je vkládání, odebírání nebo mazání.
```csharp
// Příklad manipulace
// ...
// Vložte kód s 2 na správné místo
task.OutlineCodes.Insert(2, code2);
// Zkontrolujte, zda byl kód vložen
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Závěr
tomto tutoriálu jsme se naučili shromažďovat kódy osnovy Microsoft Project pomocí Aspose.Tasks for .NET. Dodržováním těchto kroků můžete efektivně spravovat kódy osnovy ve svých projektech, čímž se zlepší organizace a přehlednost.
## FAQ
### Otázka: Mohu používat Aspose.Tasks pro .NET s jinými programovacími jazyky?
Odpověď: Ano, Aspose.Tasks for .NET primárně cílí na platformu .NET, ale také poskytuje podporu pro další programovací jazyky prostřednictvím Aspose.Tasks for Cloud.
### Otázka: Existují nějaká omezení velikosti souborů projektu, které Aspose.Tasks for .NET dokáže zpracovat?
Odpověď: Aspose.Tasks for .NET dokáže efektivně zpracovat velké soubory projektu, ale výkon se může lišit v závislosti na složitosti a velikosti souboru.
### Otázka: Je Aspose.Tasks for .NET kompatibilní s nejnovějšími verzemi Microsoft Project?
Odpověď: Ano, Aspose.Tasks for .NET podporuje různé verze Microsoft Project, včetně těch nejnovějších.
### Otázka: Mohu přizpůsobit výstupní formát při práci s Aspose.Tasks pro .NET?
Odpověď: Aspose.Tasks for .NET samozřejmě poskytuje rozsáhlé možnosti přizpůsobení výstupního formátu podle vašich požadavků.
### Otázka: Kde najdu další podporu nebo zdroje pro Aspose.Tasks pro .NET?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakoukoli pomoc nebo dotazy týkající se Aspose.Tasks for .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
