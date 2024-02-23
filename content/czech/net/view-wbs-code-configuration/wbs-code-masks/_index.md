---
title: Konfigurace kódu WBS krok za krokem v Aspose.Tasks .NET
linktitle: Nakonfigurujte masky kódu WBS v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte krok za krokem konfiguraci WBS Code Masks v projektech .NET pomocí Aspose.Tasks. Vylepšete možnosti řízení projektů bez námahy.
type: docs
weight: 14
url: /cs/net/view-wbs-code-configuration/wbs-code-masks/
---
## Úvod
Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům efektivně manipulovat s daty projektového řízení v aplikacích .NET. V tomto tutoriálu prozkoumáme proces konfigurace masky kódu WBS (Work Breakdown Structure) pomocí Aspose.Tasks.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Tasks for .NET Library: Stáhněte a nainstalujte knihovnu z[Aspose.Tasks pro dokumentaci .NET](https://reference.aspose.com/tasks/net/).
- Vývojové prostředí: Ujistěte se, že máte nastavené funkční vývojové prostředí .NET.
- Adresář dokumentů: Vyberte adresář ve vašem systému, do kterého budou uloženy soubory projektu.
## Importovat jmenné prostory
Ve svém projektu .NET zahrňte potřebné jmenné prostory pro práci s Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Krok 1: Vytvořte instanci projektu
Začněte vytvořením nové instance projektu:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Krok 2: Definujte definici kódu WBS
Nastavte definici kódu WBS pro váš projekt:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Krok 3: Přidejte masky kódu WBS
Definujte masky kódu WBS a přidejte je do projektu:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Krok 4: Vytvořte úkoly
Přidejte úkoly do projektu:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Krok 5: Přepočítat
Přepočítejte projekt, abyste zajistili správné použití kódů WBS:
```csharp
project.Recalculate();
```
## Krok 6: Zobrazte informace o masce WBS
Výstup informací o maskách WBS do konzole:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Krok 7: Uložte projekt
Uložte projekt s přidanými kódy WBS:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Gratulujeme! Úspěšně jste nakonfigurovali masky kódu WBS ve svém projektu Aspose.Tasks.
## Závěr
V tomto tutoriálu jsme prozkoumali krok za krokem proces konfigurace masky kódu WBS pomocí Aspose.Tasks pro .NET. Tato výkonná knihovna poskytuje vývojářům bezproblémový způsob, jak zlepšit možnosti řízení projektů v rámci jejich aplikací .NET.

## FAQ
### Mohu používat Aspose.Tasks zdarma?
 Aspose.Tasks nabízí bezplatnou zkušební verzi, kterou si můžete stáhnout[tady](https://releases.aspose.com/).
### Kde najdu další podporu?
 navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)za podporu komunity.
### Jak mohu získat dočasnou licenci?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Je k dispozici podrobná dokumentace?
 Ano, kompletní dokumentace je k dispozici[tady](https://reference.aspose.com/tasks/net/).
### Kde mohu zakoupit Aspose.Tasks?
 Nákup Aspose.Tasks[tady](https://purchase.aspose.com/buy).