---
title: Ismétlés hónaponként Naponként az Aspose.Tasks-ban
linktitle: Ismétlés hónaponként Naponként az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti az ismétlődő feladatokat .NET-projektekben az Aspose.Tasks segítségével. Útmutató lépésről lépésre az ismétlések kezeléséhez hónaponkénti naponként.
weight: 25
url: /hu/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ismétlés hónaponként Naponként az Aspose.Tasks-ban

## Bevezetés

A .NET fejlesztés területén az Aspose.Tasks hatékony eszköz a projektfeladatok és ütemezések kezelésére. Rengeteg funkciót kínál a projektmenedzsment munkafolyamatok egyszerűsítésére, beleértve az ismétlődő feladatok kezelését is. A hónap-naponkénti ismétlés általános követelmény a projektütemezésben, és az Aspose.Tasks erőteljes támogatást nyújt ehhez a forgatókönyvhöz.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. A C# alapvető ismerete: A C# programozási nyelv ismerete szükséges az oktatóanyagban tárgyalt fogalmak megértéséhez.
2. Az Aspose.Tasks telepítése .NET-hez: Győződjön meg arról, hogy telepítette az Aspose.Tasks for .NET-et. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
3. Integrált fejlesztői környezet (IDE): A kódolás kényelme érdekében telepítsen egy IDE-t, például a Visual Studio-t.

## Névterek importálása

C# projektben importálja a szükséges névtereket az Aspose.Tasks funkciók eléréséhez:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Bontsuk le a megadott kódpéldát lépésről lépésre útmutató formátumra:

## 1. lépés: Töltse be a projektfájlt

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Ez a kódsor inicializálja a`Project` osztályba, betöltve a "Project1.mpp" nevű projektfájlt.

## 2. lépés: Határozza meg az ismétlődő feladatparamétereket

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

Ez a szakasz meghatározza az ismétlődő feladat paramétereit, beleértve a nevét, időtartamát, ismétlési mintáját és ismétlődési tartományát.

## 3. lépés: Feladat hozzáadása a projekthez

```csharp
project.RootTask.Children.Add(parameters);
```

Itt hozzáadjuk az ismétlődő feladat paramétereit a projekthez.

## 4. lépés: Projektfájl mentése

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Végül a módosított projekt mentésre kerül a hozzáadott ismétlődő feladattal.

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan kezeljük a hónapok szerinti ismétléseket az Aspose.Tasks for .NET-ben. A megadott lépések követésével hatékonyan kezelheti a projekt ütemezésén belül ismétlődő feladatokat.

## GYIK

### 1. kérdés: Az Aspose.Tasks kompatibilis a .NET összes verziójával?

1. válasz: Az Aspose.Tasks a .NET-keretrendszer különféle verzióit támogatja, biztosítva a kompatibilitást a különböző környezetekben.

### 2. kérdés: Testreszabhatom az ismétlődési mintát?

2. válasz: Igen, az Aspose.Tasks kiterjedt testreszabási lehetőségeket kínál az ismétlődési minták meghatározásához a konkrét projektkövetelményeknek megfelelően.

### 3. kérdés: Az Aspose.Tasks támogat más projektmenedzsment funkciókat?

3. válasz: Az Aspose.Tasks a projektmenedzsment funkciók széles skáláját kínálja, beleértve a feladatkövetést, az erőforrások elosztását és a Gantt-diagram generálását.

### 4. kérdés: Elérhető az Aspose.Tasks próbaverziója?

 4. válasz: Igen, igénybe veheti az ingyenes próbaverziót[itt](https://releases.aspose.com/) hogy a vásárlási döntés meghozatala előtt feltárja az Aspose.Tasks képességeit.

### 5. kérdés: Hol kérhetek segítséget, ha problémákba ütközöm vagy kérdéseim vannak?

 A5: Meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) hogy támogatást kérjen a közösségtől vagy az Aspose csapatától.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
