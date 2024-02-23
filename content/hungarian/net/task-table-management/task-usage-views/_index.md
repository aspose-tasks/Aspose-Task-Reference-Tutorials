---
title: Feladathasználati nézetek elsajátítása az Aspose.Tasks for .NET-ben
linktitle: Konfigurálja a Feladathasználati nézeteket az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Fedezze fel az Aspose.Tasks for .NET webhelyet, és tanulja meg, hogyan konfigurálhatja a feladathasználati nézeteket. Testreszabhatja az időbeosztás beállításait, és javíthatja projektmenedzsment látványvilágát.
type: docs
weight: 24
url: /hu/net/task-table-management/task-usage-views/
---
## Bevezetés
projektmenedzsment területén a feladatok használatának vizualizálása kulcsfontosságú a hatékony tervezés és végrehajtás szempontjából. Az Aspose.Tasks for .NET robusztus megoldást kínál a feladatok használati nézeteinek megjelenítésére, lehetővé téve az időskálás beállítások és a prezentációs formátumok testreszabását. Ebben az oktatóanyagban végigvezetjük a feladathasználati nézetek Aspose.Tasks használatával történő konfigurálásának lépéseit.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1.  Aspose.Tasks for .NET: Győződjön meg arról, hogy az Aspose.Tasks könyvtár integrálva van a .NET-projektbe. Letöltheti[itt](https://releases.aspose.com/tasks/net/).
2. .NET-környezet: Működő .NET-környezetet kell beállítani a gépen.
## Névterek importálása
A .NET-projektben importálja a szükséges névtereket az Aspose.Tasks funkciók eléréséhez. Adja hozzá a következő sorokat a kódhoz:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját
 Az Aspose.Tasks funkciók használata előtt állítsa be a dokumentumkönyvtár elérési útját. cserélje ki`"Your Document Directory"` a tényleges úttal.
```csharp
String DataDir = "Your Document Directory";
```
## 2. lépés: Töltse be a projektet
 Inicializálja az Aspose.Tasks-t`Project` objektumot a projektfájl (pl. TaskUsageView.mpp) betöltésével.
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## 3. lépés: Adja meg a mentési beállításokat
 Hozzon létre egy`SaveOptions`objektumot a megjelenítési beállítások megadásához. Állítsa az időskálát „Napok” értékre, a prezentáció formátumát pedig „TaskUsage” értékre.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## 4. lépés: Mentés a Days Timescale segítségével
Mentse el a projektet a „Napok” előre meghatározott időbeállításaival.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 5. lépés: Mentés ThirdsOfMonths időskálával
Módosítsa az időskála beállításait „Hónapok harmadára” és mentse a projektet.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 6. lépés: Mentés hónapos időskálával
Állítsa az időskálát „Hónapokra”, és mentse a projektet a frissített beállításokkal.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Következtetés
A feladathasználati nézetek konfigurálása az Aspose.Tasks for .NET segítségével egyszerű folyamat. Az időskála-beállítások testreszabásával személyre szabhatja a projektfeladatok megjelenítését sajátos igényei szerint.
 Nyugodtan fedezze fel a további funkciókat és funkciókat a[dokumentáció](https://reference.aspose.com/tasks/net/).
## Gyakran Ismételt Kérdések
### Testreszabhatom az időskálát az előre meghatározott beállításokon túl?
Igen, egyéni időskálát állíthat be az intervallumok és mértékegységek megadásával.
### Vannak más prezentációs formátumok?
Az Aspose.Tasks különféle prezentációs formátumokat támogat, beleértve a GanttChart, ResourceUsage és egyebeket.
### Az Aspose.Tasks kompatibilis a különböző projektfájlformátumokkal?
Igen, az Aspose.Tasks támogatja az olyan népszerű projektfájlformátumokat, mint az MPP, XML és CSV.
### Alkalmazhatok különböző időbeállításokat bizonyos feladatokhoz?
Természetesen személyre szabhatja az időskála beállításait az egyes feladatokhoz a projekten belül.
### Hogyan kaphatok támogatást vagy kérhetek segítséget az Aspose.Tasks számára?
 meglátogatni a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásért és útmutatásért.