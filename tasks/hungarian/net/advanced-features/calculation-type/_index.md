---
title: Számítás típusa az Aspose.Tasks
linktitle: Számítás típusa az Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan testreszabhatja az értékszámításokat .NET-projektekben az Aspose.Tasks könyvtár Calculation Type segítségével.
weight: 30
url: /hu/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Számítás típusa az Aspose.Tasks

## Bevezetés

Ebben az oktatóanyagban megvizsgáljuk az Aspose.Tasks for .NET számítási típusát. Az Aspose.Tasks egy hatékony könyvtár, amely lehetővé teszi a .NET fejlesztők számára, hogy Microsoft Project fájlokkal dolgozzanak anélkül, hogy a rendszerükre Microsoft Projectet kellene telepíteni. A számítási típus lehetővé teszi számunkra, hogy meghatározzuk, hogyan számítsuk ki az értékeket a projekten belüli feladatokhoz és összefoglaló feladatokhoz.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. C# és .NET keretrendszer alapismeretei.
2. A Visual Studio telepítve van a rendszerére.
3.  Aspose.Tasks for .NET könyvtár telepítve. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
4.  Hozzáférés az Aspose.Tasks .NET dokumentációhoz referenciaként, elérhető[itt](https://reference.aspose.com/tasks/net/).

## Névterek importálása

Mielőtt belevágna a példába, feltétlenül importálja a szükséges névtereket:

```csharp
using Aspose.Tasks;
using System;


```

## 1. lépés: Hozzon létre egy új projektet

Először is hozzunk létre egy új projektobjektumot:

```csharp
var project = new Project();
```

## 2. lépés: Adjon hozzá egy feladatot

Most adjunk hozzá egy feladatot a projektünkhöz:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 3. lépés: Határozza meg a számítási típust egy kiterjesztett attribútumhoz

Létrehozunk egy kiterjesztett attribútumdefiníciót úgy, hogy a Számítás típusa képletre van állítva:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 4. lépés: Határozza meg a számítási típust az összegző sorokhoz

Ezután egy másik kiterjesztett attribútumdefiníciót hozunk létre, ahol az összegző feladatok értékeit az Átlagos összesítés típusával számítjuk ki:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan dolgozhatunk a számítási típussal az Aspose.Tasks for .NET-ben. A kiterjesztett attribútumokhoz tartozó számítási típusok meghatározásával testreszabhatjuk, hogy a projekten belül hogyan számítsa ki az értékeket a feladatokhoz és az összefoglaló feladatokhoz, így nagyobb rugalmasságot és irányítást biztosít.

## GYIK

### 1. kérdés: Mi az Aspose.Tasks számítási típusa?

1. válasz: Az Aspose.Tasks számítási típusa meghatározza, hogy a projekten belül hogyan számítsa ki a rendszer a feladatok és összefoglaló feladatok értékeit, és olyan lehetőségeket kínál, mint a Képlet és az Összegzés.

### 2. kérdés: Hogyan állíthatom be a számítási típust egy kiterjesztett attribútumhoz?

2. válasz: Beállíthatja a számítási típust egy kiterjesztett attribútumhoz, ha ennek megfelelően határozza meg a CalculationType tulajdonságát.

### 3. kérdés: Testreszabhatom a számítási típust a projekt összesítő soraihoz?

3. válasz: Igen, az Aspose.Tasks lehetővé teszi a számítási típus megadását az összegző sorokhoz, lehetővé téve az értékszámítások testreszabását az Ön igényei alapján.

### 4. kérdés: Rendelkezésre állnak különböző összesítő típusok az összefoglaló feladatszámításokhoz?

4. válasz: Igen, az Aspose.Tasks különböző összesítő típusokat biztosít, például Átlag, Összeg és Számlálás az összefoglaló feladatok értékeinek kiszámításához.

### 5. kérdés: Hol találok további forrásokat az Aspose.Tasks for .NET webhelyen?

 5. válasz: Megtekintheti a dokumentációt és a közösségi támogatási fórumokat, amelyek elérhetők a webhelyen[Aspose.Tasks .NET-hez](https://reference.aspose.com/tasks/net/) átfogó útmutatásért és segítségért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
