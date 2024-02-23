---
title: Master Extended Attribute Definice MS Project v Aspose.Tasks
linktitle: Sbírka rozšířených definic atributů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se spravovat definice rozšířených atributů v aplikaci Microsoft Project pomocí Aspose.Tasks for .NET. Přizpůsobte a vylepšete svá projektová data bez námahy.
type: docs
weight: 14
url: /cs/net/tasks-project-management/extended-attribute-definition-collection/
---
## Úvod
V tomto tutoriálu prozkoumáme, jak pracovat s definicemi rozšířených atributů v aplikaci Microsoft Project pomocí Aspose.Tasks for .NET. Rozšířené atributy nabízejí flexibilní způsob přizpůsobení a vylepšení projektových dat a umožňují uživatelům přidávat další pole nad rámec standardních polí poskytovaných ve výchozím nastavení. S Aspose.Tasks můžete bez námahy spravovat tyto rozšířené atributy a přizpůsobit tak své potřeby projektového řízení.
## Předpoklady
Než budete pokračovat, ujistěte se, že máte nainstalovány následující předpoklady:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks pro knihovnu .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).

## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory pro přístup ke třídám a metodám Aspose.Tasks ve vašem projektu .NET. Následuj tyto kroky:
## Krok 1: Otevřete svůj projekt .NET
Otevřete svůj projekt .NET v preferovaném IDE, jako je Visual Studio.
## Krok 2: Přidejte jmenný prostor Aspose.Tasks
Chcete-li importovat jmenný prostor Aspose.Tasks, přidejte na začátek souboru kódu následující řádek:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Nyní si rozdělíme poskytnuté příklady kódu do několika kroků, abychom je mohli komplexně pochopit:
## Krok 1: Načtěte soubor projektu
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Krok 2: Vymažte existující definice rozšířených atributů (volitelné)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Krok 3: Vytvořte a přidejte definici rozšířeného atributu pro úlohu
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Krok 4: Iterujte přes rozšířené atributy úlohy
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Krok 5: Vytvořte a přidejte definici rozšířeného atributu pro zdroj
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Krok 6: Vložte definici rozšířeného atributu prostředku
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Krok 7: Odeberte rozšířený atribut podle indexu
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Závěr
tomto tutoriálu jsme probrali základy práce s rozšířenými definicemi atributů v aplikaci Microsoft Project pomocí Aspose.Tasks for .NET. Pomocí těchto kroků můžete efektivně spravovat a přizpůsobovat rozšířené atributy tak, aby vyhovovaly vašim požadavkům na řízení projektu.
## FAQ
### Otázka: Mohu upravit stávající definice rozšířených atributů?
Odpověď: Ano, můžete upravit stávající definice rozšířených atributů nebo vytvořit nové podle svých potřeb.
### Otázka: Jsou rozšířené atributy podporovány ve všech verzích aplikace Microsoft Project?
Odpověď: Ano, rozšířené atributy jsou podporovány ve většině verzí aplikace Microsoft Project, včetně nejnovějších.
### Otázka: Mohu použít rozšířené atributy k výpočtu vlastních polí?
Odpověď: Rozšířené atributy lze samozřejmě použít k výpočtu vlastních polí na základě specifických kritérií, která definujete.
### Otázka: Je Aspose.Tasks kompatibilní s jinými frameworky .NET?
A: Aspose.Tasks je kompatibilní s různými .NET frameworky, což zajišťuje flexibilitu a snadnou integraci.
### Otázka: Kde najdu další zdroje a podporu pro Aspose.Tasks?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro podporu a prozkoumání dokumentace[tady](https://reference.aspose.com/tasks/net/).