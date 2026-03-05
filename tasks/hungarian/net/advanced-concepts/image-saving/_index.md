---
date: 2026-03-05
description: Tanulja meg, hogyan menthet képeket, generálhat HTML-t képekkel, és testreszabhatja
  a képek exportálását az Aspose.Tasks for .NET használatával. Lépésről‑lépésre útmutató
  a projekt HTML‑ként való mentéséhez.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Hogyan menthet képeket az Aspose.Tasks for .NET segítségével
url: /hu/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan menthetünk képeket az Aspose.Tasks for .NET használatával

## Bevezetés

Ebben az útmutatóban **megmutatjuk, hogyan menthetünk képeket** a Microsoft Project fájlokból az Aspose.Tasks API for .NET segítségével. Akár diagramokat kell beágyazni jelentésekbe, HTML oldalakat generálni, amelyek projektvizualizációkat tartalmaznak, vagy egyszerűen diagramok exportálása a cél, az alábbi lépések végigvezetik a teljes folyamaton – a projektobjektum beállításától a kép‑export visszahívások testreszabásáig.

## Gyors válaszok
- **Mit jelent a „hogyan menthetünk képeket” az Aspose.Tasks-ben?**  
  Ez azt jelenti, hogy az `IImageSavingCallback` interfészt használva szabályozhatjuk, hogy a vizuális erőforrások hová és hogyan kerülnek lemezre.
- **Menthetek-e egy projektet HTML‑ként beágyazott képekkel?**  
  Igen, a `HtmlSaveOptions` és a kép‑mentési visszahívások kombinálásával **menthetünk projektet HTML‑ként**, amely tartalmazza az összes generált képet.
- **Szükségem van licencre a képek exportálásához?**  
  Ideiglenes értékelő licenc teszteléshez elegendő; a teljes licenc a termelésben való használathoz kötelező.
- **Mely .NET verziók támogatottak?**  
  Az Aspose.Tasks for .NET támogatja a .NET Framework 4.5+, a .NET Core 3.1+, valamint a .NET 5/6+ verziókat.
- **Lehetséges-e testreszabni a képek exportálását (formátum, mappa, elnevezés)?**  
  Teljes mértékben – a visszahívás lehetővé teszi a fájlnév, formátum és célhely teljes ellenőrzését.

## Mi a „hogyan menthetünk képeket” az Aspose.Tasks kontextusában?
A képek mentése azt jelenti, hogy a projektfájl vizuális elemeit (diagramok, Gantt‑oszlopok, erőforrás‑grafikák) kinyerjük, és képfájlokba (PNG, JPEG stb.) írjuk. Az Aspose.Tasks rugalmas visszahívás‑mechanizmust biztosít, amely lehetővé teszi a pontos hely, elnevezési szabály és akár a képformátum meghatározását.

## Miért használjuk az Aspose.Tasks-et képek mentésére?
- **Teljes programozott vezérlés** – nincs szükség manuális UI‑interakcióra.  
- **Keresztplatformos** – Windows, Linux és macOS alatt is működik a .NET Core‑val.  
- **Magas hűségű renderelés** – a képek ugyanolyan minőséget őriznek, mint az eredeti Project‑nézet.  
- **Könnyű HTML generálás** – a `HtmlSaveOptions` és a kép‑visszahívások kombinálásával **automatikusan generálhat HTML‑t képekkel**.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy a következők rendelkezésre állnak:

1. Visual Studio telepítve van a fejlesztői gépén.  
2. Aspose.Tasks for .NET letöltve a [itt](https://releases.aspose.com/tasks/net/) található helyről.  
3. Alapvető ismeretek a C#‑ról és a .NET projektstruktúráról.

## Névtér importálása

Először hozza be a szükséges névtereket a forrásfájlba:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1. lépés: Projekt objektum létrehozása

Töltse be azt a Microsoft Project fájlt, amelyen dolgozni szeretne:

```csharp
var project = new Project("Project1.mpp");
```

## 2. lépés: Mentési beállítások meghatározása

Hozza létre a HTML mentési beállításokat, amelyek tartalmazni fogják a kép‑mentési visszahívásainkat is:

```csharp
var options = GetSaveOptions(1);
```

## 3. lépés: Projekt mentése HTML‑ként (save project as html)

Most exportálja a projektet egy HTML fájlba. A HTML‑ben hivatkozott képeket a következő lépésben definiált visszahívás fogja generálni:

```csharp
project.Save("document_out.html", options);
```

## 4. lépés: Kép mentési visszahívás implementálása (customize image export)

Implementálja az `IImageSavingCallback` interfészt. Itt **testreszabhatja a kép exportálás** viselkedését:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## 5. lépés: Képek mentése a megadott könyvtárba

Az `ImageSaving` metódusban határozza meg, hogy minden kép hová kerüljön. Az alábbi példa megkülönbözteti a PNG erőforrásokat a többi formátumtól:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## 6. lépés: Mentési beállítások megadása (including callbacks)

Kapcsolja össze a betűtípus, CSS és kép visszahívásokat. Ez biztosítja, hogy minden vizuális elem konzisztensen legyen kezelve:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| A képek nem jelennek meg a generált HTML‑ben | A visszahívás nem ad meg érvényes fájlútvonalat | Győződjön meg róla, hogy az `args.Path` egy írható mappára mutat, és az `args.ImageStream` helyesen van beállítva. |
| PNG fájlok rossz kiterjesztéssel kerülnek mentésre | A feltételes logika csak a „png” utótagot ellenőrzi | Használja a `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` kifejezést a megbízható ellenőrzéshez. |
| HTML hivatkozások hibásak a fájlok áthelyezése után | Relatív útvonalak megváltoztak a kimeneti mappa mozgatása során | Tartsa együtt a HTML‑t és a képmappákat, vagy frissítse az `options.ImageFolder` beállítást ennek megfelelően. |

## Összegzés

Ezekkel a lépésekkel most már tudja, **hogyan menthet képeket** egy projektfájlból, **hogyan mentheti a projektet HTML‑ként**, és **hogyan testreszabhatja a kép exportálást** a saját mappastruktúrájához igazítva. Ez a megközelítés lehetővé teszi, hogy **HTML‑t képekkel generáljon**, amely könnyedén beágyazható jelentésekbe, dokumentációs portálokba vagy webes irányítópultokba.

## Gyakran Ismételt Kérdések

**Q1: Használhatom-e az Aspose.Tasks-et projektfájlok más formátumokban való manipulálására a HTML-en kívül?**  
A1: Igen, az Aspose.Tasks számos formátumot támogat, például PDF, XLSX és MPP.

**Q2: Az Aspose.Tasks biztosít-e támogatást felhőalapú tároló integrációhoz?**  
A2: Igen, az Aspose.Tasks API‑k elérhetők népszerű felhőszolgáltatásokhoz, mint az Amazon S3 és a Google Drive.

**Q3: Az Aspose.Tasks kompatibilis a .NET Core‑ral?**  
A3: Igen, az Aspose.Tasks kompatibilis a .NET Core‑ral, így keresztplatformos alkalmazásokat fejleszthet.

**Q4: Testreszabhatom-e a mentett képek megjelenését?**  
A4: Igen, a kép mentési logikát a visszahívási metódusokban módosítva testreszabhatja a képek megjelenését.

**Q5: Az Aspose.Tasks kínál-e próbaverziót értékelési célokra?**  
A5: Igen, ingyenes próbaverziót szerezhet az Aspose.Tasks‑hez a [itt](https://releases.aspose.com/) található oldalon.

---

**Utolsó frissítés:** 2026-03-05  
**Tesztelve:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}