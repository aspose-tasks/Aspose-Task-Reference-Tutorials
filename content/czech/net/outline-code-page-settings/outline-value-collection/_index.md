---
title: Spravujte hodnoty osnovy MS Project pomocí Aspose.Tasks
linktitle: Sbírka hodnot osnovy v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se spravovat hodnoty osnovy v souborech Microsoft Project pomocí Aspose.Tasks for .NET. Výukový program krok za krokem s příklady kódu.
type: docs
weight: 17
url: /cs/net/outline-code-page-settings/outline-value-collection/
---
## Úvod
Aspose.Tasks for .NET poskytuje komplexní sadu funkcí pro interakci se soubory Microsoft Project. Jednou z takových funkcí je schopnost spravovat hodnoty osnovy v rámci projektu. V tomto tutoriálu prozkoumáme, jak shromažďovat a manipulovat s hodnotami osnovy pomocí Aspose.Tasks for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Aspose.Tasks for .NET: Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Ujistěte se, že máte nainstalované vhodné IDE, jako je Visual Studio.
3. Základní znalost C#: Výhodou bude znalost programovacího jazyka C#.
## Importovat jmenné prostory
Do souboru kódu C# importujte potřebné jmenné prostory pro přístup ke třídám a metodám Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Rozdělme poskytnutý příklad do několika kroků:
## Krok 1: Načtěte soubor projektu
 Nejprve inicializujte a`Project` objekt načtením existujícího souboru Microsoft Project:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Krok 2: Vymažte existující obrysové hodnoty
Dále z projektu vymažte všechny existující hodnoty osnovy:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Krok 3: Definujte nový kód osnovy
Nyní definujte nový kód osnovy s popisem a hodnotou:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Krok 4: Aktualizujte hodnotu osnovy
Aktualizujte hodnotu kódu osnovy:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Krok 5: Iterujte přes obrysové hodnoty
Iterujte hodnoty osnovy a vytiskněte jejich podrobnosti:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Krok 6: Manipulujte s hodnotami osnovy
Podle potřeby proveďte operace, jako je odebírání, vkládání a kopírování hodnot osnovy:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Závěr
tomto tutoriálu jsme se naučili pracovat s hodnotami osnovy v souborech Microsoft Project pomocí Aspose.Tasks for .NET. Dodržováním uvedených kroků můžete efektivně spravovat hodnoty osnovy ve svých projektech, což umožňuje větší kontrolu a flexibilitu.
## FAQ
### Otázka: Mohu současně manipulovat s více kódy osnovy?
Odpověď: Ano, můžete definovat a manipulovat s více kódy osnovy v rámci projektu pomocí Aspose.Tasks.
### Otázka: Je Aspose.Tasks kompatibilní s různými verzemi souborů Microsoft Project?
Odpověď: Ano, Aspose.Tasks podporuje různé verze souborů Microsoft Project, včetně formátů MPP a XML.
### Otázka: Jak mohu řešit chyby při práci s hodnotami osnovy?
Odpověď: Můžete implementovat mechanismy zpracování chyb, jako jsou bloky try-catch, abyste mohli ladně spravovat výjimky.
### Otázka: Mohu upravit vzhled hodnot osnovy v mém projektu?
Odpověď: Ano, Aspose.Tasks poskytuje rozsáhlá rozhraní API pro přizpůsobení vzhledu a chování hodnot osnovy podle vašich požadavků.
### Otázka: Kde najdu další zdroje a podporu pro Aspose.Tasks?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za podporu komunity a prozkoumejte[dokumentace](https://reference.aspose.com/tasks/net/) pro podrobné informace o API a funkcích.