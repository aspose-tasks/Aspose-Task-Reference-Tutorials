---
title: Fa-algoritmus használata az Aspose.Tasks-ban
linktitle: Fa-algoritmus használata az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan a feladathierarchiákat .NET-projektjeiben az Aspose.Tasks' Tree Algorithm segítségével.
type: docs
weight: 13
url: /hu/net/advanced-concepts/tree-algorithm/
---
## Bevezetés

Az Aspose.Tasks for .NET hatékony funkciókat kínál a projektmenedzsment feladatokkal, erőforrásokkal és ütemezésekkel való munkához. Az egyik ilyen funkció a Tree Algorithm, amely lehetővé teszi a felhasználók számára a feladathierarchiák hatékony kezelését. Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatjuk az Aspose.Tasks for .NET fa algoritmusát a közös munka összegyűjtésére és a munkaértékek frissítésére egy projekten belül.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET webhelyet innen[itt](https://releases.aspose.com/tasks/net/).
3. C# alapvető ismerete: A példák követéséhez a C# programozási nyelv ismerete szükséges.

## Névterek importálása

A C#-projektben importálja a szükséges névtereket az Aspose.Tasks funkciók használatához:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Most bontsuk le az egyes példákat több lépésre:

## 1. lépés: Töltse be a projektfájlt

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Töltse be a projektfájlt a memóriába a`Project` osztály.

## 2. lépés: Határozza meg a feladathierarchiát

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Határozza meg a feladathierarchiát szülő- és gyermekfeladatok hozzáadásával.

## 3. lépés: Állítsa be a Feladat tulajdonságait

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Állítson be olyan tulajdonságokat a feladatokhoz, mint a kezdő dátum, időtartam és befejezési dátum.

## 4. lépés: Erőforrás hozzáadása

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Adjon hozzá erőforrásokat a projekthez, és szükség szerint rendelje hozzá feladatokhoz.

## 5. lépés: Faalgoritmus alkalmazása

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Inicializálja a`WorkAccumulator` osztályban, és alkalmazza a Fa algoritmust a közös munka összegyűjtéséhez.

## 6. lépés: Frissítse a feladatot

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Frissítse a feladatok munkaértékeit az összegyűjtött információk alapján.

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan használhatjuk az Aspose.Tasks for .NET fa-algoritmust a feladathierarchiák hatékony manipulálására. A lépésenkénti útmutató követésével hatékonyan kezelheti a projekteken belüli feladatokat és erőforrásokat.

## GYIK

### 1. kérdés: Mi az Aspose.Tasks for .NET?

1. válasz: Az Aspose.Tasks for .NET egy hatékony API, amely lehetővé teszi a fejlesztők számára a Microsoft Project fájlok programozott kezelését a C# használatával.

### 2. kérdés: Letölthetem az Aspose.Tasks ingyenes próbaverzióját .NET-hez?

 2. válasz: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját .NET-hez a webhelyről[itt](https://releases.aspose.com/).

### 3. kérdés: Hol találom az Aspose.Tasks for .NET dokumentációját?

 3. válasz: Az Aspose.Tasks for .NET dokumentációja megtalálható[itt](https://reference.aspose.com/tasks/net/).

### 4. kérdés: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?

 4. válasz: Az Aspose.Tasks for .NET-hez kapcsolódó támogatásért keresse fel a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).

### 5. kérdés: Rendelkezésre áll-e ideiglenes licenc tesztelési célokra?

 5. válasz: Igen, ideiglenes licencet szerezhet tesztelési célból a következőtől:[itt](https://purchase.aspose.com/temporary-license/).