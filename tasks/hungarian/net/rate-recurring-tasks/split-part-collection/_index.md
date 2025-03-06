---
title: Gyűjtse össze az MS Project of Split Parts az Aspose.Tasks-ban
linktitle: Osztott alkatrészek gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan gyűjthet össze osztott részeket az MS Projectben az Aspose.Tasks for .NET segítségével. Ez az átfogó oktatóanyag lépésről lépésre végigvezeti a folyamaton.
weight: 19
url: /hu/net/rate-recurring-tasks/split-part-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gyűjtse össze az MS Project of Split Parts az Aspose.Tasks-ban

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan gyűjthetünk osztott részeket az MS Projectben az Aspose.Tasks for .NET segítségével. A feladatok részekre bontása a projektmenedzsment kulcsfontosságú szempontja lehet, és az Aspose.Tasks kényelmes módszereket kínál ennek hatékony kezelésére.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Az Aspose.Tasks telepítése .NET-hez: Győződjön meg arról, hogy telepítette az Aspose.Tasks for .NET-et. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
2. Alapvető C# ismerete: A C# programozási nyelv ismerete előnyös lesz, mivel a kódrészleteket C# nyelven fogjuk írni.

## Névterek importálása
A C# projektben adja meg a szükséges névtereket:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## 1. lépés: Állítsa be projektjét
Először hozzon létre egy új projektet a kívánt IDE-ben, és győződjön meg arról, hogy az Aspose.Tasks for .NET megfelelően hivatkozik.
## 2. lépés: Inicializálja a projektobjektumot
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Inicializáljon egy új Project objektumot az MS Project fájl elérési útjával.
## 3. lépés: Töltse le a feladatot, és ismételje meg a felosztott részeket
```csharp
var task = project.RootTask.Children.GetById(1);
// Ismételje meg a felosztott részeket
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Töltse le a feladatot a projektből, és ismételje meg a felosztott részeit, és nyomtassa ki a kezdési és befejezési dátumukat.
## 4. lépés: Szerezze meg a részre bontást index szerint
```csharp
// Szerezze meg az alkatrészt index szerint
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Keressen le egy adott osztott részt index szerint, és nyomtassa ki a kezdési dátumát.

## Következtetés
A felosztott részek kezelése az MS Project fájlokban jelentősen növelheti a projektmenedzsment hatékonyságát. Az Aspose.Tasks for .NET leegyszerűsíti ezt a folyamatot azáltal, hogy intuitív API-kat biztosít a megosztott feladatok zökkenőmentes kezelésére.
## GYIK
### K: Feloszthatom a feladatokat dinamikusan futás közben?
V: Igen, feloszthat feladatokat programozottan az Aspose.Tasks for .NET használatával.
### K: Az Aspose.Tasks támogatja az MS Project fájlok összes verzióját?
V: Az Aspose.Tasks az MS Project fájlok különféle verzióit támogatja, biztosítva a kompatibilitást a különböző platformokon.
### K: Elérhető-e próbaverzió tesztelési célokra?
 V: Igen, ingyenes próbaverziót szerezhet be a webhelyről[itt](https://releases.aspose.com/) értékeléshez.
### K: Hogyan szerezhetek ideiglenes licenceket a projektjeimhez?
 V: Ideiglenes engedélyek szerezhetők be[itt](https://purchase.aspose.com/temporary-license/) rövid távú használatra.
### K: Hol kérhetek segítséget vagy támogatást az Aspose.Tasks-szal kapcsolatban?
 V: Látogassa meg az Aspose.Tasks fórumot[itt](https://forum.aspose.com/c/tasks/15)hogy segítséget kérjen a közösségtől vagy az Aspose ügyfélszolgálati csapatától.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
