---
title: Outline Code Definíciók gyűjteménye az Aspose.Tasks .NET-ben
linktitle: Outline Code Definíciók gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a vázlatkód-definíciókat a Microsoft Project dokumentumokban az Aspose.Tasks for .NET segítségével. A projektadatok kategorizálása könnyedén.
type: docs
weight: 13
url: /hu/net/outline-code-page-settings/outline-code-definition-collection/
---
## Bevezetés
Az Aspose.Tasks egy hatékony .NET-könyvtár, amelyet a Microsoft Project dokumentumok egyszerű és hatékony kezeléséhez terveztek. Egyik kulcsfontosságú jellemzője az a képesség, hogy vázlatkód-definíciókkal dolgozhat, lehetővé téve a felhasználók számára a projektadatok hatékony rendszerezését és kategorizálását. Ebben az oktatóanyagban megvizsgáljuk, hogyan dolgozhatunk vázlatkód-definíciókkal az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következőkkel:
1. A C# alapvető ismerete: A C# programozási nyelv ismerete előnyös lesz.
2. Visual Studio: Telepítse a Visual Studio-t vagy bármely más preferált C# fejlesztői környezetet.
3.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).

## Névterek importálása
A kezdéshez feltétlenül importálja a szükséges névtereket:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 1. lépés: Töltse be a Microsoft Project dokumentumot
Először töltsön be egy Microsoft Project dokumentumot a vázlatkód-definíciókkal való munka megkezdéséhez:
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## 2. lépés: Nyissa meg az Outline Code definícióit
Most pedig nézzük meg a vázlatkód-definíciókat a projekten belül:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## 3. lépés: Adjon hozzá egyéni vázlatkód-definíciókat
Egyéni vázlatkód-definíciókat a következőképpen adhat hozzá:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## 4. lépés: Módosítsa az Outline Code definícióit
A meglévő vázlatkód-definíciók egyszerű módosítása:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## 5. lépés: Távolítsa el az Outline Code definíciókat
Távolítsa el a vázlatkód-definíciókat, amikor már nincs rájuk szükség:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## 6. lépés: Mentse el a változtatásokat
Végül mentse el a változtatásokat a projektdokumentumban:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Következtetés
Összefoglalva, az Aspose.Tasks for .NET átfogó funkcionalitást biztosít a Microsoft Project dokumentumokban található vázlatkód-definíciók kezeléséhez. Az oktatóanyagban ismertetett lépések követésével hatékonyan manipulálhatja a vázlatkód-definíciókat a projektadatok hatékony rendszerezéséhez és kategorizálásához.
## GYIK
### K: Hozzáadhatok több vázlatkód-definíciót egyetlen projekthez?
 V: Igen, több vázlatkód-definíciót is hozzáadhat egy projekthez az Ön igényei alapján. Egyszerűen használja a`Add` módszert minden egyes felvenni kívánt definícióhoz.
### K: Eltávolítható az összes vázlatkód-definíció egy projektből egyszerre?
 V: Igen, az összes vázlatkód-definíciót törölheti a projektből a következővel`Clear` módszer.
### K: Mi történik, ha megpróbálok módosítani egy csak olvasható vázlatkód-definíciót?
V: Ha egy vázlatkód-definíció csak olvasható, nem tudja közvetlenül módosítani. Mielőtt bármilyen módosítást megkísérelne, ellenőriznie kell a csak olvasható állapotát.
### K: Van-e korlátozás a projekthez hozzáadható vázlatkód-definíciók számára?
V: Az Aspose.Tasks for .NET nem ír elő semmilyen konkrét korlátozást a projekthez hozzáadható vázlatkód-definíciók számára. Ha azonban sok definícióval dolgozik, vegye figyelembe a teljesítmény következményeit.
### K: Használhatok vázlatkód-definíciókat a feladatok egyéni kritériumok alapján történő csoportosítására?
V: Igen, a vázlatkód-definíciók lehetővé teszik a feladatok egyéni kritériumok alapján történő kategorizálását, rugalmasságot biztosítva a projektadatok rendszerezésében.## Teljes forráskód