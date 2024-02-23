---
title: Az MS Project Group kritériumainak manipulálása az Aspose.Tasks-ban
linktitle: Csoportkritériumok az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel, hogyan kezelheti programozottan az MS Project fájlokat .NET-ben az Aspose.Tasks használatával. Példák lépésről lépésre lekérni a feladatcsoport- és kritériuminformációkat.
type: docs
weight: 27
url: /hu/net/tasks-project-management/group-criteria/
---
## Bevezetés
Az Aspose.Tasks for .NET egy hatékony API, amely megkönnyíti a Microsoft Project fájlokkal való munkát a .NET-alkalmazásokban. Akár projektmenedzsment szoftvert fejleszt, akár programozottan kell manipulálnia a projektadatokat, az Aspose.Tasks szolgáltatások átfogó készletét kínálja az Ön igényeinek kielégítésére.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. C# és .NET Framework ismerete
A C# programozási nyelv és a .NET Framework ismerete elengedhetetlen az oktatóanyagban található példák megértéséhez és megvalósításához.
### 2. Az Aspose.Tasks telepítése .NET-hez
 Győződjön meg arról, hogy az Aspose.Tasks for .NET telepítve van a fejlesztői környezetében. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/tasks/net/) és kövesse a mellékelt telepítési utasításokat.
### 3. Integrált fejlesztési környezet (IDE)
A C# kód írásához és végrehajtásához telepítsen egy IDE-t, például a Visual Studio-t.

## Névterek importálása
A kezdéshez importálja a szükséges névtereket a C# kódba:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. lépés: Töltsön be egy Microsoft Project fájlt
Először adja meg a Microsoft Project fájl elérési útját:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 cserélje ki`"Your Document Directory"` a projektfájl elérési útjával.
## 2. lépés: A feladatcsoportok információinak lekérése
Ezután kérjen le információkat a projektben lévő feladatcsoportokról:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Ez a kódrészlet kinyomtatja a feladatcsoportok teljes számát, lekéri a második feladatcsoportot, annak nevét és a benne lévő feltételek számát.
## 3. lépés: A feladatcsoport kritériuminformációinak lekérése
Most pedig nézzük meg a feladatcsoporton belül egy adott kritérium részleteit:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Ez a szegmens a feltétel különféle tulajdonságait jeleníti meg, például indexét, mezőjét, csoportosítási információit, cellaszínt, betűszínt, csoportintervallumot és kezdőpontot.
## 4. lépés: A feltétel betűtípus-információinak lekérése
Végül szerezze be a feltétel betűtípussal kapcsolatos részleteit:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Ez a lépés kiírja a betűtípus nevét, méretét, stílusát és azt, hogy a feltétel növekvő vagy csökkenő sorrendben van-e rendezve.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan használható az Aspose.Tasks for .NET a feladatcsoportokkal és feltételekkel kapcsolatos információk lekérésére egy Microsoft Project fájlból. A lépésenkénti útmutató követésével hatékonyan dolgozhat a projektadatokkal programozottan a .NET-alkalmazásokban.
## GYIK
### Az Aspose.Tasks képes kezelni a nagy Microsoft Project fájlokat?
Az Aspose.Tasks a nagy projektfájlok hatékony kezelésére lett optimalizálva, így biztosítva a nagy teljesítményt és megbízhatóságot.
### Az Aspose.Tasks kompatibilis a Microsoft Project összes verziójával?
Igen, az Aspose.Tasks támogatja a Microsoft Project különféle verzióit, biztosítva a különböző fájlformátumok közötti kompatibilitást.
### Az Aspose.Tasks segítségével manipulálhatom a projektadatokat?
Természetesen az Aspose.Tasks kiterjedt funkciókat kínál a projektadatok, például feladatok, erőforrások, naptárak és egyebek kezeléséhez.
### Az Aspose.Tasks támogatja a különböző .NET platformokat?
Igen, az Aspose.Tasks több .NET-platformot támogat, beleértve a .NET-keretrendszert, a .NET Core-t és a .NET Standard-t.
### Létezik olyan közösségi fórum az Aspose.Tasks számára, ahol segítséget kérhetek?
 Igen, meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) kérdéseket feltenni, tudást megosztani és együttműködni más felhasználókkal.