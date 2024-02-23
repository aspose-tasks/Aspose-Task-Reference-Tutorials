---
title: Ismétlődő feladatok információinak kinyerése az Aspose.Tasks programból
linktitle: Ismétlődő feladatok információinak kinyerése az Aspose.Tasks programból
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan bonthatja ki az ismétlődő feladatok adatait az MS Project fájlokból az Aspose.Tasks for .NET segítségével. Könnyű integráció .NET fejlesztők számára.
type: docs
weight: 13
url: /hu/net/rate-recurring-tasks/recurring-task-information/
---
## Bevezetés
Az Aspose.Tasks for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy Microsoft Project fájlokkal dolgozzanak .NET-alkalmazásaikban. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet az Aspose.Tasks segítségével kinyerni az ismétlődő feladatinformációkat az MS Project fájlokból.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. A C# programozási nyelv alapvető ismerete.
2. A Visual Studio telepítve van a rendszerére.
3.  Aspose.Tasks for .NET könyvtár telepítve. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
## Névterek importálása
A kezdéshez importálja a szükséges névtereket a C# kódba:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Most bontsuk fel a példát több lépésre:
## 1. lépés: Állítsa be a projekt fájl elérési útját
```csharp
String DataDir = "Your Document Directory";
```
 cserélje ki`"Your Document Directory"` az MS Project fájl elérési útjával.
## 2. lépés: Töltse be az MS Project fájlt
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Ez a sor inicializál egy újat`Project` objektumot az elérési út által megadott MS Project fájl betöltésével.
## 3. lépés: Olvassa el a feladatok ismétlődő információit
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Az ismétlődő feladatok információinak elérése és megjelenítése
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Szükség szerint folytassa a többi ismétlődő feladatinformáció megjelenítését
}
```
Ez a ciklus a projektben lévő összes feladaton keresztül iterál, és ellenőrzi, hogy minden feladathoz vannak-e ismétlődő információk társítva. Ha igen, akkor lekéri és megjeleníti az ismétlődő feladat különféle tulajdonságait, mint például a kezdő dátum, időtartam, befejezés dátuma stb.
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet MS Project fájlokból kinyerni az ismétlődő feladatokra vonatkozó információkat az Aspose.Tasks for .NET segítségével. Ennek a tudásnak a birtokában most már integrálhatja ezt a funkciót .NET-alkalmazásaiba, hogy hatékonyabban dolgozhasson az ismétlődő feladatokkal.
## GYIK
### K: Módosíthatom az ismétlődő feladatok adatait az Aspose.Tasks for .NET használatával?
V: Igen, az ismétlődő feladatok adatait programozottan módosíthatja a biztosított API-k segítségével.
### K: Az Aspose.Tasks támogat más projektfájlformátumokat az MS Projecten kívül?
V: Igen, az Aspose.Tasks különféle projektfájlformátumokat támogat, mint például az MPP, XML és CSV.
### K: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET számára?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### K: Hol találom az Aspose.Tasks for .NET dokumentációját?
 V: Megtalálhatja a dokumentációt[itt](https://reference.aspose.com/tasks/net/).
### K: Hogyan kaphatok technikai támogatást az Aspose.Tasks for .NET-hez?
V: Technikai támogatást az Aspose.Tasks fórumon kaphat.[itt](https://forum.aspose.com/c/tasks/15).