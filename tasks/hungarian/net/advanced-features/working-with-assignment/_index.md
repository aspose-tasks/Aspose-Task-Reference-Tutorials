---
title: Munka a hozzárendeléssel az Aspose.Tasks programban
linktitle: Munka a hozzárendeléssel az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a projekt-hozzárendeléseket .NET-ben az Aspose.Tasks segítségével. Fedezze fel a különböző kontúrokat az erőforrás-ütemezéshez.
weight: 13
url: /hu/net/advanced-features/working-with-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Munka a hozzárendeléssel az Aspose.Tasks programban

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan dolgozhatunk feladatokkal az Aspose.Tasks for .NET-ben. A hozzárendelések kulcsfontosságúak a projektmenedzsmentben, mivel erőforrásokat rendelnek hozzá a feladatokhoz, segítik az ütemezést és a haladás nyomon követését. Az Aspose.Tasks segítségével különböző kontúrokkal rendelkező erőforrás-hozzárendelési időfázisú adatok előállítására fogunk összpontosítani.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1.  Az Aspose.Tasks for .NET telepítése: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a[letöltési link](https://releases.aspose.com/tasks/net/).
2. C# és a .NET-keretrendszer alapvető ismerete: A C# programozási nyelv és a .NET-keretrendszer fogalmainak ismerete szükséges a követéshez.

## Névterek importálása

Ügyeljen arra, hogy a szükséges névtereket importálja a C# projektbe:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## 1. lépés: Hozzon létre egy projektet és egy feladatot

Kezdjük egy új projekt létrehozásával, és adjunk hozzá egy feladatot. Állítsa be a feladat kezdő dátumát, időtartamát és befejezési dátumát:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 2. lépés: Adjon hozzá egy erőforrást, és rendelje hozzá a feladathoz

Ezután adjon hozzá egy erőforrást a projekthez, és rendelje hozzá a korábban létrehozott feladathoz:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 3. lépés: Időfázisú adatok létrehozása különböző kontúrokkal

Most generáljunk időfázisú adatokat különböző kontúrokkal az erőforrás-hozzárendeléshez:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## 4. lépés: A kontúrok módosítása és az adatok generálása

Megváltoztathatjuk a kontúr típusát és ennek megfelelően időfázisos adatokat állíthatunk elő. Íme néhány példa:

```csharp
// Változtassa meg a kontúrt
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Időzített adatok generálása és nyomtatása
// Ismételje meg ezt a lépést a többi kontúrtípushoz
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan dolgozhatunk feladatokkal az Aspose.Tasks for .NET-ben. Megvizsgáltuk az erőforrás-hozzárendelési időfázisú adatok generálását különböző kontúrokkal. Ez a tudás rendkívül hasznos lehet a projektmenedzsment forgatókönyveiben.

## GYIK

### 1. kérdés: Használhatom az Aspose.Tasks-t feladatok ütemezésére a .NET-alkalmazásomban?

1. válasz: Igen, az Aspose.Tasks átfogó API-kat biztosít a .NET-alkalmazások feladatütemezéséhez és kezeléséhez.

### 2. kérdés: Elérhető az Aspose.Tasks ingyenes próbaverziója?

 2. válasz: Igen, igénybe veheti az ingyenes próbaverziót[itt](https://releases.aspose.com/).

### 3. kérdés: Vannak-e korlátozások az Aspose.Tasks feladatok vagy erőforrások számára?

3. válasz: Az Aspose.Tasks nem korlátozza a projektekben kezelhető feladatok vagy erőforrások számát.

### 4. kérdés: Testreszabhatom a kontúrokat az Aspose.Tasks erőforrás-hozzárendeléseihez?

4. válasz: Igen, amint az ebben az oktatóanyagban is látható, különféle kontúrokat állíthat be, például teknőst, harangot, csúcsot stb., a projekt követelményeinek megfelelően.

### 5. kérdés: Hol találok támogatást az Aspose.Tasks-hoz kapcsolódó lekérdezésekhez?

V5: Támogatást találhat a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) ahol a szakértők és a közösség tagjai aktívan részt vesznek a vitákban.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
