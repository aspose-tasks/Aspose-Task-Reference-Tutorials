---
title: Feladatok kezelése az Aspose.Tasks-ban
linktitle: Feladatok kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel az átfogó útmutatót az Aspose.Tasks for .NET segítségével történő feladatok kezeléséről. Tanuljon meg hozzáadni, megjeleníteni felosztott részeket, mozgatni, tulajdonságokat szerezni/beállítani stb.
weight: 15
url: /hu/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladatok kezelése az Aspose.Tasks-ban

## Bevezetés
Ha Ön .NET-fejlesztő, aki hatékonyan szeretné kezelni a projektjein belüli feladatokat, az Aspose.Tasks for .NET robusztus megoldást kínál. Ez az oktatóanyag végigvezeti Önt az Aspose.Tasks használatával végzett feladatok kezelésének különböző aspektusain, lépésről lépésre és kódpéldákat kínál. Függetlenül attól, hogy feladatokat ad hozzá, felosztott részeket jelenít meg, feladatokat ugyanazon szülő alá helyez át, feladattulajdonságokat kér/beállít, feladat-hozzárendeléseket iterál, a feladatok alapvonalait olvassa be vagy töröljön, ez az útmutató mindenre kiterjed.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1. Aspose.Tasks for .NET Library: Győződjön meg arról, hogy telepítve van az Aspose.Tasks for .NET könyvtár. Letöltheti[itt](https://releases.aspose.com/tasks/net/).
2. Dokumentumkönyvtár: Állítson be egy könyvtárat, ahol a projekt dokumentumait tárolni fogja.
## Névterek importálása
A .NET-projektben adja meg az Aspose.Tasks használatához szükséges névtereket:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Feladat hozzáadása egy projekthez
```csharp
// Hozzon létre egy új projektet
var project = new Project();
// Adjon hozzá egy feladatot
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Mentse el a projektet
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. A feladat felosztott részeinek megjelenítése
```csharp
// Töltsön be egy projektet osztott feladatokkal
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Hozzáférés egy feladathoz
var task = project.RootTask.Children.GetById(4);
// Az osztott részek megjelenítése
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Feladat áthelyezése ugyanazon szülő alá
```csharp
try
{
    // Töltsön be egy projektet
    var project = new Project(DataDir + "MoveTask.mpp");
    // Helyezze át az 5-ös azonosítójú feladatokat a 3-as azonosítójú feladat elé
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Mentse el a módosított projektet
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Feladat tulajdonságainak lekérése/beállítása
```csharp
// Hozzon létre egy új projektet
var project = new Project();
// Adjon hozzá egy feladatot és állítsa be a tulajdonságokat
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Gyűjtse össze és jelenítse meg a feladat tulajdonságait
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Feladat-hozzárendelések iterálása
```csharp
// Töltsön be egy projektet feladatokkal
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Gyűjtse össze és jelenítse meg a feladatokat
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Feladat alapvonalainak olvasása
```csharp
// Hozzon létre egy új projektet
var project = new Project();
// Adjon hozzá egy feladatot, és állítson be egy alapállapotot
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Feladat alapidőtartamának megjelenítése
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Feladat törlése
```csharp
// Hozzon létre egy új projektet
var project = new Project();
// Adjon hozzá egy feladatot
var task = project.RootTask.Children.Add("Task");
// törlés előtti és utáni feladatok számának megjelenítése
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Törölje a feladatot
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Következtetés
A feladatok kezelése az Aspose.Tasks for .NET-ben egy zökkenőmentes folyamat a mellékelt példákkal. Akár tapasztalt fejlesztő, akár csak most kezdi, ezeknek a technikáknak a beépítése javítja projektmenedzsment képességeit.
## Gyakran Ismételt Kérdések
### K: Az Aspose.Tasks kompatibilis az összes .NET keretrendszerrel?
V: Igen, az Aspose.Tasks támogatja a különböző .NET-keretrendszereket, biztosítva a kompatibilitást a fejlesztői környezettel.
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks számára?
 V: 30 napos ideiglenes licencet kaphat a következőtől[itt](https://purchase.aspose.com/temporary-license/).
### K: Vannak-e korlátozások az Aspose.Tasks osztott feladatokkal végzett munka során?
 V: Az osztott feladatok hatékony szolgáltatás, és részletes dokumentáció is megtalálható[itt](https://reference.aspose.com/tasks/net/).
### K: Testreszabhatom a feladat tulajdonságait a példákban bemutatottakon túl?
V: Abszolút! Az Aspose.Tasks kiterjedt testreszabási lehetőségeket biztosít a feladat tulajdonságaihoz. További részletekért tekintse meg a dokumentációt.
### K: Hogyan kaphatok támogatást az Aspose.Tasks programhoz?
 V: Látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásra és beszélgetésekre.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
