---
title: Könnyű SVG-generálás az Aspose.Tasks-hoz
linktitle: Az Aspose.Tasks SVG-beállításai
second_title: Aspose.Tasks .NET API
description: Tanulja meg, hogyan használhatja az Aspose.Tasks for .NET-et Microsoft Project-fájlok SVG-reprezentációinak egyszerű létrehozásához a továbbfejlesztett projektvizualizáció érdekében.
type: docs
weight: 20
url: /hu/net/saving-options/svg-options/
---
## Bevezetés
A projektmenedzsment és a feladatszervezés területén az adatok hatékony megjelenítésének képessége a legfontosabb. Az Aspose.Tasks for .NET átfogó megoldást kínál a Microsoft Project fájlok SVG-reprezentációinak létrehozására, megkönnyítve a projektek egyértelmű és vonzó betekintését. Ez az oktatóanyag az Aspose.Tasks for .NET által biztosított SVG MS Project-beállítások felhasználásával foglalkozik, lehetővé téve a felhasználók számára, hogy kihasználják a projektek továbbfejlesztett vizualizációjának erejét.
## Előfeltételek
Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1.  Az Aspose.Tasks for .NET telepítése: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: Készítsen Microsoft Project fájlt (MPP) az SVG formátumba való konvertáláshoz.
3. Fejlesztői környezet: .NET képességekkel rendelkező fejlesztői környezet beállítása.

## Névterek importálása
Mielőtt belemerülne a kód megvalósításába, feltétlenül importálja a szükséges névtereket:
```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1. lépés: Határozza meg a dokumentumkönyvtárat
 Győződjön meg arról, hogy rendelkezik egy kijelölt könyvtárral a dokumentumok számára. Cserélje ki`"Your Document Directory"` a kívánt könyvtár elérési útjával.
```csharp
String DataDir = "Your Document Directory";
```
## 2. lépés: Töltse be a projektfájlt
Töltse be a Microsoft Project fájlt (.mpp) a`Project` osztály.
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 3. lépés: Adja meg az SVG mentési beállításokat
Határozza meg az SVG mentési beállításokat, beleértve a prezentációs formátumot, a tartalomillesztést és az időskálát.
```csharp
SaveOptions options = new SvgOptions
{
    PresentationFormat = PresentationFormat.GanttChart,
    FitContent = true,
    Timescale = Timescale.ThirdsOfMonths
};
```
## 4. lépés: Mentse el a projektet SVG-ként
Mentse a projektet SVG-fájlként a megadott beállításokkal.
```csharp
project.Save(DataDir + "UseSvgOptions_out.svg", options);
```

## Következtetés
Az SVG MS Project opcióinak elsajátítása az Aspose.Tasks for .NET segítségével lehetővé teszi a projektmenedzserek és fejlesztők számára, hogy könnyedén készítsenek tetszetős ábrázolásokat projektjeikről. A vázolt lépések követésével a felhasználók zökkenőmentesen integrálhatják az SVG-generálást projektmenedzsment munkafolyamataikba, javítva az áttekinthetőséget és az érthetőséget.
## GYIK
### K: Az Aspose.Tasks képes kezelni a nagy Microsoft Project fájlokat?
V: Igen, az Aspose.Tasks célja a nagy Microsoft Project fájlok hatékony kezelése, optimális teljesítmény biztosítása.

### K: Az Aspose.Tasks kompatibilis a .NET különböző verzióival?
V: Az Aspose.Tasks természetesen támogatja a .NET különféle verzióit, rugalmasságot és kompatibilitást biztosítva a különböző környezetekben.

### K: Vannak korlátai az SVG kimeneti opcióknak?
V: Míg az Aspose.Tasks robusztus SVG-kimeneti lehetőségeket kínál, bizonyos funkciók, például a színátmenetes ecsetek korlátai lehetnek. Részletes információkért tekintse meg a dokumentációt.

### K: Testreszabhatom a generált SVG megjelenését?
V: Igen, az Aspose.Tasks kiterjedt testreszabási lehetőségeket kínál az SVG-kimenet megjelenésének testreszabásához az Ön preferenciáinak és követelményeinek megfelelően.

### K: Elérhető technikai támogatás az Aspose.Tasks felhasználók számára?
V: Igen, a felhasználók hozzáférhetnek a technikai támogatáshoz az Aspose.Tasks fórumon keresztül, vagy közvetlenül a támogatási csapattal fordulhatnak segítségért bármilyen kérdéssel vagy problémával kapcsolatban.