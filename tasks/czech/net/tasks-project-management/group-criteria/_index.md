---
title: Manipulace s kritérii skupiny MS Project v Aspose.Tasks
linktitle: Skupinová kritéria v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Prozkoumejte, jak programově manipulovat se soubory MS Project v .NET pomocí Aspose.Tasks. Získejte podrobné příklady informací o skupinách úkolů a kritériích.
type: docs
weight: 27
url: /cs/net/tasks-project-management/group-criteria/
---
## Úvod
Aspose.Tasks for .NET je výkonné API, které usnadňuje práci se soubory Microsoft Project ve vašich aplikacích .NET. Ať už vyvíjíte software pro řízení projektů nebo potřebujete manipulovat s daty projektu programově, Aspose.Tasks nabízí komplexní sadu funkcí, které splní vaše potřeby.
## Předpoklady
Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:
### 1. Znalost C# a .NET Framework
Pro pochopení a implementaci příkladů uvedených v tomto kurzu je nezbytná znalost programovacího jazyka C# a .NET Framework.
### 2. Instalace Aspose.Tasks pro .NET
 Ujistěte se, že máte ve vývojovém prostředí nainstalovaný Aspose.Tasks for .NET. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/tasks/net/) a postupujte podle dodaných pokynů k instalaci.
### 3. Integrované vývojové prostředí (IDE)
Mějte na svém systému nainstalované IDE, jako je Visual Studio, pro psaní a spouštění kódu C#.

## Importovat jmenné prostory
Chcete-li začít, importujte potřebné jmenné prostory do kódu C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Načtěte soubor Microsoft Project
Nejprve zadejte cestu k souboru Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Nahradit`"Your Document Directory"` s cestou k souboru vašeho projektu.
## Krok 2: Načtěte informace o skupinách úkolů
Dále načtěte informace o skupinách úkolů v projektu:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Tento fragment kódu vytiskne celkový počet skupin úkolů, načte druhou skupinu úkolů, její název a počet kritérií, která obsahuje.
## Krok 3: Načtěte informace o kritériu skupiny úkolů
Nyní se pojďme ponořit do podrobností o konkrétním kritériu v rámci skupiny úkolů:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Tento segment zobrazuje různé vlastnosti kritéria, jako je jeho index, pole, informace o seskupení, barva buňky, barva písma, interval skupiny a počáteční bod.
## Krok 4: Načtěte informace o písmu Criterion
Nakonec získejte podrobnosti o kritériu související s písmem:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Tento krok vytiskne název písma, velikost, styl a to, zda je kritérium seřazeno vzestupně nebo sestupně.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak používat Aspose.Tasks for .NET k načtení informací o skupinách úkolů a kritériích ze souboru aplikace Microsoft Project. Dodržováním tohoto podrobného průvodce můžete efektivně pracovat s projektovými daty programově ve svých aplikacích .NET.
## FAQ
### Dokáže Aspose.Tasks zpracovat velké soubory Microsoft Project?
Aspose.Tasks je optimalizována tak, aby efektivně zpracovávala velké projektové soubory a zajistila vysoký výkon a spolehlivost.
### Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?
Ano, Aspose.Tasks podporuje různé verze Microsoft Project a zajišťuje kompatibilitu napříč různými formáty souborů.
### Mohu manipulovat s daty projektu pomocí Aspose.Tasks?
Aspose.Tasks rozhodně poskytuje rozsáhlé funkce pro manipulaci s projektovými daty, včetně úkolů, zdrojů, kalendářů a dalších.
### Nabízí Aspose.Tasks podporu pro různé platformy .NET?
Ano, Aspose.Tasks podporuje více platforem .NET včetně .NET Framework, .NET Core a .NET Standard.
### Existuje komunitní fórum pro Aspose.Tasks, kde mohu vyhledat pomoc?
 Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) klást otázky, sdílet znalosti a spolupracovat s ostatními uživateli.