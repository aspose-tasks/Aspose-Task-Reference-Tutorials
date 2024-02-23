---
title: A Baseline Collection használata az Aspose.Tasks programban
linktitle: A Baseline Collection használata az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az Aspose.Tasks for .NET alapvonalait. Kövesse átfogó oktatóanyagunkat a lépésről lépésre történő útmutatásért.
type: docs
weight: 20
url: /hu/net/advanced-features/working-with-baseline-collection/
---
## Bevezetés

Az Aspose.Tasks for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak Microsoft Project fájlokkal .NET-alkalmazásaikban. Számos funkciója mellett erőteljes támogatást nyújt a projekteken belüli alapvonalak kezeléséhez. Az alapértékek elengedhetetlenek a projektmenedzsmenthez, mivel lehetővé teszik az eredeti projektterv és a jelenlegi állapot összehasonlítását, lehetővé téve a projekt előrehaladásának jobb nyomon követését és elemzését.

## Előfeltételek

Mielőtt belevetnénk magunkat az Aspose.Tasks alapszintű gyűjteményeivel való munkába, győződjön meg arról, hogy a következő előfeltételekkel rendelkezik:

1. Visual Studio: Telepítse a Visual Studio IDE-t a rendszerére.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a[letöltési link](https://releases.aspose.com/tasks/net/).
3. A C# alapjai: Ismerkedjen meg a C# programozási nyelvvel.
4. Microsoft Project fájl: Készítsen tesztelési célból egy Microsoft Project fájlt (.mpp).

## Névterek importálása

Az Aspose.Tasks alapszintű gyűjteményeivel való munka megkezdéséhez importálnia kell a következő névtereket:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Most bontsuk le az egyes példákat több lépésre:

## 1. lépés: Töltse be a projektfájlt

Először töltse be a Microsoft Project fájlt az Aspose.Tasks segítségével:

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 2. lépés: Erőforrás beszerzése

Ezután kérje le a kívánt erőforrást a projektből:

```csharp
var resource = project.Resources.GetByUid(1);
```

## 3. lépés: Jelenítse meg az alapinformációkat

Most jelenítsen meg információkat az erőforráshoz társított alapvonalakról:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 4. lépés: Ismétlés az alapvonalakon keresztül

Ismételje meg az erőforráshoz kapcsolódó minden alapvonalat, és nyomtassa ki a vonatkozó információkat:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 5. lépés: Távolítsa el az alapvonalakat

Törölje az erőforráshoz társított összes alapvonalat:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan dolgozhatunk az Aspose.Tasks for .NET alapszintű gyűjteményeivel. A lépésenkénti útmutató követésével könnyedén kezelheti a .NET-alkalmazások alapértékeit, ami lehetővé teszi a projektek hatékony nyomon követését és elemzését.

## GYIK

### 1. kérdés: Az Aspose.Tasks képes kezelni a nagy projektfájlokat?

1. válasz: Igen, az Aspose.Tasks a nagy projektfájlok hatékony kezelésére van optimalizálva, így biztosítva a zökkenőmentes teljesítményt.

### 2. kérdés: Az Aspose.Tasks kompatibilis a Microsoft Project összes verziójával?

2. válasz: Az Aspose.Tasks a Microsoft Project különféle verzióit támogatja, biztosítva a kompatibilitást a különböző környezetekben.

### 3. kérdés: Testreszabhatom az Aspose.Tasks alapvonalait?

3. válasz: Igen, testreszabhatja az alapvonalakat a projekt követelményei szerint az Aspose.Tasks for .NET segítségével.

### 4. kérdés: Az Aspose.Tasks támogatja a felhőplatformokat?

4. válasz: Igen, az Aspose.Tasks támogatja a népszerű felhőplatformokkal való integrációt, rugalmas telepítést biztosítva.

### 5. kérdés: Létezik közösségi fórum az Aspose.Tasks felhasználók számára, ahol segítséget kérhetnek és megoszthatják tudásukat?

 A5: Igen, meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) kapcsolatba lépni a közösséggel, és segítséget kérni szakértőktől.