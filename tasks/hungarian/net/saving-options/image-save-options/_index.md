---
title: Kép mentése MS Project Options for Aspose.Tasks
linktitle: Az Aspose.Tasks képmentési beállításai
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan mentheti az MS Project beállításait képként az Aspose.Tasks for .NET segítségével. Kövesse lépésenkénti útmutatónkat a zökkenőmentes integráció érdekében.
type: docs
weight: 11
url: /hu/net/saving-options/image-save-options/
---

## Bevezetés
A szoftverfejlesztés világában a projektfeladatok hatékony kezelése kulcsfontosságú a sikeres projektmenedzsmenthez. Az Aspose.Tasks for .NET hatékony megoldást kínál a Microsoft Project fájlokkal dolgozó fejlesztők számára, lehetővé téve számukra a projektfeladatok zökkenőmentes kezelését, konvertálását és kezelését .NET-alkalmazásaikon belül.
## Előfeltételek
Mielőtt belevágna az Aspose.Tasks for .NET használatába az MS Project beállításainak képként történő mentéséhez, győződjön meg arról, hogy a következő előfeltételek vannak:
### 1. Telepítse az Aspose.Tasks programot .NET-hez
 kezdéshez telepítenie kell az Aspose.Tasks for .NET programot a fejlesztői környezetébe. A könyvtár letölthető a[weboldal](https://releases.aspose.com/tasks/net/) és kövesse a mellékelt telepítési utasításokat.
### 2. Szerezzen engedélyt (opcionális)
 Míg az Aspose.Tasks for .NET licenc nélkül is használható kiértékelési módban, a teljes funkcionalitás és az értékelési korlátozások megszüntetése érdekében ajánlatos egy licenc beszerzése. Engedélyt szerezhet a[vásárlási oldal](https://purchase.aspose.com/buy) vagy válasszon a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) tesztelési célokra.
### 3. C# és .NET fejlesztési alapismeretek
A C# programozási nyelv és a .NET keretrendszer alapvető ismerete szükséges a példák követéséhez, és az Aspose.Tasks funkciók hatékony integrálásához az alkalmazásokba.
## Névterek importálása
Mielőtt elkezdenénk az Aspose.Tasks for .NET segítségével képként menteni az MS Project beállításait, győződjünk meg arról, hogy importáljuk a szükséges névtereket C# projektünkbe:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját
Győződjön meg arról, hogy rendelkezik egy kijelölt könyvtárral a dokumentumok számára, és ennek megfelelően állítsa be az elérési utat:
```csharp
String DataDir = "Your Document Directory";
```
## 2. lépés: Töltse be az MS Project fájlt
 Inicializáljon egy újat`Project` objektumot az MS Project fájl betöltésével:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 3. lépés: Adja meg a képmentési beállításokat
 Hozzon létre egy példányt a`ImageSaveOptions`és adja meg a kívánt beállításokat:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## 4. lépés: Adja meg a mentendő oldalakat
Ha szükséges, adja meg a menteni kívánt oldalakat. Ebben a példában a 2. oldalt adjuk hozzá:
```csharp
options.Pages.Add(2);
```
## 5. lépés: Mentse el a képet
Végül mentse a kiválasztott oldalakat képként a megadott opciókkal:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Következtetés
Az Aspose.Tasks for .NET leegyszerűsíti az MS Project fájlokkal való munkafolyamatot, lehetővé téve a fejlesztők számára, hogy könnyedén kezeljék a projektfeladatokat. Az oktatóanyagban ismertetett lépések követésével hatékonyan mentheti el az MS Project beállításait képként a .NET-alkalmazásaiban.
## GYIK
### 1. kérdés: Használhatom az Aspose.Tasks-t .NET-hez licenc nélkül?
V: Igen, az Aspose.Tasks for .NET licenc nélkül használható kiértékelési módban. Javasoljuk azonban, hogy szerezzen licencet a teljes funkcionalitáshoz, és távolítsa el a kiértékelési korlátozásokat.
### 2. kérdés: Hogyan szerezhetek ideiglenes licencet teszteléshez?
 V: Tesztelési célból ideiglenes licencet szerezhet be a webhelyen[ideiglenes licenc oldal](https://purchase.aspose.com/temporary-license/).
### 3. kérdés: Az Aspose.Tasks for .NET kompatibilis más .NET-keretrendszerekkel?
V: Igen, az Aspose.Tasks for .NET kompatibilis a különböző .NET-keretrendszerekkel, beleértve a .NET Core-t és a .NET Standard-t.
### 4. kérdés: Testreszabhatom a képmentési beállításokat?
V: Igen, testreszabhatja a képmentési beállításokat saját igényei szerint, például az oldalméret, a felbontás vagy a kimeneti formátum módosítása szerint.
### 5. kérdés: Hol találok támogatást az Aspose.Tasks for .NET-hez?
 V: Az Aspose.Tasks for .NET webhelyen támogatást és segítséget találhat[fórum](https://forum.aspose.com/c/tasks/15).