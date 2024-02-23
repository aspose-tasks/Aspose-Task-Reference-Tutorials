---
title: Projektgyűjtemények kezelése az Aspose.Tasks-ban
linktitle: Csoportgyűjtemény kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg az MS Project gyűjtemények hatékony kezelését az Aspose.Tasks for .NET használatával. Kövesse lépésenkénti útmutatónkat.
type: docs
weight: 26
url: /hu/net/tasks-project-management/group-collection/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan kezelhetjük a csoportos MS Project gyűjteményeket az Aspose.Tasks for .NET használatával. A csoportos gyűjtemények kezelése kulcsfontosságú a feladatok és erőforrások hatékony szervezéséhez és kezeléséhez a projekten belül.
## Előfeltételek
Mielőtt folytatná ezt az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Aspose.Tasks for .NET Library: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a[letöltési link](https://releases.aspose.com/tasks/net/).
2. Alapvető C# ismerete: Ismerkedjen meg a C# programozási nyelv alapjaival, mivel ez az oktatóanyag C# nyelvű kódolást tartalmaz.
3. Fejlesztői környezet: Hozzon létre egy fejlesztői környezetet, például a Visual Studio-t vagy bármely más IDE-t, amely támogatja a .NET fejlesztést.

## Névterek importálása
Először is importáljuk a szükséges névtereket az Aspose.Tasks funkciókkal való együttműködéshez a C# kódunkban.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 1. lépés: Töltse be a projektet
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Ez a lépés magában foglalja az MS Project fájl betöltését az Aspose.Tasks projektobjektumba, lehetővé téve, hogy műveleteket hajtsunk végre rajta.
## 2. lépés: Ismételje meg a feladatcsoportokat
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
Itt ismételgetjük a projekten belüli feladatcsoportokat, és az egyes csoportok menüjében olyan részleteket nyomtatunk, mint az index, a név és a láthatóság.
## 3. lépés: Ismételje meg az erőforráscsoportokat
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Hasonlóképpen, ez a lépés ismétlődik az erőforráscsoportokon, és megjeleníti azok indexét, nevét és láthatóságát a menüben.
## 4. lépés: Csoportok törlése és másolása egy másik projektbe
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Törölje a többi projektcsoportot
otherProject.TaskGroups.Clear();
// Csoportok másolása másik projektbe
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Itt töröljük egy másik projekt csoportjait, majd átmásoljuk a csoportokat az eredeti projektből.
## 5. lépés: Adjon hozzá egyéni feladatcsoportot
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
Ebben a lépésben létrehozunk egy egyéni feladatcsoportot, és hozzáadjuk a másik projekthez, ha még nincs jelen.
## 6. lépés: Távolítsa el az összes csoportot
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Végül eltávolítjuk az összes csoportot a másik projektből.

## Következtetés
A csoportos MS Project gyűjtemények kezelése az Aspose.Tasks for .NET-ben elengedhetetlen a projektadatok hatékony rendszerezéséhez és kezeléséhez. Az oktatóanyagban ismertetett lépések követésével hatékonyan kezelheti a projekteken belüli feladat- és erőforráscsoportokat, javítva ezzel az általános projektmenedzsmentet.
## GYIK
### Az Aspose.Tasks for .NET kompatibilis az MS Project összes verziójával?
Az Aspose.Tasks for .NET támogatja a Microsoft Project különféle verzióit, köztük a 2003-as, 2007-es, 2010-es, 2013-as, 2016-os és 2019-es verziókat.
### Testreszabhatom a csoport tulajdonságait az Aspose.Tasks for .NET használatával?
Igen, személyre szabhatja a csoport tulajdonságait, például a nevet és a láthatóságot az Aspose.Tasks for .NET segítségével.
### Az Aspose.Tasks for .NET kínál platformok közötti kompatibilitást?
Az Aspose.Tasks for .NET elsősorban a .NET-keretrendszert célozza meg, de használható platformok közötti forgatókönyvekben a .NET Core és a .NET Standard használatával.
### Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?
 Az Aspose.Tasks for .NET-hez a következőn keresztül kaphat támogatást[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
### Elérhető az Aspose.Tasks .NET-hez próbaverziója?
 Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját .NET-hez a webhelyről[weboldal](https://releases.aspose.com/).