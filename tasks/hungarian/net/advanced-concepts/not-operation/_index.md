---
title: A NOT művelet használata az Aspose.Tasks-ban
linktitle: A NOT művelet használata az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan használhatja a NOT műveletet az Aspose.Tasks for .NET-ben a feladatok hatékony szűrésére. Bővítse projektkezelési képességeit most.
weight: 20
url: /hu/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A NOT művelet használata az Aspose.Tasks-ban

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatjuk a NOT műveletet az Aspose.Tasks for .NET-ben. A NOT művelet lehetővé teszi egy szűrőfeltétel megfordítását, lehetővé téve olyan elemek kiválasztását, amelyek nem felelnek meg egy meghatározott kritériumnak.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:

1. Visual Studio: A kódpéldák követéséhez a Visual Studio működőképes telepítésére van szükség.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a[weboldal](https://releases.aspose.com/tasks/net/).
3. C# alapjai: A C# programozási nyelv ismerete hasznos lesz a kódpéldák megértésében.

## Névterek importálása

Először is importáljuk a kódunkhoz szükséges névtereket:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1. lépés: A projekt és a feladatok beállítása

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Kezdjük a "Project2.mpp" nevű projektfájl betöltésével a`Project` osztály által biztosított Aspose.Tasks. Győződjön meg arról, hogy a projektfájl létezik a megadott könyvtárban.

## 2. lépés: Gyűjtse össze a projektfeladatokat

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Itt létrehozunk a`ChildTasksCollector` tiltakozik a projekten belüli összes feladat összegyűjtésére. Utána használjuk`TaskUtils.Apply` módszerrel végighaladhat a projekt feladathierarchiáján, és összegyűjtheti az összes alárendelt feladatot.

## 3. lépés: Adja meg a szűrőfeltételt

```csharp
var filter = new NullCondition();
```

 Meghatározzuk a szűrőfeltételt a nevű egyéni osztály használatával`NullCondition`. Ez a feltétel a null értékkel rendelkező feladatokat választja ki.

## 4. lépés: Alkalmazza a NEM műveletet

```csharp
var condition = new Not<Task>(filter);
```

 A szűrőfeltételre a NEM műveletet alkalmazzuk a`Not<T>`osztály által biztosított Aspose.Tasks. Ez megfordítja a szűrőfeltételt, és kiválasztja azokat a feladatokat, amelyeknek nincs null értéke.

## 5. lépés: Feladatok szűrése

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Az összegyűjtött feladatokat az alkalmazott feltétel alapján egyedi segítségével szűrjük`Filter` módszer. Ez a módszer egy számtalan feladatgyűjteményt és egy szűrőfeltételt vesz fel bemeneti paraméterként, és visszaadja a feltételnek megfelelő feladatok listáját.

## 6. lépés: Szűrt feladatok feldolgozása

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Dolgozzon más tulajdonságokkal...
}
```

Végül ismételjük a szűrt feladatokat, és végrehajtjuk a kívánt műveleteket. Ebben a példában egyszerűen kinyomtatjuk a feladatok nevét a konzolra.

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan kell dolgozni a NOT művelettel az Aspose.Tasks for .NET-ben. A szűrési feltételek megfordításával szelektíven kiválaszthatunk olyan elemeket, amelyek nem felelnek meg a meghatározott kritériumoknak, ezzel növelve rugalmasságunkat a projekteken belüli feladatok kezelésében.

## GYIK

### 1. kérdés: Használhatom az Aspose.Tasks-t más .NET-keretrendszerekkel?

V: Igen, az Aspose.Tasks különféle .NET-keretrendszereket támogat, beleértve a .NET Core-t, a .NET Standard-t és a .NET-keretrendszert.

### 2. kérdés: Elérhető az Aspose.Tasks ingyenes próbaverziója?

 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[weboldal](https://releases.aspose.com/).

### 3. kérdés: Hogyan kaphatok támogatást az Aspose.Tasks-hoz?

 V: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) bármilyen támogatási kérdésre vagy technikai segítségre.

### 4. kérdés: Vásárolhatok ideiglenes licencet az Aspose.Tasks számára?

 V: Igen, vásárolhat ideiglenes licencet a[vásárlási oldal](https://purchase.aspose.com/temporary-license/).

### 5. kérdés: Hol találom az Aspose.Tasks átfogó dokumentációját?

 V: A teljes dokumentációt a következő oldalon érheti el[Aspose.Tasks dokumentációs oldal](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
