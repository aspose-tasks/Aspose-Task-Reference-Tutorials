---
title: A hozzárendelés alapvonalának kezelése az Aspose.Tasks programban
linktitle: A hozzárendelés alapvonalának kezelése az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Tanulja meg, hogyan kezelheti hatékonyan a hozzárendelési alapvonalakat az Aspose.Tasks for .NET segítségével, amely biztosítja a projekt előrehaladásának és teljesítményének pontos nyomon követését.
type: docs
weight: 14
url: /hu/net/advanced-features/assignment-baseline/
---
## Bevezetés

A projektmenedzsment feladatokon végzett munka során a hozzárendelési alapállapotok kezelése kulcsfontosságú az előrehaladás pontos nyomon követéséhez. Az Aspose.Tasks for .NET átfogó eszközkészletet biztosít a hozzárendelési alaphelyzetek hatékony kezeléséhez. Ebben az oktatóanyagban lépésről lépésre elmélyülünk a hozzárendelési alapvonalak kezelésének folyamatában.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- C# programozási nyelv alapismerete.
- A Visual Studio telepítve van a rendszerére.
- Aspose.Tasks for .NET könyvtár hozzáadva a projekthez. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
- Hozzáférés egy projektfájlhoz MPP formátumban.

## Névterek importálása

Az Aspose.Tasks használatának megkezdéséhez importálnia kell a szükséges névtereket a C# projektbe. Adja hozzá a következő névtereket a C# fájl elejéhez:

```csharp
using Aspose.Tasks;
using System;


```

## 1. lépés: Töltse be a projektet és állítsa be az alapvonalat

 Először töltse be a projektfájlt a`Project` osztály az Aspose.Tasks. Ezután állítsa be a projekt alaptípusát a segítségével`SetBaseline` módszer.

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## 2. lépés: Olvassa el a hozzárendelés alapinformációit

Iteráljon a projektben minden egyes erőforrás-hozzárendelésen keresztül, és kérjen le alapinformációkat minden egyes hozzárendeléshez.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## 3. lépés: Ellenőrizze az alapvonal egyenlőségét

Hasonlítsa össze az alapinformációkat a különböző hozzárendelésekhez az Aspose.Tasks által biztosított különféle összehasonlítási módszerekkel.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Ellenőrizze az alapvonal egyenlőségét
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Ellenőrizze az alapvonal összehasonlítását
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Az alapvonal hashkódjainak megjelenítése
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Következtetés

megbízások alaphelyzeteinek kezelése a projektmenedzsment szerves része, lehetővé téve a haladás és a teljesítmény pontos nyomon követését. Az Aspose.Tasks for .NET segítségével a hozzárendelési alapok kezelése egyszerűbbé és hatékonyabbá válik, hatékony eszközöket biztosítva a fejlesztőknek a projektmenedzsment munkafolyamatainak javításához.

## GYIK

### 1. kérdés: Az Aspose.Tasks képes-e több alapvonalat kezelni egyetlen feladathoz?

1. válasz: Igen, az Aspose.Tasks több alapvonalat támogat minden egyes feladathoz, lehetővé téve a projekt előrehaladásának átfogó nyomon követését az idő múlásával.

### 2. kérdés: Az Aspose.Tasks kompatibilis az MPP-n kívüli különböző projektfájlformátumokkal?

2. válasz: Igen, az Aspose.Tasks a projektfájlformátumok széles skáláját támogatja, beleértve az XML-t, az MPX-et és az MPP-t, biztosítva a kompatibilitást a különböző projektmenedzsment eszközökkel.

### 3. kérdés: Módosíthatom az alapadatokat programozottan az Aspose.Tasks használatával?

3. válasz: Természetesen az Aspose.Tasks kiterjedt API-kat biztosít az alapinformációk dinamikus módosításához a projekt követelményeinek megfelelően, rugalmasságot és irányítást biztosítva a projektmenedzsment folyamatok felett.

### 4. kérdés: Az Aspose.Tasks dokumentációt és támogatási forrásokat kínál a fejlesztők számára?

4. válasz: Igen, a fejlesztők hozzáférhetnek az Aspose.Tasks webhelyen található átfogó dokumentációkhoz, oktatóanyagokhoz és fórumokhoz, amelyek megkönnyítik a zökkenőmentes integrációt és a hibaelhárítást.

### 5. kérdés: Elérhető-e próbaverzió az Aspose.Tasks .NET-hez?

 5. válasz: Igen, a fejlesztők beszerezhetik az Aspose.Tasks ingyenes próbaverzióját .NET-hez innen[itt](https://releases.aspose.com/), lehetővé téve számukra, hogy a vásárlási döntés meghozatala előtt értékeljék a szolgáltatásait és képességeit.