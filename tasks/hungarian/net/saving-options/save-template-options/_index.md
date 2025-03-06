---
title: Mentse az MS Project fájlokat sablonként az Aspose.Tasks segítségével
linktitle: Mentse az Aspose.Tasks sablonopcióit
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan mentheti a Microsoft Project fájlokat sablonként az Aspose.Tasks for .NET segítségével. Szabja testre a sablonbeállításokat az egyszerűsített projektkezelés érdekében.
weight: 18
url: /hu/net/saving-options/save-template-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mentse az MS Project fájlokat sablonként az Aspose.Tasks segítségével

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a sablonok Aspose.Tasks for .NET használatával mentésének folyamatát. A sablonok hasznosak a projektstruktúrák és beállítások szabványosításához a jövőbeni felhasználáshoz. Bemutatjuk, hogyan menthetünk el egy projektet sablonként, miközben menet közben hangoljuk a tulajdonságait.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Aspose.Tasks for .NET Library: Győződjön meg arról, hogy az Aspose.Tasks for .NET könyvtár telepítve van. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
2. C# programozás ismerete: A megadott kódrészletek megértéséhez és megvalósításához alapvető C# programozási ismeretek szükségesek.
3. Microsoft Project File: Készítsen egy Microsoft Project fájlt (MPP formátum), amelyet sablonként szeretne menteni.

## Névterek importálása
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 1. lépés: Töltse be a projektet
Először is be kell töltenünk a Microsoft Project fájlt (.mpp), amelyet sablonként szeretnénk menteni.
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 2. lépés: Szerezze be a projektfájl adatait
Információk lekérése a betöltött projektfájlról, például a formátuma.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## 3. lépés: Konfigurálja a Sablon mentése opciókat
Hozzon létre sablonmentési beállításokat, és állítsa be tulajdonságait igényei szerint. Ezekkel a beállításokkal testreszabhatja, hogy milyen adatokat távolítson el a sablonból.
```csharp
var options = new SaveTemplateOptions
{
	// Távolítsa el az összes fix költséget a projektsablonból
	RemoveFixedCosts = true,
	// Távolítsa el az összes tényleges értéket a projektsablonból
	RemoveActualValues = true,
	// Távolítsa el az erőforrás-arányokat a projektsablonból
	RemoveResourceRates = true,
	// Távolítsa el az összes alapértéket a projektsablonból
	RemoveBaselineValues = true
};
```
## 4. lépés: Projekt mentése sablonként
Mentse el a projektet sablonként a megadott beállításokkal.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## 5. lépés: Szerezze be a sablonfájl adatait
Információk lekérése a mentett sablonfájlról, például a formátumáról.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Gratulálunk! Sikeresen mentett egy sablont az Aspose.Tasks for .NET segítségével, és szükség szerint testreszabta a tulajdonságait.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan menthetünk el egy Microsoft Project fájlt sablonként az Aspose.Tasks for .NET segítségével. A sablonok értékesek a projektstruktúrák és -beállítások szabványosításához, valamint a jövőbeni projektalkotások egyszerűsítéséhez.
## GYIK
### K: Testreszabhatom, hogy mely adatokat távolítsa el a sablonból?
V: Igen, beállíthatja a Sablon mentési beállításait bizonyos adatok, például fix költségek, tényleges értékek, erőforrás-arányok és alapértékek eltávolítására.
### K: Az Aspose.Tasks for .NET kompatibilis a Microsoft Project összes verziójával?
V: Az Aspose.Tasks for .NET kiterjedt kompatibilitást biztosít a Microsoft Project különféle verzióival, biztosítva a zökkenőmentes integrációt és funkcionalitást.
### K: Alkalmazhatok sablonokat meglévő projektekre?
V: Igen, alkalmazhat sablonokat meglévő projektekre, ha betölti a sablonfájlt, és szükség szerint egyesíti az aktuális projekttel.
### K: Az Aspose.Tasks for .NET támogatja a platformok közötti fejlesztést?
V: Az Aspose.Tasks for .NET elsősorban Windows platformon futó .NET-keretrendszer-alkalmazásokhoz készült.
### K: Elérhető technikai támogatás az Aspose.Tasks for .NET számára?
 V: Igen, kérhet technikai segítséget és útmutatást az Aspose.Tasks közösségtől[fórumok](https://forum.aspose.com/c/tasks/15)vagy forduljon közvetlenül a támogatási csapatukhoz.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
