---
title: Az Aspose.Tasks bitmap érvénytelen méret kivételének kezelése
linktitle: Az Aspose.Tasks bitmap érvénytelen méret kivételének kezelése
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a BitmapInvalidSizeException kivételt az Aspose.Tasks for .NET-ben projektek képként történő mentésekor. Átfogó oktatóanyag lépésről lépésre.
weight: 22
url: /hu/net/advanced-features/bitmap-invalid-size-exception/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az Aspose.Tasks bitmap érvénytelen méret kivételének kezelése

## Bevezetés

 Ebben az oktatóanyagban a kezelésével foglalkozunk`BitmapInvalidSizeException` amikor az Aspose.Tasks for .NET programmal dolgozik. Az Aspose.Tasks egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat, lehetővé téve például a projektek képként történő mentését. Időnként azonban, amikor egy projektet képként próbálunk menteni, előfordulhat, hogy egy`Invalid Size Exception` bittérképhez kapcsolódik. Ennek az oktatóanyagnak az a célja, hogy végigvezeti Önt a kivétel hatékony észlelésének és kezelésének folyamatán.

## Előfeltételek

Mielőtt folytatná ezt az oktatóanyagot, győződjön meg arról, hogy a következő előfeltételekkel rendelkezik:
1. A C# programozási nyelv alapvető ismerete.
2. Aspose.Tasks telepítve a .NET-hez.
3. Ismeri a Microsoft Project fájlokkal való munkát.

## Névterek importálása

Mielőtt elkezdené, feltétlenül importálja a szükséges névtereket:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 1. lépés: A projekt inicializálása és a nézet meghatározása

 Először inicializálja a`Project` objektumot, és definiáljon egy nézetet, például a`GanttChartView`.

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## 2. lépés: Adja meg a képmentési beállításokat

Ezután adja meg a kép mentési beállításait, beleértve a formátumot és az időskálát.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## 3. lépés: Állítsa be az időskálát és a számot

Állítsa be az időskálát, és számoljon az igényei szerint. Ebben a példában az időskálát percekre állítottuk.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## 4. lépés: Projekt mentése képként

Próbálja meg a projektet képként menteni a megadott beállításokkal.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## 5. lépés: Fogás és kezelés kivétel

 A kivételkezelés végrehajtása a`BitmapInvalidSizeException` ha a képmentési folyamat során történik.

```csharp
try
{
    // Próbálja meg menteni a projektet képként
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Kezelje a kivételt
    Console.WriteLine(ex.Message);
}
```

## Következtetés

 Összegezve, kezelése a`BitmapInvalidSizeException` Amikor a projekteket képként menti az Aspose.Tasks for .NET-ben, elengedhetetlen az alkalmazások zökkenőmentes végrehajtásához. Az ebben az oktatóanyagban ismertetett lépések követésével hatékonyan elkaphatja és kezelheti ezt a kivételt, így növelve projektmenedzsment-megoldásai robusztusságát.

## GYIK

### 1. kérdés: Mi okozza a BitmapInvalidSizeException kivételt az Aspose.Tasks programban?

1. válasz: Ez a kivétel akkor fordul elő, ha egy projektet érvénytelen bitképméret-paraméterekkel próbál meg képként menteni.

### 2. kérdés: Testreszabhatom az időskálát egy projekt képként történő mentésekor?

2. válasz: Igen, az oktatóanyagban bemutatott módon beállíthatja az időskálát és a számlálást igényei szerint.

### 3. kérdés: Hol találok további forrásokat az Aspose.Tasks for .NET használatához?

3. válasz: Megtekintheti az Aspose.Tasks által biztosított dokumentációt és támogatási fórumokat átfogó útmutatásért és segítségért.

### 4. kérdés: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?

4. válasz: Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok különféle verzióit, lehetővé téve a zökkenőmentes együttműködést.

### 5. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks számára?

5. válasz: A cikkben található hivatkozáson keresztül ideiglenes licencet szerezhet értékelési célokra.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
