---
title: Sloupec zobrazení vlastního přiřazení v Aspose.Tasks
linktitle: Sloupec zobrazení vlastního přiřazení v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak přidat vlastní sloupce zobrazení přiřazení do Aspose.Tasks pro .NET, abyste zlepšili možnosti řízení projektů.
weight: 16
url: /cs/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sloupec zobrazení vlastního přiřazení v Aspose.Tasks

## Úvod

tomto tutoriálu prozkoumáme, jak přidat vlastní sloupce pro zobrazení přiřazení pomocí Aspose.Tasks for .NET. Vlastní sloupce poskytují flexibilitu a umožňují zobrazit další informace relevantní pro potřeby řízení vašeho projektu.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Základní znalost programovacího jazyka C#.
2.  Nainstalovaná knihovna Aspose.Tasks for .NET. Pokud ne, můžete si jej stáhnout[tady](https://releases.aspose.com/tasks/net/).
3. Integrované vývojové prostředí (IDE), jako je Visual Studio.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory pro přístup ke třídám a metodám potřebným pro vytváření vlastních sloupců zobrazení přiřazení:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Krok 1: Načtěte projekt

 Chcete-li začít, načtěte soubor projektu pomocí`Project` třída:

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Krok 2: Vytvořte možnosti uložení tabulky

 Dále vytvořte instanci`Spreadsheet2003SaveOptions` což nám umožňuje přizpůsobit sloupce zobrazení přiřazení:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Krok 3: Definujte vlastní sloupec

 Nyní definujte svůj vlastní sloupec vytvořením instance`AssignmentViewColumn`. Tato třída vyžaduje název sloupce, šířku a funkci delegáta pro převod dat přiřazení na text sloupce:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Krok 4: Přidejte vlastní sloupec do možností

Přidejte vlastní sloupec do kolekce sloupců zobrazení přiřazení možností uložení:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Krok 5: Iterujte přes přiřazení

Projděte každé přiřazení zdrojů v projektu a zobrazte text vlastního sloupce:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Krok 6: Uložte projekt s vlastními sloupci

Nakonec uložte projekt se sloupci zobrazení vlastního přiřazení:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak přidat vlastní sloupce zobrazení přiřazení pomocí Aspose.Tasks for .NET. Vlastní sloupce nabízejí flexibilitu při zobrazování dalších informací přizpůsobených požadavkům vašeho projektu a rozšiřují možnosti řízení projektů.

## FAQ

### Q1: Mohu do zobrazení přiřazení přidat více vlastních sloupců?

 A1: Ano, můžete přidat více vlastních sloupců vytvořením dalších instancí`AssignmentViewColumn` a přidat je do`Columns` sbírka.

### Q2: Jsou k dispozici předdefinované převodníky pro běžná pole přiřazení?

A2: Ano, Aspose.Tasks poskytuje předdefinované převodníky pro běžná pole přiřazení, což usnadňuje extrahování dat pro vlastní sloupce.

### Q3: Mohu přizpůsobit vzhled vlastních sloupců, jako je formátování textu nebo použití stylů?

Odpověď 3: Ano, vzhled vlastních sloupců můžete upravit úpravou vlastností, jako je šířka, písmo a zarovnání.

### Q4: Je možné odebrat výchozí sloupce ze zobrazení přiřazení?

 A4: Ano, výchozí sloupce můžete odstranit jejich vyloučením z`Columns` sběr nebo nastavení jejich šířky na nulu.

### Q5: Podporuje Aspose.Tasks export projektů do jiných formátů kromě tabulek s vlastními sloupci?

Odpověď 5: Ano, Aspose.Tasks podporuje export projektů do různých formátů, jako jsou PDF, HTML a XML, což umožňuje všestranné možnosti vykazování projektů.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
