---
title: Master MS Project Outline Masks with Aspose.Tasks
linktitle: Vázlatos maszkok gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti az MS Project gyűjteményvázlat-maszkjait az Aspose.Tasks for .NET használatával. Növelje a termelékenységet ezzel az átfogó oktatóanyaggal.
type: docs
weight: 15
url: /hu/net/outline-code-page-settings/outline-mask-collection/
---
## Bevezetés
Ki szeretné használni a Microsoft Project körvonalmaszkjainak erejét az Aspose.Tasks for .NET segítségével? Jó helyre jöttél! Ebben az átfogó oktatóanyagban lépésről lépésre végigvezetjük a folyamaton, biztosítva, hogy alaposan megértse, hogyan lehet hatékonyan kezelni a körvonalmaszkokat a projektekben. Akár tapasztalt fejlesztő, akár csak most kezdi, ez az útmutató felvértezi a munkafolyamat optimalizálásához szükséges ismeretekkel és készségekkel.
## Előfeltételek
Mielőtt belevágna ebbe az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
### 1. Az Aspose.Tasks telepítése .NET-hez
 Győződjön meg arról, hogy az Aspose.Tasks for .NET telepítve van a fejlesztői környezetében. A könyvtár letölthető az Aspose webhelyéről[itt](https://releases.aspose.com/tasks/net/).
### 2. C# és .NET Framework alapismeretek
Ismerkedjen meg a C# programozási nyelvvel és a .NET-keretrendszerrel, mivel ez az oktatóanyag mindkettőt felhasználja.
### 3. Microsoft Project File
Készítsen egy Microsoft Project-fájlt (MPP) tesztelési célokra. Használhat meglévő fájlt, vagy létrehozhat egy újat a kísérletezéshez.
## Névterek importálása
Kezdjük a szükséges névterek importálásával a C# projektbe. Ez a lépés biztosítja, hogy hozzáférjen az Aspose.Tasks for .NET által biztosított szükséges osztályokhoz és funkciókhoz.

Adja hozzá a következő névtereket a kódfájl elejéhez:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Most bontsuk fel a megadott példát több lépésre, és magyarázzuk el részletesen az egyes lépéseket:
## 1. lépés: Inicializálja a projektobjektumot
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Itt létrehozunk egy új példányt a`Project` osztályt, és töltsön be egy meglévő Microsoft Project fájlt, melynek neve "OutlineValues2010.mpp".
## 2. lépés: Hozzáférés az Outline kódokhoz
```csharp
var outline = project.OutlineCodes[0];
```
A vázlatkódokat a projektből érjük el. A vázlatkódok a Microsoft Project egyéni mezői, amelyek lehetővé teszik a feladatok kategorizálását és rendszerezését.
## 3. lépés: Tisztítsa meg a körvonalmaszkokat
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Ez a lépés biztosítja, hogy minden meglévő körvonalmaszk törlésre kerüljön a további folytatás előtt.
## 4. lépés: Készítsen körvonalmaszkokat
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Új körvonalmaszkokat hozunk létre, és meghatározzuk a típusukat. Ebben a példában létrehozunk egy érvényes körvonalmaszkot és egy rosszat.
## 5. lépés: Maszkok beszúrása és szerkesztése
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Itt rossz maszkot illesztünk be a gyűjteménybe, és módosítjuk a maszk hosszát az indexével.
## 6. lépés: Távolítsa el a maszkokat
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
A rossz maszkot eltávolítjuk a gyűjteményből az indexe alapján.
## 7. lépés: Ismételje meg a maszkokat
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Ez a ciklus a gyűjteményben lévő minden körvonalmaszkon áthalad, és kinyomtatja annak tulajdonságait, mint például a hossz, a szint, az elválasztó és a típus.
## 8. lépés: Maszkok másolása egy másik projektbe
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Végül átmásoljuk a vázlatmaszkokat egyik projektről a másikra, biztosítva a konzisztenciát a különböző projektek között.
## Következtetés
Gratulálunk! Sikeresen megtanulta az MS Project gyűjteményvázlat-maszkjainak kezelését az Aspose.Tasks for .NET használatával. Ha követi ezt az oktatóanyagot, most már rendelkezik azokkal a készségekkel, amelyekkel hatékonyan kezelheti a vázlatmaszkokat a projektekben, ami végső soron javítja a termelékenységet és a munkafolyamatot.
## GYIK
### 1. kérdés: Használhatom az Aspose.Tasks for .NET programot a Microsoft Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks for .NET támogatja a Microsoft Project fájlok különféle verzióit, beleértve az MPP, MPT és XML formátumokat.
### 2. kérdés: Az Aspose.Tasks for .NET kompatibilis a .NET Core-val?
V: Igen, az Aspose.Tasks for .NET kompatibilis a .NET Core programmal, így többplatformos alkalmazásokban is használható.
### 3. kérdés: Testreszabhatom a körvonalmaszkok tulajdonságait a projekt követelményei szerint?
V: Abszolút! A vázlatmaszkokat testreszabhatja a hosszuk, szintjük, elválasztójuk és típusuk beállításával az adott projekt igényei szerint.
### 4. kérdés: Az Aspose.Tasks for .NET biztosít dokumentációt és támogatást?
V: Igen, az Aspose.Tasks for .NET átfogó dokumentációt és dedikált támogatást kínál webhelyükön és[fórumok](https://forum.aspose.com/c/tasks/15).
### 5. kérdés: Elérhető ingyenes próbaverzió az Aspose.Tasks for .NET számára?
 V: Igen, elérheti az Aspose.Tasks ingyenes próbaverzióját a .NET-hez az ő webhelyükről[weboldal](https://releases.aspose.com/tasks/net/), hogy vásárlás előtt felfedezze a szolgáltatásait és funkcióit.