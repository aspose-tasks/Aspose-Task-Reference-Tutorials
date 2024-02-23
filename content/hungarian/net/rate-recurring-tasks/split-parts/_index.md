---
title: MS Project Split Parts kezelése az Aspose.Tasks-ban
linktitle: Osztott alkatrészek kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Tanulja meg, hogyan kezelheti hatékonyan az MS Project felosztott részeket az Aspose.Tasks for .NET segítségével. Javítsa projektmenedzsment munkafolyamatát.
type: docs
weight: 18
url: /hu/net/rate-recurring-tasks/split-parts/
---

## Bevezetés
Az MS Project felosztott részeinek kezelése az Aspose.Tasks for .NET használatakor kulcsfontosságú szempont lehet a projektmenedzsmentben. Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan lehet hatékonyan kezelni a felosztott részeket.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Az Aspose.Tasks for .NET telepítése: Töltse le és telepítse az Aspose.Tasks for .NET webhelyről[weboldal](https://releases.aspose.com/tasks/net/).
   
2. A C# alapvető ismerete: A C# programozási nyelv ismerete előnyös lesz.

## Névterek importálása
Győződjön meg arról, hogy a C# kódban importálta a szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## 1. lépés: Projektpéldány létrehozása
```csharp
var project = new Project();
```
 Hozzon létre egy új példányt a`Project` osztály.
## 2. lépés: A projekt kezdési és befejezési dátumának beállítása
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Állítsa be a projekt kezdési és befejezési dátumát.
## 3. lépés: Feladat hozzáadása
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Adjon hozzá egy új feladatot a projekthez.
## 4. lépés: A feladat tulajdonságainak beállítása
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Állítson be olyan tulajdonságokat, mint a kézi állapot, a kezdési dátum és a feladat időtartama.
## 5. lépés: Erőforrás-hozzárendelések hozzáadása
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Adjon hozzá erőforrás-hozzárendeléseket a feladathoz.
## 6. lépés: A hozzárendelés tulajdonságainak beállítása
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Állítson be olyan tulajdonságokat a feladathoz, mint a kezdési dátum, a munka és a befejezés dátuma.
## 7. lépés: Időfázisú adatok generálása
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Időfázisú adatokat generál a feladathoz a projektnaptár alapján.
## 8. lépés: A feladat felosztása
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Ossza fel a feladatot több részre a megadott időkereten belül.
## 9. lépés: A felosztott részek ismétlése
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Ismételje meg a feladat felosztott részeit, és nyomtassa ki a kezdési és befejezési dátumukat.

## Következtetés
Az MS Project felosztott részeinek hatékony kezelése az Aspose.Tasks for .NET-ben kulcsfontosságú a projektmenedzsment hatékonysága szempontjából. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen kezelheti a megosztott feladatokat, és javíthatja a projektkezelési munkafolyamatot.
## GYIK
### K: Használhatom az Aspose.Tasks for .NET-et más .NET-keretrendszerekkel?
V: Igen, az Aspose.Tasks for .NET kompatibilis különféle .NET-keretrendszerekkel, beleértve a .NET Core-t és a .NET Standard-t.
### K: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET számára?
 V: Igen, ingyenes próbaverziót szerezhet be a webhelyen[itt](https://releases.aspose.com/).
### K: Az Aspose.Tasks for .NET támogatja az erőforráskezelést?
V: Igen, az Aspose.Tasks for .NET lehetővé teszi a projekt erőforrásainak hatékony kezelését.
### K: Testreszabhatom a projektnaptárakat az Aspose.Tasks for .NET használatával?
V: Természetesen testreszabhatja a projektnaptárakat a projekt követelményei szerint.
### K: Hol találok támogatást az Aspose.Tasks for .NET-hez?
 V: Támogatást és segítséget találhat a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).