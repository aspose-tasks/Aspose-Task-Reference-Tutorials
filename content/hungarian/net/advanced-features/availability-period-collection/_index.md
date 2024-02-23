---
title: Az Aspose.Tasks elérhetőségi időszakainak gyűjteménye
linktitle: Az Aspose.Tasks elérhetőségi időszakainak gyűjteménye
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti az erőforrások rendelkezésre állási időszakait az Aspose.Tasks for .NET-ben. Ez a lépésenkénti oktatóanyag végigvezeti Önt a rendelkezésre állási időszakok hozzáadásával, frissítésével és eltávolításával, így biztosítva a hatékony projekterőforrás-tervezést.
type: docs
weight: 18
url: /hu/net/advanced-features/availability-period-collection/
---
## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk, hogyan dolgozhatunk az Aspose.Tasks for .NET erőforrás rendelkezésre állási időszakának gyűjteményével. A rendelkezésre állási időszakok kezelése kulcsfontosságú a projektmenedzsment számára, lehetővé téve számunkra, hogy meghatározzuk, mikor állnak rendelkezésre erőforrások a projekten belüli feladatokhoz.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
3. Alapvető ismeretek: C# és .NET keretrendszer ismerete.

## Névterek importálása

Először is importálnunk kell a szükséges névtereket a projektünkbe:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Bontsuk fel a példakódot több lépésre, és értsük meg az egyes részeket:

## 1. lépés: Inicializálja a projektet és az erőforrást

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Itt egy projektfájlt töltünk be, és egy adott erőforrást kapunk az azonosítója alapján.

## 2. lépés: Törölje a meglévő rendelkezésre állási időszakokat

```csharp
resource.AvailabilityPeriods.Clear();
```

Töröljük az erőforráshoz kapcsolódó meglévő rendelkezésre állási időszakokat.

## 3. lépés: Adjon hozzá rendelkezésre állási időszakokat

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

Megismételjük a rendelkezésre állási időszakok gyűjteményét, és hozzáadjuk őket az erőforráshoz.

## 4. lépés: Adjon meg egy új rendelkezésre állási időszakot

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

A 2013-as évre létrehozunk egy új rendelkezésre állási időszakot, és beillesztjük a gyűjteménybe.

## 5. lépés: Az elérhetőségi időszakok megjelenítése

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

Kinyomtatjuk az erőforráshoz kapcsolódó minden rendelkezésre állási időszak számát és részleteit.

## 6. lépés: Másolja a rendelkezésre állási időszakokat egy másik erőforrásba

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

A rendelkezésre állási időszakokat egyik forrásból a másikba másoljuk.

## 7. lépés: Frissítse és távolítsa el az elérhetőségi időszakokat

```csharp
// Frissítse a rendelkezésre álló egységeket egy adott időszakra
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Távolítson el egy adott időszakot
otherResource.AvailabilityPeriods.Remove(period2013);
```

Frissítjük a rendelkezésre álló egységeket egy adott időszakra vonatkozóan, és bizonyos időszakokat eltávolítunk a gyűjteményből.

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan kell dolgozni a rendelkezésre állási időszak gyűjteményeivel az Aspose.Tasks for .NET-ben. Az erőforrások rendelkezésre állásának kezelése elengedhetetlen a hatékony projekttervezéshez és -végrehajtáshoz.

## GYIK

### 1. kérdés: Hozzáadhatok egyéni mezőket a rendelkezésre állási időszakokhoz?

1. válasz: Nem, az Aspose.Tasks for .NET rendelkezésre állási időszakai nem támogatják az egyéni mezőket.

### 2. kérdés: A rendelkezésre állási időszakok meghatározott feladatokhoz kapcsolódnak?

2. válasz: Nem, a rendelkezésre állási időszakok erőforrásokhoz vannak társítva, és meghatározzák, hogy általában mikor állnak rendelkezésre a feladatokhoz.

### 3. kérdés: Importálhatok-e elérhetőségi időszakokat külső forrásokból?

3. válasz: Igen, importálhat rendelkezésre állási időszakokat különböző adatforrásokból az Aspose.Tasks for .NET API-k használatával.

### 4. kérdés: Hogyan kezelhetem az átfedő rendelkezésre állási időszakokat?

4. válasz: Az Aspose.Tasks for .NET nem biztosít beépített mechanizmusokat az átfedő időszakok kezelésére. Előfordulhat, hogy egyéni logikát kell alkalmaznia az ilyen forgatókönyvek kezeléséhez.

### 5. kérdés: Van-e korlátozás az erőforrás rendelkezésre állási időszakainak számára?

5. válasz: Nincs előre meghatározott korlát az erőforrás rendelkezésre állási időszakainak számára, de a teljesítmény csökkenhet nagy számú periódussal.