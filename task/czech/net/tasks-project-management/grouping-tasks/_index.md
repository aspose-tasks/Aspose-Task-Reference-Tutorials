---
title: Efektivní seskupování úkolů MS Project s Aspose.Tasks
linktitle: Seskupování úkolů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se efektivně seskupovat úkoly Microsoft Project pomocí Aspose.Tasks for .NET.
type: docs
weight: 25
url: /cs/net/tasks-project-management/grouping-tasks/
---
## Úvod
Správa úloh v aplikaci Microsoft Project může být někdy náročná, zejména pokud jde o jejich efektivní organizaci. Aspose.Tasks for .NET nabízí komplexní řešení tím, že poskytuje funkce pro efektivní seskupování úkolů. V tomto tutoriálu prozkoumáme, jak seskupit úkoly MS Project pomocí Aspose.Tasks for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
1.  Knihovna Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí .NET.
3. Základní znalost C#: Výhodou bude znalost programovacího jazyka C#.

## Importovat jmenné prostory
Nejprve musíte do svého projektu C# importovat potřebné jmenné prostory, abyste mohli používat funkce Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Načtěte soubor MS Project
Začněte načtením souboru MS Project pomocí následujícího kódu:
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Krok 2: Přístup ke skupinám úkolů
Dále přistupme ke skupinám úkolů v rámci projektu:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## Krok 3: Načtěte informace o skupině
Nyní načtěte informace o skupině úkolů:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## Krok 4: Přístupová kritéria skupiny
Přístup ke kritériím nastaveným pro skupinu úkolů:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## Krok 5: Načtěte informace o kritériu
Získejte podrobné informace o každém kritériu:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
Pomocí následujících kroků můžete efektivně seskupovat úkoly MS Project pomocí Aspose.Tasks for .NET, čímž se zlepší organizace a správa dat vašeho projektu.

## Závěr
Na závěr, Aspose.Tasks for .NET poskytuje výkonné funkce pro seskupování úkolů MS Project, což umožňuje lepší organizaci a správu projektových dat. Podle kroků uvedených v tomto kurzu můžete efektivně využívat tyto funkce ve svých aplikacích .NET.
## FAQ
### Mohu seskupit úkoly na základě vlastních kritérií?
Ano, pomocí Aspose.Tasks for .NET můžete definovat vlastní kritéria pro seskupování úkolů podle vašich specifických požadavků.
### Podporuje Aspose.Tasks různé verze souborů MS Project?
Ano, Aspose.Tasks podporuje různé verze souborů MS Project, což zajišťuje kompatibilitu a bezproblémovou integraci.
### Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET od[tady](https://releases.aspose.com/).
### Mohu upravit vzhled seskupených úkolů?
Aspose.Tasks rozhodně poskytuje možnosti přizpůsobení vzhledu seskupených úkolů, včetně barev buněk, písem a stylů.
### Kde najdu podporu pro Aspose.Tasks pro .NET?
 Podporu a pomoc pro Aspose.Tasks pro .NET najdete v[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).