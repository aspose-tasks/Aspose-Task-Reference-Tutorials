---
title: Naptári kivételek gyűjteménye az Aspose.Tasks-ban
linktitle: Naptári kivételek gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Tanulja meg, hogyan kezelheti hatékonyan a naptárkivételeket a .NET-projektekben az Aspose.Tasks segítségével, biztosítva a pontos ütemezést és az erőforrás-kezelést.
type: docs
weight: 13
url: /hu/net/calendar-scheduling/calendar-exception-collection/
---
## Bevezetés

projektmenedzsmentben a pontos ütemezés elengedhetetlen a sikerhez. A valós forgatókönyvek azonban gyakran megkövetelik a szokásos ütemezéstől való eltérést ünnepek, különleges események vagy egyéb tényezők miatt. Az Aspose.Tasks for .NET robusztus megoldást kínál az ilyen kivételek kezelésére a Calendar Exception Collection szolgáltatáson keresztül. Ez az oktatóanyag lépésről lépésre végigvezeti Önt a funkció használatának folyamatán.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1.  Aspose.Tasks for .NET: Győződjön meg arról, hogy a könyvtár telepítve van. Letöltheti[itt](https://releases.aspose.com/tasks/net/).
2. A C# alapismerete: A C# programozási nyelv ismerete segít a példák megértésében.
3. Fejlesztési környezet: Állítsa be a kívánt fejlesztői környezetet, például a Visual Studio vagy a JetBrains Rider.

## Névterek importálása

Mielőtt elkezdené a munkát az Aspose.Tasks for .NET-hez, importálnia kell a szükséges névtereket a projektbe. Ez a lépés lehetővé teszi a naptárkivételek kezeléséhez szükséges osztályok és metódusok elérését.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Most bontsuk fel a példát több lépésre:

## 1. lépés: A projekt betöltése és a naptár visszakeresése

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Ebben a lépésben betöltünk egy projektfájlt, és lekérjük a kívánt naptárt az UID alapján.

## 2. lépés: Törölje a meglévő kivételeket és állítsa be a szabványos naptárat

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Ez a lépés törli a meglévő kivételeket a naptárból, és normál konfigurációra állítja be.

## 3. lépés: Munkaidő-kivétel meghatározása és hozzáadása

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Ez a lépés munkaidő-kivételt határoz meg meghatározott kezdési és befejezési dátumokkal, valamint az ezen dátumokon belüli munkaidővel, és hozzáadja azt a naptárhoz.

## 4. lépés: Határozza meg és adja hozzá a nem munkaidő-kivételeket

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Adjon hozzá további kivételeket, ha szükséges

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Ez a lépés meghatározza a munkaidőn kívüli kivételeket, például a szabadságokat, és hozzáadja őket a naptárhoz.

## 5. lépés: Jelenítse meg a naptári kivételeket

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Ez a lépés megjeleníti a hozzáadott naptári kivételeket a részletekkel együtt.

## 6. lépés: Távolítsa el az összes kivételt

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Végül ez a lépés eltávolítja az összes kivételt a naptárból.

## Következtetés

naptári kivételek kezelése kulcsfontosságú a projekt pontos ütemezéséhez. Az Aspose.Tasks for .NET leegyszerűsíti ezt a feladatot azáltal, hogy átfogó szolgáltatáskészletet biztosít, beleértve a Calendar Exception Collectiont. Az oktatóanyagban ismertetett lépések követésével hatékonyan kezelheti a projektjein belüli különböző ütemezési forgatókönyveket.

## GYIK

### 1. kérdés: Hozzáadhatok több kivételt egyetlen naptárhoz?

 1. válasz: Igen, a naptárhoz több kivételt is hozzáadhat a`AddRange` módszer.

### 2. kérdés: Hogyan kezelhetem az ismétlődő kivételeket, például a heti ünnepeket?

2. válasz: Programozottan kiszámíthatja az ismétlődő kivételeket, és egyéni logika segítségével hozzáadhatja őket a naptárhoz.

### 3. kérdés: Lehetséges-e naptárkivételek importálása külső forrásokból?

3. válasz: Igen, beolvashat naptárkivételeket külső forrásokból, például adatbázisokból vagy CSV-fájlokból, és integrálhatja azokat a projektjébe.

### 4. kérdés: Mi történik, ha átfedő kivételek vannak a naptárban?

4. válasz: Az Aspose.Tasks for .NET lehetővé teszi az egymást átfedő kivételek kezelését prioritások meghatározásával vagy az ütközések feloldásával a projekt követelményei alapján.

### 5. kérdés: Testreszabhatom-e a munkaidőt minden egyes napra, kivételen belül?

5. válasz: Igen, egyedi munkaidőket határozhat meg az egyes napokra, kivételeken belül, hogy megfeleljen a konkrét ütemezési igényeknek.