---
title: MS Project Legends konfigurálása az Aspose.Tasks-ban
linktitle: Az oldalmagyarázat konfigurálása az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan konfigurálhat MS Project oldaljelmagyarázatokat .NET-ben az Aspose.Tasks segítségével a hatékony projektkezelés érdekében. Lépésről lépésre bemutatott útmutató.
weight: 18
url: /hu/net/outline-code-page-settings/page-legend/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Legends konfigurálása az Aspose.Tasks-ban

## Bevezetés
A .NET fejlesztés területén a feladatok hatékony kezelése kulcsfontosságú, különösen a projektmenedzsment terén. Az Aspose.Tasks for .NET hatékony eszközként jelenik meg, amely számos funkciót kínál a feladatkezelési folyamatok egyszerűsítésére. Az egyik ilyen funkció az MS Project oldalak jelmagyarázatainak konfigurálása, így a felhasználók értékes betekintést nyerhetnek a projektadatok bemutatásába.
## Előfeltételek
Mielőtt belevágna az MS Project oldaljelmagyarázatainak konfigurálásába az Aspose.Tasks for .NET használatával, győződjön meg arról, hogy teljesülnek a következő előfeltételek:
1. Telepítés: Telepítse az Aspose.Tasks for .NET programot a fejlesztői környezetébe. Letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
2. Alapvető ismeretek a .NET-ről: Ismerkedjen meg a .NET-fejlesztés alapjaival, beleértve a projektek beállítását és a névterekkel való munkát.
3. Fejlesztési környezet: Használjon integrált fejlesztői környezetet (IDE), például a Visual Studio-t a zökkenőmentes kódolási élmény érdekében.
4. Projektfájl: Készítsen egy Microsoft Project fájlt (MPP) a kísérletezésre.

## Névterek importálása
A .NET-projektben importálja a szükséges névtereket az Aspose.Tasks for .NET által biztosított funkciók eléréséhez.
1. Projekt megnyitása: Indítsa el .NET-projektjét a kívánt IDE-ben.
2. Névterek importálása: A kódfájl elején importálja a szükséges névtereket:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Bontsuk le a példát lépésről lépésre útmutató formátumra, hogy átfogóan megértsük az MS Project oldalak jelmagyarázatainak konfigurálását az Aspose.Tasks for .NET használatával.

## 1. lépés: Adja meg a dokumentumkönyvtárat
Állítsa be a dokumentumkönyvtár elérési útját, ahol a Microsoft Project fájl található.

```csharp
String DataDir = "Your Document Directory";
```
## 2. lépés: Töltse be a projektet
 Inicializálja a`Project` osztályba a Microsoft Project fájl betöltésével.

```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
## 3. lépés: Olvassa el az oldalmagyarázat információit
Az oldal jelmagyarázatának elérése a projekt alapértelmezett nézetéből.

```csharp
var legend = project.DefaultView.PageInfo.Legend;
```
## 4. lépés: Jelmagyarázat információk megjelenítése
Adja meg a jelmagyarázat részleteit, például bal oldali szöveget, bal oldali képet, középre igazított szöveget, középre helyezett képet, jobb oldali szöveget, jobb oldali képet, jelmagyarázat állapotát és szélességét.

```csharp
Console.WriteLine("Legend left text: {0} ", legend.LeftText);
Console.WriteLine("Legend left image: {0} ", legend.LeftImage);
Console.WriteLine("Legend center text: {0} ", legend.CenteredText);
Console.WriteLine("Legend center image: {0} ", legend.CenteredImage);
Console.WriteLine("Legend right text: {0} ", legend.RightText);
Console.WriteLine("Legend right image: {0} ", legend.RightImage);
Console.WriteLine("Legend On: {0} ", legend.LegendOn);
Console.WriteLine("Legend Width: {0} ", legend.Width);
```
## 5. lépés: Módosítsa a jelmagyarázatot
Ha szükséges, módosítsa a jelmagyarázatot. Ebben a példában a bal oldali szöveget változtatjuk meg.

```csharp
legend.LeftText = "New Left Text";
```
## 6. lépés: Mentse el a változtatásokat
Mentse el a projektfájlban végzett módosításokat.

```csharp
project.Save(DataDir + "WorkWithPageLegend_out.mpp", SaveFileFormat.Mpp);
```

## Következtetés
Összefoglalva, az MS Project oldalak jelmagyarázatainak konfigurációjának elsajátítása az Aspose.Tasks for .NET használatával jelentősen javíthatja a projektkezelési képességeket a .NET ökoszisztémán belül. A vázolt lépések és előfeltételek követésével a fejlesztők zökkenőmentesen integrálhatják ezt a funkciót projektjeikbe, biztosítva a projektadatok jobb megjelenítését és értelmezését.
## GYIK
### K: Használhatom az Aspose.Tasks for .NET-et más .NET-keretrendszerekkel?
V: Igen, az Aspose.Tasks for .NET kompatibilis a különböző .NET-keretrendszerekkel, rugalmasságot és alkalmazkodóképességet biztosítva a különböző projektkövetelmények között.
### K: Elérhető az Aspose.Tasks próbaverziója .NET-hez?
 V: Igen, elérheti az ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/), amely lehetővé teszi, hogy vásárlás előtt felfedezze szolgáltatásait.
### K: Vannak korlátozások az Aspose.Tasks for .NET ideiglenes licenceinek használatakor?
V: Az ideiglenes licencek teljes hozzáférést biztosítanak az Aspose.Tasks-hoz a .NET-funkciókhoz, de időkorlátos. Alkalmasak rövid távú projektekre vagy értékelési célokra.
### K: Testreszabhatom az oldal jelmagyarázatait a megadott példán túl?
V: Természetesen az Aspose.Tasks for .NET kiterjedt testreszabási lehetőségeket kínál, amelyek lehetővé teszik az oldalak jelmagyarázatainak testreszabását az adott projekt követelményei szerint.
### K: Hol találok támogatást vagy közösségi fórumokat az Aspose.Tasks for .NET-hez?
 V: Támogatást kérhet, és kapcsolatba léphet a közösséggel a webhelyen[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15), ahol válaszokat találhat kérdéseire, és kapcsolatba léphet más fejlesztőkkel.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
