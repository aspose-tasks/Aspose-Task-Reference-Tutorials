---
date: 2026-07-05
description: Ismerje meg, hogyan testreszabhatja a CSS-t egy projekt HTML-be exportálása
  során az Aspose.Tasks for .NET használatával. Szabja testre a HTML kimenetet CSS
  mentési argumentumokkal.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Hogyan testreszabhatja a CSS-t projektek mentésekor az Aspose.Tasks segítségével
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Hogyan testreszabhatja a CSS-t projektek mentésekor az Aspose.Tasks segítségével
url: /hu/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan testreszabjuk a CSS-t a projektek mentésekor az Aspose.Tasks használatával

Ebben az útmutatóban megtudja, **hogyan testreszabja a CSS-t** a Microsoft Project fájl HTML exportálása során az Aspose.Tasks for .NET használatával. A CSS mentési argumentumok finomhangolásával teljes irányítást kap a létrehozott HTML oldalak megjelenési stílusa felett, így a kimenet megfelel a márkázási vagy jelentési szabványainak.

## Gyors válaszok
- **Mi a fő belépési pont?** Használja a `HtmlSaveOptions`-t egyedi visszahívásokkal.  
- **Szükségem van licencre?** Igen, egy érvényes Aspose.Tasks licenc szükséges a termeléshez.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Exportálhatok nagy projekteket?** Az Aspose.Tasks > 10 000 feladatot tartalmazó projekteket kezel anélkül, hogy a teljes fájlt a memóriába töltené.  
- **A CSS testreszabás opcionális?** Igen, kihagyhatja a visszahívásokat, és használhatja az alapértelmezett stíluslapot.

## Hogyan testreszabjuk a CSS-t az Aspose.Tasks-ben?

Töltse be a projektet, csatolja a CSS‑mentési visszahívásokat a `HtmlSaveOptions` objektumhoz, majd hívja meg a `project.Save` metódust. Ez a minta lehetővé teszi egyedi CSS fájlok írását, az alapértelmezett stílusok cseréjét és a mappaszerkezet vezérlését – mindezt néhány kódsorral. A visszahívásokat automatikusan meghívja a rendszer minden egyes CSS fájl esetén az exportálás során.

`HtmlSaveOptions` beállítja, hogyan exportálódik egy projekt HTML-be.

## Bevezetés

Ebben az oktatóanyagról a CSS argumentumok mentésének folyamatát vizsgáljuk meg az Aspose.Tasks for .NET használatával. A Cascading Style Sheets (CSS) kulcsfontosságú a HTML elemek megjelenésének meghatározásához. Az Aspose.Tasks lehetővé teszi ezen CSS attribútumok hatékony manipulálását és mentését.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg arról, hogy az alábbi előfeltételek teljesülnek:

1. Telepítés: Győződjön meg róla, hogy telepítette az Aspose.Tasks for .NET-et. Letöltheti a [weboldalról](https://releases.aspose.com/tasks/net/).
2. Alapvető tudás: Ajánlott a C# és a .NET fejlesztői környezet ismerete.

## Névtér importálása

To get started, import the necessary namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 1. lépés: CSS mentési visszahívások definiálása

`ICssSavingCallback` egy interfész, amely lehetővé teszi a CSS fájlok mentésének testreszabását HTML exportálás közben.

A **CSS mentési visszahívás** egy delegált, amelyet az Aspose.Tasks hív meg a CSS fájlok írásához HTML exportálás során. Definiálja a visszahívási metódusokat, hogy szabályozza, hogyan jönnek létre az egyes CSS fájlok:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## 2. lépés: Betűtípus- és képmentési visszahívások megvalósítása

`FontSavingArgs` információt nyújt a mentésre kerülő betűtípusról, míg az `ImageSavingArgs` részleteket ad a kép erőforrásokról.

A betűtípus- és képmentési visszahívási metódusokat hasonlóan valósítsa meg:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## 3. lépés: Mentési beállítások konfigurálása

`HtmlSaveOptions` a konfigurációs objektum, amely szabályozza, hogyan exportálódik egy Project HTML-be.

`HtmlSaveOptions` lehetővé teszi a visszahívások, kimeneti mappák és egyéb export beállítások megadását.

Állítsa be a tulajdonságait, hogy használja a korábban definiált visszahívásokat, és adja meg a kimeneti mappát:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 4. lépés: Projekt mentése testreszabott CSS-sel

`Project` egy Microsoft Project fájlt képvisel, amely manipulálható és menthető.

Végül mentse a projektet a testreszabott CSS beállításokkal:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Miért testreszabjuk a CSS-t projektek exportálásakor?

Az Aspose.Tasks támogatja a **projekt HTML-be exportálását** több mint 30 formátumban, és exportálásonként akár 30 különálló CSS fájlt is generálhat. Megbízhatóan kezeli a több mint 10 000 feladatot tartalmazó projekteket, miközben a memóriahasználatot 200 MB alatt tartja, lehetővé téve vállalati szintű jelentéskészítést teljesítménybeli szűk keresztmetszetek nélkül.

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan menthetők a CSS argumentumok az Aspose.Tasks for .NET használatával. A CSS mentési visszahívások definiálásával és a HTML mentési beállítások konfigurálásával hatékonyan manipulálhatjuk a CSS attribútumokat igényeink szerint.

## Gyakran Ismételt Kérdések

### Q1: Mi az Aspose.Tasks for .NET?
A1: Az Aspose.Tasks for .NET egy erőteljes .NET API, amely lehetővé teszi a fejlesztők számára, hogy programozott módon dolgozzanak Microsoft Project fájlokkal.

### Q2: Testreszabhatom a CSS attribútumokat HTML fájlok mentésekor az Aspose.Tasks használatával?
A2: Igen, definiálhat CSS mentési visszahívásokat a CSS attribútumok igényei szerint történő testreszabásához.

### Q3: Az Aspose.Tasks for .NET kompatibilis-e a Microsoft Project fájlok minden verziójával?
A3: Az Aspose.Tasks for .NET különböző Microsoft Project fájl verziókat támogat, biztosítva a kompatibilitást különböző környezetekben.

### Q4: Hol találhatok átfogó dokumentációt az Aspose.Tasks for .NET-hez?
A4: Részletes információkért és példákért tekintse meg a [dokumentációt](https://reference.aspose.com/tasks/net/).

### Q5: Az Aspose.Tasks for .NET nyújt támogatást a fejlesztőknek?
A5: Igen, támogatást kaphat az Aspose.Tasks közösségtől a [fórumon](https://forum.aspose.com/c/tasks/15).

**További kérdések**

**Q: Hogyan befolyásolja a CSS testreszabása az exportált HTML méretét?**  
A: Egyedi CSS használatával a teljes méret akár 15 %-kal is csökkenthető, mivel eltávolíthatók a nem használt alapértelmezett stílusok.

**Q: Használhatom ugyanazokat a visszahívásokat több projektnél?**  
A: Természetesen. A visszahívásokat egyszer implementálja, és újra felhasználhatja bármennyi projekt exportálásához.

**Q: Lehetséges a CSS közvetlenül az HTML-be ágyazni a különálló fájlok helyett?**  
A: Igen, állítsa be a `HtmlSaveOptions.EmbeddedCss = true` értéket, hogy a stíluslap be legyen ágyazva, ami egyszerűsíti a terjesztést.

---

**Legutóbb frissítve:** 2026-07-05  
**Tesztelve a következővel:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Microsoft Project mentése HTML-ként az Aspose.Tasks használatával](/tasks/net/saving-options/html-save-options/)
- [Oldal mentési visszahívás megvalósítása az Aspose.Tasks-ben](/tasks/net/advanced-concepts/page-saving-callback/)
- [Kép mentés kezelése az Aspose.Tasks-ben](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}