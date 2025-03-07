---
title: Feladatgyűjtemények kezelése az Aspose.Tasks alkalmazásban
linktitle: Feladatgyűjtemények kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Fedezze fel a hatékony feladatgyűjtemény-kezelést az Aspose.Tasks for .NET-ben. A létrehozástól a szerkesztésig könnyedén sajátíthatja el a projektmenedzsmentet.
weight: 18
url: /hu/net/task-table-management/task-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladatgyűjtemények kezelése az Aspose.Tasks alkalmazásban

## Bevezetés
Ha a .NET használatával elmélyül a projektmenedzsment világában, az Aspose.Tasks a legjobb megoldás a feladatgyűjtemények zökkenőmentes kezelésére. Ez az oktatóanyag végigvezeti Önt a feladatgyűjtemények hatékony kezelésének folyamatán, biztosítva, hogy a legtöbbet hozza ki ebből a hatékony könyvtárból.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- C# programozási nyelv alapismerete.
- A Visual Studio telepítve van a gépedre.
- Aspose.Tasks a .NET könyvtárhoz letöltve és hivatkozva a projektben.
## Névterek importálása
Kezdésként importáljuk a szükséges névtereket a C# projektbe:
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Ezek a névterek hozzáférést biztosítanak a hatékony feladatkezeléshez szükséges alapvető osztályokhoz és metódusokhoz.
Most bontsuk le az oktatóanyagot egy sor lépésre, biztosítva az egyértelműséget és az egyszerűséget.
## 1. lépés: Projektpéldány létrehozása
```csharp
var project = new Project();
```
 Példányosítson egy új projektet a`Project` osztály.
## 2. lépés: A Feladatgyűjtemény készenlétének ellenőrzése
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
Ellenőrizze, hogy a feladatgyűjtemény írásvédett-e.
## 3. lépés: Feladatok létrehozása
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// Állítson be további feladattulajdonságokat, például kezdést, időtartamot és befejezést
// Hasonló lépések a 2. és a 3. feladathoz
```
Hozzon létre feladatokat a projekten belül, és állítsa be tulajdonságaikat.
## 4. lépés: Projektfeladatok nyomtatása
```csharp
foreach (var child in project.RootTask.Children)
{
    // A feladat részleteinek kinyomtatása
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
Nyomtassa ki a projekten belüli egyes feladatok részleteit.
## 5. lépés: Feladatok szerkesztése
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
Szerkessze a feladatokat azonosítójuk vagy felhasználói azonosítójuk használatával.
## 6. lépés: Ismétlődő feladat hozzáadása
```csharp
var parameters = new RecurringTaskParameters
{
    // Állítsa be az ismétlődő feladatparamétereket
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
Adjon hozzá egy ismétlődő feladatot a projekthez.
## 7. lépés: Gyűjtemény átalakítása listává
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
Konvertálja a feladatgyűjteményt listává, és hajtson végre műveleteket az egyes feladatokon.
## Következtetés
feladatgyűjtemények kezelése az Aspose.Tasks for .NET-ben gyerekjáték ezzel a lépésenkénti útmutatóval. Akár feladatokat hoz létre, szerkeszt vagy töröl, az Aspose.Tasks lehetővé teszi a projektmenedzsment zökkenőmentes kezelését.
## Gyakran Ismételt Kérdések
### Az Aspose.Tasks kompatibilis a .NET Core programmal?
Igen, az Aspose.Tasks támogatja a .NET Core-t, így többplatformos alkalmazásokban is használható.
### Exportálhatok projektfeladatokat különböző fájlformátumokba?
Teljesen! Az Aspose.Tasks sokoldalú exportálási lehetőségeket kínál, beleértve a PDF, XLSX és MPP-t.
### Hogyan kezelhetem a feladatok közötti függőséget?
 A feladatfüggőségeket a segítségével állíthatja be`TaskLink` osztály által biztosított Aspose.Tasks.
### Létezik közösségi fórum az Aspose.Tasks támogatására?
 Igen, itt találhat támogatást és kapcsolatba léphet a közösséggel[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
### Kaphatok ideiglenes licencet az Aspose.Tasks számára?
 Igen, kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
