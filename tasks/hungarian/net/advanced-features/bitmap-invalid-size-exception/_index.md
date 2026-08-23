---
date: 2026-03-21
description: Ismerje meg, hogyan exportáljon képet, és hogyan kezelje a BitmapInvalidSizeException
  kivételt a projekt képként való mentésekor az Aspose.Tasks for .NET-ben. Tartalmazza
  a projekt képként való mentésének és PNG formátumba történő exportálásának lépéseit.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hogyan exportáljunk képet, és kezeljük az érvénytelen méret kivételt
url: /hu/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan exportáljunk képet – Bitmap Invalid Size kivétel kezelése az Aspose.Tasks-ben

Ebben az útmutatóban megtanulja, **hogyan exportáljon képet** egy Microsoft Project fájlból az Aspose.Tasks for .NET segítségével, és ami még fontosabb, hogyan kezelje a `BitmapInvalidSizeException` kivételt, amely a folyamat során előfordulhat. A projekt képként történő exportálása gyakori igény jelentésműszerfalakhoz, dokumentációhoz vagy egyszerűen egy ütemterv vizuális pillanatképe megosztásához. A végére képes lesz **projekt mentésére képként** megbízhatóan, és akár **projekt exportálására PNG** formátumba is, váratlan összeomlások nélkül.

## Gyors válaszok
- **Milyen kivétel fordulhat elő kép exportálásakor?** `BitmapInvalidSizeException`  
- **Melyik formátumot használja a példában?** PNG (`SaveFileFormat.Png`)  
- **Szükség van-e speciális licencre?** Érvényes Aspose.Tasks licenc szükséges a termelésben való használathoz.  
- **Módosíthatom-e az időskálát?** Igen – beállíthatja az időskála egységét (percek, órák, napok stb.).  
- **Kompatibilis a kód a .NET Core-rel?** Teljesen – ugyanaz az API működik .NET Framework és .NET Core alatt is.

## Mi az a BitmapInvalidSizeException?
A `BitmapInvalidSizeException` akkor kerül dobásra, amikor a képhez számított bitmap méretek kívül esnek a támogatott tartományon (például a szélesség vagy magasság nulla, vagy meghaladja a belső korlátokat). Ez általában akkor fordul elő, amikor az időskála vagy a nézetbeállítások olyan képet eredményeznek, amely túl nagy vagy túl kicsi.

## Miért exportáljunk projektet képként?
- **Vizuális jelentés** – Gantt-diagram beágyazása PDF‑ekbe, Word dokumentumokba vagy weboldalakra.  
- **Platformfüggetlen megosztás** – A PNG fájlok bármilyen eszközön megtekinthetők Microsoft Project nélkül.  
- **Teljesítmény** – A képek könnyűek a teljes projektfájlokhoz képest, így gyors előnézetet biztosítanak.

## Előfeltételek
1. Alapvető C# és .NET fejlesztési ismeretek.  
2. Aspose.Tasks for .NET telepítve (NuGet csomag `Aspose.Tasks`).  
3. Egy minta Microsoft Project fájl (például `Blank2010.mpp`).  

## Névterek importálása
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Lépésről‑lépésre útmutató

### 1. lépés: Inicializálja a projektet és válasszon nézetet
Először hozzon létre egy `Project` példányt, és válassza ki a megjeleníteni kívánt nézetet (ebben a példában az első Gantt-diagram nézetet használjuk).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### 2. lépés: Állítsa be a kép mentési beállításokat (Projekt exportálása PNG-be)
Adja meg a kívánt képformátumot, és mondja meg az Aspose.Tasks‑nek, hogy a nézetben definiált időskálát használja.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### 3. lépés: Az időskála egységének módosítása (Kép méretének szabályozása)
Az időskála módosítása befolyásolja a bitmap méreteket. Ebben a példában **percek** egységet használunk, hogy a kép mérete kezelhető maradjon.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### 4. lépés: Próbálja meg menteni a projektet képként
Ez a sor hajtja végre a tényleges **projekt mentését képként** műveletet.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### 5. lépés: A BitmapInvalidSizeException elkapása és kezelése
Tegye a mentési hívást egy `try / catch` blokkba, hogy az alkalmazás elegánsan reagáljon, ha a bitmap mérete érvénytelen.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| A kivétel továbbra is dobódik az időskála módosítása után | Az időskála még mindig túl nagy bitmapet eredményez | Csökkentse a `view.MiddleTimescaleTier.Count` értékét vagy válasszon durvább `TimescaleUnit`‑ot (pl. Órák). |
| A kimeneti fájl üres | Helytelen fájlútvonal vagy hiányzó írási jogosultság | Ellenőrizze, hogy a `DataDir` írható mappára mutat, és a fájlnév `.png`‑re végződik, ha más formátumot használ. |
| A kép minősége gyenge | Az alap DPI alacsony lehet | Állítsa a `options.DpiX` és `options.DpiY` értékeket magasabbra (pl. 300). |

## Gyakran Ismételt Kérdések

**K: Mi okozza a BitmapInvalidSizeException‑t az Aspose.Tasks-ben?**  
A: Akkor fordul elő, amikor a számított bitmap méretek érvénytelenek – általában azért, mert az időskála olyan képet eredményez, amely túl nagy vagy nulla szélesség/magasság.

**K: Testreszabhatom-e az időskálát kép exportálásakor?**  
Igen. A `view.MiddleTimescaleTier.Unit` és `Count` értékek módosításával a saját igényeihez igazíthatja, ahogy a bemutatóban is látható.

**K: Támogatja-e az Aspose.Tasks más képformátumokat a PNG-en kívül?**  
Természetesen. A `SaveFileFormat` tartalmazza a JPEG, BMP, GIF és TIFF formátumokat is. Csak cserélje ki az enum értékét az `ImageSaveOptions`‑ban.

**K: Szükséges-e licenc a képek exportálásához egy éles környezetben?**  
Igen. Bár a könyvtár értékelő módban működik, egy kereskedelmi licenc eltávolítja az értékelési korlátozásokat és teljes támogatást biztosít.

**K: Hogyan javíthatom az exportált PNG minőségét?**  
Növelje a DPI beállításokat (`options.DpiX` és `options.DpiY`) vagy módosítsa a nézet időskáláját, hogy nagyobb bitmapet kapjon.

## Összegzés
A fenti lépések követésével most már tudja, **hogyan exportáljon képet** egy projektfájlból, hogyan **mentse a projektet képként**, és hogyan kezelje elegánsan a `BitmapInvalidSizeException` kivételt. Ezek a technikák megerősítik a jelentéskészítési folyamatokat, és biztosítják, hogy a vizuális exportok megbízhatóan működjenek különböző projektméretek és időskálák esetén.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Utolsó frissítés:** 2026-03-21  
**Tesztelve:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

---