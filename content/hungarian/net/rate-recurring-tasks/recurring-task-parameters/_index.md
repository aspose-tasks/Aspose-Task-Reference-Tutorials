---
title: Ismétlődő feladatparaméterek beállítása az Aspose.Tasks-ban
linktitle: Ismétlődő feladatparaméterek beállítása az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan állíthat be ismétlődő feladatparamétereket a Microsoft Projectben az Aspose.Tasks for .NET használatával. Átfogó oktatóanyag lépésről lépésre.
type: docs
weight: 14
url: /hu/net/rate-recurring-tasks/recurring-task-parameters/
---
## Bevezetés
Ebben az oktatóanyagban végigvezetjük a Microsoft Project ismétlődő feladatok paramétereinek beállításán az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. A C# programozási nyelv alapvető ismerete.
2. Telepített Visual Studio vagy bármely más C# IDE.
3. Aspose.Tasks for .NET könyvtár telepítve és hivatkozva a projektben.

## Névterek importálása
Először is importálnia kell a szükséges névtereket a C# kódba:
```csharp
using Aspose.Tasks;
using System;

```
## 1. lépés: Határozza meg a dokumentumkönyvtárat
```csharp
String DataDir = "Your Document Directory";
```
 Cserélje ki`"Your Document Directory"` a dokumentumkönyvtár elérési útjával.
## 2. lépés: Töltse be a projektfájlt
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Ez a kódsor betölti a Microsoft Project fájlt a`project` változó.
## 3. lépés: Határozza meg az ismétlődő feladatparamétereket
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Itt adhatja meg az ismétlődő feladat paramétereit, például a feladat nevét, időtartamát, ismétlődési mintáját, ismétlődési tartományát, valamint azt, hogy figyelmen kívül kell-e hagyni az erőforrásnaptárt.
## 4. lépés: Állítsa be a naptárat az ismétlődő feladatokhoz
```csharp
parameters.SetCalendar(project, "Standard");
```
Ez a lépés beállítja az ismétlődő feladat naptárát. Ebben a példában a naptárt "Normál"-ra állítja.
## 5. lépés: Paraméterek hozzáadása a projekthez
```csharp
project.RootTask.Children.Add(parameters);
```
Végül adja hozzá a paramétereket a projekt gyökérfeladatához.

## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan állíthatja be a Microsoft Project ismétlődő feladatok paramétereit az Aspose.Tasks for .NET használatával. Ezen lépések követésével hatékonyan kezelheti a projektekben ismétlődő feladatokat.
## GYIK
### Testreszabhatom tovább az ismétlődési mintát?
Igen, az Aspose.Tasks különféle ismétlődési mintákat és lehetőségeket kínál a projekt követelményei szerint testreszabható.
### Vásárlás előtt van próbaverzió?
 Igen, letölthet egy ingyenes próbaverziót az Aspose.Tasks oldalról[weboldal](https://purchase.aspose.com/buy) hogy értékelje a könyvtár jellemzőit.
### Az Aspose.Tasks támogat más projektfájlformátumokat?
Igen, az Aspose.Tasks különféle projektfájlformátumokat támogat, beleértve az MPP-t, az XML-t, az XLSX-et stb.
### Kaphatok-e támogatást, ha bármilyen problémába ütközöm a megvalósítás során?
Igen, felkeresheti az Aspose.Tasks fórumot, ha segítségre van szüksége a közösségtől, vagy kapcsolatba léphet az ügyfélszolgálattal közvetlen segítségért.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks számára?
 Ideiglenes engedélyt szerezhet a[weboldal](https://purchase.aspose.com/temporary-license/) tesztelési célokra.