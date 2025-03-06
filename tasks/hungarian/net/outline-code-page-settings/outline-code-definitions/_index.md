---
title: Az MS Project Outline kódkezelési definíciói az Aspose.Tasks-ban
linktitle: Outline Code definíciók kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti az MS Project vázlatkód-definícióit az Aspose.Tasks for .NET segítségével, amely felhatalmazza projektmenedzsment alkalmazásait.
weight: 12
url: /hu/net/outline-code-page-settings/outline-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az MS Project Outline kódkezelési definíciói az Aspose.Tasks-ban

## Bevezetés
Microsoft Project egy hatékony eszköz a projektek kezelésére, és az Aspose.Tasks for .NET átfogó támogatást nyújt a projektfájlok programozott kezeléséhez. A projektmenedzsment egyik lényeges szempontja a feladatok vázlatkódok segítségével történő megszervezése. Ebben az oktatóanyagban megvizsgáljuk, hogyan kezeljük az MS Project vázlatkód-definícióit az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt belevágnánk a megvalósításba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. Az Aspose.Tasks telepítése .NET-hez
 Győződjön meg arról, hogy az Aspose.Tasks for .NET telepítve van a fejlesztői környezetében. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
### 2. A C# és a .NET-keretrendszer alapvető ismerete
Ismerkedjen meg a C# programozási nyelvvel és a .NET keretrendszerrel, mivel ez az oktatóanyag középszintű C# ismereteket igényel.
### 3. Integrált fejlesztési környezet (IDE)
A kódoláshoz és a hibakereséshez telepítsen egy IDE-t, például a Visual Studio-t.
## Névterek importálása
A kódolás megkezdése előtt importáljuk a szükséges névtereket az Aspose.Tasks for .NET használatához.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Most bontsuk le a megadott példát több lépésre a világos megértés érdekében.
## 1. lépés: Töltse be a projektfájlt
Először is be kell töltenünk az MS Project fájlt az alkalmazásunkba.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 2. lépés: Készítsen vázlatkód-definíciót
Most hozzunk létre egy új vázlatkód-definíciót.
```csharp
var outline = new OutlineCodeDefinition();
```
## 3. lépés: Állítsa be a mező számát és nevét
Állítsa be a mező számát és nevét a körvonalkódhoz.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## 4. lépés: Állítsa be a GUID-t és az egyéb tulajdonságokat
Állítsa be a GUID-t és a vázlatkód egyéb tulajdonságait.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## 5. lépés: Adja hozzá a körvonalmaszkot
Adjon hozzá egy körvonalmaszkot a vázlatkódhoz.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## 6. lépés: Állítsa be az Egyéb tulajdonságokat
Állítsa be a vázlatkód további tulajdonságait.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## 7. lépés: Környezeti érték hozzáadása
Végül adjunk hozzá egy vázlatértéket a vázlatkódhoz.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell kezelni az MS Project vázlatkód-definícióit az Aspose.Tasks for .NET használatával. A lépésenkénti útmutató követésével hatékonyan kezelheti a projektfájlok vázlatkódjait programozottan.
## GYIK
### 1. kérdés: Használhatom az Aspose.Tasks for .NET-et az MS Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks for .NET támogatja az MS Project fájlok különféle verzióit, beleértve az MPP és XML formátumokat.
### 2. kérdés: Az Aspose.Tasks for .NET kompatibilis a .NET Core-val?
V: Igen, az Aspose.Tasks for .NET kompatibilis a .NET Core-al, lehetővé téve többplatformos alkalmazások fejlesztését.
### 3. kérdés: Módosíthatom az erőforrás-hozzárendeléseket az Aspose.Tasks for .NET használatával?
V: Igen, az Aspose.Tasks for .NET kiterjedt szolgáltatásokat kínál az erőforrás-hozzárendelések kezeléséhez, beleértve a hozzárendelések hozzáadását, frissítését és eltávolítását.
### 4. kérdés: Az Aspose.Tasks for .NET támogatja az egyéni mezők olvasását az MS Project fájlokból?
V: Az Aspose.Tasks for .NET természetesen támogatja az egyéni mezők, köztük a vázlatkódok olvasását és írását az MS Project fájlokból.
### 5. kérdés: Létezik közösségi fórum az Aspose.Tasks for .NET számára?
 V: Igen, csatlakozhat az Aspose.Tasks for .NET közösségi fórumához[itt](https://forum.aspose.com/c/tasks/15) kérdéseket feltenni, tudást megosztani és együttműködni más fejlesztőkkel.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
