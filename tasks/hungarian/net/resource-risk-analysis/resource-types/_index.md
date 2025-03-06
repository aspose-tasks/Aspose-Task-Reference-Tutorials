---
title: Az Aspose.Tasks erőforrásainak típusai
linktitle: Az Aspose.Tasks erőforrásainak típusai
second_title: Aspose.Tasks .NET API
description: Az Aspose.Tasks for .NET alkalmazásban megtanulhatja, hogyan dolgozhat különböző típusú erőforrásokkal, beleértve a munka-, anyag- és költségforrásokat, egy lépésről lépésre bemutatott oktatóanyag segítségével.
weight: 14
url: /hu/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az Aspose.Tasks erőforrásainak típusai

## Bevezetés
Az Aspose.Tasks for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak Microsoft Project fájlokkal. Függetlenül attól, hogy feladatokat, erőforrásokat vagy ütemezéseket kezel, az Aspose.Tasks leegyszerűsíti a folyamatot azáltal, hogy átfogó API-készletet biztosít. Ebben az oktatóanyagban az Aspose.Tasks for .NET használatával projektjei során felhasználható különböző típusú erőforrásokba fogunk belemenni.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Visual Studio: Telepítse a Visual Studio-t, amely egy hatékony integrált fejlesztői környezet (IDE) .NET-fejlesztéshez.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
3. C# alapismeretek: Ismerkedjen meg a C#-val, a .NET fejlesztéshez használt programozási nyelvvel.

## Névterek importálása
Először is importáljuk a szükséges névtereket az Aspose.Tasks for .NET funkcióinak eléréséhez:
```csharp
    
```

## 1. lépés: Hozzon létre egy új projektpéldányt
```csharp
var project = new Project();
```
Ez a sor inicializál egy új Project objektumot, amely a projekttel kapcsolatos összes adat és művelet tárolójaként szolgál.
## 2. lépés: Munkaerőforrás hozzáadása
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Itt létrehozunk egy új munkaerőforrást "Work Resource" néven, és a típusát ResourceType.Work néven adjuk meg.
## 3. lépés: Anyagforrás hozzáadása
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Ez a lépés hozzáad egy "Material Resource" nevű anyagerőforrást, amelynek típusa ResourceType.Material. Ezenkívül az anyagcímkét "kg"-ként adjuk meg a mértékegység jelzésére.
## 4. lépés: Költségforrás hozzáadása
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Végül hozzáadunk egy „Költségforrás” nevű költségforrást, és a típusát ResourceType.Cost néven állítjuk be. Ezenkívül a költségértéket 59,99-re állítottuk be, ami az erőforráshoz társított pénzbeli értéket jelenti.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan dolgozhatunk különböző típusú erőforrásokkal az Aspose.Tasks for .NET-ben, beleértve a munka-, anyag- és költségforrásokat. A lépésenkénti útmutató követésével hatékonyan kezelheti a projektek erőforrásait programozottan.
## GYIK
### K: Használhatom az Aspose.Tasks for .NET-et más projektmenedzsment szoftverformátumokkal?
V: Igen, az Aspose.Tasks különféle formátumokat támogat, beleértve a Microsoft Projectet (MPP), a Primavera P6-ot és egyebeket.
### K: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET számára?
 V: Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### K: Hogyan kaphatok technikai támogatást az Aspose.Tasks for .NET-hez?
 V: Látogassa meg az Aspose.Tasks fórumot[itt](https://forum.aspose.com/c/tasks/15) technikai segítségért.
### K: Vásárolhatok ideiglenes licencet az Aspose.Tasks for .NET számára?
 V: Igen, vásárolhat ideiglenes licencet[itt](https://purchase.aspose.com/temporary-license/).
### K: Az Aspose.Tasks for .NET tartalmaz dokumentációt referenciaként?
 V: Igen, megtalálja a dokumentációt[itt](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
