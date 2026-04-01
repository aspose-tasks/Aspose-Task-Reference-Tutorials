---
date: 2026-04-01
description: Ismerje meg, hogyan állíthat be ismétlődést az Aspose.Tasks for .NET-ben,
  hogyan adhat hozzá ismétlődő feladatot, és hogyan automatizálhatja az ismétlődő
  feladatokat hónap, hét és nap szerint.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Ismétlés hónap, hét, nap szerint az Aspose.Tasks-ben
second_title: Aspose.Tasks .NET API
title: Hogyan állítsuk be az ismétlődést az Aspose.Tasks-ben (hónap, hét, nap)
url: /hu/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be az ismétlődést az Aspose.Tasks-ben (Hónap, Hét, Nap)

## Bevezetés

Ha **hogyan állítsuk be az ismétlődést** kell megvalósítani a feladatokhoz egy projektben, az Aspose.Tasks for .NET tiszta, programozott módot kínál az ismétlődő feladatdefiníciók hozzáadására, amelyek havonta, hetente vagy naponta futnak. Ebben az útmutatóban egy valós példán keresztül mutatjuk be, hogyan **adjunk hozzá ismétlődő feladat** bejegyzéseket, **automatizáljuk az ismétlődő feladatokat**, és kezeljük őket közvetlenül C# kódból. A végére készen áll majd arra, hogy ezt a képességet bármely ütemezési vagy projektmenedzsment megoldásba integrálja.

## Gyors válaszok
- **Mi jelent a „recurrence” az Aspose.Tasks-ben?** Egy mintát (napi, heti, havi) határoz meg, amely automatikusan hoz létre feladatpéldányokat egy dátumtartományon belül.  
- **Melyik elsődleges metódus hozza létre az ismétlődést?** `RecurringTaskParameters` kombinálva egy adott `RecurrencePattern`-el.  
- **Szükségem van licencre a kód futtatásához?** A próbaverzió értékelésre használható; a kereskedelmi licenc szükséges a termeléshez.  
- **Ütemezhetek heti feladatokat a havi helyett?** Igen – cserélje a `MonthlyRecurrencePattern`-ot `WeeklyRecurrencePattern`-ra.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 és későbbi.

## Mi az ismétlődés az Aspose.Tasks-ben?

Az ismétlődés egy szabálykészlet, amely azt mondja az Aspose.Tasks-nek, hogy rendszeres időközönként – napi, heti vagy havi – generáljon feladatpéldányokat anélkül, hogy manuálisan másolná őket. Ez a funkció elengedhetetlen azokhoz a projektekhez, amelyek rutintevékenységeket tartalmaznak, például állapotértekezleteket, ellenőrzéseket vagy karbantartási munkákat.

## Miért használjuk az ismétlődés funkciókat?

- **Idő megtakarítás:** Nincs szükség a feladatok kézi másolására.  
- **Hibák csökkentése:** A könyvtár garantálja a konzisztens dátumokat és időtartamokat.  
- **Rugalmasság:** Kombináljon mintákat (pl. „az első vasárnap minden 2 hónapban”).  
- **Automatizálás:** Tökéletes ütemezések generálásához CI csővezetékekben vagy jelentéskészítő eszközökben.

## Előfeltételek

1. **Alapvető C# ismeretek** – néhány C# sort fog írni.  
2. **Aspose.Tasks for .NET telepítve** – szerezze be a [letöltési oldalról](https://releases.aspose.com/tasks/net/).  
3. **Egy .mpp projektfájl** – a `Project1.mpp` fájlt fogjuk forrásként használni.

## Névterek importálása

A kezdéshez importálja a szükséges Aspose.Tasks névtereket:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 1. lépés: Projektfájl betöltése

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Létrehozunk egy `Project` példányt, amely egy meglévő Microsoft Project fájlra mutat.

### 2. lépés: Ismétlődő feladat paraméterek meghatározása

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Itt **ismétlődő feladat** paramétereket **hozzuk létre**:

- **TaskName** – a generált feladat neve.  
- **Duration** – mennyi ideig tart egy-egy előfordulás.  
- **RecurrencePattern** – egy havi minta, amely minden 2 hónapban az első vasárnapon ismétlődik.  
- **RecurrenceRange** – a kezdő és befejező dátumok, amelyek a menetrendet határolják.

### 3. lépés: Ismétlődő feladat hozzáadása a projekthez

```csharp
project.RootTask.Children.Add(parameters);
```

Ez a sor **hozzáadja az ismétlődő feladatot** a projekt hierarchia gyökeréhez.

### 4. lépés: Frissített projekt mentése

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

A projekt új `.mpp` fájlként kerül mentésre, amely most már tartalmazza az automatizált ütemezést.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Feladat nem jelenik meg** | Az ismétlődés tartománya kívül esik a projekt dátumain. | Ellenőrizze, hogy a `Start` és `Finish` értékek a projekt naptárán belül vannak-e. |
| **Helytelen hétnap** | `WeekDay` enum eltérés. | Használja a `DayOfWeek.Monday` … `DayOfWeek.Sunday` értékeket szükség szerint. |
| **Licenc kivétel** | Érvényes licenc nélkül futtatás a termelésben. | Alkalmazzon ideiglenes vagy teljes licencet a mentés előtt. |

## Gyakran Ismételt Kérdések

### Q1: Testreszabhatom az ismétlődési mintát a megadott példákon túl?

Igen, az Aspose.Tasks for .NET kiterjedt testreszabási lehetőségeket kínál az ismétlődési mintákhoz, lehetővé téve, hogy azokat az Ön konkrét igényeihez igazítsa.

### Q2: Elérhető-e próbaverzió az Aspose.Tasks for .NET-hez?

Igen, ingyenes próbaverziót szerezhet az Aspose.Tasks for .NET-ből a [kiadási oldalon](https://releases.aspose.com/).

### Q3: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?

Segítséget kérhet és csatlakozhat a közösséghez az [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15).

### Q4: Elérhetők-e ideiglenes licencek az Aspose.Tasks for .NET-hez?

Igen, ideiglenes licenceket szerezhet a [vásárlási oldalon](https://purchase.aspose.com/temporary-license/) tesztelési és értékelési célokra.

### Q5: Hol találok átfogó dokumentációt az Aspose.Tasks for .NET-hez?

Részletes [dokumentációt](https://reference.aspose.com/tasks/net/) talál az Aspose weboldalán, amely alapos útmutatót nyújt a könyvtár használatához.

---

**Utolsó frissítés:** 2026-04-01  
**Tesztelve:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}