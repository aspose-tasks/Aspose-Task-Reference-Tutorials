---
title: Hatékonyan kezelheti az MS projektszűrőket az Aspose.Tasks segítségével
linktitle: Szűrőgyűjtemény kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az MS Project szűrőgyűjteményeit az Aspose.Tasks for .NET segítségével.
weight: 17
url: /hu/net/tasks-project-management/filter-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hatékonyan kezelheti az MS projektszűrőket az Aspose.Tasks segítségével

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet hatékonyan kezelni az MS Project szűrőgyűjteményeit az Aspose.Tasks for .NET használatával. A szűrők kezelése kulcsfontosságú a projektadatok hatékony rendszerezéséhez és elemzéséhez. Az Aspose.Tasks robusztus funkcionalitást biztosít a feladat- és erőforrásszűrők zökkenőmentes kezeléséhez.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Az Aspose.Tasks for .NET telepítése: Töltse le és telepítse az Aspose.Tasks for .NET webhelyről[letöltési link](https://releases.aspose.com/tasks/net/).
2. Hozzáférés a .NET fejlesztőkörnyezethez: Győződjön meg arról, hogy be van állítva egy .NET fejlesztői környezet az Aspose.Tasks használatához.

## Névterek importálása
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 1. lépés: Töltse be a projektfájlt
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## 2. lépés: Ismételje meg a feladatszűrőket
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## 3. lépés: Ismételje meg az erőforrásszűrőket
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## 4. lépés: Szűrők törlése és másolása
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Törölje a többi projekt szűrőit
otherProject.TaskFilters.Clear();
// Szűrők másolása másik projektbe
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## 5. lépés: Adjon hozzá egyéni feladatszűrőt
```csharp
// Egyéni feladatszűrő hozzáadása
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## 6. lépés: Távolítsa el az összes szűrőt
```csharp
// Távolítsa el az összes szűrőt
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
Az alábbi lépések követésével hatékonyan kezelheti az MS Project szűrőgyűjteményeit az Aspose.Tasks for .NET segítségével.

## Következtetés
Az MS Project gyűjteményekben található szűrők hatékony kezelése kulcsfontosságú a projektadatok rendszerezéséhez és elemzéséhez. Az Aspose.Tasks for .NET átfogó funkcionalitást biztosít a feladat- és erőforrásszűrők zökkenőmentes kezelésére, lehetővé téve a fejlesztők számára a projektmenedzsment feladatok hatékony egyszerűsítését.
## GYIK
### K: Az Aspose.Tasks kezelni tudja az összetett projektstruktúrákat?
V: Az Aspose.Tasks robusztus szolgáltatásokat kínál a különféle projektstruktúrák kezelésére, beleértve az összetetteket is, átfogó projektmenedzsment képességeket biztosítva.
### K: Az Aspose.Tasks kompatibilis az MS Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks az MS Project fájlformátumok széles skáláját támogatja, biztosítva a kompatibilitást a különböző verziók között.
### K: Testreszabhatom a szűrőket konkrét projektkövetelményeknek megfelelően?
V: Abszolút! Az Aspose.Tasks lehetővé teszi a fejlesztők számára, hogy egyedi projektszükségletekre szabott egyedi szűrőket hozzanak létre, növelve a rugalmasságot és a hatékonyságot.
### K: Az Aspose.Tasks biztosít dokumentációt és támogatási forrásokat?
V: Igen, az Aspose.Tasks kiterjedt dokumentációt, oktatóanyagokat és egy dedikált támogatási fórumot kínál a fejlesztőknek a projekt megvalósításának minden lépésében.
### K: Elérhető az Aspose.Tasks próbaverziója?
V: Igen, a fejlesztők hozzáférhetnek az Aspose.Tasks ingyenes próbaverziójához, hogy a vásárlási döntés meghozatala előtt felfedezzék annak funkcióit.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
