---
title: Feladathivatkozások kezelése az Aspose.Tasks-ban
linktitle: Feladathivatkozások kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel az Aspose.Tasks for .NET erejét a projektfeladat-hivatkozások hatékony kezelésében. Kövesse lépésről lépésre útmutatónkat, hogy javítsa projektmenedzsment-élményét.
weight: 19
url: /hu/net/task-table-management/task-link-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladathivatkozások kezelése az Aspose.Tasks-ban

## Bevezetés
Üdvözöljük az Aspose.Tasks for .NET feladathivatkozásainak kezeléséről szóló, lépésről lépésre szóló útmutatóban! A feladathivatkozások döntő szerepet játszanak a projektmenedzsmentben, lehetővé téve a feladatok közötti kapcsolatok létrehozását és függőségek létrehozását. Ebben az oktatóanyagban végigvezetjük a feladathivatkozás-gyűjtemények Aspose.Tasks használatával történő munkafolyamatán.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1.  Aspose.Tasks for .NET Library: Töltse le és telepítse az Aspose.Tasks könyvtárat. Megtalálhatod a könyvtárat[itt](https://releases.aspose.com/tasks/net/).
2. Mintaprojektfájl: Készítsen egy mintaprojektfájlt (pl. "SampleProject.mpp"), amelyet követni szeretne a példákkal együtt.
Most pedig kezdjük!
## Névterek importálása
A .NET-projektben feltétlenül importálja az Aspose.Tasks használatához szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. lépés: Töltse be a projektet és a hozzáférési feladatokat
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
// Töltse be a projektet
var project = new Project(DataDir + "SampleProject.mpp");
// A feladatok elérése azonosító alapján
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## 2. lépés: Hozzon létre feladathivatkozásokat
Kapcsolja össze a feladatokat a függőségek megállapításához:
```csharp
// A feladatok összekapcsolása a FinishToStart függőséggel
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## 3. lépés: Nyomtasson feladathivatkozásokat
Nyomtassa ki a projekt feladathivatkozásait:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//Iteráljon feladathivatkozásokon keresztül
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## 4. lépés: Szerkessze a feladathivatkozást
Feladathivatkozás szerkesztése indexeléréssel:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## 5. lépés: Távolítsa el a feladathivatkozásokat
Távolítsa el az összes feladathivatkozást a projektből:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Következtetés
Gratulálunk! Sikeresen megtanulta a feladathivatkozások kezelését az Aspose.Tasks for .NET programban. Ez az átfogó útmutató a projekt betöltését, a feladathivatkozások létrehozását, a hivatkozások nyomtatását, a hivatkozások szerkesztését és a feladathivatkozások eltávolítását tárgyalta.
Nyugodtan fedezze fel az Aspose.Tasks által kínált további funkciókat és funkciókat a projektmenedzsment élményének javítása érdekében.
## GYIK
### Az Aspose.Tasks kompatibilis a .NET összes verziójával?
Igen, az Aspose.Tasks úgy lett kialakítva, hogy zökkenőmentesen működjön a .NET összes verziójával.
### Létrehozhatok egyéni feladathivatkozás-típusokat az Aspose.Tasks használatával?
Jelenleg az Aspose.Tasks támogatja a szabványos feladathivatkozás-típusokat, és egyéni hivatkozástípusok nem állnak rendelkezésre.
### Hogyan alkalmazhatok megszorításokat az Aspose.Tasks feladataira?
 Megszorításokat alkalmazhat a`ConstraintType` tulajdona a`Task` osztályban Aspose.Feladatok.
### Vannak-e korlátozások az Aspose.Tasks által kezelhető projektfájlok méretére vonatkozóan?
Az Aspose.Tasks hatékonyan tudja kezelni a nagy projektfájlokat, minimális teljesítményhatás mellett.
### Létezik közösségi fórum az Aspose.Tasks támogatására?
 Igen, támogatást találhat, és kapcsolatba léphet a közösséggel a webhelyen[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
