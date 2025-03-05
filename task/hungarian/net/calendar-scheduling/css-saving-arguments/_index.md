---
title: CSS Argumentumok mentése az Aspose.Tasks-ban
linktitle: CSS Argumentumok mentése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan mentheti a CSS-argumentumokat az Aspose.Tasks for .NET-ben a HTML-kimenet testreszabásához. Fokozza a prezentációt személyre szabott CSS-beállításokkal.
type: docs
weight: 20
url: /hu/net/calendar-scheduling/css-saving-arguments/
---
## Bevezetés

Ebben az oktatóanyagban a CSS-argumentumok Aspose.Tasks for .NET használatával mentésének folyamatát mutatjuk be. A Cascading Style Sheets (CSS) kulcsfontosságú a HTML-elemek megjelenítésének meghatározásához. Az Aspose.Tasks lehetővé teszi ezen CSS-attribútumok hatékony kezelését és mentését.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1.  Telepítés: Győződjön meg arról, hogy telepítette az Aspose.Tasks for .NET programot. Letöltheti a[weboldal](https://releases.aspose.com/tasks/net/).

2. Alapvető ismeretek: C# és .NET fejlesztői környezet ismerete ajánlott.

## Névterek importálása

A kezdéshez importálja a szükséges névtereket:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## 1. lépés: Határozza meg a CSS mentési visszahívásokat

Először is meghatározzuk a CSS mentési visszahívási módszereket a CSS fájlok mentésének kezelésére:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Itt valósítsa meg a CSS mentési logikáját
    }
}
```

## 2. lépés: Hajtsa végre a betűtípus- és képmentési visszahívásokat

Ezután hasonló módon hajtsa végre a betűtípus- és képmentési visszahívási módszereket:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Itt valósítsa meg a betűtípus-mentési logikáját
}

public void ImageSaving(ImageSavingArgs args)
{
    // Itt valósítsa meg képmentési logikáját
}
```

## 3. lépés: Konfigurálja a mentési beállításokat

Most állítsa be a HTML mentési beállításokat a megvalósított visszahívások használatához:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Konfigurálja a HTML mentési beállításokat
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 4. lépés: Projekt mentése testreszabott CSS-szel

Végül mentse el projektjét a testreszabott CSS-beállításokkal:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan menthetők el a CSS-argumentumok az Aspose.Tasks for .NET használatával. A CSS mentési visszahívások meghatározásával és a HTML mentési opciók konfigurálásával hatékonyan tudjuk kezelni a CSS attribútumokat igényeinknek megfelelően.

## GYIK

### 1. kérdés: Mi az Aspose.Tasks for .NET?

1. válasz: Az Aspose.Tasks for .NET egy hatékony .NET API, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal.

### 2. kérdés: Testreszabhatom a CSS-attribútumokat, amikor HTML-fájlokat mentünk az Aspose.Tasks programmal?

2. válasz: Igen, megadhat CSS mentési visszahívásokat a CSS-attribútumok igényei szerint testreszabásához.

### 3. kérdés: Az Aspose.Tasks for .NET kompatibilis a Microsoft Project fájlok összes verziójával?

3. válasz: Az Aspose.Tasks for .NET támogatja a Microsoft Project fájlok különféle verzióit, így biztosítja a kompatibilitást a különböző környezetekben.

### 4. kérdés: Hol találom az Aspose.Tasks for .NET átfogó dokumentációját?

A4: Hivatkozhat a[dokumentáció](https://reference.aspose.com/tasks/net/) részletes információkért és példákért.

### 5. kérdés: Az Aspose.Tasks for .NET támogatja a fejlesztőket?

 5. válasz: Igen, támogatást kaphat az Aspose.Tasks közösségtől a következőn keresztül[fórum](https://forum.aspose.com/c/tasks/15).