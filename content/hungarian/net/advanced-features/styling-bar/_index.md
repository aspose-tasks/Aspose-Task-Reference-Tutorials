---
title: Styling Bar az Aspose.Tasks-ban
linktitle: Styling Bar az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Tanulja meg, hogyan lehet sávokat stílusozni az Aspose.Tasks for .NET-ben a projektek megjelenítésének javítása érdekében.
type: docs
weight: 19
url: /hu/net/advanced-features/styling-bar/
---
## Bevezetés

A stílussávok kialakítása az Aspose.Tasks programban lényeges szempont a látványos projekttervek elkészítésében. Az Aspose.Tasks API által kínált rugalmasság révén a fejlesztők testreszabhatják a sávok különböző aspektusait, például a színt, a formát és a szövegstílust, hogy javítsák a projekt megjelenítését. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet a sávokat stílusozni az Aspose.Tasks for .NET használatával, az egyes példákat kezelhető lépésekre bontva.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1.  Aspose.Tasks for .NET Library: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a[letöltési oldal](https://releases.aspose.com/tasks/net/).
2. Fejlesztői környezet: Hozzon létre egy fejlesztői környezetet .NET keretrendszer támogatással.
3. A C# alapvető ismerete: A C# programozási nyelv ismerete előnyös lesz.

## Névterek importálása

Először is importáljuk a szükséges névtereket az Aspose.Tasks osztályok és metódusok eléréséhez:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 1. lépés: Töltse be a projektet

kezdéshez töltse be a projektfájlt az Aspose.Tasks API segítségével:

```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## 2. lépés: Konfigurálja a mentési beállításokat

Határozza meg a mentési beállításokat, megadva az alkalmazandó sávstílusokat:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## 3. lépés: Határozza meg a sáv stílusát

Hozzon létre egy új sávstílust, és szabja testre annak tulajdonságait:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Állítsa be a sávelem típusát
style.BarColor = Color.Green; // Állítsa be a sáv színét
style.BarShape = BarShape.HalfHeight; // Állítsa be a sáv alakját
style.StartShape = Shape.LeftBracket; // Állítsa be a formát a sáv elején
style.StartShapeColor = Color.Aqua; // Állítsa be a kezdő alakzat színét
style.EndShape = Shape.RightBracket; // Állítsa be a formát a rúd végén
style.EndShapeColor = Color.Aquamarine; // Állítsa be a végforma színét
style.TextStyle = new TextStyle(); // Állítsa be a szövegstílust
style.TextStyle.BackgroundColor = Color.Black; // Állítsa be a szöveg háttérszínét
```

## 4. lépés: A Text Converter testreszabása

Opcionálisan testreszabhatja a szövegkonvertálót a szöveg megjelenítésének módosításához:

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

## 5. lépés: Adja hozzá a sáv stílusát a Beállításokhoz

Adja hozzá a konfigurált sávstílust a mentési beállításokhoz:

```csharp
options.BarStyles.Add(style);
```

## 6. lépés: Mentse el a projektet

Végül mentse el a projektet az alkalmazott sávstílusokkal:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Következtetés

Az Aspose.Tasks for .NET sávstílusainak testreszabása lehetővé teszi a fejlesztők számára, hogy tetszetős projektterveket készítsenek. Az oktatóanyagban ismertetett lépések követésével hatékonyan stílusozhatja a sávokat, hogy megfeleljenek a konkrét projektvizualizációs követelményeknek.

## GYIK

### 1. kérdés: Alkalmazhatok több sávstílust egyetlen projektre?

1. válasz: Igen, ugyanazon a projekten belül több sávstílust is meghatározhat és alkalmazhat különböző típusú feladatokra.
   
### 2. kérdés: Lehetséges dinamikusan módosítani a sávstílusokat futás közben?

2. válasz: Igen, az alkalmazáson belül bizonyos feltételek vagy felhasználói beállítások alapján dinamikusan módosíthatja a sávstílusokat.
   
### 3. kérdés: Az Aspose.Tasks támogatja a projektek stílusos sávokkal történő exportálását különböző fájlformátumokba?

3. válasz: Igen, az Aspose.Tasks támogatja a projektek stílusos sávokkal történő exportálását különféle formátumokba, például PDF, XLSX és HTML.
   
### 4. kérdés: Elérhetők előre meghatározott sávstílusok az Aspose.Tasks-ban?

4. válasz: Míg az Aspose.Tasks alapértelmezett sávstílusokat biztosít, a fejlesztők egyéni sávstílusokat is létrehozhatnak a projekt követelményeihez szabva.
   
### 5. kérdés: Lekérhetem és módosíthatom a meglévő sávstílusokat egy projekten belül az API használatával?

5. válasz: Igen, lekérheti és módosíthatja a meglévő sávstílusokat programozottan az Aspose.Tasks for .NET API használatával.