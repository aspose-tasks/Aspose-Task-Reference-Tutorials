---
title: Haladó ÉS művelet az Aspose.Tasks-ban
linktitle: Haladó ÉS művelet az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan hajthat végre speciális ÉS műveleteket az Aspose.Tasks for .NET-ben a projektfeladatok hatékony szűréséhez több feltétel alapján.
weight: 10
url: /hu/net/advanced-features/advanced-and-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Haladó ÉS művelet az Aspose.Tasks-ban

## Bevezetés

 Ebben az oktatóanyagban az Aspose.Tasks for .NET fejlett ÉS műveleteivel foglalkozunk, amely egy hatékony eszköz a feladatok és projektek kezelésére. Megvizsgáljuk, hogyan lehet több feltétel alapján szűrni a projektfeladatokat a`Util.And` osztály.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:

1. C# programozási nyelv alapismerete.
2.  Aspose.Tasks telepítve a .NET-hez. Ha nem, letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
3. Integrált fejlesztői környezet (IDE), például a Visual Studio.

## Névterek importálása

Először is importáljuk a szükséges névtereket a C# projektünkbe:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## 1. lépés: A projekt inicializálása és a feladatok összegyűjtése

Kezdje egy új Aspose.Tasks projekt inicializálásával, és gyűjtsön össze benne minden feladatot:

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## 2. lépés: Adja meg a szűrési feltételeket

Ezután határozza meg a szűrési feltételeket. Ebben a példában két feltételt hozunk létre: egyet az összefoglaló feladatok szűrésére, egy másikat a nem nulla feladatok szűrésére:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## 3. lépés: Kombinálja a feltételeket az ÉS művelettel

 Most kombinálja a feltételeket a`Util.And` osztály egy összetett feltétel létrehozásához:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 4. lépés: Alkalmazza a Feltétel és a Szűrési feladatokat

Alkalmazza a kombinált feltételt az összegyűjtött feladatokra, és szűrje őket aszerint:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## 5. lépés: Szűrt feladatok kimenete

Végül adja ki a szűrt feladatokat:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // A további feldolgozás itt végezhető el
}
```

## Következtetés

 Ebben az oktatóanyagban megtanultuk, hogyan hajthatunk végre speciális ÉS műveleteket az Aspose.Tasks for .NET-ben. A feltételek kombinálásával a`Util.And`osztályba, több szempont alapján is hatékonyan tudjuk szűrni a feladatokat.

## GYIK

### 1. kérdés: Mi az Aspose.Tasks for .NET?

V: Az Aspose.Tasks for .NET egy robusztus API, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat .NET-alkalmazásokban.

### 2. kérdés: Alkalmazhatok kettőnél több feltételt az Util.And használatával?

V: Igen, az Util.And használható tetszőleges számú feltétel kombinálására összetett szűrési feltételek létrehozásához.

### 3. kérdés: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET számára?

 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).

### 4. kérdés: Hol találom az Aspose.Tasks for .NET dokumentációját?

 V: Megtalálhatja a dokumentációt[itt](https://reference.aspose.com/tasks/net/).

### 5. kérdés: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?

V: Támogatást kaphat az Aspose.Tasks közösségi fórumon[itt](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
