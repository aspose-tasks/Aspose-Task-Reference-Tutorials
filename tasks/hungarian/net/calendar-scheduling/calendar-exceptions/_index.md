---
date: 2026-04-13
description: Ismerje meg, hogyan törölhet naptárkivételt az Aspose.Tasks .NET verziójában,
  és ellenőrizze a kivétel dátumát az ASP.NET naptár ütemezésének kezelése során.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Naptárkivétel törlése az Aspose.Tasks használatával
second_title: Aspose.Tasks .NET API
title: Naptárkivétel törlése az Aspose.Tasks segítségével
url: /hu/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Naptárkivétel törlése az Aspose.Tasks segítségével

## Bevezetés

Ebben az útmutatóban megtanulja, hogyan **delete calendar exception** és kezelje a többi naptárkivételt az Aspose.Tasks-ben a .NET keretrendszer használatával. A naptárkivételek lehetővé teszik, hogy modellezze a szabadságokat, ideiglenes zárásokat vagy bármilyen különleges időszakot, amikor a normál munkarend megváltozik. A kivételek hozzáadásának, lekérdezésének és eltávolításának megértése elengedhetetlen a pontos projektütemezéshez, különösen **ASP.NET calendar scheduling** szcenáriók esetén.

## Gyors válaszok
- **Mi a fő módszer egy kivétel eltávolításához?** Use the `Delete()` method on the `CalendarException` object.  
- **Melyik osztály ellenőrzi a dátumot egy kivétel ellen?** `CalendarException.CheckException()`—useful to **check exception date**.  
- **Szükségem van licencre a kód futtatásához?** Igen, egy érvényes Aspose.Tasks licenc szükséges a termelésben való használathoz.  
- **Hozzáadhatok több kivételt egy naptárhoz?** Természetesen; a `Exceptions` gyűjtemény sok bejegyzést támogat.  
- **Támogatott .NET verziók?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Mi a naptárkivétel?

A **calendar exception** egy eltérést jelent a szabályos munkanaptártól — tekintse úgy, mint egy szabályt, amely azt mondja: „ezeken a dátumokon a munkaidő más vagy egyáltalán nincs.” Az Aspose.Tasks-ben minden kivétel saját munkavégzési időkkel, ismétlődési mintával és jelzőkkel rendelkezhet, amelyek azt mutatják, hogy a nap munkanap-e.

## Miért kezeljük a naptárkivételeket az ASP.NET Calendar Scheduling-ban?

- **Pontos ütemtervek:** A projektek automatikusan figyelembe veszik a szabadságokat és a különleges zárásokat, megakadályozva a irreális határidőket.  
- **Rugalmasság:** Napi, heti, havi vagy éves mintákat definiálhat, amelyek megfelelnek a valós üzleti naptáraknak.  
- **Automatizálás:** A kivétel dátumának programozott ellenőrzése lehetővé teszi, hogy dinamikus ütemezési logikát építsen ASP.NET alkalmazásokban.

## Előfeltételek

- Alapvető C# programozási ismeretek.  
- Visual Studio (bármely friss verzió).  
- Aspose.Tasks for .NET könyvtár hozzáadva a projekthez (NuGet-en vagy manuális hivatkozással).  

## Névtér importálása

Először importálja a szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;
```

## 1. lépés: Naptárkivétel törlése

Egy nem kívánt kivétel eltávolítása egyszerű. Az alábbi kód betölti a projektet, kiválasztja az első naptárat, megjeleníti az alapinformációkat, törli az első kivételt, majd mutatja a frissített számot.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Pro tipp:** Mindig ellenőrizze, hogy a kivétel index létezik-e, mielőtt meghívná a `Delete()`-t, hogy elkerülje a `IndexOutOfRangeException`-t.

## 2. lépés: Naptárkivétel munkavégzési idő lekérése

Ha meg kell vizsgálnia egy kivételhez definiált munkavégzési órákat, használja a `GetWorkingTime()`-t. Ez a példa azt is bemutatja, hogyan **check exception date** a `CheckException` segítségével.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 3. lépés: Naptárkivételek definiálása

Az alábbiakban egy teljes útmutató látható, amely bemutatja, hogyan **add**, **check**, és **remove** naptárkivételeket. Figyelje meg a `CheckException` használatát a **check exception date** egy adott pillanatra.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Gyakori problémák és tippek

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **`IndexOutOfRangeException` törléskor** | Megpróbál egy nem létező kivételt törölni. | Ellenőrizze, hogy a `calendar.Exceptions.Count` > index, mielőtt meghívná a `Delete()`-t. |
| **Helytelen munkavégzési idők** | `DayWorking` vagy `WorkingTimes` helytelen beállítása. | Használja a `exception.WorkingTimes.Add(new WorkingTime(...))`-t explicit időszakok meghatározásához. |
| **A kivétel nem ismerhető fel** | A `CheckException` `false`-t ad vissza, mert a dátum kívül esik a meghatározott tartományon. | Ellenőrizze újra a `FromDate`/`ToDate` és a `Type` (Daily, Weekly, stb.) értékeket. |

## Gyakran ismételt kérdések

**Q: Hozzáadhatok több kivételt egyetlen naptárhoz?**  
A: Igen, annyi kivételt hozzáadhat, amennyire szükség van a szabadságok, karbantartási időszakok vagy bármilyen speciális ütemezési szabályok modellezéséhez.

**Q: Hogyan **check exception date** egy adott napra?**  
A: Használja a `CheckException(DateTime date)` metódust egy `CalendarException` példányon. `true` értéket ad vissza, ha a megadott dátum a kivétel tartományába esik.

**Q: Lehet eltávolítani egy meglévő kivételt egy naptárból?**  
A: Természetesen. Hozzáférhet a `Exceptions` gyűjteményhez, és meghívhatja a `Remove()`-t vagy a `Delete()`-t a konkrét `CalendarException` objektumon.

**Q: Milyen típusú naptárkivételek támogatottak?**  
A: Az Aspose.Tasks támogatja a Daily, Weekly, Monthly és Yearly kivételtípusokat, ami rugalmasságot biztosít szinte bármilyen ismétlődési minta modellezéséhez.

**Q: Testreszabhatom a munkavégzési órákat konkrét kivételdátumokhoz?**  
A: Igen. Kivétel létrehozása után töltse fel a `WorkingTimes` gyűjteményét `WorkingTime` objektumokkal, amelyek meghatározzák az adott nap kezdő- és befejezési időpontját.

## Következtetés

Áttekintettük a **delete calendar exception** műveletek teljes életciklusát, a meglévő kivételek vizsgálatától az újak hozzáadásáig és a dátumok ellenőrzéséig. E technikák elsajátítása biztosítja, hogy projekt ütemezései tiszteletben tartsák a valós naptárakat, így az ASP.NET naptár ütemezési megoldásai robusztusak és megbízhatóak lesznek.

---

**Utoljára frissítve:** 2026-04-13  
**Tesztelve ezzel:** Aspose.Tasks for .NET (latest release)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}