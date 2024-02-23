---
title: Könnyű MS Project ismétlődő időközök az Aspose.Tasks-ban
linktitle: Ismétlődő intervallumok kezelése az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Fedezze fel, hogyan kezelheti könnyedén az ismétlődő intervallumokat az MS Projectben az Aspose.Tasks for .NET segítségével.
type: docs
weight: 12
url: /hu/net/rate-recurring-tasks/recurring-intervals/
---
## Bevezetés
Hatékonyan szeretné kezelni az ismétlődő intervallumokat a Microsoft Project fájlokban az Aspose.Tasks for .NET segítségével? Ez az átfogó oktatóanyag lépésről lépésre végigvezeti a folyamaton, biztosítva, hogy könnyedén kezelhesse a projektjei ismétlődő időközeit. Mielőtt belevágna az oktatóanyagba, tekintsünk át néhány előfeltételt, hogy biztosan készen álljon a kezdésre.
## Előfeltételek
Mielőtt folytatná ezt az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következőkkel:
1. C# programozás ismerete: A C# programozási nyelv és szintaxisának alapvető ismerete szükséges.
2. A Visual Studio telepítve: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren a .NET-alkalmazások kódolásához és fordításához.
3. Aspose.Tasks for .NET Library: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat. től lehet kapni[itt](https://releases.aspose.com/tasks/net/).

## Névterek importálása
Kezdje a szükséges névterek importálásával az Aspose.Tasks for .NET könyvtár által biztosított funkciók eléréséhez.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Most bontsuk le az egyes példákat több lépésre, és magyarázzuk el őket részletesen.
## 1. lépés: Projektobjektum inicializálása:
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
Itt inicializáljuk a`Project` osztályt a Microsoft Project fájl elérési útjának megadásával.
## 2. lépés: Állítsa be az állapot dátumát:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Ez a lépés beállítja a projekt állapotának dátumát a kezdő dátumra.
## 3. lépés: A Gantt-diagram nézet elérése:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Elérjük a projekt Gantt-diagram nézetét.
## 4. lépés: Olvassa el az előrehaladási sort:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Ez a lépés a folyamatsorok ismétlődő intervallumát kéri le a Gantt-diagram nézetből.
## 5. lépés: Időközi információ megjelenítése:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Itt információkat jelenítünk meg az intervallumról, a heti hét számáról és a heti napokról.
## 6. lépés: Az ismétlődő intervallum újradefiniálása:
```csharp
var newInterval = new RecurringInterval();
```
 Létrehozunk egy új példányt`RecurringInterval` az ismétlődő intervallum újradefiniálásához.
## 7. lépés: Állítsa be a havi fejlődési vonalakat:
```csharp
// Állítsa be a havi előrehaladási sorokat napra lebontva.
interval.MonthlyDay = true;
// Állítsa be a havi folyamatsorok napszámát.
interval.MonthlyDayDayNumber = 1;
// Állítsa be a havi folyamatsorok havi számát.
interval.MonthlyDayMonthNumber = 1;
// Állítsa be a folyamatvonalakat az első vagy az utolsó előre meghatározott nap szerint.
interval.MonthlyFirstLast = true;
// Állítsa be a havi folyamatsorok első vagy utolsó napjának típusát.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Állítsa be a folyamatvonalak havi számát.
interval.MonthlyFirstLastMonthNumber = 1;
```
Ezek a lépések konfigurálják a havi folyamatsorokat a megadott paraméterek szerint.
## 8. lépés: Frissítse az előrehaladási vonalakat:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Frissítjük a folyamatvonalakat a Gantt-diagram nézetben az újonnan meghatározott ismétlődő intervallumokkal.
## 9. lépés: Projekt mentése PDF formátumban:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Végül elmentjük a projektet a frissített ismétlődő időközzel PDF fájlként.

## Következtetés
Összefoglalva, az ismétlődő intervallumok kezelése a Microsoft Project fájlokban az Aspose.Tasks for .NET használatával egyszerűbbé válik a könyvtár által biztosított átfogó funkciókkal. Az ebben az oktatóanyagban felvázolt útmutató lépésenkénti követésével hatékonyan kezelheti a projektjei ismétlődő időközeit, javítva a termelékenységet és a szervezettséget.
### GYIK
### Használhatom az Aspose.Tasks for .NET programot más programozási nyelvekkel?
Igen, az Aspose.Tasks for .NET használható bármely .NET által támogatott nyelven, például C# és VB.NET.
### Elérhető az Aspose.Tasks .NET-hez próbaverziója?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?
 Támogatást kaphat az Aspose.Tasks fórumon[itt](https://forum.aspose.com/c/tasks/15).
### Vásárolhatok ideiglenes licencet az Aspose.Tasks for .NET számára?
 Igen, vásárolhat ideiglenes licencet innen[itt](https://purchase.aspose.com/temporary-license/).
### Hol találom az Aspose.Tasks for .NET teljes dokumentációját?
 A teljes dokumentáció megtalálható[itt](https://reference.aspose.com/tasks/net/).