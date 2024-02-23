---
title: Uložit soubory MS Project jako šablony pomocí Aspose.Tasks
linktitle: Uložit možnosti šablony pro Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se ukládat soubory Microsoft Project jako šablony pomocí Aspose.Tasks for .NET. Přizpůsobte nastavení šablony pro zjednodušené řízení projektů.
type: docs
weight: 18
url: /cs/net/saving-options/save-template-options/
---
## Úvod
tomto tutoriálu projdeme procesem uložení šablony pomocí Aspose.Tasks for .NET. Šablony jsou užitečné pro standardizaci projektových struktur a nastavení pro budoucí použití. Ukážeme si, jak uložit projekt jako šablonu, a přitom ladit jeho vlastnosti.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Aspose.Tasks for .NET Library: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Znalost programování v C#: K pochopení a implementaci poskytnutých úryvků kódu je nutná základní znalost programování v C#.
3. Soubor Microsoft Project: Připravte si soubor Microsoft Project (formát MPP), který chcete uložit jako šablonu.

## Importovat jmenné prostory
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Krok 1: Načtěte projekt
Nejprve musíme načíst soubor Microsoft Project (.mpp), který chceme uložit jako šablonu.
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Krok 2: Získejte informace o souboru projektu
Načte informace o načteném souboru projektu, jako je jeho formát.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Krok 3: Nakonfigurujte možnosti uložení šablony
Vytvořte možnosti uložení šablony a nakonfigurujte její vlastnosti podle svých požadavků. Tyto možnosti umožňují přizpůsobit, jaká data mají být ze šablony odstraněna.
```csharp
var options = new SaveTemplateOptions
{
	// Odstraňte všechny fixní náklady ze šablony projektu
	RemoveFixedCosts = true,
	// Odstraňte všechny skutečné hodnoty ze šablony projektu
	RemoveActualValues = true,
	// Odeberte sazby zdrojů ze šablony projektu
	RemoveResourceRates = true,
	// Odstraňte všechny základní hodnoty ze šablony projektu
	RemoveBaselineValues = true
};
```
## Krok 4: Uložte projekt jako šablonu
Uložte projekt jako šablonu se zadanými možnostmi.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Krok 5: Získejte informace o souboru šablony
Získejte informace o uloženém souboru šablony, jako je jeho formát.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Gratulujeme! Úspěšně jste uložili šablonu pomocí Aspose.Tasks for .NET a podle potřeby přizpůsobili její vlastnosti.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak uložit soubor Microsoft Project jako šablonu pomocí Aspose.Tasks for .NET. Šablony jsou cenné pro standardizaci projektových struktur a nastavení, zefektivnění tvorby budoucích projektů.
## FAQ
### Otázka: Mohu přizpůsobit, která data se mají ze šablony odstranit?
Odpověď: Ano, můžete nakonfigurovat možnosti Uložit šablonu tak, abyste odstranili konkrétní data, jako jsou fixní náklady, skutečné hodnoty, sazby zdrojů a výchozí hodnoty.
### Otázka: Je Aspose.Tasks for .NET kompatibilní se všemi verzemi Microsoft Project?
Odpověď: Aspose.Tasks for .NET poskytuje rozsáhlou kompatibilitu s různými verzemi Microsoft Project a zajišťuje bezproblémovou integraci a funkčnost.
### Otázka: Mohu použít šablony na existující projekty?
Odpověď: Ano, šablony můžete aplikovat na existující projekty načtením souboru šablony a jeho sloučením s aktuálním projektem podle potřeby.
### Otázka: Podporuje Aspose.Tasks for .NET vývoj napříč platformami?
A: Aspose.Tasks for .NET je primárně navržen pro aplikace .NET framework běžící na platformách Windows.
### Otázka: Je k dispozici technická podpora pro Aspose.Tasks pro .NET?
 Odpověď: Ano, technickou pomoc a pokyny můžete vyhledat od komunity Aspose.Tasks.[fórech](https://forum.aspose.com/c/tasks/15) nebo kontaktujte přímo jejich tým podpory.