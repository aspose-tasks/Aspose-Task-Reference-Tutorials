---
date: 2026-04-13
description: Ismerje meg, hogyan állíthat be munkaidőket és kezelheti a naptárgyűjteményeket
  az Aspose.Tasks for .NET-ben. Importáljon naptárakat a Microsoft Projectből, távolítson
  el naptárakat a projektből, és könnyedén szerezze be a naptárat név szerint.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Naptárgyűjtemény kezelése az Aspose.Tasks‑ben
second_title: Aspose.Tasks .NET API
title: Munkaidő beállítása az Aspose.Tasks naptárgyűjteményben
url: /hu/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Munkaidő beállítása az Aspose.Tasks naptárgyűjteményben

Ebben az útmutatóban megtanulja, hogyan **állíthat be munkaidőt**, és kezelheti a naptárgyűjteményeket az Aspose.Tasks for .NET segítségével. A naptárak meghatározzák a munkanapokat, ünnepnapokat és kivételeket, így azok elsajátítása lehetővé teszi a projekt ütemezésének pontos irányítását. Bemutatjuk továbbá, hogyan importálhat naptárakat a Microsoft Projectből, hogyan távolíthat el egy naptárat egy projektből, és hogyan kérhet le egy naptárat név alapján.

## Gyors válaszok
- **Mi a fő osztály a naptárakhoz?** `Project.Calendars` gyűjtemény.
- **Hogyan állíthatom be a munkaidőt?** Hozzon létre vagy módosítson egy `Calendar` objektumot, és határozza meg a `WorkingTime`-ját.
- **Importálhatok naptárakat a Microsoft Projectből?** Igen – töltsön be egy MPP fájlt, és érje el annak naptárait.
- **Hogyan távolítható el egy naptár egy projektből?** Használja a `Project.Calendars.Remove(calendar)` metódust.
- **Hogyan kérhető le egy naptár név alapján?** Hívja a `Project.Calendars.GetByName("YourCalendar")` metódust.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy a következőkkel rendelkezik:

1. Visual Studio: Telepítse a Visual Studio-t vagy bármely más, .NET fejlesztéshez kompatibilis IDE-t.  
2. Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET-et innen: [here](https://releases.aspose.com/tasks/net/).  
3. Alapvető C# ismeretek: A C# programozási nyelv ismerete előnyös lesz.

## Névterek importálása

Először importáljuk a szükséges névtereket az Aspose.Tasks használatához:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Új naptár létrehozása

### 1. lépés: Új `Project` objektum inicializálása.
```csharp
var project = new Project();
```

### 2. lépés: Naptárak hozzáadása a projekt naptárgyűjteményéhez.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 3. lépés: A naptárak bejárása és nevének megjelenítése.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Hogyan állítsuk be a munkaidőt egy naptárhoz?

A **munkaidő beállításához** módosítja egy `Calendar` `WorkingTime` gyűjteményét.  
Például definiálhat egy szabványos 9‑17 órás munkanapot, vagy egyedi kivételeket adhat hozzá.  
Ennek a kódja megegyezik a később bemutatott példákkal, amikor egy szabványos naptárat hozunk létre.

## Naptár cseréje egy új naptárral

### 1. lépés: Létező projekt betöltése.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2. lépés: A meglévő naptár eltávolítása (ha létezik).  
Ez bemutatja a **naptár eltávolítása a projektből** szcenáriót.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 3. lépés: Új naptár hozzáadása.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Naptár lekérése név vagy azonosító alapján

### 1. lépés: Projekt betöltése.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2. lépés: Naptárak lekérése név vagy UID alapján.  
Ez szemlélteti a **naptár lekérése név alapján** műveletet.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 3. lépés: Naptár részleteinek megjelenítése.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Naptárak bejárása

### 1. lépés: Projekt betöltése.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 2. lépés: Naptárak számának lekérése.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 3. lépés: A naptárgyűjtemény bejárása és nevek megjelenítése.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Szabványos naptár létrehozása

### 1. lépés: Új projekt inicializálása.
```csharp
var project = new Project();
```

### 2. lépés: Új naptár definiálása és szabványossá tétele.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 3. lépés: Projekt mentése.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Gyakori problémák és megoldások

- **Naptár nem található a `GetByName` használatakor** – Győződjön meg arról, hogy a pontos név megegyezik a naptár hozzáadásakor használt esetérzékeny névvel.  
- **A munkaidő nem alkalmazódik** – A `WorkingTime` beállítása után ne felejtse el menteni a projektet; különben a változások csak memóriában maradnak.  
- **A naptárak importálása MPP fájlból sikertelen** – Ellenőrizze, hogy a forrásfájl érvényes Microsoft Project fájl, és hogy rendelkezik olvasási jogosultsággal.

## Gyakran Ismételt Kérdések

### Q1: Létrehozhatok egyedi munkanapokat az Aspose.Tasks-ben?

A1: Igen, egyedi munkanapokat hozhat létre a naptárakhoz kivételeket hozzáadva.

### Q2: Lehetséges naptárakat importálni Microsoft Project fájlokból?

A2: Teljesen, az Aspose.Tasks támogatja a naptárak importálását Microsoft Project fájlokból.

### Q3: Hogyan távolíthatok el egy konkrét naptárat egy projektből?

A3: Egy naptárat a gyűjteményből lekérve, majd a `Remove` metódus meghívásával távolíthat el.

### Q4: Támogatja az Aspose.Tasks a naptárak exportálását különböző formátumokba?

A4: Igen, az Aspose.Tasks lehetővé teszi a naptárak exportálását különböző formátumokba, például XML, MPP stb.

### Q5: Testreszabhatom a munkaidőt egy naptárban konkrét napokra?

A5: Természetesen, a naptárban kivételek segítségével meghatározhatja a munkaidőt egyedi napokra.

## Gyakran Ismételt Kérdések

**Q: Mi a legjobb mód egy 24‑órás műszak naptár beállítására?**  
A: Hozzon létre egy új naptárat, törölje a meglévő `WorkingTime` bejegyzéseket, és minden hétköznapra adjon hozzá egyetlen `WorkingTime` tartományt 00:00-tól 24:00-ig.

**Q: Másolhatok egy naptárat egy projektből a másikba?**  
A: Igen – exportálja a naptárat XML-be a `project.Save` segítségével, majd importálja egy másik projektbe a `new Project(xmlPath)` használatával.

**Q: Hogyan importálhatok programozottan naptárakat a Microsoft Projectből?**  
A: Töltse be az MPP fájlt a `new Project("source.mpp")` paranccsal; a naptárak a `project.Calendars` segítségével elérhetők.

**Q: Van korlát a projektben lévő naptárak számát illetően?**  
A: Gyakorlatilag nincs; a gyűjtemény annyi naptárt tárolhat, amennyi a memória engedi, de a teljesítmény érdekében érdemes a listát kezelhető méretűen tartani.

**Q: A naptár módosításai automatikusan frissítik a hozzá kapcsolt feladatokat?**  
A: Igen – a naptárhoz kapcsolt feladatok a projekt mentése után tükrözik a frissített munkaidőket.

---

**Utolsó frissítés:** 2026-04-13  
**Tesztelve:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}