---
date: 2026-04-03
description: Ismerje meg, hogyan használja az Aspose.Tasks-et ismétlődő feladatok
  hozzáadásához a projektben, és hogyan mentse a projektet MPP formátumban. Ez az
  útmutató lépésről lépésre mutatja be az Év/Hét/Nap ismétlés funkciót.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Ismétlés év, hét, nap szerint az Aspose.Tasks-ben
second_title: Aspose.Tasks .NET API
title: Hogyan használjuk az Aspose.Tasks-et – Ismétlés év, hét, nap szerint
url: /hu/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Éves ismétlés hét nap szerint az Aspose.Tasks-ben

## Bevezetés

Amikor **how to use Aspose.Tasks**-et kell használni összetett ismétlődő ütemezések kezelésére, a könyvtár finomhangolt vezérlést biztosít az éves minták felett. Ebben az útmutatóban végigvezetünk egy feladat létrehozásán, amely egy adott hónap meghatározott hétnapján ismétlődik több év alatt. A végére képes leszel **add recurring task project** bejegyzéseket létrehozni és **save project as MPP** néhány C# sorral.

## Gyors válaszok
- **Mit jelent a “Repetition by Year Week Day”?** Egy feladatot ismétel egy kiválasztott hétnapon (pl. első vasárnap) egy adott hónapban minden évben.  
- **Mely .NET verziók támogatottak?** Minden modern .NET Framework és .NET Core/5/6 verzió.  
- **Szükség van licencre a kód futtatásához?** Egy ingyenes próba verzió fejlesztéshez elegendő; a termeléshez kereskedelmi licenc szükséges.  
- **Módosítható az ismétlődés időtartama?** Igen – beállítható kezdő dátum, befejező dátum vagy rögzített előfordulásszám.  
- **Az eredmény MPP fájl lesz?** Természetesen – a projekt MPP fájlként kerül mentésre, készen a Microsoft Project számára.

## Mi a “Repetition by Year Week Day” funkció?

Ez a funkció lehetővé teszi egy éves ismétlődés definiálását, amely egy adott **hét napját** (pl. vasárnap) és a **pozíciót** a hónapban (első, második, utolsó stb.) célozza meg. Ideális például negyedéves felülvizsgálatokhoz, éves auditokhoz vagy bármely naptár‑alapú ritmusú eseményhez.

## Miért használjuk az Aspose.Tasks‑et ismétlődő feladatokhoz?

- **Pontosság** – Teljes vezérlés a hónapok, hétnapok és sorszámok felett.  
- **Kompatibilitás** – Natív MPP fájlokat generál, amelyek hibátlanul nyílnak meg a Microsoft Projectben.  
- **Nincs COM interop** – Tiszta .NET API, nincs szükség Office telepítésre.  
- **Skálázhatóság** – Kis projektekhez és vállalati szintű ütemezésekhez egyaránt alkalmas.

## Előfeltételek

Mielőtt a kódba merülnél, győződj meg róla, hogy rendelkezel:

1. **Alap .NET ismeretekkel** – C# és objektum‑orientált koncepciók ismerete.  
2. **Aspose.Tasks for .NET** – Töltsd le a [letöltési link](https://releases.aspose.com/tasks/net/)‑ről, és add hozzá a DLL‑t a projektedhez.  
3. **Hozzáférés a hivatalos dokumentációhoz** – A [dokumentáció](https://reference.aspose.com/tasks/net/) kimerítő részleteket tartalmaz minden osztályról.  
4. **Fejlesztői IDE** – Visual Studio, Rider vagy bármely kompatibilis .NET szerkesztő.

Most, hogy minden készen áll, nézzük meg a megvalósítást.

## Hogyan használjuk az Aspose.Tasks‑et ismétlődő feladatokhoz

### Szükséges névterek importálása

Először hozd be a szükséges névtereket, hogy a projektek, feladatok és mentési beállítások kezelhetők legyenek.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 1. lépés: Projekt és feladatparaméterek inicializálása

Hozz létre egy új `Project` példányt, majd definiálj egy `RecurringTaskParameters` objektumot, amely leírja az ismétlődési mintát.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tipp:** Állítsd be a `Month`, `WeekDay` és `Position` értékeket a valós ütemezésednek megfelelően.

### 2. lépés: Paraméterek hozzáadása a projekthez

Illeszd be az ismétlődő feladat definícióját a projekt gyökerébe.

```csharp
project.RootTask.Children.Add(parameters);
```

### 3. lépés: Projekt mentése MPP‑ként

Végül mentsd a projektet egy MPP fájlba, hogy megnyitható legyen a Microsoft Projectben vagy bármely kompatibilis megjelenítőben.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Ez bemutatja a **save project as mpp** funkciót egyetlen kódsorban.

## Gyakori problémák és megoldások

| Tünet | Valószínű ok | Megoldás |
|---------|--------------|-----|
| Nem jelennek meg feladatok a MPP fájl megnyitása után | Az ismétlődés időtartam dátumai kívül esnek a projekt naptárán | Ellenőrizd, hogy a `Start` és `Finish` dátumok a projekt munkaidejében legyenek |
| `ArgumentNullException` kivétel a `Add` hívásakor | `parameters` null vagy nincs teljesen inicializálva | Győződj meg róla, hogy minden kötelező tulajdonság (TaskName, Duration, RecurrencePattern) be van állítva |
| Rossz hétnap lett kiválasztva | `WeekDay` enum érték nem egyezik | Használd a `DayOfWeek.Monday` … `DayOfWeek.Sunday` értékeket a szükséges naphoz |

## Gyakran feltett kérdések

**K: Testreszabható-e az ismétlődési minta a példán túl?**  
V: Igen, az Aspose.Tasks lehetővé teszi a `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` vagy akár egyedi `RecurrenceRange` objektumok kombinálását bármilyen ütemezéshez.

**K: Az Aspose.Tasks for .NET kompatibilis-e más projektmenedzsment szoftverekkel?**  
V: Teljesen – a könyvtár MPP, XML és Primavera formátumokat olvas és ír, így zökkenőmentes adatcserét biztosít.

**K: Hogyan kezeljem a kivételeket vagy módosításokat az ismétlődő feladatoknál?**  
V: Használd az `ExceptionTask` osztályt specifikus előfordulások felülírásához, vagy szerkeszd a `RecurringTaskParameters`‑t, majd mentsd újra a projektet.

**K: Támogatja-e az Aspose.Tasks a felhőalapú megoldásokat?**  
V: Igen, az API futtatható Azure Functions‑ben, AWS Lambda‑ban vagy bármely .NET‑kompatibilis felhőszolgáltatásban.

**K: Elérhető-e próba verzió az Aspose.Tasks for .NET‑hez?**  
V: Igen, a [weboldal](https://releases.aspose.com/) ingyenes próbaverziót kínál, amely lehetővé teszi a funkciók kipróbálását vásárlás előtt.

**K: Hogyan adhatok hozzá ismétlődő feladatot egy meglévő projekthez anélkül, hogy felülírnám a többi adatot?**  
V: Töltsd be a meglévő projektet a `new Project("Existing.mpp")`‑vel, add hozzá a `RecurringTaskParameters`‑t a `RootTask.Children`‑hez, majd `Save`-old a fájlt.

## Következtetés

Az **how to use Aspose.Tasks** a **Repetition by Year Week Day** szcenárióhoz való elsajátításával képes leszel **add recurring task project** bejegyzéseket létrehozni, amelyek tökéletesen illeszkednek a valós naptárakhoz, és **save project as MPP** a zökkenőmentes együttműködés érdekében. Illeszd be ezeket a kódrészleteket saját megoldásaidba a tervezési pontosság növelése és a manuális munka csökkentése érdekében.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}