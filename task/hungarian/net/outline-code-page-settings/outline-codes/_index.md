---
title: projektvázlat kódjainak kezelése az Aspose.Tasks for .NET-ben
linktitle: Outline kódok kezelése az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Ismerje meg az MS Project vázlatkódjainak kezelését az Aspose.Tasks for .NET segítségével. Egyszerűsítse a projektszervezést könnyedén.
type: docs
weight: 10
url: /hu/net/outline-code-page-settings/outline-codes/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan kezelheti a Microsoft Project vázlatkódjait az Aspose.Tasks for .NET használatával. A vázlatkódok olyan egyéni mezők a Microsoft Projectben, amelyek lehetővé teszik a felhasználók számára, hogy meghatározott feltételek szerint kategorizálják és rendezzék a feladatokat. Az Aspose.Tasks leegyszerűsíti ezen vázlatkódok programozott olvasásának és kezelésének folyamatát.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Aspose.Tasks for .NET Library: Töltse le és telepítse az Aspose.Tasks for .NET könyvtárat a[weboldal](https://releases.aspose.com/tasks/net/).
2. Fejlesztői környezet: Állítson be megfelelő fejlesztői környezetet a .NET programozáshoz, például a Visual Studio-t.
3. Alapvető C# ismerete: A C# programozási nyelv ismerete előnyös lesz a kódpéldák megértéséhez.

## Névterek importálása
A kezdéshez importálnia kell a szükséges névtereket a C# projektbe. Ez lehetővé teszi az Aspose.Tasks könyvtár által biztosított osztályok és metódusok elérését.
1. Visual Studio megnyitása: Indítsa el a Visual Studio IDE-jét.
2. Új projekt létrehozása: Indítson el egy új C#-projektet, vagy nyisson meg egy meglévőt, ahol az Aspose.Tasks-t kívánja használni.
3. Aspose.Tasks Referencia hozzáadása: Kattintson jobb gombbal a projektre a Solution Explorerben, válassza a „NuGet-csomagok kezelése” lehetőséget, keresse meg az „Aspose.Tasks” kifejezést, és telepítse a legújabb verziót.
4. Aspose.Tasks névtér importálása: A C#-fájl tetején direktíva használatával adja hozzá a következőket:
```csharp
using Aspose.Tasks;
using System;

```
## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először állítsa be az MS Project fájlt tartalmazó könyvtár elérési útját.
```csharp
String DataDir = "Your Document Directory";
```
 Cserélje ki`"Your Document Directory"` a projektfájl tényleges elérési útjával.
## 2. lépés: Töltse be a projektfájlt
 Példányosítson egy újat`Project` objektumot az MS Project fájl betöltésével.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Ez inicializálja a projektobjektumot a megadott fájllal.
## 3. lépés: Olvassa el a vázlatkódokat
Ismételje meg a projekt összes feladatát, és kérje le a vázlatkódjaikat.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Ez a kódrészlet végigfut az egyes feladatokon, ellenőrzi, hogy vannak-e vázlatkódjai, és kinyomtat olyan részleteket, mint a mezőazonosító, az értékazonosító és az értékazonosító a feladathoz társított minden egyes vázlatkódhoz.

## Következtetés
Összefoglalva, az Aspose.Tasks for .NET hatékony lehetőségeket biztosít a Microsoft Project vázlatkódjainak programozott kezeléséhez. Az ebben az oktatóanyagban vázolt lépések követésével hatékonyan olvashatja és kezelheti az MS Project fájljaiban lévő vázlatkódokat a C# használatával.
## GYIK
### K: Módosíthatom a vázlatkódokat az Aspose.Tasks segítségével?
V: Igen, a vázlatkódokat programozottan módosíthatja az Aspose.Tasks for .NET használatával. Egyszerűen csak hozzáférhet a feladatok vázlatos kódjaihoz, és szükség szerint frissítheti az értékeket.
### K: Az Aspose.Tasks kompatibilis a Microsoft Project összes verziójával?
V: Az Aspose.Tasks a Microsoft Project verziók széles skáláját támogatja, beleértve a 2003-as, 2007-es, 2010-es, 2013-as, 2016-os és 2019-es verziókat.
### K: Az Aspose.Tasks licencet igényel kereskedelmi használatra?
V: Igen, az Aspose.Tasks kereskedelmi használatához érvényes licenc szükséges. A licencet az Aspose webhelyéről szerezheti be.
### K: Kipróbálhatom az Aspose.Tasks-t vásárlás előtt?
V: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a webhelyről, hogy értékelje szolgáltatásait és képességeit.
### K: Hol kaphatok támogatást az Aspose.Tasks-hoz?
 V: Támogatást kaphat az Aspose.Tasks-hoz, ha felkeresi a fórumot a címen[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).## Teljes forráskód