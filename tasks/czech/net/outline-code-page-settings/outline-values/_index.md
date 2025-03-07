---
title: Zvládnutí hodnot osnovy MS Project pomocí Aspose.Tasks
linktitle: Správa hodnot osnovy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat hodnoty osnovy MS Project pomocí Aspose.Tasks pro .NET. Snadno přizpůsobte obrysy projektu.
weight: 16
url: /cs/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zvládnutí hodnot osnovy MS Project pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu prozkoumáme, jak spravovat hodnoty osnovy Microsoft Project pomocí knihovny Aspose.Tasks pro .NET. S Aspose.Tasks můžete snadno manipulovat s kódy osnovy, vytvářet nové hodnoty osnovy a upravovat osnovy projektu podle svých požadavků.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1.  Instalace Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí, jako je Visual Studio, s kompatibilitou s rozhraním .NET.
3. Základní porozumění programování v C#: Seznamte se se základy programovacího jazyka C#, protože C# budeme používat pro práci s knihovnou Aspose.Tasks.

## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do kódu C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Načtěte soubor projektu
```csharp
// Cesta k adresáři dokumentů.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Tento krok inicializuje nový objekt Project a načte soubor Microsoft Project ze zadaného adresáře.
## Krok 2: Definujte definice kódu osnovy
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Zde definujeme dva objekty OutlineCodeDefinition a přidáme je do kolekce OutlineCodes projektu.
## Krok 3: Definujte masku obrysu
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Tento krok nastaví OutlineMask pro definici kódu osnovy.
## Krok 4: Vytvořte obrysové hodnoty
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
V tomto kroku vytvoříme dva objekty OutlineValue a nastavíme jejich vlastnosti, jako je hodnota, ID hodnoty, typ, popis a stav sbalení.

## Závěr
Správa hodnot osnovy MS Project pomocí Aspose.Tasks pro .NET je s poskytovanými funkcemi přímočará. Podle kroků uvedených v tomto kurzu můžete efektivně manipulovat s kódy osnovy a hodnotami a přizpůsobit osnovy projektu podle svých potřeb.
## FAQ
### Otázka: Mohu používat Aspose.Tasks s jinými frameworky .NET?
Odpověď: Ano, Aspose.Tasks je kompatibilní s různými .NET frameworky, což zajišťuje flexibilitu ve vašem vývojovém prostředí.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi Aspose.Tasks z[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat podporu pro Aspose.Tasks?
 Odpověď: Pro podporu a pomoc můžete navštívit fórum Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks?
Odpověď: Ano, můžete si zakoupit dočasnou licenci pro Aspose.Tasks od[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Kde najdu podrobnou dokumentaci k Aspose.Tasks?
 Odpověď: Můžete se podívat na kompletní dostupnou dokumentaci[tady](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
