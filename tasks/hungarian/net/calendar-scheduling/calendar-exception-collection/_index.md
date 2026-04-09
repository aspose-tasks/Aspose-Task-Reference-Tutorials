---
date: 2026-04-09
description: Tanulja meg, hogyan állíthat be szabványos naptárat, és kezelheti a projekt
  ünnepnapjait .NET projektjeiben az Aspose.Tasks használatával a pontos ütemezéshez.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Standard naptár beállítása és kivételek kezelése az Aspose.Tasks-ben
second_title: Aspose.Tasks .NET API
title: Állítsa be a szabványos naptárat, és kezelje a kivételeket az Aspose.Tasks-ben
url: /hu/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a szabványos naptárat és kezelje a kivételeket az Aspose.Tasks-ben

## Bevezetés

A pontos ütemezés minden sikeres projekt gerince, és a valós világban a tervek gyakran eltérnek az alapértelmezett munkanaptártól ünnepek, különleges események vagy váratlan leállások miatt. Az Aspose.Tasks for .NET megkönnyíti a **szabványos naptár** beállítását, majd egyedi kivételek hozzáadását. Ebben az útmutatóban megtanulja, hogyan töltsön be egy projekt naptárat, állítsa be a szabványos naptárat, és kezelje a projekt ünnepnapokat a Calendar Exception Collection funkción keresztül.

## Gyors válaszok
- **Mit csinál a „set standard calendar”?** Visszaállítja a naptárat az alapértelmezett munkaidőre (9 h‑17 h, hétfő‑péntek), mielőtt egyedi kivételeket adna hozzá.  
- **Melyik metódus törli a meglévő kivételeket?** A `Calendar.Exceptions.Clear()` eltávolítja az összes korábban definiált kivételt.  
- **Hogyan adhatok hozzá egy ünnepnapot?** Hozzon létre egy `CalendarException`-t, ahol `DayWorking = false`, és adja hozzá a gyűjteményhez.  
- **Szükséges újratölteni a projektet a módosítások után?** Nem, a változások közvetlenül az memóriában lévő `Project` objektumra vonatkoznak.  
- **Milyen könyvtárak szükségesek?** Aspose.Tasks for .NET (bármely támogatott .NET verzió) és a `System` névtér.

## Előfeltételek

Mielőtt belemerülne a kódba, győződjön meg róla, hogy rendelkezik:

1. **Aspose.Tasks for .NET** – töltse le [itt](https://releases.aspose.com/tasks/net/).  
2. Alapvető **C#** ismeretek – néhány rövid kódrészletet fog írni.  
3. Fejlesztői környezet, például **Visual Studio** vagy **JetBrains Rider**.

## Névterek importálása

Ezek a `using` direktívák hozzáférést biztosítanak a naptárkezeléshez szükséges osztályokhoz.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Mi az a Calendar Exception?

A *calendar exception* egy olyan időszakot jelöl, amikor a normál munkarend módosul – például vállalati szintű ünnepnap vagy ideiglenes túlóra ütemezés. Kivétel hozzáadásával a naptárhoz valós világbeli korlátozásokat modellezhet anélkül, hogy az alap naptárat módosítaná.

## Hogyan állítsuk be a szabványos naptárat az Aspose.Tasks-ben

Az első lépés a projektfájl betöltése és a kívánt naptár lekérése.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### 1. lépés: A meglévő kivételek törlése és a szabványos naptár visszaállítása

Új szabályok hozzáadása előtt jó gyakorlat a régi kivételek törlése és a **szabványos naptár** beállítása. Ez tiszta alapot biztosít.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### 2. lépés: Munkavégzési idő kivétel definiálása

Néha ideiglenes ütemtervet kell létrehozni (pl. meghosszabbított munkaidő egy termékbevezetéshez). Az alábbi kódrészlet egy munkavégzési idő kivételt definiál, amely több napra kiterjed, és két napi munkaperiódust tartalmaz.

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

### 3. lépés: Nem munkavégzési idő kivételek hozzáadása (ünnepnapok)

A **projekt ünnepnapok kezelése** érdekében hozzon létre olyan kivételeket, ahol a `DayWorking` értéke `false`. Az alábbi példa egy kétnapos ünnepnap blokkot ad hozzá.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### 4. lépés: Naptárkivétel megjelenítése (ellenőrzés)

Kivételek hozzáadása után gyakran szeretnénk ellenőrizni, hogy helyesen rögzültek-e. Az alábbi ciklus kiírja minden kivétel részleteit a konzolra.

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

### 5. lépés: Minden kivétel eltávolítása (tisztítás)

Ha vissza kell állítani a naptárat az eredeti állapotába, programozottan eltávolíthatja az összes kivételt.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A kivételek nem jelennek meg mentés után | A projekt nem lett mentve a módosítások után | Hívja a `project.Save("output.mpp")` metódust a módosítások után. |
| Átfedő kivételek váratlan munkavégzési órákat okoznak | Az Aspose.Tasks az átfedő időszakoknál az utoljára hozzáadott kivételt használja | Rendezze gondosan az `Add` hívásokat, vagy állítsa be manuálisan a prioritásokat. |
| `MakeStandardCalendar` visszaállítja az egyedi munkavégzési időket | Szándékosan törli az egyedi időket; szükség esetén adja hozzá újra a hívás után | Adja hozzá egyedi `WorkingTime` objektumait a `MakeStandardCalendar` meghívása után. |

## Gyakran ismételt kérdések

**K: Hozzáadhatok több kivételt egy naptárhoz?**  
Igen, több kivételt is hozzáadhat egy naptárhoz az `AddRange` metódus használatával.

**K: Hogyan kezelem az ismétlődő kivételeket, például heti ünnepnapokat?**  
Programozottan kiszámíthatja az ismétlődő kivételeket, és egyedi logikával hozzáadhatja őket a naptárhoz.

**K: Lehetséges naptárkivétel importálása külső forrásokból?**  
Igen, naptárkivételeket beolvashat külső forrásokból, például adatbázisokból vagy CSV fájlokból, és integrálhatja őket a projektbe.

**K: Mi történik, ha átfedő kivételek vannak a naptárban?**  
Az Aspose.Tasks for .NET lehetővé teszi az átfedő kivételek kezelését prioritások meghatározásával vagy a konfliktusok megoldásával a projekt követelményei alapján.

**K: Testreszabhatom az egyes napok munkavégzési időit egy kivételen belül?**  
Igen, egy kivételen belül egyes napokhoz egyedi munkavégzési időket adhat meg, hogy megfeleljen a speciális ütemezési igényeknek.

## Következtetés

Először a **szabványos naptár** beállításával, majd egyedi kivételek hozzáadásával teljes irányítást kap a projekt ütemezése felett, így egyszerűen **kezelheti a projekt ünnepnapokat** és bármilyen egyéb speciális idővonalat. Az Aspose.Tasks Calendar Exception Collection tiszta, programozott módot biztosít a valós világ naptárainak modellezésére közvetlenül .NET alkalmazásaiban.

---

**Utoljára frissítve:** 2026-04-09  
**Tesztelve:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}