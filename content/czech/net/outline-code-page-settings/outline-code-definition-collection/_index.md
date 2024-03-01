---
title: Sbírka definic kódu osnovy v Aspose.Tasks .NET
linktitle: Sbírka definic kódu osnovy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se manipulovat s definicemi osnovy kódu v dokumentech Microsoft Project pomocí Aspose.Tasks for .NET. Snadná kategorizace dat vašeho projektu.
type: docs
weight: 13
url: /cs/net/outline-code-page-settings/outline-code-definition-collection/
---
## Úvod
Aspose.Tasks je výkonná knihovna .NET navržená pro snadnou a efektivní manipulaci s dokumenty Microsoft Project. Jednou z jeho klíčových funkcí je schopnost pracovat s obrysovými definicemi kódu, což uživatelům umožňuje efektivně organizovat a kategorizovat data projektu. V tomto tutoriálu prozkoumáme, jak pracovat s definicemi osnovy kódu pomocí Aspose.Tasks for .NET.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
1. Základní porozumění C#: Výhodou bude znalost programovacího jazyka C#.
2. Visual Studio: Nainstalujte Visual Studio nebo jakékoli jiné preferované vývojové prostředí C#.
3.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).

## Importovat jmenné prostory
Chcete-li začít, nezapomeňte importovat potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Krok 1: Načtěte dokument Microsoft Project
Nejprve načtěte dokument Microsoft Project a začněte pracovat s definicemi kódu osnovy:
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Krok 2: Přístup k definicím kódu osnovy
Nyní se podívejme na definice kódu osnovy v rámci projektu:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Krok 3: Přidejte vlastní definice kódu osnovy
Vlastní definice kódu osnovy můžete přidat následovně:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Krok 4: Upravte definice kódu osnovy
Snadno upravte stávající definice kódu osnovy:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Krok 5: Odstraňte definice kódu osnovy
Odstraňte definice kódu osnovy, když již nejsou potřeba:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Krok 6: Uložte změny
Nakonec uložte změny do projektového dokumentu:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Závěr
Závěrem lze říci, že Aspose.Tasks for .NET poskytuje komplexní funkce pro správu definic obrysového kódu v dokumentech Microsoft Project. Podle kroků uvedených v tomto kurzu můžete efektivně manipulovat s definicemi kódu osnovy a efektivně organizovat a kategorizovat data projektu.
## FAQ
### Otázka: Mohu přidat více definic kódu osnovy do jednoho projektu?
 Odpověď: Ano, do projektu můžete přidat více definic kódu osnovy na základě vašich požadavků. Jednoduše použijte`Add` metodu pro každou definici, kterou chcete zahrnout.
### Otázka: Je možné odstranit všechny definice kódu osnovy z projektu najednou?
 Odpověď: Ano, můžete vymazat všechny definice kódu osnovy z projektu pomocí`Clear` metoda.
### Otázka: Co se stane, když se pokusím upravit definici kódu osnovy pouze pro čtení?
Odpověď: Pokud je definice kódu osnovy pouze pro čtení, nebudete ji moci přímo upravit. Než se pokusíte o jakékoli úpravy, budete muset zkontrolovat jeho stav pouze pro čtení.
### Otázka: Existují nějaká omezení počtu definic kódu osnovy, které mohu přidat do projektu?
Odpověď: Aspose.Tasks for .NET neklade žádná konkrétní omezení na počet definic kódu osnovy, které můžete přidat do projektu. Při práci s velkým počtem definic však zvažte dopady na výkon.
### Otázka: Mohu použít definice kódu osnovy k seskupení úkolů na základě vlastních kritérií?
Odpověď: Ano, definice obrysového kódu vám umožňují kategorizovat úkoly na základě vlastních kritérií a poskytují flexibilitu při organizování projektových dat.## Kompletní zdrojový kód