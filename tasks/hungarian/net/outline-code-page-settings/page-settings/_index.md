---
title: Konfigurálja az MS Project oldalbeállításait az Aspose.Tasks segítségével
linktitle: Oldalbeállítások konfigurálása az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan konfigurálhatja az MS Project oldalbeállításait az Aspose.Tasks for .NET használatával. Egyszerű lépésekkel testreszabhatja a tájolást, a méretet és egyebeket.
weight: 20
url: /hu/net/outline-code-page-settings/page-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurálja az MS Project oldalbeállításait az Aspose.Tasks segítségével

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a Microsoft Project oldalbeállításainak konfigurálását az Aspose.Tasks for .NET használatával. Az Aspose.Tasks egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Aspose.Tasks for .NET: Győződjön meg arról, hogy telepítette az Aspose.Tasks for .NET-et. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
2. Fejlesztői környezet: A .NET fejlesztéshez be kell állítani egy fejlesztői környezetet a Visual Studio vagy bármely más preferált IDE segítségével.

## Névterek importálása
A kezdéshez importálnia kell a szükséges névtereket a projektbe. Ezek a névterek hozzáférést biztosítanak az MS Project fájlok kezeléséhez szükséges Aspose.Tasks osztályokhoz és metódusokhoz.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1. lépés: Töltse be a projektfájlt
Először is be kell töltenie azt az MS Project fájlt, amelyhez konfigurálni szeretné az oldalbeállításokat.
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## 2. lépés: Nyissa meg az oldalbeállításokat
Ezután elérheti a projektfájl oldalbeállításait.
```csharp
// Szerezd meg a beállításokat
var settings = project.DefaultView.PageInfo.PageSettings;
```
## 3. lépés: Konfigurálja az oldalbeállításokat
Most állítsuk be az oldalbeállítások különféle tulajdonságait az Ön igényei szerint.
```csharp
// Állítsa az oldal tájolását állóra
settings.IsPortrait = true;
// Állítsa be a nyomtatandó oldalak számát szélességben
settings.PagesInWidth = 5;
// Állítsa be a nyomtatandó oldalak számát magasságban
settings.PagesInHeight = 7;
// Állítsa be a normál méret százalékos arányát a nyomtatáshoz
settings.PercentOfNormalSize = 200;
// Állítsa be a papírméretet
settings.PaperSize = PrinterPaperSize.PaperB4;
// Állítsa be az első oldalszámot a nyomtatáshoz
settings.FirstPageNumber = 3;
```
## 4. lépés: Mentse el a projektfájlt
Végül mentse el a projektfájlt a frissített oldalbeállításokkal.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan konfigurálhatja a Microsoft Project oldalbeállításait az Aspose.Tasks for .NET használatával. Az alábbi lépések követésével könnyedén testreszabhatja az oldal tájolását, méretét és egyéb nyomtatási beállításokat igényei szerint.

## GYIK
### K: Konfigurálhatom az oldalbeállításokat több MS Project fájlhoz egyszerre?
V: Igen, végignézhet több projektfájlon, és mindegyikre ugyanazokat az oldalbeállításokat alkalmazhatja.
### K: Vissza lehet állítani az oldalbeállításokat az alapértelmezettre?
V: Természetesen egyszerűen kihagyhatja a konfigurációs lépéseket, vagy visszaállíthatja a beállításokat az alapértelmezett értékekre.
### K: Vannak-e korlátozások a támogatott papírméretekre vonatkozóan?
V: Az Aspose.Tasks a papírméretek széles skáláját támogatja, beleértve a szabványos és egyéni méreteket is.
### K: Automatizálhatom az oldalbeállítások konfigurációs folyamatát?
V: Természetesen ezt a funkciót integrálhatja alkalmazása munkafolyamatába az oldalbeállítások konfigurálásának automatizálása érdekében.
### K: Az Aspose.Tasks támogatja az .mpp-n kívül más fájlformátumokat is?
V: Igen, az Aspose.Tasks különféle fájlformátumokat támogat, többek között az XML-t, az MPT-t és a HTML-t.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
