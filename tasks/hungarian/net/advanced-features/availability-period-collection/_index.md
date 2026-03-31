---
date: 2026-03-21
description: Ismerje meg, hogyan kezelheti az erőforrások rendelkezésre állási időszakait,
  és érhet el hatékony projekt‑erőforrás‑elérhetőséget az Aspose.Tasks for .NET segítségével.
  Ez a lépésről‑lépésre útmutató bemutatja, hogyan adhat hozzá, frissíthet és távolíthat
  el rendelkezésre állási időszakokat.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projekt erőforrások elérhetősége – Az elérhetőségi időszakok kezelése az Aspose.Tasks-ben
url: /hu/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projekt erőforrás elérhetőség: Elérhetőségi időszakok gyűjteménye az Aspose.Tasks-ben

A **projekt erőforrás elérhetőség** kezelése a sikeres projekttervezés alapvető része. Ebben az oktatóanyagról megtanulja, **hogyan kezelje az elérhetőséget** az erőforrások számára az Aspose.Tasks for .NET API segítségével, lépésről‑lépésre, a projekt betöltésétől az időszakok másolásáig erőforrások között.

## Gyors válaszok
- **Mi a fő osztály az elérhetőségi időszakokhoz?** `AvailabilityPeriod` a `Aspose.Tasks` névtérben.  
- **Törölhetem a meglévő időszakokat?** Igen, hívd a `resource.AvailabilityPeriods.Clear()` metódust.  
- **Hogyan adhatok hozzá új időszakot?** Hozz létre egy `AvailabilityPeriod` objektumot, és használd az `Add` vagy `Insert` metódust.  
- **Lehet-e időszakokat másolni egy másik erőforrásra?** Természetesen – használd a `CopyTo` metódust, majd add hozzá az egyes elemeket a cél erőforráshoz.  
- **Szükség van licencre a termelési környezetben?** Igen, egy kereskedelmi Aspose.Tasks licenc szükséges a nem‑próba telepítésekhez.

## Mi az a projekt erőforrás elérhetőség?
A projekt erőforrás elérhetőség meghatározza azokat a dátumokat és egységeket (kapacitás százalékában), amikor egy erőforrás feladatokra rendelhető. Ezeknek az időszakoknak a szabályozásával elkerülhető a túlterhelés, és javítható a menetrend pontossága.

## Miért használjuk az Aspose.Tasks-et az elérhetőségi időszakok kezelésére?
- **Teljes .NET integráció** – nincs COM interop, tisztán kezelt kód.  
- **Finomhangolt vezérlés** – pontos kezdő/lezáró dátumok és tört egységek beállítása.  
- **Egyszerű másolás** – az elérhetőségi adatok áthelyezése erőforrások között manuális feldolgozás nélkül.  
- **Teljesítmény‑optimalizált** – nagy MPP fájlokkal is hatékonyan működik.

## Előfeltételek
1. **Visual Studio** – bármelyik újabb verzió (2019, 2022 vagy későbbi).  
2. **Aspose.Tasks for .NET** – letölthető innen: [here](https://releases.aspose.com/tasks/net/).  
3. **Alapvető C# ismeretek** – ismerned kell az osztályokat, gyűjteményeket és a LINQ‑t.

## Névterek importálása

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Importáljuk a fő Aspose.Tasks névteret a szabványos .NET gyűjteményekkel, amelyekre később szükség lesz.

## 1. lépés: A projekt és az erőforrás inicializálása

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Itt betöltünk egy meglévő MPP fájlt, és lekérjük azt az erőforrást, amelynek az elérhetőségét szerkeszteni szeretnénk (ID = 1).

## 2. lépés: A meglévő elérhetőségi időszakok törlése

```csharp
resource.AvailabilityPeriods.Clear();
```

A törlés eltávolítja az előzőleg definiált időszakokat, így tiszta lappal kezdhetünk.

## 3. lépés: Elérhetőségi időszakok hozzáadása

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Lekérünk egy `AvailabilityPeriod` objektumok gyűjteményét (a `GetPeriods` segédfüggvénynek máshol kell definiálva lennie), és minden egyes elemet hozzáadunk, ellenőrizve, hogy a gyűjtemény írható‑e.

## 4. lépés: Új elérhetőségi időszak beszúrása

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Ez egy egyedi időszakot hoz létre a 2013‑as évre, és a 1. pozícióba (második hely) szúrja be, ha még nem létezik.

## 5. lépés: Elérhetőségi időszakok megjelenítése

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Egy gyors konzol‑kiíratás mutatja a teljes darabszámot és minden időszak részleteit – hasznos hibakereséshez vagy ellenőrzéshez.

## 6. lépés: Elérhetőségi időszakok másolása egy másik erőforrásra

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Az egész gyűjteményt egy tömbbe másoljuk, töröljük a cél erőforrás időszakait, majd újra feltöltjük. Ez bemutatja, hogyan lehet duplikálni az elérhetőségi adatokat erőforrások között.

## 7. lépés: Elérhetőségi időszakok frissítése és eltávolítása

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Itt módosítjuk a második‑utolsó időszak `AvailableUnits` értékét, majd eltávolítjuk a korábban hozzáadott 2013‑as időszakot.

## Gyakori problémák és megoldások
- **Írásvédett gyűjtemény hiba** – Győződj meg róla, hogy a projekt nincs csak‑olvasás módban megnyitva, vagy hogy a `resource.AvailabilityPeriods.Clear()` metódust meghívtad az új elemek hozzáadása előtt.  
- **Átfedő időszakok** – Az Aspose.Tasks nem egyesíti automatikusan az átfedéseket; saját logikát kell írnod az észleléshez és feloldáshoz.  
- **Helytelen dátumformátum** – Mindig `DateTime` objektumokat használj; a karakterlánc‑feldolgozás helyi beállításokhoz kötött hibákat okozhat.

## Gyakran ismételt kérdések

**Q: Hozzáadhatok egyéni mezőket az elérhetőségi időszakokhoz?**  
A: Nem, az Aspose.Tasks for .NET elérhetőségi időszakai nem támogatják az egyéni mezőket.

**Q: Az elérhetőségi időszakok konkrét feladatokhoz vannak kapcsolva?**  
A: Nem, ezek erőforrásokhoz tartoznak, és azt határozzák meg, mikor érhető el az erőforrás általánosan a feladatokhoz.

**Q: Importálhatok elérhetőségi időszakokat külső forrásokból?**  
A: Igen, importálhatsz időszakokat CSV‑ből, XML‑ből vagy adatbázisból úgy, hogy `AvailabilityPeriod` objektumokat hozol létre, és hozzáadod a gyűjteményhez.

**Q: Hogyan kezelem az átfedő elérhetőségi időszakokat?**  
A: Az átfedéseket nem oldja fel automatikusan; saját validációt kell implementálnod a konfliktusok egyesítéséhez vagy elutasításához.

**Q: Van korlátozás az egy erőforrásra vonatkozó elérhetőségi időszakok számában?**  
A: Nincs kódolt korlát, de nagyon nagy gyűjtemények befolyásolhatják a teljesítményt; ahol lehetséges, érdemes az időszakokat konszolidálni.

## Összegzés

Ebben az útmutatóban mindent áttekintettünk, ami a **projekt erőforrás elérhetőség** kezeléséhez szükséges az Aspose.Tasks for .NET‑el – a projekt inicializálásától a régi adatok törlésén, az időszakok hozzáadásán, beszúrásán, másolásán, frissítésén és eltávolításán keresztül. Ezeknek a lépéseknek a elsajátítása segít pontos erőforrás‑naptárakat fenntartani és reális projektmenetrendet biztosítani.

---

**Utolsó frissítés:** 2026-03-21  
**Tesztelt verzió:** Aspose.Tasks for .NET (legújabb kiadás)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}