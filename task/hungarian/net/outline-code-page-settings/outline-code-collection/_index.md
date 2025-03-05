---
title: Gyűjtemény MS Project of Outline Codes Aspose.Tasks
linktitle: Vázlatkódok gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan gyűjthet össze Microsoft Project vázlatkódokat az Aspose.Tasks for .NET használatával. Ez az átfogó oktatóanyag lépésről lépésre tartalmaz utasításokat.
type: docs
weight: 11
url: /hu/net/outline-code-page-settings/outline-code-collection/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan gyűjthetünk Microsoft Project vázlatkódokat az Aspose.Tasks for .NET használatával. A folyamatot lépésenkénti utasításokra bontjuk az egyértelműség és érthetőség érdekében.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Visual Studio: Telepítse a Visual Studio-t a rendszerére.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET webhelyet innen[itt](https://releases.aspose.com/tasks/net/).
3. C# programozás alapjai: A C# ismerete előnyös lesz.

## Névterek importálása
Először is importálja a szükséges névtereket az Aspose.Tasks funkció eléréséhez a C# projektben.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## 1. lépés: Töltse be a projektfájlt
 Kezdje a Microsoft Project fájl betöltésével a`Project` osztály.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## 2. lépés: Gyűjtse össze a körvonalkódokat
Hozzon létre egy gyűjtőt a projektfeladatok vázlatkódjainak összegyűjtéséhez.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## 3. lépés: Ismételje meg a feladatokat és a vázlatkódokat
Ismételje meg az összegyűjtött feladatokat és vázolja fel a kódokat, nyomtassa ki a részleteket.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## 4. lépés: Adjon hozzá egyéni vázlatkód-definíciót
Adjon hozzá egyéni vázlatkód-definíciót a projekthez.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## 5. lépés: Hozzon létre és illesszen be körvonalkódot
Hozzon létre egy vázlatkódot, és illessze be egy feladatba.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## 6. lépés: Manipulálja a körvonalkódokat
Szükség szerint módosítsa a vázlatkódokat, például beillesztheti, eltávolíthatja vagy törölheti.
```csharp
// Példa a manipulációra
// ...
// Helyezze be a kódot a 2-vel a megfelelő helyre
task.OutlineCodes.Insert(2, code2);
// Ellenőrizze, hogy a kód be lett-e helyezve
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan gyűjthetünk Microsoft Project vázlatkódokat az Aspose.Tasks for .NET segítségével. Ha követi ezeket a lépéseket, hatékonyan kezelheti a vázlatkódokat a projekteken belül, javítva a szervezettséget és az átláthatóságot.
## GYIK
### K: Használhatom az Aspose.Tasks for .NET programot más programozási nyelvekkel?
V: Igen, az Aspose.Tasks for .NET elsősorban a .NET platformot célozza meg, de az Aspose.Tasks for Cloudon keresztül más programozási nyelvekhez is támogatást nyújt.
### K: Vannak-e korlátozások az Aspose.Tasks for .NET által kezelhető projektfájlok méretére vonatkozóan?
V: Az Aspose.Tasks for .NET hatékonyan tudja kezelni a nagy projektfájlokat, de a teljesítmény a fájl összetettségétől és méretétől függően változhat.
### K: Az Aspose.Tasks for .NET kompatibilis a Microsoft Project legújabb verzióival?
V: Igen, az Aspose.Tasks for .NET támogatja a Microsoft Project különféle verzióit, beleértve a legújabbakat is.
### K: Testreszabhatom a kimeneti formátumot, amikor az Aspose.Tasks for .NET programmal dolgozom?
V: Természetesen az Aspose.Tasks for .NET kiterjedt lehetőségeket kínál a kimeneti formátum testreszabásához az Ön igényei szerint.
### K: Hol találok további támogatást vagy forrásokat az Aspose.Tasks for .NET-hez?
 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) az Aspose.Tasks for .NET-hez kapcsolódó segítségért vagy kérdésért.