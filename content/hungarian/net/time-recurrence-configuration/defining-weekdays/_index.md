---
title: A hétköznapok elsajátítása az Aspose.Tasks-ban .NET-hez
linktitle: Hétköznapok meghatározása az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel a hétköznapok meghatározásának erejét az Aspose.Tasks .NET-ben. Kövesse részletes oktatóanyagunkat a projektnaptárak hatékony kezeléséhez, a munkaidő testreszabásához stb.
type: docs
weight: 10
url: /hu/net/time-recurrence-configuration/defining-weekdays/
---
## Bevezetés
Ha a projektmenedzsment világába merül az Aspose.Tasks for .NET használatával, a hétköznapok megértése és manipulálása kulcsfontosságú szempont. A hétköznapok hatékony kezelése és testreszabása a projektnaptárban jelentősen befolyásolhatja a projektek ütemezését. Ebben az oktatóanyagban végigvezetjük Önt a hétköznapok Aspose.Tasks segítségével történő meghatározásának folyamatán, lépésről lépésre bemutatva a jobb érthetőség érdekében példákat.
## Előfeltételek
Mielőtt nekivágnánk ennek az útnak, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- A C# programozási nyelv alapvető ismerete.
-  Aspose.Tasks for .NET könyvtár telepítve. Ha nem, töltsd le innen[itt](https://releases.aspose.com/tasks/net/).
## Névterek importálása
Kezdje azzal, hogy importálja a szükséges névtereket a projektbe:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Ellenőrizze a hétköznapok egyenlőségét
```csharp
// Az Ön dokumentumkönyvtára
String DataDir = "Your Document Directory";
// Projektfájl betöltése
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Hozzáférés hétköznap
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Ellenőrizze az egyenlőséget különböző tulajdonságok alapján
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Adjon hozzá hasonló kimeneti utasításokat a DayWorking, FromDate, ToDate és WorkingTimes számára
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Hétköznap klónozása
```csharp
// Projektfájl betöltése
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Hozzon létre egy mély másolatot a hétköznapokról
var weekDay2 = weekDay1.Clone();
// Mindkét hétköznap kimeneti tulajdonságai
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Adjon hozzá hasonló kimeneti utasításokat a DayWorking, FromDate, ToDate és WorkingTimes számára
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Szerezze be a hétköznapok hash kódját
```csharp
// Projektfájl betöltése
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Mindkét hétköznap kimeneti tulajdonságai
// Adjon hozzá hasonló kimeneti utasításokat a DayWorking, FromDate, ToDate és WorkingTimes számára
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Hozzon létre egy új naptárat meghatározott hétköznapokkal
```csharp
// Hozzon létre egy új projektet
var project = new Project();
// Határozzon meg egy naptárt
var calendar = project.Calendars.Add("Calendar1");
// Adjon hozzá munkanapokat és kivételes napokat
// Adjon hozzá hasonló kimeneti utasításokat a FromDate és a ToDate számára
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Állítsa be a munkaidőt péntekre
// Adjon hozzá hasonló kimeneti utasításokat a DayWorking, FromDate, ToDate és WorkingTimes számára
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Állítsa be az alapértelmezett munkaidőt egy napra
```csharp
// Hozzon létre egy új projektet
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Adjon hozzá alapértelmezett munkaidőt hétfőtől péntekig
// Adjon hozzá hasonló kimeneti utasításokat a DayWorking, FromDate, ToDate és WorkingTimes számára
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Ismételje meg kedden, szerdán, csütörtökön és pénteken
// Állítson be munkaszüneti napot szombatra és vasárnapra
// Adjon hozzá hasonló kimeneti utasításokat a DayWorking, FromDate, ToDate és WorkingTimes számára
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Következtetés
Ebben az oktatóanyagban az Aspose.Tasks for .NET hétköznapjainak meghatározásának alapvető szempontjait ismertetjük. A hétköznapok manipulálása kulcsfontosságú készség a hatékony projektmenedzsmenthez. Kísérletezzen a megadott példákkal, szabja őket a projekt igényeihez, és aknázza ki az Aspose.Tasks teljes potenciálját.
## GYIK
### Meghatározhatok egyéni munkaidőt minden napra?
Igen, a megadott példák segítségével egyedi munkaidőket állíthat be adott hétköznapokra.
### Lehetséges több kivételes napot hozzáadni a naptárhoz?
Teljesen. Módosítsa a kódot a negyedik példában, hogy további kivételnapokat tartalmazzon.
### Hogyan távolíthatok el egy adott hétköznapot a naptárból?
Használja az Aspose.Tasks könyvtár által biztosított megfelelő módszereket a hétköznapok szükség szerinti eltávolításához.
### A hétköznapokon végrehajtott változtatások megmaradnak a projektfájlban?
Igen, a hétköznapokon végrehajtott módosítások mentéskor megjelennek a projektfájlban.
### Használhatom az Aspose.Tasks-t más programozási nyelvekkel?
Az Aspose.Tasks különféle programozási nyelveket támogat, de az itt található példák kifejezetten a .NET-re vonatkoznak.