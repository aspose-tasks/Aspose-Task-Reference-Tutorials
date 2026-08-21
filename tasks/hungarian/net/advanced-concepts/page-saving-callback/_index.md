---
date: 2026-03-16
description: Tanulja meg, hogyan valósíthatja meg az oldal mentésének visszahívását
  az Aspose.Tasks for .NET-ben, lehetővé téve a többoldalas dokumentum kimeneti adatfolyamainak
  testreszabott kezelését.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Oldalmentés visszahívásának implementálása az Aspose.Tasks-ben
url: /hu/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Page mentési visszahívás implementálása az Aspose.Tasks-ben

## Bevezetés

Ebben az útmutatóban megtanulja, hogyan **valósítsa meg a page saving callback-et** az Aspose.Tasks for .NET-ben. Ez a hatékony funkció lehetővé teszi, hogy egy többoldalas dokumentum minden oldalát egy ön által választott stream‑be irányítsa, teljes irányítást biztosítva a kimenet tárolása vagy további feldolgozása felett.

## Gyors válaszok
- **Mit csinál a page saving callback?** Minden renderelt oldalt külön stream‑be rögzít, így egyenként kezelheti őket.  
- **Milyen formátumba exportálhatok?** Bármelyik, amelyet az `ImageSaveOptions` támogat, például PNG, JPEG, PDF.  
- **Szükség van licencre?** Érvényes Aspose.Tasks licenc szükséges a termelési használathoz.  
- **Használható .NET Core‑dal?** Igen, az Aspose.Tasks teljes mértékben támogatja a .NET Core‑t és a .NET 5/6+ verziókat.  
- **A callback szálbiztos?** A callback ugyanazon a szálon fut, amely a renderelést végzi, így a szokásos szálbiztonsági szabályok érvényesek.

## Mi az a **implement page saving callback**?
A **implement page saving callback** minta lehetővé teszi, hogy egyedi logikát illesszen be az Aspose.Tasks mentési folyamatába. A fájlba írás helyett minden oldalhoz egy `Stream` objektumot kap, amelyet memóriában tárolhat, felhő tárolóba tölthet fel, vagy további feldolgozást végezhet rajta.

## Miért exportáljuk a projektet PNG‑ként callback‑kel?
A projekt PNG‑ként való exportálása minden Gantt-diagram oldalról raszteres képet ad, ami ideális jelentésekhez, e‑mailekhez vagy weboldalakba ágyazáshoz. A callback használatával minden oldalt külön `MemoryStream`‑ben tarthat anélkül, hogy ideiglenes fájlokat hozna létre a lemezen.

## Előfeltételek

1. **C# ismeretek** – alapvető tudás osztályokról, interfészekről és streamekről.  
2. **Aspose.Tasks for .NET** – letölthető és telepíthető innen: [here](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider vagy bármely .NET‑kompatibilis szerkesztő.

## Névtér importálása

A kezdéshez importálja a szükséges névtereket:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## 1. lépés: Projekt objektum létrehozása

Töltsön be egy meglévő MPP fájlt egy `Project` példányba:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## 2. lépés: Kép mentési beállítások konfigurálása

Állítsa be az `ImageSaveOptions`‑t PNG kimenethez, és csatolja a saját callback‑et:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Pro tipp:** A `RenderToSinglePage = false` beállítás biztosítja, hogy minden Gantt-diagram oldal külön-külön legyen renderelve, ami elengedhetetlen ahhoz, hogy a callback különálló streameket kapjon.

## 3. lépés: Projekt mentése callback‑kel

Hívja meg a `Save` metódust, a `Stream.Null`‑t adva meg, mivel a tényleges streameket a callback biztosítja:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## 4. lépés: Mentett oldal streamek feldolgozása

A mentési művelet befejezése után a callback egy `MemoryStream` objektumok gyűjteményét tartja – egyet oldalanként. Most már iterálhat rajtuk:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## 5. lépés: Egyedi Page Saving Callback implementálása

Hozzon létre egy sealed osztályt, amely megvalósítja az `IPageSavingCallback` interfészt. Ez az osztály minden oldal stream‑jét egy listába gyűjti későbbi felhasználásra.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Gyakori hibák és hibaelhárítás

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Nem érkezik oldal** | `RenderToSinglePage` `true`‑ra van állítva. | Állítsa `RenderToSinglePage = false`‑ra a különálló oldalak generálásához. |
| **A streamek üresek** | `KeepStreamOpen` `true`‑ra van állítva, de később nem zárja le. | Hagyja `false`‑on (alapértelmezett) és engedje, hogy a callback automatikusan lezárja a streameket. |
| **Memória‑hiány** | Nagyon nagy projektek sok magas felbontású PNG‑t generálnak. | Dolgozza fel a streameket egyesével, vagy növelje a VM memóriakorlátait. |

## Gyakran feltett kérdések

**Q1: Mi az a page saving callback az Aspose.Tasks‑ben?**  
A: A page saving callback lehetővé teszi, hogy minden oldal mentési folyamatát elfogja, és egy egyedi `Stream`‑et biztosítson az adott oldalhoz.

**Q2: Használhatok különböző formátumokat az oldalak mentéséhez ezzel a callback‑kel?**  
A: Igen. A `SaveFileFormat` módosításával exportálhat PNG, JPEG, PDF, SVG stb. formátumokba.

**Q3: Az Aspose.Tasks kompatibilis a .NET Core‑dal?**  
A: Teljes mértékben. Az Aspose.Tasks támogatja a .NET Core, .NET 5 és .NET 6 verziókat.

**Q4: Hogyan kezeljem a hibákat a page saving folyamat során?**  
A: A callback logikát try/catch blokkokba ágyazza, és naplózza a kivételeket. Az `OnFinish` metódus jó hely a végső takarításra.

**Q5: Hol találok további forrásokat és támogatást az Aspose.Tasks‑hez?**  
A: Látogasson el az [Aspose.Tasks fórumra](https://forum.aspose.com/c/tasks/15) segítségért, tekintse meg a dokumentációt [itt](https://reference.aspose.com/tasks/net/), vagy fedezze fel a további funkciókat és licencelési lehetőségeket az [Aspose.Tasks weboldalon](https://purchase.aspose.com/buy).

---

**Utoljára frissítve:** 2026-03-16  
**Tesztelt verzió:** Aspose.Tasks 24.12 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}