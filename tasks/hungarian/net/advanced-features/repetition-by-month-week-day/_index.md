---
title: Ismétlés hónaponként Hét naponként Aspose.Tasks-ban
linktitle: Ismétlés hónaponként Hét naponként Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan állíthat be ismétléseket havi, heti és napi bontásban az Aspose.Tasks for .NET alkalmazásban az ismétlődő feladatok hatékony automatizálása érdekében.
type: docs
weight: 26
url: /hu/net/advanced-features/repetition-by-month-week-day/
---
## Bevezetés

A szoftverfejlesztés területén, különösen a projektmenedzsment alkalmazásokban, az ismétlődő feladatok hatékony kezelésének képessége a legfontosabb. Az Aspose.Tasks for .NET egy hatékony könyvtár, amelyet arra terveztek, hogy egyszerűsítse a projektfeladatok létrehozását és kezelését, beleértve az ismétlődő feladatokat is. Az Aspose.Tasks által biztosított egyik ilyen funkció az ismétlések havi, heti és napi bontásának lehetősége, biztosítva, hogy a feladatokat manuális beavatkozás nélkül, ütemezetten hajtsák végre.

## Előfeltételek

Mielőtt belemerülne a havi, hét és nap szerinti ismétlések beállításának bonyolultságába az Aspose.Tasks for .NET használatával, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. C# alapvető ismerete: A C# programozási nyelv ismerete elengedhetetlen a megadott kódpéldák megértéséhez és megvalósításához.
   
2.  Az Aspose.Tasks for .NET telepítése: Győződjön meg arról, hogy letöltötte és telepítette az Aspose.Tasks for .NET könyvtárat. A könyvtárat beszerezheti a[letöltési oldal](https://releases.aspose.com/tasks/net/).

3. Hozzáférés egy .mpp projektfájlhoz: Készítsen egy Microsoft Project fájlt (.mpp), mivel azt az ismétlések végrehajtásának bemutatására fogjuk használni hónap, hét és nap szerint.

## Névterek importálása

Az Aspose.Tasks for .NET használatának megkezdéséhez a C# alkalmazásban importálnia kell a szükséges névtereket. A következőképpen teheti meg:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Bontsuk fel a megadott kódrészletet több lépésre, hogy alaposan megértsük az egyes részeket.

## 1. lépés: Töltse be a projektfájlt

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Ez a lépés egy új példány létrehozását jelenti a`Project` osztályt, és betölt egy meglévő Microsoft Project fájlt (`Project1.mpp`) a megadott könyvtárból.

## 2. lépés: Határozza meg az ismétlődő feladatparamétereket

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Ebben a lépésben meghatározzuk egy ismétlődő feladat paramétereit. Megadjuk a feladat nevét, időtartamát, ismétlési mintáját (havonta) és ismétlődési tartományát (adott dátummal fejeződik be).

## 3. lépés: Adjon hozzá ismétlődő feladatot a projekthez

```csharp
project.RootTask.Children.Add(parameters);
```

Itt hozzáadjuk a meghatározott ismétlődő feladat paramétereket a projekt gyökérfeladatához.

## 4. lépés: Projektfájl mentése

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Végül elmentjük a módosított projektfájlt a hozzáadott ismétlődő feladattal.

## Következtetés

Összefoglalva, az ismétlések havi, heti és nap szerinti beállítása az Aspose.Tasks for .NET-ben egy egyszerű folyamat, amely képessé teszi a fejlesztőket arra, hogy hatékonyan automatizálják a projektjeiken belül ismétlődő feladatok kezelését. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen integrálhatja ezt a funkciót C#-alkalmazásaiba, így időt és erőfeszítést takaríthat meg a projektmenedzsmentben.

## GYIK

###1. kérdés: Testreszabhatom az ismétlődési mintát a megadott példákon túl?

1. válasz: Igen, az Aspose.Tasks for .NET kiterjedt testreszabási lehetőségeket kínál az ismétlődési mintákhoz, amelyek lehetővé teszik, hogy azokat az Ön egyedi igényeihez igazítsa.

###2. kérdés: Elérhető az Aspose.Tasks próbaverziója .NET-hez?

 2. válasz: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a .NET-hez a[kiadások oldala](https://releases.aspose.com/).

###3. kérdés: Hogyan szerezhetek támogatást az Aspose.Tasks for .NET-hez?

 3. válasz: Segítséget kérhet, és kapcsolatba léphet a közösséggel a webhelyen[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).

###4. kérdés: Rendelkezésre állnak ideiglenes licencek az Aspose.Tasks for .NET számára?

 4. válasz: Igen, ideiglenes licenceket szerezhet be a[vásárlási oldal](https://purchase.aspose.com/temporary-license/) tesztelési és értékelési célokra.

###Q5: Hol találom az Aspose.Tasks for .NET átfogó dokumentációját?

 V5: Olvassa el a részleteset[dokumentáció](https://reference.aspose.com/tasks/net/) elérhető az Aspose honlapján, ahol részletes útmutatást talál a könyvtár használatáról.