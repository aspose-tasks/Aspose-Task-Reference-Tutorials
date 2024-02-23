---
title: A havi ismétlődési minták kezelése az Aspose.Tasks-ban
linktitle: A havi ismétlődési minták kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ezzel a lépésenkénti oktatóanyaggal megtudhatja, hogyan kezelheti a havi ismétlődési mintákat az Aspose.Tasks for .NET-ben.
type: docs
weight: 18
url: /hu/net/advanced-concepts/monthly-recurrence-patterns/
---
## Bevezetés

Az Aspose.Tasks for .NET egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat. Az egyik alapvető funkció, amelyet kínál, az ismétlődő feladatok hatékony kezelésének képessége. Ebben az oktatóanyagban lépésről lépésre megvizsgáljuk, hogyan dolgozhatunk a havi ismétlődési mintákkal az Aspose.Tasks használatával.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek telepítve vannak:

## Névterek importálása

Először győződjön meg arról, hogy importálta a szükséges névtereket a .NET-projektben:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Most bontsuk le a havi ismétlődési minták kezelésének folyamatát több lépésre:

## 1. lépés: Inicializálja a projektet

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 2. lépés: Állítsa be az ismétlődő feladatok paramétereit

Határozza meg az ismétlődő feladat paramétereit, beleértve a feladat nevét, időtartamát és ismétlődési mintáját:

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

## 3. lépés: Paraméterek hozzáadása a projekthez

```csharp
project.RootTask.Children.Add(parameters);
```

## 4. lépés: Mentse el a projektet

Mentse el a módosított projektet az ismétlődő feladattal:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Következtetés

havi ismétlődési minták kezelése az Aspose.Tasks for .NET-ben egyszerű és hatékony. Az oktatóanyagban ismertetett lépések követésével egyszerűen hozhat létre ismétlődő feladatokat meghatározott havi intervallumokkal és ismétlődési tartományokkal.

## GYIK

### 1. kérdés: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok összes verziójával?

1. válasz: Az Aspose.Tasks támogatja a Microsoft Project fájlok különféle verzióit, beleértve az MPP-t, az MPT-t, az XML-t és az MPX-et.

### 2. kérdés: Testreszabhatom az ismétlődési mintát?

2. válasz: Igen, az Aspose.Tasks kiterjedt lehetőségeket kínál az ismétlődési minták testreszabására, beleértve a napi, heti, havi és éves.

### 3. kérdés: Elérhető az Aspose.Tasks ingyenes próbaverziója?

 3. válasz: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).

### 4. kérdés: Hogyan kaphatok támogatást az Aspose.Tasks-hoz?

 4. válasz: Kérhet segítséget, és részt vehet a megbeszéléseken[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).

### 5. kérdés: Hol vásárolhatok licencet az Aspose.Tasks számára?

 5. válasz: Az Aspose.Tasks licencet megvásárolhatja a webhelyen[itt](https://purchase.aspose.com/buy)