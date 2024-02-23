---
title: A Gantt-diagram nézeteinek elsajátítása az Aspose.Tasks programban
linktitle: Gantt-diagram nézetei az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan testreszabhatja a Gantt-diagram nézeteit a Microsoft Project fájlokban az Aspose.Tasks for .NET segítségével. Lépésről lépésre útmutató a hatékony projektmenedzsmenthez.
type: docs
weight: 22
url: /hu/net/tasks-project-management/gantt-chart-views/
---
## Bevezetés
A Gantt-diagramok hatékony eszközök a projektmenedzsmentben a feladatok, idővonalak és függőségek megjelenítésére. Az Aspose.Tasks for .NET robusztus képességeket biztosít a Microsoft Project-fájlok Gantt-diagramnézeteivel való munkavégzéshez. Ebben az oktatóanyagban megvizsgáljuk, hogyan használható az Aspose.Tasks a Gantt-diagram nézeteinek manipulálására, a megjelenésük testreszabására és PDF-fájlként való mentésére.
## Előfeltételek
Mielőtt folytatná, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
### 1. Az Aspose.Tasks telepítése .NET-hez
 Győződjön meg arról, hogy telepítette az Aspose.Tasks for .NET-et. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/tasks/net/)és kövesse a dokumentációban található telepítési utasításokat[itt](https://reference.aspose.com/tasks/net/).
### 2. Microsoft Project File
Készítsen egy Microsoft Project fájlt (`Project2.mpp`), amelyet a Gantt-diagram nézetekkel való munkához fog használni.
### 3. C# és .NET Framework alapismeretek
Ez az oktatóanyag feltételezi, hogy rendelkezik a C# programozási nyelv és a .NET keretrendszer alapvető ismereteivel.
## Névterek importálása
Mielőtt elkezdené a Gantt-diagram nézetekkel való munkát az Aspose.Tasks programban, importálnia kell a szükséges névtereket a C#-kódba. A következőképpen teheti meg:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Bontsuk fel a megadott példakódot több lépésre, és magyarázzuk el részletesen az egyes lépéseket:
## 1. lépés: Töltse be a projektfájlt
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Ez a lépés magában foglalja a Microsoft Project fájl betöltését (`Project2.mpp` ) a`Project` osztály.
## 2. lépés: Állítsa be az állapot dátumát
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Itt beállítjuk a projekt állapotának dátumát a kezdő dátumra.
## 3. lépés: Nyissa meg a Gantt-diagram nézetet
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
A projektből elérjük a Gantt-diagram nézetet. Az Aspose.Tasks lehetővé teszi az olyan nézetek elérését, mint a Gantt-diagram, a Hálózati diagram és a Feladathasználat.
## 4. lépés: A Gantt-diagram nézet testreszabása
Most pedig szabjuk testre a Gantt-diagram nézet különböző szempontjait:
### Állítsa be a sáv kerekítését
```csharp
view.BarRounding = false;
```
Ez beállítja, hogy a Gantt-diagram oszlopai a legközelebbi napra kerekedjenek-e.
### Állítsa be a sáv méretét
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Ez határozza meg a Gantt-sávok magasságát a diagramon.
### Összegző sávok elrejtése
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Meghatározza, hogy az összesítő sávok el legyenek-e rejtve az összefoglaló feladatok kibontásakor.
### Állítsa be a nem munkaidő színét
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Meghatározza a munkaszüneti idő színét a Gantt-diagramon.
### Roll Up Gantt Bars
```csharp
view.RollUpGanttBars = true;
```
Adja meg, hogy a Gantt-diagram oszlopait fel kell-e görgetni.
### Show Bar Splits
```csharp
view.ShowBarSplits = true;
```
Meghatározza, hogy meg kell-e jeleníteni a Gantt-diagram feladatfelosztásait.
### rajzokat mutatni
```csharp
view.ShowDrawings = true;
```
Meghatározza, hogy a Gantt-diagram rajzait meg kell-e jeleníteni.
### Időskála Méret százalék
```csharp
view.TimescaleSizePercentage = 10;
```
Beállít egy százalékot az egységek közötti távolság beállításához az időskála szintjén.
## 5. lépés: Mentse el a Gantt-diagramnézetet PDF formátumban
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Végül elmentjük a testreszabott Gantt-diagram nézetet PDF fájlként.
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell dolgozni Gantt-diagramnézetekkel az Aspose.Tasks for .NET-ben. A megadott lépések követésével hatékonyan kezelheti és testreszabhatja a Gantt-diagramokat a projekt követelményei szerint.
## GYIK
### K: Tovább szabhatom a Gantt-diagram sávjainak megjelenését?
V: Igen, az Aspose.Tasks széles körű lehetőségeket kínál a Gantt-diagram sávjainak megjelenésének testreszabására, beleértve a színeket, formákat és méreteket.
### K: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok különféle verzióit, beleértve az MPP, MPT és XML formátumokat.
### K: Exportálhatok Gantt-diagram nézeteket PDF-től eltérő formátumba?
V: Az Aspose.Tasks teljes mértékben támogatja a Gantt-diagram nézetek többféle formátumba, köztük PNG, JPEG és XPS formátumba történő exportálását.
### K: Az Aspose.Tasks támogatja az összetett projektütemezési algoritmusokat?
V: Igen, az Aspose.Tasks fejlett ütemezési algoritmusokat biztosít az összetett projektütemezések hatékony kezelésére.
### K: Van olyan közösségi fórum, ahol segítséget kérhetek, vagy megoszthatom az Aspose.Tasks-szal kapcsolatos tapasztalataimat?
 V: Igen, meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) kapcsolatba léphet más felhasználókkal, kérdéseket tehet fel, és megoldásokat találhat kérdéseire.