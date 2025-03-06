---
title: Lépésről lépésre WBS-kód konfigurálása az Aspose.Tasks .NET-ben
linktitle: A WBS kódmaszkok konfigurálása az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Fedezze fel a WBS kódmaszkok konfigurálását lépésről lépésre .NET-projektekben az Aspose.Tasks használatával. Fokozza a projektmenedzsment képességeit erőfeszítés nélkül.
type: docs
weight: 14
url: /hu/net/view-wbs-code-configuration/wbs-code-masks/
---
## Bevezetés
Az Aspose.Tasks for .NET egy hatékony könyvtár, amely feljogosítja a fejlesztőket a projektmenedzsment adatok hatékony kezelésére a .NET-alkalmazásokban. Ebben az oktatóanyagban megvizsgáljuk a Work Breakdown Structure (WBS) kódmaszkok Aspose.Tasks használatával történő konfigurálásának folyamatát.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
-  Aspose.Tasks for .NET Library: Töltse le és telepítse a könyvtárat innen[Aspose.Tasks .NET-dokumentációhoz](https://reference.aspose.com/tasks/net/).
- Fejlesztői környezet: Győződjön meg arról, hogy be van állítva működő .NET fejlesztői környezet.
- Dokumentumkönyvtár: Válasszon ki egy könyvtárat a rendszeren a projektfájlok tárolására.
## Névterek importálása
A .NET-projektben adja meg az Aspose.Tasks használatához szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## 1. lépés: Hozzon létre egy projektpéldányt
Kezdje egy új projektpéldány létrehozásával:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 2. lépés: Határozza meg a WBS-kód definícióját
Állítsa be a WBS kóddefiníciót a projekthez:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 3. lépés: WBS kódmaszkok hozzáadása
Határozza meg a WBS kódmaszkokat, és adja hozzá őket a projekthez:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## 4. lépés: Hozzon létre feladatokat
Feladatok hozzáadása a projekthez:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## 5. lépés: Számolja újra
Számolja újra a projektet, hogy megbizonyosodjon a WBS kódok helyes alkalmazásáról:
```csharp
project.Recalculate();
```
## 6. lépés: Jelenítse meg a WBS maszk információit
Információk a WBS-maszkokról a konzolon:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## 7. lépés: Mentse el a projektet
Mentse el a projektet a hozzáadott WBS kódokkal:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Gratulálunk! Sikeresen konfigurálta a WBS kódmaszkokat az Aspose.Tasks projektben.
## Következtetés
Ebben az oktatóanyagban a WBS kódmaszkok Aspose.Tasks for .NET használatával történő konfigurálásának lépésről lépésre történő folyamatát vizsgáltuk meg. Ez a nagy teljesítményű könyvtár zökkenőmentes módot biztosít a fejlesztők számára a projektmenedzsment képességek fejlesztésére .NET-alkalmazásaikon belül.

## GYIK
### Használhatom ingyenesen az Aspose.Tasks-t?
 Az Aspose.Tasks ingyenes próbaverziót kínál, amelyet letölthet[itt](https://releases.aspose.com/).
### Hol találok további támogatást?
 Meglátogatni a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásért.
### Hogyan szerezhetek ideiglenes engedélyt?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Létezik részletes dokumentáció?
 Igen, a teljes dokumentáció rendelkezésre áll[itt](https://reference.aspose.com/tasks/net/).
### Hol vásárolhatom meg az Aspose.Tasks-t?
 Vásárolja meg az Aspose.Tasks-t[itt](https://purchase.aspose.com/buy).