---
title: Az MS Project megjelenítési beállításainak konfigurálása az Aspose.Tasks-ban
linktitle: Projektmegjelenítési beállítások konfigurálása az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan konfigurálhatja programozottan az MS Project megjelenítési beállításait az Aspose.Tasks for .NET használatával. Könnyedén testreszabhatja projektje megjelenését.
type: docs
weight: 17
url: /hu/net/project-management-integration/project-display-options/
---
## Bevezetés
Microsoft Project számos megjelenítési lehetőséget kínál a projekt megjelenésének testreszabásához. Az Aspose.Tasks for .NET robusztus keretrendszert biztosít ezen beállítások programozott kezeléséhez. Ebben az oktatóanyagban megvizsgáljuk, hogyan konfigurálhatjuk az MS Project megjelenítési beállításait az Aspose.Tasks segítségével.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Aspose.Tasks for .NET: Töltse le és telepítse a könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: rendelkezzen egy érvényes MS Project fájllal (.mpp) a megjelenítési beállítások alkalmazásához.
3. Alapszintű C# ismerete: C# programozási nyelv ismerete szükséges.

## Névterek importálása
Először is importálja a szükséges névtereket a C# kódjába:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 1. lépés: Töltse be a projektfájlt
 Töltse be az MS Project fájlt a`Project` Az Aspose által biztosított osztály. Feladatok:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 2. lépés: Konfigurálja a megjelenítési beállításokat
Most konfiguráljuk az MS Projectben elérhető különféle megjelenítési lehetőségeket:
### Feladatütemezési figyelmeztetések letiltása
A manuálisan ütemezett feladatokkal kapcsolatos ütemezési ütközésekre vonatkozó figyelmeztetések letiltása (Project 2010 és újabb verziókhoz):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Szóköz hozzáadása a címke előtt
Állítsa be, hogy szóközt adjon a számérték és az idő rövidítése előtt:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Állítsa be a címkekijelzőt az időegységekhez
Testreszabhatja a különböző időegységek megjelenítési módját:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Projektösszefoglaló feladat megjelenítése
Összefoglaló információk megjelenítése a teljes projektről egyetlen sorban:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Feladatütemezési javaslatok engedélyezése
Javaslatok megjelenítése a manuálisan ütemezett feladatokkal kapcsolatos ütközések ütemezésére vonatkozóan:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Húzza alá a hiperhivatkozásokat
A projekten belüli hiperhivatkozások aláhúzásának beállítása:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## 3. lépés: Mentse el a projektet
Végül mentse el a projektet az alkalmazott megjelenítési beállításokkal:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell konfigurálni az MS Project megjelenítési beállításait az Aspose.Tasks for .NET használatával. Ezekkel a képességekkel programozottan hatékonyan testreszabhatja projektfájljainak megjelenését.
## GYIK
### K: Alkalmazhatom ezeket a megjelenítési beállításokat csak meghatározott feladatokra?
V: Igen, az Aspose.Tasks API segítségével szelektíven alkalmazhatja a megjelenítési beállításokat az egyes feladatokra.
### K: Ezek a megjelenítési beállítások befolyásolják a mögöttes projektadatokat?
V: Nem, ezek a beállítások csak a projekt vizuális megjelenítését módosítják, és nem módosítják az alapul szolgáló adatokat.
### K: Kompatibilisek ezek a megjelenítési beállítások a Microsoft Project összes verziójával?
V: Nem, egyes beállítások az MS Project bizonyos verzióira vonatkozhatnak. A kompatibilitás részleteit a dokumentációban találja.
### K: Visszaállíthatom a megjelenítési beállításokat az alapértelmezett beállításokra?
V: Igen, az Aspose.Tasks API segítségével visszaállíthatja a megjelenítési beállításokat az alapértelmezett értékekre.
### K: Vannak korlátai a megjelenítési beállítások programozott testreszabásának?
V: Míg az Aspose.Tasks kiterjedt testreszabási lehetőségeket biztosít, előfordulhat, hogy bizonyos megjelenítési lehetőségek nem érhetők el programozottan az MS Project fájlformátumának korlátai miatt.