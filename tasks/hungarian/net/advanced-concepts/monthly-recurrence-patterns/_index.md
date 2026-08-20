---
date: 2026-03-08
description: Tanulja meg, hogyan hozhat létre havi ismétlődő feladatot az Aspose.Tasks
  for .NET-ben ezzel a lépésről‑lépésre útmutatóval.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hogyan hozhatunk létre havi ismétlődő feladatot az Aspose.Tasks-ben
url: /hu/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Havi Ismétlődő Feladat Létrehozása az Aspose.Tasks Segítségével

## Introduction

Az Aspose.Tasks for .NET lehetővé teszi, hogy programozottan manipulálja a Microsoft Project fájlokat, és az egyik leggyakoribb valós igény a **havi ismétlődő feladat** ütemezések létrehozása. Akár projektkövető eszközt épít, erőforrás-elosztást automatizál, vagy ismétlődő karbantartási munkákat generál, ez az útmutató lépésről lépésre bemutatja, hogyan adjon hozzá havi ismétlődési mintát egy feladathoz.

## Quick Answers
- **Mit jelent a “havi ismétlődő feladat”?** Egy feladat, amely minden hónapban egy meghatározott nap‑ vagy hétmintára ismétlődik.  
- **Melyik API osztály kezeli az ismétlődést?** `RecurringTaskParameters` együtt a `MonthlyRecurrencePattern`-nel.  
- **Szükségem van licencre a minta futtatásához?** Egy ingyenes próba verzió elegendő értékeléshez; licenc szükséges a termeléshez.  
- **Módosíthatom az intervallumot?** Igen – állítsa be a `RepetitionInterval` értékét a megjelenések közötti hónapok számára.  
- **Milyen fájlformátumok támogatottak?** Mind a `.mpp`, mind a `.xml` Project fájlok betölthetők és menthetők.

## What is a Monthly Recurrence Pattern?

A havi ismétlődési minta megmondja a Microsoft Projectnek (és az Aspose.Tasks-nek), hogy egy feladatnak havonta milyen gyakran kell ismétlődnie. Megadhat egy fix napot a hónapban (pl. az 1‑et) vagy egy relatív pozíciót (pl. az utolsó péntek). Az API ezeket a szabályokat a projektfájl alapszerkezetébe fordítja.

## Why use Aspose.Tasks for this?

- **Teljes irányítás** – Nincsenek UI korlátozások; a minta minden aspektusát kódból definiálja.  
- **Kereszt‑platform** – működik .NET Framework, .NET Core és .NET 5/6+ környezetben.  
- **Microsoft Project nem szükséges** – fájlokat generálhat vagy módosíthat egy szerveren vagy CI pipeline-ban.  

## Prerequisites

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

- .NET 6 (vagy .NET 5/Framework 4.7+) telepítve.  
- Aspose.Tasks for .NET NuGet csomag hozzáadva a projektjéhez.  
- Egy minta Project fájl (`Project1.mpp`) egy ismert mappában (`DataDir`).  

## Import Namespaces

Először importálja a feladatokkal való munka és a projektek mentéséhez szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Step 1: Initialize the Project

Hozzon létre egy `Project` példányt, amely az Ön meglévő `.mpp` fájljára mutat. Ez betölti a fájlt a memóriába, hogy módosíthassa.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Pro tip:** Ha a fájl nem létezik, az Aspose.Tasks automatikusan létrehoz egy új üres projektet.

## Step 2: Set Recurring Task Parameters

Határozza meg a havi ismétlődő feladat részleteit, beleértve a nevét, időtartamát és a alkalmazni kívánt havi mintát.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` azt jelenti, hogy a feladat a **hónap első napján** fordul elő.  
- `RepetitionInterval = 2` azt eredményezi, hogy a feladat **két havonta** ismétlődik.  
- `Start` és `Finish` határozza meg azt az időablakot, amelyen belül az ismétlődés aktív.

## Step 3: Add Parameters to the Project

Csatolja a `RecurringTaskParameters` objektumot a gyökérfeladat gyermekgyűjteményéhez. Ez hatékonyan létrehozza az ismétlődő feladatot a projekt hierarchiájában.

```csharp
project.RootTask.Children.Add(parameters);
```

## Step 4: Save the Project

Mentse el a változásokat egy új fájlba. Bármely támogatott formátumot választhat; itt a natív `.mpp` formátumot használjuk.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

A kód futtatása után nyissa meg a létrejött fájlt a Microsoft Projectben, hogy lássa a most létrehozott havi ismétlődő feladatot.

## Common Issues and Solutions

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A feladat nem jelenik meg a mentés után | A projekt nem frissült a UI-ban | Nyissa meg újra a fájlt, vagy hívja meg a `project.UpdateTaskLinks()` metódust mentés előtt. |
| Hibás kezdő dátum | `Start` hétvégére van állítva | Használjon olyan `DateTime` értéket, amely munkanapra esik, vagy állítsa be a naptárat. |
| Az ismétlődési intervallum figyelmen kívül marad | `ByMonthDayRepetition` használata `DayPosition` = 0 értékkel | Győződjön meg arról, hogy a `DayPosition` 1‑31 között van. |

## Conclusion

Az itt bemutatott lépések követésével most már tudja, hogyan **hozzon létre havi ismétlődő feladat** ütemezéseket az Aspose.Tasks for .NET segítségével. Az API finomhangolt vezérlést biztosít az ismétlődési intervallumok, a kezdő‑befejező tartományok és a konkrét napminták felett, lehetővé téve a komplex projekttervezési forgatókönyvek automatizálását.

## FAQ's

### Q1: Az Aspose.Tasks kompatibilis-e a Microsoft Project minden verziójával?

A1: Az Aspose.Tasks különböző Microsoft Project fájlverziókat támogat, beleértve az MPP, MPT, XML és MPX formátumokat.

### Q2: Testreszabhatom-e tovább az ismétlődési mintát?

A2: Igen, az Aspose.Tasks kiterjedt lehetőségeket kínál az ismétlődési minták testreszabására, beleértve a napi, heti, havi és éves mintákat.

### Q3: Van ingyenes próba verzió az Aspose.Tasks-hez?

A3: Igen, ingyenes próba verziót szerezhet az Aspose.Tasks weboldalán [itt](https://releases.aspose.com/).

### Q4: Hogyan kaphatok támogatást az Aspose.Tasks-hez?

A4: Segítséget kérhet és részt vehet a megbeszélésekben az [Aspose.Tasks fórumon](https://forum.aspose.com/c/tasks/15).

### Q5: Hol vásárolhatok licencet az Aspose.Tasks-hez?

A5: Licencet vásárolhat az Aspose.Tasks weboldalán [itt](https://purchase.aspose.com/buy).

## Frequently Asked Questions

**Q: Használhatom ezt a kódot .NET Core alkalmazásban?**  
A: Természetesen. Az Aspose.Tasks for .NET teljes mértékben támogatja a .NET Core 3.1 és későbbi verziókat.

**Q: Hogyan változtathatom meg az ismétlődést „a hónap utolsó munkanapjára”?**  
A: Használja a `ByMonthDayRepetition`-t `DayPosition = -1` értékkel (a negatív értékek a hónap végétől számolnak) és állítsa be a `WeekDay`-t ennek megfelelően.

**Q: Mi történik, ha az ismétlődési tartomány meghaladja a projekt naptárát?**  
A: Az API tiszteletben tartja a projekt naptárát; a nem munkanapokra eső előfordulások vagy kihagyásra kerülnek, vagy a naptár beállításai szerint áthelyezésre kerülnek.

**Q: Lehet-e törölni egy adott előfordulását egy ismétlődő feladatnak?**  
A: Igen. Az ismétlődő feladat hozzáadása után lekérheti az egyes előfordulásokat a `Task.GetOccurrences()` segítségével, és törölheti a feleslegeseket.

**Q: Kezeli-e az Aspose.Tasks automatikusan az időzóna‑különbségeket?**  
A: A könyvtár UTC‑ben tárolja a dátumokat; szükség esetén a szabványos .NET `DateTime` metódusokkal konvertálhat helyi időre.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}