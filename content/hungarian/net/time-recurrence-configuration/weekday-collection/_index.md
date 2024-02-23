---
title: A hétköznapok elsajátítása az Aspose.Tasks-ban
linktitle: Hétköznapok gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel az Aspose.Tasks for .NET erejét a hétköznapok egyszerű kezelésében. Szabja testre a munkanapokat, távolítsa el a hétvégéket, és készítsen egyszerűen speciális naptárakat.
type: docs
weight: 11
url: /hu/net/time-recurrence-configuration/weekday-collection/
---
## Bevezetés
Az Aspose.Tasks for .NET egy hatékony könyvtár, amely megkönnyíti a projektmenedzsment adatok hatékony kezelését. Ebben az oktatóanyagban megvizsgáljuk az Aspose.Tasks hétköznapjainak gyűjteményét, amely lehetővé teszi a munkanapok testreszabását, a hétvégék eltávolítását, és speciális naptárak létrehozását a projekt követelményeinek megfelelően. Akár tapasztalt fejlesztő, akár újonc, ez a lépésről lépésre végigvezeti Önt az Aspose.Tasks for .NET hétköznapjainak kezelésén.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
-  Telepítse az Aspose.Tasks for .NET könyvtárat. Letöltheti a[Aspose.Tasks for .NET letöltési oldal](https://releases.aspose.com/tasks/net/).
- C# programozási nyelv ismerete.
- Integrált fejlesztői környezet (IDE), például a Visual Studio.
## Névterek importálása
Kezdje a szükséges névterek importálásával a C# projektbe:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. lépés: Hozzon létre egy projektpéldányt
Új Aspose.Tasks projekt inicializálása:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 2. lépés: Nyissa meg a naptárat
A projekt naptárának lekérése:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## 3. lépés: A hétköznapok testreszabása
Meglévő hétköznapok törlése és alapértelmezett munkanapok beállítása:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// További hétköznapok hozzáadása hasonló módon...
```
## 4. lépés: Munkaidő hozzáadása
Munkaidő hozzáadása adott hétköznapokhoz:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## 5. lépés: Jelenítse meg a naptárinformációkat
A naptár részleteinek megjelenítése a konzolon:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Minden hétköznap és munkaidő megjelenítése...
```
## 6. lépés: Távolítsa el a hétvégéket
A szombat és a vasárnap eltávolítása a hétköznapokból:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## 7. lépés: Jelenítse meg a frissített munkaidőket
Frissített munkaidő kimenet a hétvégék eltávolítása után:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Minden frissített hétköznap és munkaidő megjelenítése...
```
## 8. lépés: Hozzon létre egy 24 órás naptárat
Hozzon létre egy 24 órás naptárat, és másolja ki a hétköznapokat:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Következtetés
Ebben az oktatóanyagban az Aspose.Tasks for .NET hatékony képességeit fedeztük fel a projektnaptárak hétköznapjainak kezelésében. A munkanapok testreszabásától a speciális, 24 órás naptárak létrehozásáig az Aspose.Tasks leegyszerűsíti a folyamatot, rugalmasságot és irányítást biztosítva a projektmenedzsmentben.
## Gyakran Ismételt Kérdések
### K: Használhatom az Aspose.Tasks for .NET programot más programozási nyelvekkel?
V: Az Aspose.Tasks elsősorban a .NET nyelveket támogatja, de Java-verziókat is kínál.
### K: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET számára?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[Az Aspose.Tasks kiadási oldal](https://releases.aspose.com/).
### K: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?
 V: Látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásért, vagy fontolja meg egy támogatási terv megvásárlását.
### K: Hol találom az Aspose.Tasks for .NET átfogó dokumentációját?
 V: Lásd a[Aspose.Tasks .NET dokumentációhoz](https://reference.aspose.com/tasks/net/) részletes információkért.
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for .NET számára?
 V: Ideiglenes licencet szerezhet be a[ideiglenes licenc oldal](https://purchase.aspose.com/temporary-license/).