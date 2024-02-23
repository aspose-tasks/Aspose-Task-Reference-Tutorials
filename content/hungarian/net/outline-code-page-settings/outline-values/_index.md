---
title: Az MS Project Outline értékek elsajátítása az Aspose.Tasks segítségével
linktitle: Az Aspose.Tasks körvonalértékeinek kezelése
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az MS Project vázlatértékeit az Aspose.Tasks for .NET használatával. Könnyedén testreszabhatja a projekt körvonalait.
type: docs
weight: 16
url: /hu/net/outline-code-page-settings/outline-values/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan kezelheti a Microsoft Project vázlatértékeit a .NET Aspose.Tasks könyvtárával. Az Aspose.Tasks segítségével könnyedén módosíthatja a vázlatkódokat, új vázlatértékeket hozhat létre, és a projektvázlatokat igényei szerint testreszabhatja.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Az Aspose.Tasks for .NET telepítése: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
2. Fejlesztői környezet: Győződjön meg arról, hogy be van állítva egy fejlesztői környezet, például a Visual Studio, amely kompatibilis a .NET keretrendszerrel.
3. A C# programozás alapjai: Ismerkedjen meg a C# programozási nyelv alapjaival, mivel az Aspose.Tasks könyvtárral a C#-t fogjuk használni.

## Névterek importálása
Kezdje azzal, hogy importálja a szükséges névtereket a C# kódjába:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 1. lépés: Töltse be a projektfájlt
```csharp
// A dokumentumok könyvtárának elérési útja.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Ez a lépés inicializál egy új Project objektumot, és betölti a Microsoft Project fájlt a megadott könyvtárból.
## 2. lépés: Határozza meg az Outline Code definícióit
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Itt definiálunk két OutlineCodeDefinition objektumot, és hozzáadjuk őket a projekt OutlineCodes gyűjteményéhez.
## 3. lépés: Határozza meg a körvonalmaszkot
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Ez a lépés beállít egy OutlineMask-ot a vázlatkód meghatározásához.
## 4. lépés: Vázlati értékek létrehozása
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
Ebben a lépésben létrehozunk két OutlineValue objektumot, és beállítjuk a tulajdonságaikat, például az értéket, az értékazonosítót, a típust, a leírást és az összecsukási állapotot.

## Következtetés
Az MS Project vázlatértékeinek kezelése az Aspose.Tasks for .NET használatával a biztosított funkciókkal egyszerű. Az ebben az oktatóanyagban vázolt lépések követésével hatékonyan manipulálhatja a vázlatkódokat és értékeket a projektvázlatok igényeinek megfelelő testreszabásához.
## GYIK
### K: Használhatom az Aspose.Tasks-t más .NET-keretrendszerekkel?
V: Igen, az Aspose.Tasks kompatibilis a különböző .NET-keretrendszerekkel, rugalmasságot biztosítva a fejlesztői környezetben.
### K: Elérhető az Aspose.Tasks próbaverziója?
 V: Igen, elérheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### K: Hogyan kaphatok támogatást az Aspose.Tasks-hoz?
 V: Támogatásért és segítségért keresse fel az Aspose.Tasks fórumot.[itt](https://forum.aspose.com/c/tasks/15).
### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks számára?
 V: Igen, vásárolhat ideiglenes licencet az Aspose.Tasks számára a következőtől:[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol találom az Aspose.Tasks részletes dokumentációját?
 V: Tekintse meg a rendelkezésre álló átfogó dokumentációt[itt](https://reference.aspose.com/tasks/net/).