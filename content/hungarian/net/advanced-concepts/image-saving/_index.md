---
title: A képmentés kezelése az Aspose.Tasks programban
linktitle: A képmentés kezelése az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a képmentést az Aspose.Tasks for .NET-ben a lépésenkénti útmutatók segítségével. Zökkenőmentesen integrálja a képmentési funkciókat .NET-alkalmazásaiba.
type: docs
weight: 10
url: /hu/net/advanced-concepts/image-saving/
---
## Bevezetés

Ebben az oktatóanyagban az Aspose.Tasks for .NET rendszerben történő képmentés kezelési folyamatát mutatjuk be. Az Aspose.Tasks egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat. A projektfájlokkal végzett munka során az egyik gyakori feladat a képek mentése, amelyek diagramokat, grafikonokat vagy más vizuális elemeket tartalmazhatnak. A folyamatot lépésről lépésre lebontjuk, biztosítva az egyértelműséget és a megértést.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET webhelyet innen[itt](https://releases.aspose.com/tasks/net/).
3. A C# alapjai: Ismerkedjen meg a C# programozási nyelv alapjaival.

## Névterek importálása

Először is importáljuk a szükséges névtereket a projektünkbe:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1. lépés: Hozzon létre egy projektobjektumot

Először hozzon létre egy Project objektumot a Microsoft Project fájlból:

```csharp
var project = new Project("Project1.mpp");
```

## 2. lépés: Adja meg a mentési beállításokat

Határozza meg a projekt mentési beállításait az oldalak és egyéb beállítások megadásával:

```csharp
var options = GetSaveOptions(1);
```

## 3. lépés: Mentse el a projektet HTML-ként

Mentse a projektet HTML-ként a megadott beállításokkal:

```csharp
project.Save("document_out.html", options);
```

## 4. lépés: Végezze el a képmentő visszahívást

Valósítsa meg az ImageSavingCallback felületet a képmentés kezeléséhez:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // A képmentési logika ide tartozik
    }
}
```

## 5. lépés: Mentse el a képeket a megadott könyvtárba

Az ImageSaving metóduson belül adja meg a logikát, hogy a képeket a kívánt könyvtárba mentse:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Mentse a beágyazott erőforrásokat
}
else
{
    // Takarítson meg rendszeres erőforrásokat
}
```

## 6. lépés: Adja meg a mentési beállításokat

Adja meg a mentési beállításokat, beleértve a CSS, betűtípusok és képek visszahívásait:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Itt adja meg a mentési beállításokat
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Következtetés

Összefoglalva, az Aspose.Tasks for .NET rendszerben a képmentés kezelése magában foglalja a mentési beállítások meghatározását és a visszahívások végrehajtását a mentési folyamat hatékony kezelése érdekében. Az oktatóanyagban ismertetett lépések követésével zökkenőmentesen integrálhatja a képmentési funkciókat .NET-alkalmazásaiba.

## GYIK

### 1. kérdés: Az Aspose.Tasks segítségével kezelhetem a HTML-en kívül más formátumú projektfájlokat?

1. válasz: Igen, az Aspose.Tasks különféle formátumokat támogat, például PDF, XLSX és MPP.

### 2. kérdés: Az Aspose.Tasks támogatja a felhőalapú tárolás integrációját?

2. válasz: Igen, az Aspose.Tasks API-kat kínál a népszerű felhőalapú tárolási szolgáltatásokhoz, például az Amazon S3-hoz és a Google Drive-hoz.

### 3. kérdés: Az Aspose.Tasks kompatibilis a .NET Core programmal?

3. válasz: Igen, az Aspose.Tasks kompatibilis a .NET Core-al, lehetővé téve többplatformos alkalmazások fejlesztését.

### 4. kérdés: Testreszabhatom a mentett képek megjelenését?

4. válasz: Igen, testreszabhatja a mentett képek megjelenését a visszahívási módokon belüli képmentési logika módosításával.

### 5. kérdés: Az Aspose.Tasks kínál próbaverziókat értékelési célokra?

 5. válasz: Igen, beszerezheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).