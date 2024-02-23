---
title: MS Project fájlok mentése különböző formátumokban az Aspose.Tasks programban
linktitle: Fájlok mentése különböző formátumokban az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan mentheti az MS Project fájlokat különböző formátumokban az Aspose.Tasks for .NET segítségével. Egyszerű lépések a hatékony projektmenedzsmenthez.
type: docs
weight: 17
url: /hu/net/rate-recurring-tasks/save-file-formats/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan mentheti a Microsoft Project fájlokat különböző formátumokban az Aspose.Tasks for .NET segítségével. Az Aspose.Tasks egy hatékony API, amely lehetővé teszi a fejlesztők számára a projektfájlok programozott kezelését és kezelését.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET webhelyet innen[itt](https://releases.aspose.com/tasks/net/).
2. Fejlesztői környezet: .NET fejlesztői környezet beállítása, például a Visual Studio.
3. A C# alapvető ismerete: A C# programozási nyelv ismerete előnyös lesz.

## Névterek importálása
Ügyeljen arra, hogy importálja a szükséges névtereket a C# fájl elejére:
```csharp

using Aspose.Tasks.Saving;
```
## 1. lépés: Hozzon létre egy projektobjektumot
Először hozzon létre egy Project objektumot, és töltse be a Microsoft Project fájlt.
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## 2. lépés: Projekt mentése CSV formátumban
Most mentsük el a projektet CSV formátumban. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## 3. lépés: Fedezzen fel más formátumokat
 Az Aspose.Tasks különféle formátumokat támogat a projektfájlok mentéséhez, például XML, PDF, XLSX stb. Ezeket a formátumokat egyszerűen módosíthatja a`SaveFileFormat` paramétereket a`Save` módszer.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Az alábbi lépések követésével könnyedén mentheti a Microsoft Project fájlokat különböző formátumokban az Aspose.Tasks for .NET segítségével.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet MS Project fájlokat menteni különböző formátumokban az Aspose.Tasks for .NET segítségével. Az Aspose.Tasks leegyszerűsíti a projektfájlok programozott kezelésének folyamatát, rugalmasságot és hatékonyságot kínálva a fejlesztőknek.
## GYIK
### K: Az Aspose.Tasks kompatibilis a Microsoft Project összes verziójával?
V: Az Aspose.Tasks támogatja a Microsoft Project 2003 XML, a Microsoft Project 2007 MPP és a Microsoft Project 2010 MPP formátumokat.
### K: Kipróbálhatom az Aspose.Tasks-t vásárlás előtt?
 V: Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### K: Hogyan kaphatok támogatást az Aspose.Tasks-hoz?
 V: Támogatást kaphat az Aspose.Tasks közösségi fórumon.[itt](https://forum.aspose.com/c/tasks/15).
### K: Rendelkezésre állnak ideiglenes licencek az Aspose.Tasks számára?
 V: Igen, ideiglenes licencek állnak rendelkezésre értékelési célokra. Kaphatsz egyet[itt](https://purchase.aspose.com/temporary-license/).
### K: Mi az Aspose.Tasks ára?
 V: Az árakkal kapcsolatos információk az Aspose.Tasks vásárlási oldalán találhatók[itt](https://purchase.aspose.com/buy).