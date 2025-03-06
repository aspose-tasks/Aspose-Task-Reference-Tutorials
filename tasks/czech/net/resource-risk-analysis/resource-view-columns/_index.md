---
title: Přizpůsobte si sloupce zobrazení zdrojů MS Project v Aspose.Tasks
linktitle: Přizpůsobení sloupců zobrazení zdrojů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně přizpůsobit sloupce zobrazení zdrojů MS Project pomocí Aspose.Tasks for .NET. Vytvářejte přizpůsobené pohledy pro lepší řízení projektů.
type: docs
weight: 17
url: /cs/net/resource-risk-analysis/resource-view-columns/
---
## Úvod
Aspose.Tasks for .NET je výkonné API, které umožňuje vývojářům pracovat se soubory Microsoft Project programově. Jedním z běžných úkolů při řízení projektů je přizpůsobení zobrazení tak, aby zobrazovaly konkrétní informace. V tomto tutoriálu prozkoumáme, jak přizpůsobit sloupce zobrazení prostředků MS Project pomocí Aspose.Tasks for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Aspose.Tasks for .NET Library: Můžete si ji stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Soubor Microsoft Project: Mějte po ruce vzorový soubor MS Project pro testování.
3. Vývojové prostředí: Vývojové prostředí nastavené s rámcem .NET.
## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory do našeho projektu:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Krok 1: Načtěte soubor projektu
Načtěte soubor MS Project pomocí Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Krok 2: Získejte zdroj a definujte možnosti
Dále získejte zdroj, jehož sloupce zobrazení chcete přizpůsobit, a definujte možnosti uložení PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Krok 3: Definujte vlastní sloupce
Nyní definujte vlastní sloupce pro zobrazení zdrojů. Můžete zadat různá pole a dokonce použít delegáty pro vlastní výpočty:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Krok 4: Iterujte přes sloupce
Iterujte definované sloupce a zobrazte jejich vlastnosti:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Krok 5: Uložte přizpůsobené zobrazení
Nakonec nastavte vlastní zobrazení a uložte jej jako soubor PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Pomocí následujících kroků můžete efektivně přizpůsobit sloupce zobrazení prostředků MS Project pomocí Aspose.Tasks for .NET.
## Závěr
Přizpůsobení sloupců zobrazení zdrojů MS Project je nezbytné pro zobrazení relevantních informací přizpůsobených potřebám vašeho projektu. S Aspose.Tasks for .NET se tento úkol stává přímočarým a efektivním a umožňuje vám snadno vytvářet přizpůsobená zobrazení.
## FAQ
### Mohu přizpůsobit zobrazení pro jiné prvky kromě zdrojů?
Ano, Aspose.Tasks umožňuje přizpůsobení úkolů, přiřazení a dalších prvků projektu.
### Podporuje Aspose.Tasks ukládání pohledů v jiných formátech než PDF?
Ano, pohledy můžete ukládat v různých formátech, jako jsou XLSX, HTML a obrázky.
### Je možné použít formátování na vlastní zobrazení?
Aspose.Tasks rozhodně poskytuje rozsáhlé možnosti formátování pro vylepšení vzhledu vašich přizpůsobených zobrazení.
### Mohu dynamicky aktualizovat vlastní zobrazení na základě změn dat projektu?
Ano, můžete aktualizovat a znovu vytvořit vlastní pohled, kdykoli se změní podkladová data projektu.
### Podporuje Aspose.Tasks vývoj napříč platformami?
Aspose.Tasks for .NET primárně cílí na platformy .NET, ale jsou k dispozici i verze pro Javu a další platformy.