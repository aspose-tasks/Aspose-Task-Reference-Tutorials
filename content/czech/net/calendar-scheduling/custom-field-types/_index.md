---
title: Vlastní typy polí v Aspose.Tasks
linktitle: Vlastní typy polí v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se pracovat s vlastními typy polí v Aspose.Tasks pro .NET. Podrobný průvodce s příklady kódu a často kladenými dotazy.
type: docs
weight: 23
url: /cs/net/calendar-scheduling/custom-field-types/
---
## Úvod

Vítejte v našem tutoriálu o práci s vlastními typy polí v Aspose.Tasks pro .NET! Aspose.Tasks je výkonná knihovna, která umožňuje vývojářům programově manipulovat se soubory Microsoft Project. V tomto tutoriálu se zaměříme na pochopení a využití vlastních typů polí, což je zásadní aspekt práce s projektovými daty.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

### 1. Visual Studio nainstalováno

Ujistěte se, že máte v systému nainstalované Visual Studio. Můžete si jej stáhnout z webu společnosti Microsoft.

### 2. Aspose.Tasks pro .NET

 V projektu Visual Studio musíte mít nainstalovanou knihovnu Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).

### 3. Základní znalost C#

Spolu s tímto tutoriálem je nezbytná znalost programovacího jazyka C#.

## Importovat jmenné prostory

Začněme importem potřebných jmenných prostorů do našeho projektu. Tento krok je nezbytný pro přístup ke třídám a metodám poskytovaným knihovnou Aspose.Tasks.

```csharp

```

Nyní si uvedený příklad rozdělíme do několika kroků a podrobně porozumíme každému kroku.

## Krok 1: Vytvořte objekt projektu

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Tento řádek vytvoří novou instanci souboru`Project` třídy a načte soubor projektu "Project2.mpp" ze zadaného adresáře.

## Krok 2: Definujte vlastní pole

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

 Zde definujeme vlastní pole typu`Text` pro úkoly. upřesňujeme`ExtendedAttributeTask.Text1` k označení umístění pole a zadání názvu vlastního pole, což je v tomto případě "MůjText".

## Krok 3: Přidejte definici vlastního pole do projektu

```csharp
project.ExtendedAttributes.Add(definition);
```

Nakonec přidáme definici vlastního pole do kolekce rozšířených atributů projektu.

## Závěr

V tomto tutoriálu jsme se naučili pracovat s vlastními typy polí v Aspose.Tasks pro .NET. Pochopení a využití vlastních polí je nezbytné pro efektivní správu projektových dat a přizpůsobení projektových souborů podle konkrétních požadavků.

## FAQ

### Q1: Mohu používat Aspose.Tasks s jinými frameworky .NET?

A1: Ano, Aspose.Tasks je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Standard.

### Q2: Je Aspose.Tasks vhodný pro aplikace na podnikové úrovni?

A2: Rozhodně! Aspose.Tasks poskytuje robustní funkce a vynikající podporu, takže je vhodný pro aplikace na podnikové úrovni.

### Q3: Podporuje Aspose.Tasks více formátů souborů projektu?

Odpověď 3: Ano, Aspose.Tasks podporuje různé formáty souborů projektu, včetně MPP, XML a HTML.

### Q4: Mohu manipulovat s daty zdrojů pomocí Aspose.Tasks?

Odpověď 4: Ano, Aspose.Tasks umožňuje manipulovat s daty úkolů i zdrojů v rámci souborů projektu.

### Q5: Existuje komunitní fórum pro uživatele Aspose.Tasks?

 A5: Ano, můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) komunikovat s ostatními uživateli a získat podporu od týmu Aspose.