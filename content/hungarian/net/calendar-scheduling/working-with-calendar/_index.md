---
title: Munka a naptárral az Aspose.Tasks programban
linktitle: Munka a naptárral az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Az Aspose.Tasks for .NET segítségével könnyedén kezelheti a projektnaptárakat, kiszámíthatja az időtartamokat, kezelheti a kivételeket.
type: docs
weight: 10
url: /hu/net/calendar-scheduling/working-with-calendar/
---
## Bevezetés

Az Aspose.Tasks for .NET hatékony szolgáltatásokat nyújt a naptárak kezeléséhez, lehetővé téve a fejlesztők számára a projekt ütemezésének és az erőforrások kiosztásának hatékony kezelését. Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatja az Aspose.Tasks-t a naptárak használatához, és lefedi az olyan alapvető műveleteket, mint a naptárinformációk lekérése, a munkahetek meghatározása, a munkaórák kiszámítása stb.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy beállította a következő előfeltételeket:

- A C# programozási nyelv alapvető ismerete.
-  Az Aspose.Tasks telepítése .NET-hez. Ha nincs telepítve, töltse le innen[itt](https://releases.aspose.com/tasks/net/).
- A Visual Studio vagy bármely más preferált .NET fejlesztői környezet ismerete.

## Névterek importálása

A kódolás megkezdése előtt feltétlenül importálja a szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Most bontsuk le az egyes példákat több lépésre, lépésről lépésre útmutató formátumban:

## 1. lépés: A naptárinformációk lekérése

A projekt naptáradatainak lekéréséhez kövesse az alábbi lépéseket:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // A naptárak információinak lekérése
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Ismételje meg a projekt minden naptárát.
- Nyomtassa ki az egyes naptárak UID-jét és nevét.

## 2. lépés: Olvassa el a munkahetekre vonatkozó információkat

A munkahétre vonatkozó információk naptárból való olvasásához kövesse az alábbi lépéseket:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezze meg a naptárt UID szerint.
- Iteráljon minden munkahetet a naptárban.
- Minden munkahét nevének, kezdő dátumának és befejező dátumának nyomtatása.
- Váltson végig munkanapokon és munkaidőn belül minden héten.

## 3. lépés: Olvassa el a naptár tulajdonságait

A projektnaptárak tulajdonságainak olvasásához kövesse az alábbi lépéseket:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Ismételje meg a projekt minden naptárát.
- Nyomtassa ki az UID-t, nevet és azt, hogy alapnaptár-e.
- Nyomtasson munkaidőt minden naptípushoz.

## 4. lépés: Számítsa ki a munkaórákat

Egy feladat munkaóráinak kiszámításához kövesse az alábbi lépéseket:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Tekintse meg a feladatok részleteit, például a naptárat, a kezdő dátumot és a befejezési dátumot.
- Számítsa ki a munkaidőt úgy, hogy minden napot megismétel, és ellenőrizze, hogy munkanapról van-e szó.
- Adja össze a teljes időtartamot percekben.

## 5. lépés: Hétköznapok meghatározása a naptárhoz

A naptár hétköznapjainak meghatározásához kövesse az alábbi lépéseket:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Magyarázat:
- Hozzon létre egy új projektet és naptárat.
- Adjon hozzá alapértelmezett munkanapokat (hétfőtől csütörtökig) és egyéni munkaidőket péntekre.
- Állítsa be a szombatot és a vasárnapot munkaszüneti napként.

## 6. lépés: Írja be a frissített naptáradatokat az MPP-be

Frissített naptáradatok MPP-fájlba írásához kövesse az alábbi lépéseket:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/).");
    }
}
```

Magyarázat:
- Töltse be a projektfájlt, és töltse le a szabványos naptárat.
- Módosítsa a naptáradatokat, például a kivételeket és a munkaidőket.
- Mentse el a frissített projektet a módosított naptáradatokkal.

## 7. lépés: Számítsa ki a felosztott feladat befejezési dátumát

Egy felosztott feladat befejezési dátumának kiszámításához kövesse az alábbi lépéseket:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Magyarázat:
- Töltse be a projektfájlt, és töltse le a felosztott feladatot.
- Szerezd meg a projekt naptárát.
- Számítsa ki a befejezési dátumot az egyéni időtartam alapján.

## 8. lépés: A naptári kivételek lekérése

naptárkivételekkel kapcsolatos információk lekéréséhez kövesse az alábbi lépéseket:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Ismételje meg az egyes naptárakat és a kivételeket.
- Nyomtassa ki az egyes kivételek kezdő és befejező dátumát.

## 9. lépés: Szerezze be az alaperőforrás-naptárt

Ha egy erőforrás naptárának alapnaptárával szeretne dolgozni, kövesse az alábbi lépéseket:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Adjon hozzá egy erőforrást és annak naptárát.
- Nyomtassa ki az összes erőforrás alapnaptárnevét.

## 10. lépés: Törölje a naptárat

Ha törölni szeretne egy naptárt egy projektből, kövesse az alábbi lépéseket:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezze meg a naptárt név szerint.
- Törölje a naptárt.

## 11. lépés: Kérje le a befejezési dátumot a kezdéssel és a munkával

A befejezési dátum kezdési dátum és munka alapján történő kiszámításához kövesse az alábbi lépéseket:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezd meg a szabványos naptárat.
- Határozza meg a kezdési dátumot és a munka időtartamát.
- Számítsa ki a befejezési dátumot a kezdési dátum és a munka alapján.

## 12. lépés: Kezdje a következő munkanapot

A következő munkanap naptár használatával indításához kövesse az alábbi lépéseket:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezze meg a naptárt UID szerint.
- Adja meg a következő munkanap kezdési időpontját.

## 13. lépés: Az előző munkanap befejezése

Az előző munkanap végének naptár használatával történő megjelenítéséhez kövesse az alábbi lépéseket:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezze meg a naptárt UID szerint.
- Az előző munkanap befejezési időpontjának lekérése.

## 14. lépés: A kezdési dátum a befejezéstől és az időtartam lekérése

A kezdési dátum befejezési dátum és időtartam szerinti meghatározásához kövesse az alábbi lépéseket:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezze meg a naptárt UID szerint.
- Számítsa ki a kezdési dátumot a befejezés dátumából és időtartamából.

## 15. lépés: Állítsa be a munkaidőt

Ha egy adott dátumra szeretné megadni a munkaidőt, kövesse az alábbi lépéseket:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezze meg a naptárt UID szerint.
- Szerezze meg a megadott dátumra vonatkozó munkaidőt.

## 16. lépés: Szerezze be a munkaidőt

Ha egy adott dátumra szeretne munkaidőt kapni, kövesse az alábbi lépéseket:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Magyarázat:
- Töltse be a projektfájlt.
- Szerezze meg a naptárt UID szerint.
- Szerezze meg a megadott dátumra vonatkozó munkaidőket.

## Következtetés

naptárak használata az Aspose.Tasks for .NET-ben kulcsfontosságú a projekt ütemezésének hatékony kezeléséhez. A mellékelt példákkal és lépésenkénti útmutatókkal egyszerűen kezelheti a naptáradatokat, kiszámíthatja a feladatok időtartamát, és hatékonyan kezelheti a kivételeket. Ha ezeket a funkciókat integrálja alkalmazásaiba, egyszerűsítheti a projektmenedzsment folyamatokat és biztosíthatja a pontos ütemezést.

## GYIK

### 1. kérdés: Szükségem van licencre az Aspose.Tasks for .NET használatához?

 1. válasz: Igen, érvényes licencre van szüksége az Aspose.Tasks for .NET használatához az alkalmazásokban. Vásárolhat teljes licencet, vagy szerezhet 30 napos ideiglenes licencet[itt](https://purchase.aspose.com/temporary-license/).

### 2. kérdés: Módosíthatom a naptárkivételeket programozottan?

2. válasz: Igen, programozottan hozzáadhat, frissíthet vagy törölhet naptárkivételeket az Aspose.Tasks for .NET API-k használatával.

### 3. kérdés: Hogyan számíthatom ki a feladatok befejezési dátumait egyéni időtartammal?

 3. válasz: Az Aspose.Tasks for .NET olyan módszereket biztosít, mint a`GetTaskFinishDateFromDuration()` a feladatok befejezési dátumának kiszámításához egyéni időtartamok alapján.

### 4. kérdés: Lehetséges egyéni naptárak, például éjszakai műszakos naptárak létrehozása?

4. válasz: Igen, létrehozhat egyéni naptárakat, például éjszakai műszakos naptárakat az Aspose.Tasks segítségével .NET API-khoz.

### 5. kérdés: Lekérhetek-e információkat a naptári kivételekről a projektfájlokból?

5. válasz: Igen, az Aspose.Tasks for .NET segítségével könnyedén lekérheti a naptárkivételekre vonatkozó információkat a projektfájlokból.