---
title: A fejléc- és láblécinformációk kibontása az Aspose.Tasks segítségével
linktitle: Fejléc- és láblécinformációk az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg a fejléc- és láblécadatok kinyerését az MS Project fájlokból az Aspose.Tasks for .NET segítségével. Egyszerű, hatékony és fejlesztőbarát megoldás.
weight: 29
url: /hu/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A fejléc- és láblécinformációk kibontása az Aspose.Tasks segítségével

## Bevezetés
Az Aspose.Tasks for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára a Microsoft Project fájlok egyszerű kezelését. Ebben az oktatóanyagban megtanuljuk, hogyan lehet lekérni a fejléc- és lábléc-információkat az MS Project fájlokból az Aspose.Tasks segítségével.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Visual Studio: Telepítse a Visual Studio-t a rendszerére.
2.  Aspose.Tasks for .NET: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
3. C# alapismeretek: C# programozási nyelv ismerete.

## Névterek importálása
Először is importálnia kell a szükséges névtereket a C# projektbe. Ez lehetővé teszi az Aspose.Tasks könyvtár által biztosított osztályok és metódusok elérését.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 1. lépés: Inicializálja a projektobjektumot
 A kezdéshez inicializálnia kell a`Project` objektumot egy meglévő MS Project fájl betöltésével.
```csharp
// A dokumentumok könyvtárának elérési útja.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## 2. lépés: Fejléc és lábléc információk lekérése
 Miután betöltötte a projektfájlt, a fejléc- és láblécadatokat a`PageInfo` ingatlan.
```csharp
var info = project.DefaultView.PageInfo;
// Fejléc információk
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Lábléc információk
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Ezeket az egyszerű lépéseket követve könnyen lekérheti a fejléc- és lábléc-információkat az MS Project fájlokból az Aspose.Tasks for .NET segítségével.

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan lehet fejléc- és lábléc-információkat kinyerni az MS Project fájlokból az Aspose.Tasks for .NET segítségével. Ez a nagy teljesítményű könyvtár leegyszerűsíti a Project fájlokkal való munkát C# alkalmazásokban, és robusztus eszközöket biztosít a fejlesztőknek a manipulációhoz.
### GYIK
### Módosíthatom a fejléc- és láblécinformációkat az Aspose.Tasks segítségével?
Igen, a fejléc- és láblécinformációkat programozottan módosíthatja az Aspose.Tasks for .NET használatával.
### Az Aspose.Tasks támogat más projektfájlformátumokat is az MS Projecten kívül?
Igen, az Aspose.Tasks különféle projektfájlformátumokat támogat, beleértve az MPP-t, az XML-t és az MPX-et.
### Elérhető az Aspose.Tasks ingyenes próbaverziója?
 Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Tasks dokumentációját?
 Az Aspose.Tasks dokumentációját megtalálja[itt](https://reference.aspose.com/tasks/net/).
### Hogyan kaphatok támogatást az Aspose.Tasks programhoz?
 Támogatást kaphat az Aspose.Tasks-hoz, ha felkeresi a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
