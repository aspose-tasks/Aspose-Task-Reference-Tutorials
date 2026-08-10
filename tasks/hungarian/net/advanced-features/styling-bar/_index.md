---
date: 2026-04-06
description: Ismerje meg, hogyan változtathatja meg a sávok stílusát és testreszabhatja
  a sávok színeit az Aspose.Tasks for .NET-ben a projekt megjelenítésének javítása
  érdekében.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Stílus eszköztár az Aspose.Tasks‑ben
second_title: Aspose.Tasks .NET API
title: Hogyan változtassuk meg a sáv stílusát az Aspose.Tasks-ben
url: /hu/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan változtassuk meg a sávok stílusát az Aspose.Tasks-ben

## Bevezetés

Ha **hogyan változtassuk meg a sávot** megjelenését szeretné módosítani egy Microsoft Project fájlban, az Aspose.Tasks for .NET teljes irányítást ad a sávok színe, alak és szövegstílus felett. A sávszínek és egyéb vizuális attribútumok testreszabásával a projekttervek sokkal könnyebben olvashatóak és jobban illeszkednek a szervezet márkaarculatához. Ebben az útmutatóban egy teljes, lépésről‑lépésre példát mutatunk be, amely bemutatja, hogyan változtassuk meg a sávok stílusát, a projekt betöltésétől a módosított vizuális szabályokkal történő exportig.

## Gyors válaszok
- **Mit tudok testreszabni?** Sávok, mérföldkövek és feladat szöveg a Gantt-diagramokban.  
- **Melyik formátum támogatja a stílusos sávokat?** PDF, XLSX, HTML és a natív MPP, ha `PdfSaveOptions`‑szel mentik.  
- **Szükségem van licencre?** Kereskedelmi licenc szükséges a termelésben való használathoz; egy ingyenes próba a teszteléshez elegendő.  
- **Alkalmazhatok több stílust?** Igen – adjon hozzá annyi `BarStyle` objektumot, amennyire szüksége van.  
- **Kompatibilis a .NET Core‑ral?** Teljesen – működik a .NET Framework‑kel és a .NET Core/5/6+-tal.

## Mi az a sávstílus az Aspose.Tasks-ben?

A sávstílus lehetővé teszi, hogy vizuális szabályokat definiáljon, amelyeket az Aspose.Tasks motor alkalmaz a Gantt-diagramok megjelenítésekor. Minden szabály (egy **BarStyle**) egy adott elem típusra – feladatokra, mérföldkövekre vagy összegző feladatokra – irányul, és lehetővé teszi színek, alakok és akár egyéni szöveg beállítását.

## Miért testreszabjuk a sávszíneket?

A sávszínek testreszabása segíti az érintetteket abban, hogy azonnal felismerjék a kritikus útvonalakat, a késedelmes feladatokat vagy a mérföldköveket. Emellett lehetővé teszi a vállalati színpaletta egyeztetését, így a jelentések professzionálisak és a márka arculatához illeszkednek.

## Előfeltételek

Mielőtt elkezdenénk, győződjön meg róla, hogy rendelkezik:

1. **Aspose.Tasks for .NET** – töltse le a [letöltési oldalról](https://releases.aspose.com/tasks/net/).  
2. Egy fejlesztői környezet, amely támogatja a .NET‑et (Framework 4.6+, .NET Core 3.1+ vagy újabb).  
3. Alapvető ismeretek a C#‑ról – a példák egyszerű, önálló kódot használnak.

## Névterek importálása

First, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1. lépés: Projekt betöltése

Load an existing MPP file (or create a new one) so you have a project object to work with:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## 2. lépés: Mentési beállítások konfigurálása

Create a `PdfSaveOptions` instance and initialise the `BarStyles` collection where we’ll store our custom styles:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## 3. lépés: Sávstílus definiálása

Now we build a `BarStyle` object and set the properties that control how the bar looks. This is where we **customize bar colors** and shapes:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## 4. lépés: Szövegkonverter testreszabása (opcionális)

If you want to tweak the text that appears on the bar, you can assign a custom converter. The example prefixes task names that don’t already start with “T”:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## 5. lépés: Sávstílus hozzáadása a beállításokhoz

Add the fully configured style to the `BarStyles` collection of the save options:

```csharp
options.BarStyles.Add(style);
```

## 6. lépés: Projekt mentése

Finally, export the project. The PDF (or other format) will render the Gantt chart using the bar style we defined:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Sávstílus nem alkalmazva** | `BarStyles` gyűjtemény üres volt vagy nem lett csatolva a mentési beállításokhoz. | Győződjön meg róla, hogy a `BarStyle`-t hozzáadja az `options.BarStyles`-hez a `Save` hívása előtt. |
| **A színek másként jelennek meg PDF‑ben** | A PDF renderelés más színprofilt használhat. | Használjon szabványos `System.Drawing.Color` értékeket vagy definiáljon egyedi ARGB színeket. |
| **A szövegkonverter null referenciát dob** | A `Tsk.Name` feladattulajdonság néhány feladatnál null. | Adjon hozzá null‑ellenőrzést a `task.Get(Tsk.Name)` hívása előtt. |

## Gyakran Ismételt Kérdések

### Q1: Alkalmazhatok több sávstílust egy projektre?

A1: Igen, több sávstílust definiálhat és alkalmazhat a projektben lévő különböző feladattípusokra.

### Q2: Lehetséges a sávstílusok dinamikus módosítása futásidőben?

A2: Igen, a sávstílusokat dinamikusan módosíthatja bizonyos feltételek vagy felhasználói beállítások alapján az alkalmazásában.

### Q3: Támogatja az Aspose.Tasks a projektek exportálását stílusos sávokkal különböző fájlformátumokba?

A3: Igen, az Aspose.Tasks támogatja a projektek exportálását stílusos sávokkal különböző formátumokba, például PDF, XLSX és HTML.

### Q4: Vannak előre definiált sávstílusok az Aspose.Tasks-ben?

A4: Bár az Aspose.Tasks alapértelmezett sávstílusokat biztosít, a fejlesztők egyedi sávstílusokat is létrehozhatnak a projekt igényeihez igazítva.

### Q5: Lekérhetem és módosíthatom a meglévő sávstílusokat egy projektben az API‑val?

A5: Igen, a meglévő sávstílusokat programozottan lekérheti és módosíthatja az Aspose.Tasks for .NET API‑val.

## Gyakran Feltett Kérdések

**Q: Hogyan változtathatom meg a sáv színét a normál feladatoknál a mérföldköveknél?**  
A: Állítsa be `style.ItemType = BarItemType.Task;` és adja meg a kívánt `Color` értéket a `style.BarColor`‑nak.

**Q: Használhatom ezt a megközelítést a sávok stílusozására HTML‑exportáláskor?**  
A: Igen. Használja a `HtmlSaveOptions`‑t, és töltse fel a `BarStyles` gyűjteményét ugyanúgy.

**Q: Van korlát a definiálható sávstílusok számában?**  
A: Gyakorlatilag nincs; annyit hozzáadhat, amennyire szüksége van, de nagy gyűjtemények esetén vegye figyelembe a teljesítményt.

**Q: Szükséges a `project.Calculate()` meghívása a stílusok módosítása után?**  
A: Nem, a stílusok a mentési művelet során kerülnek alkalmazásra; újraszámítás csak ütemezési változások esetén szükséges.

---

**Utoljára frissítve:** 2026-04-06  
**Tesztelve ezzel:** Aspose.Tasks 24.11 for .NET  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}