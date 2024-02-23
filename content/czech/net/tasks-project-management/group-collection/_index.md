---
title: Správa kolekcí projektů v Aspose.Tasks
linktitle: Správa kolekce skupiny v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak efektivně spravovat kolekce MS Project pomocí Aspose.Tasks for .NET. Postupujte podle našeho podrobného průvodce.
type: docs
weight: 26
url: /cs/net/tasks-project-management/group-collection/
---
## Úvod
tomto tutoriálu prozkoumáme, jak spravovat skupinové kolekce MS Project pomocí Aspose.Tasks for .NET. Správa skupinových kolekcí je zásadní pro efektivní organizaci a manipulaci s úkoly a zdroji v rámci vašeho projektu.
## Předpoklady
Než budete pokračovat v tomto kurzu, ujistěte se, že máte následující předpoklady:
1.  Aspose.Tasks for .NET Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[odkaz ke stažení](https://releases.aspose.com/tasks/net/).
2. Základní znalost C#: Seznamte se se základy programovacího jazyka C#, protože tento tutoriál zahrnuje kódování v C#.
3. Vývojové prostředí: Nastavte vývojové prostředí, jako je Visual Studio nebo jakékoli jiné IDE, které podporuje vývoj .NET.

## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory pro práci s funkcemi Aspose.Tasks v našem kódu C#.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Krok 1: Načtěte projekt
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Tento krok zahrnuje načtení souboru MS Project do objektu projektu Aspose.Tasks, což nám umožňuje provádět s ním operace.
## Krok 2: Iterujte přes skupiny úkolů
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Zde iterujeme skupiny úkolů v rámci projektu a vytiskneme podrobnosti, jako je index, název a viditelnost v nabídce pro každou skupinu.
## Krok 3: Iterujte přes skupiny prostředků
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Podobně tento krok iteruje přes skupiny prostředků a zobrazuje jejich index, název a viditelnost v nabídce.
## Krok 4: Vymažte a zkopírujte skupiny do jiného projektu
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Vymazat skupiny ostatních projektů
otherProject.TaskGroups.Clear();
// Zkopírujte skupiny do jiného projektu
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Zde vymažeme skupiny jiného projektu a poté do něj zkopírujeme skupiny z původního projektu.
## Krok 5: Přidejte vlastní skupinu úkolů
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
V tomto kroku vytvoříme vlastní skupinu úkolů a přidáme ji do jiného projektu, pokud ještě není přítomna.
## Krok 6: Odeberte všechny skupiny
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Nakonec odstraníme všechny skupiny z druhého projektu.

## Závěr
Správa skupinových kolekcí MS Project v Aspose.Tasks pro .NET je nezbytná pro efektivní organizaci a manipulaci s daty projektu. Dodržováním kroků uvedených v tomto kurzu můžete efektivně pracovat se skupinami úkolů a zdrojů v rámci svých projektů a zlepšit tak celkové řízení projektu.
## FAQ
### Je Aspose.Tasks for .NET kompatibilní se všemi verzemi MS Project?
Aspose.Tasks for .NET podporuje různé verze Microsoft Project, včetně 2003, 2007, 2010, 2013, 2016 a 2019.
### Mohu upravit vlastnosti skupiny pomocí Aspose.Tasks for .NET?
Ano, vlastnosti skupiny, jako je název a viditelnost, můžete upravit pomocí Aspose.Tasks for .NET.
### Nabízí Aspose.Tasks for .NET kompatibilitu napříč platformami?
Aspose.Tasks for .NET primárně cílí na .NET framework, ale lze jej použít v multiplatformních scénářích s .NET Core a .NET Standard.
### Jak mohu získat podporu pro Aspose.Tasks pro .NET?
 Podporu pro Aspose.Tasks for .NET můžete získat prostřednictvím[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks for .NET z webu[webová stránka](https://releases.aspose.com/).