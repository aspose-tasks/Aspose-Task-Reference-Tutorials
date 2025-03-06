---
title: Naptípus-gyűjtemény kezelése az Aspose.Tasks-ban
linktitle: Naptípus-gyűjtemény kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Tanulja meg, hogyan kezelheti hatékonyan a nap típusú gyűjteményeket az Aspose.Tasks for .NET alkalmazásban. Egyszerűen hozhat létre, módosíthat és kezelhet naptárkivételeket.
weight: 28
url: /hu/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Naptípus-gyűjtemény kezelése az Aspose.Tasks-ban

## Bevezetés

 Az Aspose.Tasks for .NET robusztus funkcionalitást biztosít a nap típusú gyűjtemények kezeléséhez, ami kulcsfontosságú a heti naptári kivételek meghatározásához projektmenedzsment alkalmazásokban. Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatjuk a`DayTypeCollection` osztályt hatékonyan. 

## Előfeltételek

Mielőtt folytatnánk az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
3. C# alapismeretek: C# programozási nyelv és .NET keretrendszer fogalmak ismerete.

## Névterek importálása

A kezdéshez importálnia kell a szükséges névtereket a C# projektbe:

```csharp
using Aspose.Tasks;
using System;


```

Most bontsuk fel a megadott példát több lépésre:

## 1. lépés: Töltse be a projektet és a naptárat

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Ez a lépés inicializál egy új projektpéldányt, és lekéri a naptárt az UID alapján.

## 2. lépés: Ismételje meg a naptári kivételeket

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Itt végigfutjuk az egyes naptárkivételeket, és kinyomtatjuk a nevét és a kapcsolódó naptípusokat.

## 3. lépés: Módosítsa a naptári kivételeket

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Ez a lépés bemutatja, hogyan lehet módosítani a naptári kivételeket naptípusok hozzáadásával, eltávolításával vagy frissítésével.

## 4. lépés: Új naptári kivételek létrehozása és manipulálása

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

Ebben az utolsó lépésben új naptárkivételeket hozunk létre, és naptípusok hozzáadásával és másolásával kezeljük őket.

## Következtetés

 Összefoglalva, a nap típusú gyűjtemények kezelése az Aspose.Tasks for .NET-ben elengedhetetlen a heti naptárkivételek meghatározásához és módosításához a projektmenedzsment alkalmazásokban. Az oktatóanyagban található lépésenkénti útmutató követésével hatékonyan használhatja a`DayTypeCollection` osztályban a különböző naptárműveletek kezelésére.

## GYIK

### 1. kérdés: Az Aspose.Tasks for .NET használható Gantt-diagramok programozott létrehozására?

1. válasz: Igen, az Aspose.Tasks for .NET API-kat biztosít Gantt-diagramok létrehozásához és kezeléséhez .NET-alkalmazásokban.

### 2. kérdés: Az Aspose.Tasks for .NET kompatibilis mind a .NET Core, mind a .NET Framework programmal?

2. válasz: Igen, az Aspose.Tasks for .NET támogatja a .NET Core-t és a .NET-keretrendszert is.

### 3. kérdés: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?

 A3: Támogatást kaphat, ha felkeresi a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) ahol kérdéseket tehet fel, és kapcsolatba léphet más felhasználókkal.

### 4. kérdés: Az Aspose.Tasks for .NET ingyenes próbaverziót kínál?

 4. válasz: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a .NET-hez[itt](https://releases.aspose.com/).

### 5. kérdés: Vásárolhatok ideiglenes licencet az Aspose.Tasks for .NET számára?

 5. válasz: Igen, az ideiglenes licencek megvásárolhatók a[Aspose honlapja](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
