---
title: Napi naptári ismétlés az Aspose.Tasks-ban
linktitle: Napi naptári ismétlés az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan hozhat létre ismétlődő feladatokat napi naptárismétléssel az Aspose.Tasks for .NET alkalmazásban. Fokozatmentesen fokozza a projektmenedzsment hatékonyságát.
weight: 25
url: /hu/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Napi naptári ismétlés az Aspose.Tasks-ban

## Bevezetés

 Az Aspose.Tasks for .NET hatékony eszközkészletet biztosít a feladatok és projektek programozott kezeléséhez. Egyik figyelemre méltó tulajdonsága a napi naptárismétlések hatékony kezelése. Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatjuk a`DailyCalendarRepetition` osztályt más releváns osztályokkal együtt, hogy napi ismétlődéssel ismétlődő feladatokat hozzon létre egy megadott naptár alapján.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy az alábbiakat beállította:

1.  Telepítés: Győződjön meg arról, hogy az Aspose.Tasks for .NET telepítve van. Ha nem, letöltheti innen[itt](https://releases.aspose.com/tasks/net/).

2. Névtér importálása: Importálja a szükséges névtereket a projektbe:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## 1. lépés: Inicializálja a projektet

Először is be kell töltenünk egy meglévő projektet, vagy létre kell hoznunk egy újat, amellyel dolgozhatunk:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 2. lépés: Határozza meg a naptárat

Ezután létrehozunk egy 24 órás naptárat, és hozzárendeljük a projekthez:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## 3. lépés: Állítsa be az ismétlődő feladatok paramétereit

Most állítsuk be ismétlődő feladatunk paramétereit. Meghatározzuk a nevét, időtartamát, ismétlődési mintáját és tartományát:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## 4. lépés: Állítsa be a naptárat a feladathoz

A meghatározott naptár társítása a feladattal:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## 5. lépés: Adja hozzá a feladatot a projekthez

Adja hozzá a feladatot meghatározott paraméterekkel a projekthez:

```csharp
project.RootTask.Children.Add(parameters);
```

## 6. lépés: Mentse el a projektet

Végül mentse el a projektet a hozzáadott ismétlődő feladattal:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Sikeresen létrehozott egy projektet egy ismétlődő feladattal, amely naponta ismétlődik egy 24 órás naptár alapján az Aspose.Tasks for .NET segítségével!

## Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan használható az Aspose.Tasks for .NET a napi naptárismétlések hatékony kezelésére. E lépések követésével zökkenőmentesen integrálhatja az ismétlődő feladatokat a projektekbe, javítva a termelékenységet és a szervezettséget.

## GYIK

### 1. kérdés: Testreszabhatom az egyes ismétlések időtartamát?

V1: Igen, az egyes ismétlések időtartamát igénye szerint módosíthatja a kód paramétereinek módosításával.

### 2. kérdés: Beállítható-e különböző naptárak különböző feladatokhoz ugyanazon a projekten belül?

2. válasz: Az Aspose.Tasks lehetővé teszi, hogy konkrét naptárakat rendeljen hozzá az egyes feladatokhoz, rugalmasságot biztosítva az ütemezésben.

### 3. kérdés: Az Aspose.Tasks támogat más ismétlődési mintákat a napi rendszeren kívül?

3. válasz: Igen, az Aspose.Tasks az ismétlődési minták széles skáláját kínálja, például heti, havi, éves stb., kielégítve a különféle projektigényeket.

### 4. kérdés: Meg tudom képzelni az Aspose.Tasks segítségével létrehozott ismétlődő feladatokat?

4. válasz: Természetesen az Aspose.Tasks vizualizációs lehetőségeket kínál az ismétlődő feladatok hatékony elemzéséhez és nyomon követéséhez.

### 5. kérdés: Elérhető az Aspose.Tasks próbaverziója?

 5. válasz: Igen, igénybe veheti az Aspose.Tasks ingyenes próbaverzióját[itt](https://releases.aspose.com/) hogy vásárlás előtt ismerkedjen meg funkcióival.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
