---
title: Testreszabhatja a munkaheteket az Aspose.Tasks szolgáltatásban
linktitle: Munkahetek gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan szabhatja testre a munkaheteket az Aspose.Tasks for .NET-ben. Lépésről lépésre szóló útmutató személyre szabott projektnaptárak létrehozásához. Letöltés most!
type: docs
weight: 17
url: /hu/net/time-recurrence-configuration/workweek-collection/
---
## Bevezetés
Üdvözöljük az Aspose.Tasks for .NET használatával egyéni munkahét létrehozásáról szóló oktatóanyagunkban! Ebben a lépésenkénti útmutatóban végigvezetjük a projektben szereplő naptár személyre szabott munkahét meghatározásának folyamatán. Az Aspose.Tasks egy hatékony könyvtár, amely képessé teszi a fejlesztőket arra, hogy hatékonyan dolgozzanak Microsoft Project dokumentumokkal .NET-alkalmazásaikban.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks könyvtárat. A letöltési linket megtalálod[itt](https://releases.aspose.com/tasks/net/).
3. C# alapismeretek: Ismerkedjen meg a C# programozási nyelv alapjaival.
## Névterek importálása
A C# projektben feltétlenül importálja a szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. lépés: Hozzon létre egy projektet és naptárt
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## 2. lépés: Egyéni munkahét meghatározása
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## 3. lépés: Állítsa be a munkanapokat
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## 4. lépés: Jelenítse meg a munkahetekre vonatkozó információkat
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Ez az átfogó útmutató lehetővé teszi az egyéni munkahetek hatékony létrehozását és kezelését az Aspose.Tasks for .NET segítségével.
## Következtetés
Összefoglalva, az Aspose.Tasks for .NET robusztus megoldást kínál a projektnaptárak kezelésére egyedi munkahetekkel. Az oktatóanyag követésével megtanulta, hogyan hozhat létre és jeleníthet meg információkat a projektben az egyéni munkahetekről.
## GYIK
### Lehet több egyéni munkahetem egyetlen projektben?
Igen, több egyéni munkahetet is hozzáadhat egy projektnaptárhoz.
### Hogyan módosíthatom a meglévő munkaheteket?
 Használja a biztosított`WorkWeek`tulajdonságok és módszerek a meglévő munkahetek módosítására.
### Az Aspose.Tasks kompatibilis a .NET Core programmal?
Igen, az Aspose.Tasks támogatja a .NET Core-t.
### Exportálhatom az egyéni munkahetekkel rendelkező projektet Microsoft Project fájlformátumba?
Természetesen az Aspose.Tasks lehetővé teszi a projektek különböző formátumokban történő elmentését, beleértve a Microsoft Projectet is.
### Hol kérhetek támogatást az Aspose.Tasks-hoz kapcsolódó lekérdezésekhez?
 Meglátogatni a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) bármilyen támogatásért vagy segítségért.