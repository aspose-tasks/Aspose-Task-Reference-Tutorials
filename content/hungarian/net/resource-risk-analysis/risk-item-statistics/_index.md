---
title: Statisztikák az Aspose.Tasks kockázati elemeire vonatkozóan
linktitle: Statisztikák az Aspose.Tasks kockázati elemeire vonatkozóan
second_title: Aspose.Tasks .NET API
description: Az Aspose.Tasks for .NET segítségével felszabadíthatja a kockázatelemzés erejét az MS Project fájlokban. Szerezzen betekintést, mérsékelje a bizonytalanságot, és könnyítse meg a projekt sikerét.
type: docs
weight: 21
url: /hu/net/resource-risk-analysis/risk-item-statistics/
---
## Bevezetés
Szeretné javítani projektmenedzsment képességeit az Aspose.Tasks for .NET használatával? Merüljön el a kockázatelemzés birodalmában az MS Project fájlokban található kockázati tételekre vonatkozó statisztikák beszerzéséről szóló, lépésről lépésre bemutatott útmutatónkkal. Az Aspose.Tasks hatékony képességeinek kihasználásával felbecsülhetetlen értékű betekintést nyerhet a projektek bizonytalanságaiba, és megalapozott döntéseket hozhat a kockázatok hatékony csökkentése érdekében.
## Előfeltételek
Mielőtt nekivágnánk ennek az útnak, győződjön meg arról, hogy a következő előfeltételeket teljesíti:
1.  Aspose.Tasks for .NET Library: Töltse le és telepítse a könyvtárat a[Aspose.Tasks .NET dokumentációhoz](https://reference.aspose.com/tasks/net/), Ez a könyvtár robusztus eszközökkel ruházza fel az MS Project fájlok programozott kezeléséhez.
2. .NET fejlesztői környezet: Állítsa be .NET fejlesztői környezetét, beleértve a Visual Studio-t vagy bármely más választott IDE-t, hogy megkönnyítse az Aspose.Tasks projektekbe való zökkenőmentes integrációját.

## Névterek importálása
Az Aspose.Tasks funkcióinak kihasználásához építse be a szükséges névtereket a projektbe:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## 1. lépés: Adja meg az adatkönyvtárat
```csharp
String DataDir = "Your Document Directory";
```
 Biztosítsa a cserét`"Your Document Directory"` dokumentumkönyvtár elérési útjával, ahol az MS Project fájljai találhatók.
## 2. lépés: Konfigurálja a kockázatelemzési beállításokat
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Állítsa be a`IterationsCount` a projekt követelményei alapján a kockázatelemzés pontosságának ellenőrzése érdekében.
## 3. lépés: Töltse be az MS Project fájlt
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Töltse be a kívánt MS Project fájlt a`project` tárgy további elemzésre.
## 4. lépés: A feladat meghatározása és a kockázati minta inicializálása
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Adja meg a kockázatelemzés feladatát, és konfigurálja a kockázati mintát olyan megfelelő paraméterekkel, mint az eloszlás típusa, az optimista és pesszimista időtartamok és a megbízhatósági szint.
## 5. lépés: A projekt kockázatainak elemzése
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Indítsa el a kockázatelemzési folyamatot a meghatározott beállítások és projektadatok felhasználásával.
## 6. lépés: Statisztikák lekérése és megjelenítése
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Az MS Project fájl kockázati elemeivel kapcsolatos különféle statisztikai mérőszámok lekérése és megjelenítése, beleértve a várható értéket, a szórást, a százalékos értékeket, a minimum- és maximumértékeket.

## Következtetés
Összefoglalva, a kockázatelemzés elsajátítása az MS Project fájlokban az Aspose.Tasks for .NET használatával lehetőségek tárházát nyitja meg a projektmenedzserek és az érdekelt felek számára. Átfogó oktatóanyagunk követésével magabiztosan navigálhat a bizonytalanságok között, így biztosítva a sikeres projekteredményeket.
## GYIK
### Integrálhatom az Aspose.Tasks-t más .NET-könyvtárakba a kiterjesztett funkcionalitás érdekében?
Teljesen! Az Aspose.Tasks zökkenőmentesen integrálódik a különböző .NET-könyvtárakba, lehetővé téve a képességek bővítését a projekt követelményei szerint.
### Elérhető az Aspose.Tasks .NET-hez próbaverziója?
 Igen, felfedezheti az Aspose.Tasks szolgáltatásait, ha eléri a[ingyenes próbaverzió](https://releases.aspose.com/) elérhető honlapunkon.
### Milyen gyakran jelennek meg az Aspose.Tasks frissítései és fejlesztései?
Arra törekszünk, hogy az Aspose.Tasks rendszeres időközönként frissítések és fejlesztések kiadásával folyamatosan fejlesztjük az Aspose.Tasks-t, biztosítva, hogy mindig hozzáférhessen a legújabb funkciókhoz és optimalizálásokhoz.
### Kaphatok technikai támogatást az Aspose.Tasks-hoz?
Biztosan! Elkötelezett ügyfélszolgálati csapatunk készséggel áll a rendelkezésére[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) hogy segítsünk a megvalósítás során felmerülő kérdésekben vagy kihívásokban.
### Kínál-e ideiglenes licenceket rövid távú projektekhez?
 Igen, ha szüksége van az Aspose.Tasks-re egy rövid távú projekthez, akkor igénybe veheti kényelmes szolgáltatásunkat[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) lehetőséget, hogy hosszú távú kötelezettségvállalások nélkül teljesítse licencelési igényeit.