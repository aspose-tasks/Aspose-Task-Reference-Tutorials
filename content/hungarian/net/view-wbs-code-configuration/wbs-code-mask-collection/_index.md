---
title: A WBS kódmaszkok elsajátítása az Aspose.Tasks segítségével .NET-hez
linktitle: WBS kódmaszkok gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Javítsa a projektmenedzsmentet az Aspose.Tasks for .NET segítségével. Ebben az átfogó oktatóanyagban tanulja meg a WBS kódmaszkok könnyű létrehozását, kezelését és átvitelét.
type: docs
weight: 15
url: /hu/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Bevezetés
projektmenedzsment dinamikus világában kulcsfontosságú a feladatok hatékony megszervezése. Az Aspose.Tasks for .NET hatékony megoldást kínál a projektmunka lebontási struktúra (WBS) kódjainak könnyed kezelésére. Ebben az oktatóanyagban a WBS kódmaszkok gyűjteményével foglalkozunk, és megvizsgáljuk, hogyan valósíthatjuk meg és kezelhetjük őket az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt nekivágnánk ennek a kódolási útnak, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- C# programozási nyelv gyakorlati ismerete.
-  Aspose.Tasks for .NET telepítve van a fejlesztői környezetben. Ha nem, töltse le[itt](https://releases.aspose.com/tasks/net/).
- Egy kódszerkesztő, mint a Visual Studio a zökkenőmentes kódolási élményért.
## Névterek importálása
A kezdéshez importáljuk a szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Inicializálja a projekt és a WBS kóddefiníciót
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Határozza meg a WBS kódmaszkokat
Törölje a meglévő kódmaszkokat, és adjon hozzá újakat:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. A kódmaszkok információinak megjelenítése
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Adjon hozzá feladatokat a projekthez
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. A feladat információinak lekérése
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Kódmaszkok kezelése
Távolítsa el a kódmaszkot, és győződjön meg róla, hogy eltávolította:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Másolja a kódmaszkokat egy másik projektbe
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Kódmaszkok megjelenítése egy másik projektben
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Adjon hozzá feladatokat a másik projekthez
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Jelenítse meg a WBS kódokat az Egyéb projektben
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Következtetés
Az Aspose.Tasks for .NET segítségével a WBS-kódok kezelése egyszerű feladattá válik. Ez az oktatóanyag a WBS kódmaszkok létrehozásával, manipulálásával és átvitelével foglalkozott, és átfogó útmutatót ad a projektmenedzsment tapasztalatainak javításához.
## GYIK
### K: Használhatom az Aspose.Tasks for .NET programot más programozási nyelvekkel?
V: Az Aspose.Tasks elsősorban a .NET nyelveket támogatja, de felfedezheti a más nyelvekkel való együttműködési lehetőségeket.
### K: Elérhető az Aspose.Tasks próbaverziója .NET-hez?
 V: Igen, letöltheti a próbaverziót.[itt](https://releases.aspose.com/).
### K: Hogyan kérhetek segítséget vagy jelenthetem be az Aspose.Tasks for .NET-hez kapcsolódó problémákat?
 V: Látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) támogatásért és megbeszélésekért.
### K: Mi a WBS kódok célja a projektmenedzsmentben?
V: A WBS kódok segítenek a projektfeladatok hierarchikus megszervezésében és felépítésében, szisztematikus megközelítést biztosítva a projekttervezéshez.
### K: Testreszabhatom a WBS-kódok formátumát az Aspose.Tasks for .NET-ben?
V: Az Aspose.Tasks for .NET használatával teljes mértékben Ön szabályozhatja a WBS-kódok formátumát és szerkezetét.