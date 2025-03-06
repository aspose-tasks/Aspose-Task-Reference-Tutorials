---
title: A naptári kivételek kezelése az Aspose.Tasks-ban
linktitle: A naptári kivételek kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a naptárkivételeket az Aspose.Tasks for .NET programban lépésenkénti oktatóanyagok és példák segítségével.
type: docs
weight: 12
url: /hu/net/calendar-scheduling/calendar-exceptions/
---
## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan kezelhetjük a naptárkivételeket az Aspose.Tasks programban a .NET keretrendszer használatával. A naptári kivételek lehetővé teszik számunkra, hogy különleges dátumokat vagy időszakokat határozzunk meg a projektnaptárban, amikor a szokásos munkarend megváltozik, például ünnepnapok vagy ideiglenes bezárások. A naptárkivételek kezelésének különféle módszereit ismertetjük lépésről lépésre az Aspose.Tasks for .NET használatával.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- C# programozási nyelv alapismerete.
- A Visual Studio telepítve van a rendszerére.
- Aspose.Tasks for .NET könyvtár hozzáadva a projekthez.

## Névterek importálása

Először is importáljuk a projektünkhöz szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;


```

## 1. lépés: Naptári kivétel törlése

Naptárkivétel törléséhez kövesse az alábbi lépéseket:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Naptárinformációk megjelenítése
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Távolítsa el az első kivételt
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## 2. lépés: A naptári kivétel munkaidő-beszámítása

Egy naptárkivétel munkaidejének lekéréséhez kövesse az alábbi lépéseket:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Naptár- és kivételinformációk megjelenítése
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // A munkaidő és a részletek megjelenítése
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 3. lépés: Naptári kivételek meghatározása

Naptárkivételek hozzáadásához vagy eltávolításához kövesse az alábbi lépéseket:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Hozzon létre egy új naptárkivételt
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Állítsa be a kivétel részleteit
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Ellenőrizze, hogy egy dátum kivétel-e
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Adja hozzá a kivételt a naptárhoz
    calendar.Exceptions.Add(exception);

    // Távolítsa el a kivételt, ha létezik
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Új kivétel hozzáadása
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Kivételek nyomtatása
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Következtetés

Ebben a cikkben az Aspose.Tasks for .NET naptárkivételeinek kezelésének különböző szempontjait ismertetjük. A megadott lépések követésével hatékonyan kezelheti a kivételeket a projekt ütemezésében, biztosítva a munkaidő és a különleges események pontos megjelenítését.

## GYIK

### 1. kérdés: Hozzáadhatok több kivételt egyetlen naptárhoz?

1. válasz: Igen, több kivételt is hozzáadhat a naptárhoz, hogy megfeleljen a különféle különleges dátumoknak vagy időszakoknak.

### 2. kérdés: Hogyan ellenőrizhetem, hogy egy adott dátum kivételt képez-e?

 V2: Használhatja a`CheckException()` módszer annak ellenőrzésére, hogy egy adott dátum kivétel alá esik-e.

### 3. kérdés: Eltávolítható-e egy meglévő kivétel a naptárból?

 3. válasz: Igen, eltávolíthatja a kivételeket, ha eléri a`Exceptions` a naptár gyűjtése és a`Remove()` módszer.

### 4. kérdés: Milyen típusú naptári kivételek támogatottak?

A4. válasz: Az Aspose.Tasks különféle típusú kivételeket támogat, beleértve a napi, heti, havi és éves kivételeket, rugalmasságot biztosítva a kivételszabályok meghatározásában.

### 5. kérdés: Testreszabhatom a munkaidőt bizonyos kivételes dátumokhoz?

5. válasz: Igen, egyéni munkaidőket határozhat meg az egyes kivételdátumokhoz az Aspose.Tasks által biztosított megfelelő módszerekkel.