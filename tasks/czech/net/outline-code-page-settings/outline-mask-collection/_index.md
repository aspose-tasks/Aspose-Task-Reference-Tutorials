---
title: Master MS Project obrysové masky s Aspose.Tasks
linktitle: Kolekce obrysových masek v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se manipulovat s maskami obrysu kolekce MS Project pomocí Aspose.Tasks for .NET. Zvyšte produktivitu pomocí tohoto komplexního návodu.
weight: 15
url: /cs/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master MS Project obrysové masky s Aspose.Tasks

## Úvod
Chcete využít sílu obrysových masek Microsoft Project pomocí Aspose.Tasks for .NET? Jste na správném místě! V tomto komplexním tutoriálu vás provedeme procesem krok za krokem a zajistíme, že získáte solidní znalosti o tom, jak efektivně manipulovat s maskami obrysu ve vašich projektech. Ať už jste zkušený vývojář nebo teprve začínáte, tato příručka vás vybaví znalostmi a dovednostmi potřebnými k optimalizaci vašeho pracovního postupu.
## Předpoklady
Než se pustíte do tohoto výukového programu, ujistěte se, že máte splněny následující předpoklady:
### 1. Instalace Aspose.Tasks pro .NET
Ujistěte se, že máte Aspose.Tasks for .NET nainstalované ve svém vývojovém prostředí. Knihovnu si můžete stáhnout z webu Aspose[tady](https://releases.aspose.com/tasks/net/).
### 2. Základní znalost C# a .NET Framework
Seznamte se s programovacím jazykem C# a rozhraním .NET Framework, protože tento tutoriál využije obojí.
### 3. Soubor Microsoft Project
Připravte si soubor Microsoft Project (MPP) pro účely testování. Pro experimentování můžete použít existující soubor nebo vytvořit nový.
## Importovat jmenné prostory
Začněme importem potřebných jmenných prostorů do vašeho projektu C#. Tento krok zajistí, že budete mít přístup k požadovaným třídám a funkcím poskytovaným Aspose.Tasks for .NET.

Na začátek souboru kódu přidejte následující jmenné prostory:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Nyní rozdělíme poskytnutý příklad do několika kroků a podrobně vysvětlíme každý krok:
## Krok 1: Inicializujte objekt projektu
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Zde vytvoříme novou instanci`Project` třídy a načtěte existující soubor Microsoft Project s názvem "OutlineValues2010.mpp".
## Krok 2: Přístup ke kódům osnovy
```csharp
var outline = project.OutlineCodes[0];
```
Přistupujeme k obrysovým kódům z projektu. Kódy osnovy jsou vlastní pole v aplikaci Microsoft Project, která umožňují kategorizovat a organizovat úkoly.
## Krok 3: Vymažte obrysové masky
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Tento krok zajistí, že všechny existující masky obrysu budou vymazány, než budete pokračovat dále.
## Krok 4: Vytvořte obrysové masky
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Vytváříme nové obrysové masky a určujeme jejich typy. V tomto příkladu vytvoříme platnou masku obrysu a jednu špatnou.
## Krok 5: Vložte a upravte masky
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Zde vložíme do kolekce špatnou masku a upravíme délku masky pomocí jejího indexu.
## Krok 6: Odstraňte masky
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Odebereme nesprávnou masku z kolekce na základě jejího indexu.
## Krok 7: Opakujte masky
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Tato smyčka iteruje přes každou masku obrysu v kolekci a vytiskne její vlastnosti, jako je délka, úroveň, oddělovač a typ.
## Krok 8: Zkopírujte masky do jiného projektu
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Nakonec zkopírujeme masky obrysu z jednoho projektu do druhého, čímž zajistíme konzistenci napříč různými projekty.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak manipulovat s maskami obrysu kolekce MS Project pomocí Aspose.Tasks pro .NET. Sledováním tohoto výukového programu jste nyní vybaveni dovednostmi pro efektivní správu masek obrysů ve vašich projektech, což v konečném důsledku zvýší vaši produktivitu a pracovní postup.
## FAQ
### Q1: Mohu použít Aspose.Tasks pro .NET s různými verzemi souborů aplikace?
Odpověď: Ano, Aspose.Tasks for .NET podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.
### Q2: Je Aspose.Tasks for .NET kompatibilní s .NET Core?
Odpověď: Ano, Aspose.Tasks for .NET je kompatibilní s .NET Core, což vám umožňuje používat jej v multiplatformních aplikacích.
### Q3: Mohu přizpůsobit vlastnosti obrysových masek podle požadavků mého projektu?
A: Rozhodně! Masky obrysu můžete přizpůsobit úpravou jejich délky, úrovně, oddělovače a typu tak, aby vyhovovaly vašim specifickým potřebám projektu.
### Q4: Poskytuje Aspose.Tasks pro .NET dokumentaci a podporu?
Odpověď: Ano, Aspose.Tasks for .NET nabízí komplexní dokumentaci a vyhrazenou podporu prostřednictvím svých webových stránek a[fórech](https://forum.aspose.com/c/tasks/15).
### Q5: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi Aspose.Tasks for .NET z jejich[webová stránka](https://releases.aspose.com/tasks/net/). prozkoumat jeho vlastnosti a funkce před nákupem.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
