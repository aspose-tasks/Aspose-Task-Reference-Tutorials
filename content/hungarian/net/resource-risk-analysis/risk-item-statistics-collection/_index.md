---
title: Gyűjtse össze az MS Project kockázati elem statisztikáit az Aspose.Tasks-ban
linktitle: Kockázati tétel statisztikák gyűjtése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan gyűjthet kockázati tételekre vonatkozó statisztikákat MS Project fájlokból az Aspose.Tasks for .NET segítségével. Növelje projektmenedzsment képességeit.
type: docs
weight: 22
url: /hu/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan gyűjthetünk kockázati tételekre vonatkozó statisztikákat MS Project fájlokból az Aspose.Tasks for .NET segítségével. Ez a könyvtár hatékony funkciókat kínál a projektadatok elemzéséhez, beleértve a kockázatértékelést és a statisztikai elemzést.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks könyvtárat. Beszerezheti a[letöltési oldal](https://releases.aspose.com/tasks/net/).
2. Fejlesztői környezet: legyen beállítva egy fejlesztői környezet a .NET programozáshoz.

## Névterek importálása
A kódolás megkezdése előtt feltétlenül importálja a szükséges névtereket a projektbe:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## 1. lépés: Töltse be a projektfájlt
Először is be kell töltenie az MS Project fájlt az alkalmazásba. Így érheti el:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## 2. lépés: Adja meg a kockázatelemzési beállításokat
Inicializálja a kockázatelemzés beállításait, beleértve az iterációk számát is, az alábbiak szerint:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## 3. lépés: Inicializálja a kockázati mintát
Állítson be egy kockázati mintát az elemzéshez, adja meg az eloszlás típusát, az optimista és pesszimista százalékokat, valamint a megbízhatósági szintet:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## 4. lépés: Végezze el a kockázatelemzést
 Példányosítsa a`RiskAnalyzer` osztály, és elemezze a projektet:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## 5. lépés: Statisztikák lekérése
A kockázati tétel statisztikáinak lekérése, például a korai befejezés, az elemzés eredményéből:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## 6. lépés: Statisztikák nyomtatása
Ismételje meg a statisztikákat, és nyomtassa ki a részleteket:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Egyéb vonatkozó statisztikák nyomtatása...
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan használható az Aspose.Tasks for .NET a kockázati tételekre vonatkozó statisztikák gyűjtésére MS Project fájlokból. Ezen lépések követésével hatékonyan elemezheti a projektadatokat és felmérheti a lehetséges kockázatokat, segítve a jobb döntéshozatalt és a projektmenedzsmentet.

## GYIK
### K: Az Aspose.Tasks képes kezelni a nagy MS Project fájlokat?
V: Igen, az Aspose.Tasks képes hatékonyan kezelni a nagy MS Project fájlokat, megbízható teljesítményt és méretezhetőséget kínálva.
### K: Az Aspose.Tasks támogat más projektfájlformátumokat is az .mpp-n kívül?
V: Igen, az Aspose.Tasks különféle projektfájlformátumokat támogat, beleértve az XML-t és az MPT-t.
### K: Az Aspose.Tasks alkalmas vállalati szintű projektmenedzsment alkalmazásokhoz?
V: Természetesen az Aspose.Tasks úgy lett kialakítva, hogy megfeleljen a vállalati szintű projektmenedzsment alkalmazások igényeinek, robusztus szolgáltatásokat és kiterjedt dokumentációt biztosítva.
### K: Testreszabhatom az Aspose.Tasks kockázatelemzési beállításait?
V: Igen, az Aspose.Tasks rugalmasságot kínál a kockázatelemzési beállítások konfigurálásában, hogy megfeleljenek az Ön konkrét projektkövetelményeinek és forgatókönyveinek.
### K: Elérhető technikai támogatás az Aspose.Tasks felhasználók számára?
 V: Igen, az Aspose.Tasks felhasználók hozzáférhetnek a technikai támogatáshoz az Aspose-on keresztül.[fórumok](https://forum.aspose.com/c/tasks/15), ahol kérdéseket tehetnek fel, problémákat jelenthetnek be, és kapcsolatba léphetnek a közösséggel.