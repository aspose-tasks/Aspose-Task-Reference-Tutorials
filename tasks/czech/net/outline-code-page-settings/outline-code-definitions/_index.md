---
title: MS Project Outline Code Handling Definice v Aspose.Tasks
linktitle: Manipulace s definicemi kódu osnovy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak zacházet s definicemi kódu osnovy MS Project pomocí Aspose.Tasks pro .NET, čímž posílíte své aplikace pro řízení projektů.
type: docs
weight: 12
url: /cs/net/outline-code-page-settings/outline-code-definitions/
---
## Úvod
Microsoft Project je výkonný nástroj pro správu projektů a Aspose.Tasks for .NET poskytuje komplexní podporu pro programovou manipulaci se soubory projektů. Jedním ze základních aspektů projektového řízení je organizování úkolů pomocí osnovy kódů. V tomto tutoriálu prozkoumáme, jak zacházet s definicemi osnovy kódu MS Project pomocí Aspose.Tasks pro .NET.
## Předpoklady
Než se pustíme do implementace, ujistěte se, že máte následující předpoklady:
### 1. Instalace Aspose.Tasks pro .NET
 Ujistěte se, že jste ve svém vývojovém prostředí nainstalovali Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
### 2. Základní porozumění C# a .NET Framework
Seznamte se s programovacím jazykem C# a frameworkem .NET, protože tento tutoriál vyžaduje znalost C# na střední úrovni.
### 3. Integrované vývojové prostředí (IDE)
Mějte na svém systému nainstalované IDE, jako je Visual Studio, pro kódování a ladění.
## Importovat jmenné prostory
Než začneme kódovat, importujme potřebné jmenné prostory pro práci s Aspose.Tasks for .NET.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Nyní rozeberme poskytnutý příklad do několika kroků pro jasné pochopení.
## Krok 1: Načtěte soubor projektu
Nejprve musíme načíst soubor MS Project do naší aplikace.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Krok 2: Vytvořte definici kódu osnovy
Nyní vytvoříme novou definici kódu osnovy.
```csharp
var outline = new OutlineCodeDefinition();
```
## Krok 3: Nastavte číslo pole a název
Nastavte číslo pole a název pro kód osnovy.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## Krok 4: Nastavte GUID a další vlastnosti
Nastavte GUID a další vlastnosti kódu osnovy.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Krok 5: Přidejte obrysovou masku
Přidejte masku osnovy do kódu osnovy.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Krok 6: Nastavte další vlastnosti
Nastavte další vlastnosti kódu osnovy.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Krok 7: Přidejte obrysovou hodnotu
Nakonec do kódu osnovy přidejte hodnotu osnovy.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Závěr
V tomto tutoriálu jsme se naučili, jak zacházet s definicemi osnovy kódu MS Project pomocí Aspose.Tasks for .NET. Podle podrobného průvodce můžete efektivně manipulovat s kódy osnovy v souborech projektu programově.
## FAQ
### Q1: Mohu použít Aspose.Tasks pro .NET s různými verzemi souborů MS Project?
Odpověď: Ano, Aspose.Tasks for .NET podporuje různé verze souborů MS Project, včetně formátů MPP a XML.
### Q2: Je Aspose.Tasks for .NET kompatibilní s .NET Core?
Odpověď: Ano, Aspose.Tasks for .NET je kompatibilní s .NET Core, což vám umožňuje vyvíjet aplikace pro různé platformy.
### Q3: Mohu manipulovat s přiřazením prostředků pomocí Aspose.Tasks for .NET?
Odpověď: Ano, Aspose.Tasks for .NET poskytuje rozsáhlé funkce pro manipulaci s přiřazením zdrojů, včetně přidávání, aktualizace a odstraňování přiřazení.
### Q4: Podporuje Aspose.Tasks pro .NET čtení vlastních polí ze souborů MS Project?
Odpověď: Aspose.Tasks for .NET samozřejmě podporuje čtení a zápis vlastních polí, včetně obrysových kódů, ze souborů MS Project.
### Q5: Existuje komunitní fórum pro Aspose.Tasks pro .NET?
 Odpověď: Ano, můžete se připojit ke komunitnímu fóru pro Aspose.Tasks pro .NET[tady](https://forum.aspose.com/c/tasks/15) klást otázky, sdílet znalosti a spolupracovat s ostatními vývojáři.