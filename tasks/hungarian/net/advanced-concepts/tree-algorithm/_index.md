---
date: 2026-03-19
description: Tanulja meg, hogyan adjon hozzá erőforrást a projekthez, és számítsa
  ki a feladat időtartamát az Aspose.Tasks fa algoritmusával, valamint hogyan rendelje
  hozzá az erőforrásokat a feladatokhoz .NET‑ben.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Erőforrás hozzáadása a projekthez fa algoritmussal az Aspose.Tasks-ben
url: /hu/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erőforrás hozzáadása projekthez a Fa Algoritmus segítségével az Aspose.Tasks-ben

## Bevezetés

Ebben az útmutatóban megtudja, **hogyan adjon hozzá erőforrást a projekthez**, az Aspose.Tasks for .NET által biztosított hatékony Fa Algoritmus kihasználásával. Lépésről lépésre végigvezetjük a feladathierarchia létrehozásán, a feladat időtartamának kiszámításán és az erőforrások feladatokhoz rendelésén – mindezt egyértelmű, másolható módon, amelyet saját megoldásába illeszthet.

## Gyors válaszok
- **Mi a Fa Algoritmus feladata?** Egy feladathierarchiát jár be, hogy hatékonyan összegyűjtse a munkamennyiségeket.  
- **Melyik fő műveletet fed le ez az útmutató?** Erőforrás hozzáadása a projekthez és a munkamennyiségek frissítése.  
- **Szükségem van licencre?** Ideiglenes vagy teljes licenc szükséges a termelésben való használathoz.  
- **Használhatom .NET Core‑dal?** Igen, az Aspose.Tasks támogatja a .NET Framework‑öt és a .NET Core‑t.  
- **Mennyi időt vesz igénybe a megvalósítás?** Körülbelül 10‑15 perc egy egyszerű projektfájlhoz.

## Mi az a „erőforrás hozzáadása projekthez” az Aspose.Tasks-ben?

Erőforrás hozzáadása a projekthez azt jelenti, hogy létrehozunk egy `Resource` objektumot, meghatározzuk típusát (pl. work), és a `ResourceAssignments` segítségével egy vagy több feladathoz kapcsoljuk. Ez lehetővé teszi a tervező számára, hogy kiszámolja a ráfordítást, a költséget és a projekt teljes időtartamát.

## Miért használjuk a Fa Algoritmust az erőforrás munkaszámításokhoz?

A Fa Algoritmus egyszer bejárja a feladattafát, és a levélfeladatok munkáját felhalmozva összegzi a szummár feladatoknál. Ez a megközelítés sokkal hatékonyabb, mint minden feladat egyenkénti iterálása, különösen nagy, mély hierarchiájú projektek esetén. Emellett garantálja, hogy a szummár munkamennyiségek szinkronban maradjanak a gyermekekkel.

## Előfeltételek

1. **Visual Studio** – bármelyik legújabb kiadás (2019, 2022 vagy újabb).  
2. **Aspose.Tasks for .NET** – töltsd le [innen](https://releases.aspose.com/tasks/net/).  
3. **Alap C# ismeretek** – kényelmesen kell tudnod osztályokkal, objektumokkal és egyszerű LINQ‑al dolgozni.

## Névtér importálása

A C# projektedben importáld a szükséges névtereket az Aspose.Tasks funkciók használatához:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Most bontsuk le minden példát több lépésre:

## 1. lépés: Projektfájl betöltése

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Töltsd be a projektfájlt a memóriába a `Project` osztály segítségével.

## 2. lépés: Feladathierarchia meghatározása

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Határozd meg a feladathierarchiát szülő‑ és gyermekfeladatok hozzáadásával.

## 3. lépés: Feladat tulajdonságainak beállítása (beleértve a **feladat időtartamának kiszámítását**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Itt **kiszámítjuk a feladat időtartamát** azzal, hogy a munkával töltött órákat `Duration` objektummá alakítjuk, majd meghatározzuk a befejezési dátumot.

## 4. lépés: Erőforrás hozzáadása (**erőforrások feladatokhoz rendelése**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Ez a kódrészlet **hozzáad egy erőforrást a projekthez** és **erőforrásokat rendel feladatokhoz**, így a tervező tudja, ki felelős a munkáért.

## 5. lépés: Fa Algoritmus alkalmazása

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Inicializáld a `WorkAccumulator` osztályt, és alkalmazd a Fa Algoritmust a hierarchiában lévő közös munka összegyűjtésére.

## 6. lépés: Feladatmunka frissítése

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Frissítsd a feladatok munkamennyiségeit a begyűjtött információk alapján.

## Gyakori problémák és tippek

- **Hiányzó naptárbeállítások:** Ha a befejezési dátum hibásnak tűnik, győződj meg róla, hogy a projekt naptár helyesen van beállítva a `GetFinishDateByStartAndWork` hívása előtt.  
- **Erőforrás típus eltérés:** Mindig állítsd be a `Rsc.Type` értékét `ResourceType.Work`‑ra a munkához kapcsolódó erőforrásoknál; egyébként a munka összegzés nulla lehet.  
- **Pro tipp:** A munka frissítése után hívd meg a `project.Save("UpdatedProject.mpp")` függvényt a változások mentéséhez.

## Következtetés

Ezeknek a lépéseknek a követésével most már tudod, hogyan **adj hozzá erőforrást a projekthez**, **számítsd ki a feladat időtartamát**, és **rendelj erőforrásokat feladatokhoz** az Aspose.Tasks Fa Algoritmusával. Ez a módszer egyszerűsíti a hierarchiakezelést és pontosan tartja a szummár munkamennyiségeket minimális kóddal.

## Gyakran Ismételt Kérdések

### Q1: Mi az Aspose.Tasks for .NET?

A1: Az Aspose.Tasks for .NET egy erőteljes API, amely lehetővé teszi a fejlesztők számára, hogy C#‑ban programozottan manipulálják a Microsoft Project fájlokat.

### Q2: Letölthetek ingyenes próbaverziót az Aspose.Tasks for .NET‑ből?

A2: Igen, ingyenes próbaverziót tölthetsz le az Aspose.Tasks for .NET‑ből [innen](https://releases.aspose.com/).

### Q3: Hol találom az Aspose.Tasks for .NET dokumentációját?

A3: A dokumentációt megtalálod [itt](https://reference.aspose.com/tasks/net/).

### Q4: Hogyan kaphatok támogatást az Aspose.Tasks for .NET‑hez?

A4: Támogatásért látogasd meg az [Aspose.Tasks fórumot](https://forum.aspose.com/c/tasks/15).

### Q5: Van ideiglenes licenc tesztelési célokra?

A5: Igen, ideiglenes licencet kaphatsz tesztelési célokra [innen](https://purchase.aspose.com/temporary-license/).

## Gyakran Ismételt Kérdések

**K: Használhatom ezt a megközelítést egy meglévő nagy projektfájllal?**  
A: Természetesen. A Fa Algoritmus bármely `Project` példányon működik, mérettől függetlenül.

**K: A algoritmus frissíti a költségértékeket is?**  
A: A példa a munkára fókuszál, de kiterjeszthető a költségre is, ha a `Tsk.Cost` értékeket hasonló módon halmozod.

**K: Mely .NET verziók támogatottak?**  
A: Az Aspose.Tasks támogatja a .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ és .NET 6+ verziókat.

**K: Hogyan kezelem a több erőforrást egy feladathoz?**  
A: Adj minden erőforrást a `project.ResourceAssignments.Add(task, resource)` metódussal; az akkumulátor automatikusan összeadja a munkájukat.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}