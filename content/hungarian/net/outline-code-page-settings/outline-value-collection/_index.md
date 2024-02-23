---
title: Kezelje az MS Project Outline értékeket az Aspose.Tasks segítségével
linktitle: Vázlati értékek gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a vázlatértékeket a Microsoft Project fájlokban az Aspose.Tasks for .NET segítségével. Lépésről lépésre bemutató oktatóprogram kódpéldákkal.
type: docs
weight: 17
url: /hu/net/outline-code-page-settings/outline-value-collection/
---
## Bevezetés
Az Aspose.Tasks for .NET szolgáltatások átfogó készletét kínálja a Microsoft Project fájlokkal való interakcióhoz. Az egyik ilyen funkció a vázlatértékek kezelésének képessége egy projekten belül. Ebben az oktatóanyagban megvizsgáljuk, hogyan gyűjthet össze és kezelhet körvonalértékeket az Aspose.Tasks for .NET segítségével.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Aspose.Tasks for .NET: A könyvtár letölthető innen[itt](https://releases.aspose.com/tasks/net/).
2. Fejlesztési környezet: Győződjön meg arról, hogy megfelelő IDE telepítve van, például a Visual Studio.
3. Alapszintű C# ismerete: A C# programozási nyelv ismerete előnyt jelent.
## Névterek importálása
A C# kódfájlba importálja a szükséges névtereket az Aspose.Tasks osztályok és metódusok eléréséhez:
```csharp
using Aspose.Tasks;
using System;

```
Bontsuk fel a megadott példát több lépésre:
## 1. lépés: Töltse be a projektfájlt
 Először inicializálja a`Project` objektumot egy meglévő Microsoft Project fájl betöltésével:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 2. lépés: Törölje a meglévő vázlatértékeket
Ezután törölje a meglévő vázlatértékeket a projektből:
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
## 3. lépés: Új vázlatkód meghatározása
Most határozzon meg egy új vázlatkódot leírással és értékkel:
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
## 4. lépés: Az Outline Value frissítése
Frissítse a körvonalkód értékét:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## 5. lépés: Ismételje meg a vázlatos értékeket
Ismételje meg a vázlatos értékeket, és nyomtassa ki a részleteket:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## 6. lépés: Manipulálja a vázlatértékeket
Szükség szerint hajtson végre olyan műveleteket, mint a vázlatértékek eltávolítása, beillesztése és másolása:
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
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan dolgozhatunk a Microsoft Project fájlokban található vázlatértékekkel az Aspose.Tasks for .NET használatával. A megadott lépések követésével hatékonyan kezelheti a vázlatértékeket projektjein belül, ami nagyobb irányítást és rugalmasságot tesz lehetővé.
## GYIK
### K: Manipulálhatok több vázlatkódot egyszerre?
V: Igen, az Aspose.Tasks segítségével több vázlatkódot is meghatározhat és kezelhet egy projekten belül.
### K: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok különféle verzióit, beleértve az MPP és XML formátumokat.
### K: Hogyan kezelhetem a hibákat a vázlatértékekkel való munka során?
V: A kivételek kecses kezelése érdekében hibakezelési mechanizmusokat, például try-catch blokkokat alkalmazhat.
### K: Testreszabhatom a vázlatértékek megjelenését a projektemben?
V: Igen, az Aspose.Tasks kiterjedt API-kat biztosít a vázlatértékek megjelenésének és viselkedésének testreszabásához az Ön igényei szerint.
### K: Hol találhatok további forrásokat és támogatást az Aspose.Tasks számára?
 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásért és fedezze fel a[dokumentáció](https://reference.aspose.com/tasks/net/) az API-kkal és funkciókkal kapcsolatos részletes információkért.