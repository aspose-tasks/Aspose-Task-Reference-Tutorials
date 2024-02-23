---
title: Správa kolekce atributů MS Project v Aspose.Tasks
linktitle: Správa rozšířené kolekce atributů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se efektivně spravovat rozšířené atributy MS Project pomocí Aspose.Tasks for .NET. Bezproblémová manipulace s atributy úkolů pomocí podrobného vedení.
type: docs
weight: 12
url: /cs/net/tasks-project-management/extended-attribute-collection/
---
## Úvod
Hledáte efektivní správu rozšířených atributů MS Project pomocí Aspose.Tasks for .NET? V tomto tutoriálu vás provedeme procesem krok za krokem. Pojďme se ponořit!
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Visual Studio: Nainstalujte Visual Studio do svého systému.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Seznamte se se základy programovacího jazyka C#.

## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Načtěte soubor projektu
Nejprve načtěte soubor MS Project pomocí následujícího fragmentu kódu:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Krok 2: Přístup k úloze a rozšířeným atributům
Přístup ke konkrétní úloze a jejím rozšířeným atributům:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Krok 3: Vymažte rozšířené atributy
V případě potřeby vymažte stávající rozšířené atributy:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Krok 4: Vytvořte rozšířené definice atributů
Vytvořte definice pro nové rozšířené atributy:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Krok 5: Iterujte přes rozšířené atributy úlohy
Iterujte přes rozšířené atributy úlohy:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Krok 6: Přidejte rozšířené atributy
Přidejte k úloze nové rozšířené atributy:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Krok 7: Práce s rozšířenými atributy
Podle potřeby provádějte operace s rozšířenými atributy.
## Krok 8: Odeberte rozšířené atributy
Odeberte rozšířené atributy podle indexu nebo podmíněně:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Krok 9: Zkopírujte atributy do jiného úkolu
Zkopírujte atributy do jiného úkolu v rámci stejného nebo jiného projektu:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Závěr
Správa kolekcí rozšířených atributů MS Project je s Aspose.Tasks pro .NET bezproblémová. Dodržováním kroků popsaných v tomto kurzu můžete efektivně pracovat s rozšířenými atributy a vylepšit tak možnosti řízení projektů.
## FAQ
### Otázka: Mohu manipulovat s rozšířenými atributy ve více projektech?
Odpověď: Ano, můžete kopírovat rozšířené atributy mezi úkoly v různých projektech pomocí Aspose.Tasks for .NET.
### Otázka: Existují omezení počtu rozšířených atributů na úlohu?
Odpověď: Aspose.Tasks for .NET neukládá žádná vlastní omezení počtu rozšířených atributů na úlohu.
### Otázka: Mohu vytvořit vlastní pole rozšířených atributů?
A: Rozhodně! Aspose.Tasks for .NET vám umožňuje definovat vlastní pole rozšířených atributů přizpůsobená požadavkům vašeho projektu.
### Otázka: Podporuje Aspose.Tasks pro .NET čtení a zápis do souborů MS Project různých verzí?
Odpověď: Ano, Aspose.Tasks for .NET podporuje formáty souborů MS Project napříč různými verzemi.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).