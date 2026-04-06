---
date: 2026-04-06
description: Tanulja meg, hogyan adjon hozzá erőforrást a projekthez, és állítsa be
  az erőforrás elérhetőségi időszakait az Aspose.Tasks for .NET használatával. Lépésről‑lépésre
  útmutató az erőforrásnaptárak kezeléséhez.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Az elérhetőségi időszakok kezelése az Aspose.Tasks-ben
second_title: Aspose.Tasks .NET API
title: Erőforrás hozzáadása a projekthez és elérhetőség beállítása az Aspose.Tasks-ben
url: /hu/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erőforrás hozzáadása a projekthez és elérhetőség beállítása az Aspose.Tasks-ben

## Bevezetés

Ebben az útmutatóban megtanulja, **hogyan adjon hozzá erőforrást a projekthez**, majd definiálja annak elérhetőségi időszakait az Aspose.Tasks .NET könyvtár segítségével. Az erőforrásnaptárak kezelése elengedhetetlen a reális projektmenetrendekhez, és az alábbi lépések végigvezetik a teljes folyamaton – a projekt példány létrehozásától az egyes időszakok részleteinek kiírásáig.

## Gyors válaszok
- **Mi a fő cél?** Erőforrás hozzáadása egy projekthez és annak elérhetőségi időszakainak beállítása.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for .NET.  
- **Szükségem van licencre a termeléshez?** Igen, kereskedelmi licenc szükséges.  
- **Támogatott .NET verziók?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Megvalósítási idő?** Általában 15 perc alatt alapvető forgatókönyvek esetén.

## Mi az a „erőforrás hozzáadása a projekthez”?

Erőforrás hozzáadása a projekthez egy helyőrzőt hoz létre egy személy, eszköz vagy anyag számára, amely feladatokhoz rendelhető. Miután az erőforrás létezik, **beállíthatja az erőforrás elérhetőségét**, definiálhatja annak munkanaptárát, és a tervező figyelembe veszi ezeket a korlátokat.

## Miért konfigurálja a munkarendet és az elérhetőségi időszakokat?

- **Pontos tervezés:** A feladatok csak akkor kerülnek ütemezésre, amikor az erőforrás ténylegesen szabad.  
- **Költségkontroll:** Az elérhetőségi egységek a részmunkaidős erőfeszítést tükrözik, segítve a munkaerőköltségek pontos kiszámítását.  
- **Erőforrás kiegyenlítés:** A motor automatikusan kiegyenlíti a túlterheléseket, ha ismeri az egyes erőforrások naptárát.

## Előfeltételek

1. Visual Studio (vagy bármely .NET‑kompatibilis IDE).  
2. Aspose.Tasks for .NET – letöltés innen: [itt](https://releases.aspose.com/tasks/net/).  
3. Alap C# ismeretek.

## Névterek importálása

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Hogyan adjon hozzá erőforrást a projekthez?

### 1. lépés: Új `Project` példány létrehozása

```csharp
var project = new Project();
```

Ez az objektum a teljes projektfájlt képviseli a memóriában.

### 2. lépés: Erőforrás hozzáadása a projekthez

```csharp
var resource = project.Resources.Add("Work Resource");
```

A hívás egy **erőforrást** hoz létre *Work Resource* néven, amelyet később feladatokhoz csatolhat.

### 3. lépés: Elérhetőségi időszakok meghatározása

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` egy segédmetódus (megvalósítás nem látható), amely `AvailabilityPeriod` objektumok gyűjteményét adja vissza. Minden időszak egy kezdő dátumot, egy befejező dátumot és az egységeket (a teljes munkaidő százalékában) tartalmazza, amelyekben az erőforrás elérhető.

### 4. lépés: Időszakok hozzáadása az erőforráshoz

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Itt **beállítjuk az erőforrás elérhetőségét** úgy, hogy végigiterálunk a gyűjteményen, és minden időszakot hozzáadunk az erőforrás naptárához.

### 5. lépés: Az elérhetőségi részletek megjelenítése

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

A konzol kimenet lehetővé teszi, hogy ellenőrizze, az időszakok helyesen lettek-e tárolva.

## Gyakori hibák és tippek

- **Dátum pontosság:** `AvailableFrom` és `AvailableTo` `DateTime` értékek; győződjön meg róla, hogy éjfélre vannak beállítva, ha egész napos időszakokat szeretne.  
- **Egységek tartománya:** Az érvényes értékek 0‑100 %; a tartományon kívüli értékek kivételt okoznak.  
- **Átfedő időszakok:** Az átfedő időszakok automatikusan egyesülnek, de átláthatóbb, ha különállóak maradnak.

## Gyakran ismételt kérdések

### Q1: Használhatom az Aspose.Tasks for .NET-et kereskedelmi projektekben?
A1: Igen, az Aspose.Tasks for .NET használható kereskedelmi projektekben. Licencet vásárolhat [itt](https://purchase.aspose.com/buy).

### Q2: Elérhető ingyenes próba az Aspose.Tasks for .NET-hez?
A2: Igen, ingyenes próbaverziót szerezhet az Aspose.Tasks for .NET-hez [itt](https://releases.aspose.com/).

### Q3: Hol találom az Aspose.Tasks for .NET dokumentációját?
A3: A dokumentációt megtalálja [itt](https://reference.aspose.com/tasks/net/).

### Q4: Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?
A4: Támogatást kaphat a közösségi fórumon [itt](https://forum.aspose.com/c/tasks/15).

### Q5: Kínálnak ideiglenes licenceket az Aspose.Tasks for .NET-hez?
A5: Igen, ideiglenes licencek elérhetők [itt](https://purchase.aspose.com/temporary-license/).

---

**Utolsó frissítés:** 2026-04-06  
**Tesztelve ezzel:** Aspose.Tasks for .NET (legújabb stabil kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}