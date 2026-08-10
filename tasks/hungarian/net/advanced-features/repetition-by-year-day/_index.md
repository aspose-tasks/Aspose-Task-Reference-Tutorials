---
date: 2026-04-03
description: Ismerje meg a projektmenedzsment feladatütemezését, és hogy hogyan adjon
  hozzá ismétlődő feladatot az Aspose.Tasks for .NET használatával, beleértve a projekt
  MPP formátumban való mentését.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Év napja szerinti ismétlés az Aspose.Tasks-ben
second_title: Aspose.Tasks .NET API
title: Projektmenedzsment feladatütemezés éves napismétléssel az Aspose.Tasks-ben
url: /hu/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektmenedzsment feladatütemezés év nap ismétléssel az Aspose.Tasks-ben

## Bevezetés

A hatékony **project management task scheduling** bármely sikeres projekt gerince. Amikor a feladatok éves rendszerességgel ismétlődnek – például éves auditok, karbantartási időszakok vagy szezonális felülvizsgálatok – ezeknek a visszatérő eseményeknek a kézi kezelése hibára hajlamos és időigényes lehet. Az Aspose.Tasks for .NET leegyszerűsíti ezt, lehetővé téve, hogy programozottan határozz meg év‑nap mintákat, így a legfontosabbra koncentrálhatsz: az érték szállítására. Ebben az útmutatóban megtanulod **how to add recurring task** logikát egy adott év napja alapján, és pontosan megmutatjuk, **how to save project as MPP** a Microsoft Project zökkenőmentes integrációjához.

## Gyors válaszok
- **Mi jelent a “year day repetition”?** Egy feladatot ütemez egy adott hónap adott napjára minden évben.  
- **Melyik API osztály hozza létre az ismétlődést?** `YearlyRecurrencePattern` combined with `ByYearDayRepetition`.  
- **Beállíthatok kezdő és befejező dátumot?** Yes, using `EndByRecurrenceRange`.  
- **Milyen fájlformátum jön létre?** The project is saved as an MPP file (`SaveFileFormat.Mpp`).  
- **Szükségem van licencre a termeléshez?** A commercial license is required for non‑evaluation use.

## Előfeltételek

Mielőtt belemerülnél az útmutatóba, győződj meg róla, hogy a következő előfeltételek rendelkezésre állnak:

1. Aspose.Tasks for .NET könyvtár: Töltsd le és telepítsd az Aspose.Tasks for .NET könyvtárat a [weboldalról](https://releases.aspose.com/tasks/net/).  
2. Fejlesztői környezet: Állíts be egy megfelelő fejlesztői környezetet a Visual Studio-val vagy bármely más kedvelt .NET IDE-vel.  
3. Alapvető C# ismeretek: Ismerkedj meg a C# programozási nyelv alapjaival, hogy követhesd a kódrészleteket.  
4. Projektmenedzsment fogalmak: A projektmenedzsment és feladatütemezés koncepcióinak megértése segíti az útmutató anyagának hatékony elsajátítását.

## Névterek importálása

Mielőtt elkezdenénk a kódolást, importáljuk a szükséges névtereket, hogy megkönnyítsük a feladatkezelést az Aspose.Tasks for .NET használatával.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Most bontsuk le a megadott példát több lépésre, és részletesen magyarázzuk el minden egyes lépést.

## Hogyan adjunk hozzá ismétlődő feladatot év nap mintával

### 1. lépés: Projektfájl betöltése

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Itt egy új `Project` objektumot inicializálunk, és betöltünk egy meglévő projektfájlt, amelynek neve **Project1.mpp**.

### 2. lépés: Ismétlődő feladat paramétereinek meghatározása

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

Ebben a lépésben meghatározzuk az ismétlődő feladat paramétereit. Megadjuk a feladat nevét, időtartamát és az ismétlődési mintát. Éves ismétlődéshez a `YearlyRecurrencePattern`-t használjuk, és a `ByYearDayRepetition`-nel állítjuk be, hogy a **július 1. napján** ismétlődjön. Ezen felül meghatározzuk az ismétlődés tartományát 2018. július 1. és 2019. július 1. között.

### 3. lépés: Feladat hozzáadása a projekthez

```csharp
project.RootTask.Children.Add(parameters);
```

Itt hozzáadjuk a meghatározott ismétlődő feladat paramétereit a projekt gyökérfeladatához.

### 4. lépés: Projekt mentése MPP formátumban

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Végül **mentjük a projektet MPP fájlként**, így készen áll a Microsoft Project vagy bármely kompatibilis megjelenítőben való megnyitásra.

## Miért fontos ez

- **Automation** – Eltávolítja a éves feladatok kézi bevitelét, csökkentve az emberi hibákat.  
- **Consistency** – Biztosítja, hogy ugyanaz a nap‑hónap minta több évben is alkalmazásra kerüljön.  
- **Integration** – A létrejött MPP fájl megosztható azzal a stakeholderekkel, akik a Microsoft Project-re támaszkodnak.  

## Gyakori hibák és tippek

- **DateTime precision** – Győződj meg arról, hogy a kezdési időpont illeszkedik a projekt naptárához; ellenkező esetben a feladat eltoltnak tűnhet.  
- **Time zones** – Az API `DateTime` objektumokkal dolgozik; fontold meg az UTC konverziót, ha az alkalmazás több régiót fed le.  
- **License enforcement** – Értékelő módban a mentett MPP vízjelet tartalmazhat; használj érvényes licencet a termeléshez.

## Gyakran ismételt kérdések

**Q: Kezelni tudja az Aspose.Tasks a komplex ismétlődési mintákat?**  
A: Igen, az Aspose.Tasks átfogó támogatást nyújt különféle ismétlődési mintákhoz, beleértve az éves, havi, heti és napi ismétléseket.

**Q: Kompatibilis az Aspose.Tasks különböző projektfájl formátumokkal?**  
A: Teljes mértékben, az Aspose.Tasks támogatja a népszerű projektfájl formátumokat, mint például MPP, XML és CSV, biztosítva a kompatibilitást a különböző projektmenedzsment eszközök között.

**Q: Kínál az Aspose.Tasks dokumentációt és támogatást fejlesztőknek?**  
A: Igen, a fejlesztők hozzáférhetnek kiterjedt dokumentációhoz, és segítséget kérhetnek az Aspose.Tasks közösségi fórumain bármilyen kérdés vagy probléma esetén.

**Q: Testreszabhatom a feladat tulajdonságait, például az időtartamot és a kezdő dátumot az Aspose.Tasks használatával?**  
A: Természetesen, az Aspose.Tasks erős API-kat biztosít a feladattulajdonságok dinamikus manipulálásához, lehetővé téve a fejlesztők számára az időtartamok, kezdő dátumok, függőségek és egyéb elemek testreszabását.

**Q: Alkalmas az Aspose.Tasks kis‑ és nagyvállalati projektekhez egyaránt?**  
A: Igen, az Aspose.Tasks úgy lett tervezve, hogy kielégítse a fejlesztők igényeit minden méretű projektnél, az egyedi feladatoktól a nagyvállalati projektekig.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}