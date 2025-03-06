---
title: Master MS Project Rates az Aspose.Tasks segítségével
linktitle: Árak gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a díjakat MS Project fájlokban az Aspose.Tasks for .NET segítségével. Lépésről lépésre bemutató útmutató a hatékony erőforrás-kezeléshez.
weight: 11
url: /hu/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master MS Project Rates az Aspose.Tasks segítségével

## Bevezetés
Üdvözöljük oktatóanyagunkban az MS Project díjainak kezeléséről az Aspose.Tasks for .NET használatával! Ebben az útmutatóban végigvezetjük az Aspose.Tasks használatával az MS Project fájljaiban lévő díjszabásokkal való munkafolyamaton. Akár tapasztalt fejlesztő, akár csak most kezdi a .NET-fejlesztést, ez az oktatóanyag lépésről lépésre útmutatást ad a projektek díjainak hatékony kezeléséhez.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. A Visual Studio telepítve
Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren. Letöltheti a webhelyről, ha még nem tette meg.
### 2. Aspose.Tasks for .NET
 Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a[weboldal](https://releases.aspose.com/tasks/net/).
### 3. C# és .NET alapismeretek
Ismerkedjen meg a C# programozási nyelvvel és a .NET keretrendszer alapjaival, hogy jobban megértse az oktatóanyagban található kódpéldákat.
## Névterek importálása
C# projektben importálja a szükséges névtereket az Aspose.Tasks funkciók használatához:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Most bontsuk le az egyes példákat több lépésre:
## 1. lépés: Töltsön be egy MS Project fájlt
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Itt létrehozunk egy újat`Project` objektumot egy meglévő MS Project fájl betöltésével.
## 2. lépés: Adjon hozzá egy erőforrást, és állítsa be a munkát és az árakat
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Új erőforrást adunk a projekthez, beállítjuk a típusát munkaként, munkamennyiségként és normál díjként.
## 3. lépés: Adjon hozzá árakat az erőforráshoz
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Árakat adunk az erőforráshoz, megadva a kezdő és befejező dátumot, a normál tarifát és a díjformátumot.
## 4. lépés: Nyomtatási díjinformációk
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Ez a lépés információkat nyomtat az erőforráshoz társított díjakról.
## 5. lépés: Frissítse az árfolyamot
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Frissítjük egy adott árfolyam végi dátumát.
## 6. lépés: Távolítsa el az árakat
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Ez a lépés eltávolítja egy adott típusú összes tarifát.
## 7. lépés: Ismételje meg a fennmaradó árakat
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Végül megismételjük az eltávolítás után fennmaradó arányokat.
## Következtetés
Összefoglalva, ez az oktatóanyag átfogó útmutatót tartalmaz az MS Project fájlokban lévő díjak kezeléséhez az Aspose.Tasks for .NET használatával. Az ebben az oktatóanyagban felvázolt lépésenkénti utasítások követésével hatékonyan kezelheti a projekteken belüli díjakat, így biztosítva a pontos erőforrás-kezelést.
## GYIK
### K: Használhatom az Aspose.Tasks for .NET-et más projektmenedzsment szoftverekkel?
V: Igen, az Aspose.Tasks for .NET támogatja az integrációt különféle projektmenedzsment szoftverekkel, beleértve az MS Projectet, a Primaverát és még sok mást.
### K: Az Aspose.Tasks for .NET kompatibilis az MS Project fájlok különböző verzióival?
V: Az Aspose.Tasks for .NET támogatja a különböző verziójú MS Project fájlokkal való munkát, biztosítva a rugalmasságot és a kompatibilitást.
### K: Az Aspose.Tasks for .NET kínál dokumentációt és támogatást?
 V: Igen, az Aspose.Tasks oldalon átfogó dokumentációt és támogatási fórumokat találhat[weboldal](https://reference.aspose.com/tasks/net/).
### K: Kipróbálhatom az Aspose.Tasks-t .NET-hez a vásárlás előtt?
V: Igen, igénybe veheti az Aspose.Tasks for .NET ingyenes próbaverzióját, hogy értékelje szolgáltatásait és kompatibilitását az Ön követelményeivel.
### K: Hogyan vásárolhatok licencet az Aspose.Tasks for .NET számára?
 V: Az Aspose.Tasks for .NET-hez licencet vásárolhat a webhelyen[weboldal](https://purchase.aspose.com/temporary-license/)amely rugalmas licencelési lehetőségeket biztosít az Ön igényeinek megfelelően.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
