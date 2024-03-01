---
title: Testreszabhatja a Gantt-diagram oszlopait az Aspose.Tasks segítségével
linktitle: Aspose.Tasks Gantt-diagram oszlopai
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan szabhatja személyre a Gantt-diagram oszlopait az Aspose.Tasks for .NET-ben, hogy hatékonyan jelenítse meg a konkrét feladatadatokat.
type: docs
weight: 21
url: /hu/net/tasks-project-management/gantt-chart-columns/
---
## Bevezetés
A Gantt-diagramok a projektmenedzsment alapvető eszközei, amelyek vizuálisan ábrázolják a feladatokat, az idővonalakat és az erőforrásokat. Az Aspose.Tasks for .NET hatékony lehetőségeket kínál a Gantt-diagramok kezeléséhez, beleértve az oszlopok testreszabását a konkrét feladatadatok megjelenítéséhez. Ebben az oktatóanyagban megvizsgáljuk, hogyan dolgozhatunk Gantt-diagram oszlopaival az Aspose.Tasks for .NET használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Telepítés: Aspose.Tasks for .NET telepítve a rendszerére. Ha nem, töltse le és telepítse innen[itt](https://releases.aspose.com/tasks/net/).
2. .NET fejlesztői környezet: A C# és a .NET keretrendszer gyakorlati ismerete.
3. Mintaprojektfájl: rendelkezzen egy minta Microsoft Project fájllal (`.mpp`) praktikus kísérletezésre. Ha nem rendelkezik ilyennel, létrehozhat egy egyszerű projektet az MS Projectben, és elmentheti.

## Névterek importálása
Először is importálnia kell a szükséges névtereket az Aspose.Tasks for .NET használatához:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 1. lépés: Töltse be a projektfájlt
 Töltse be a projektfájlt a`Project` Az Aspose által biztosított osztály. Feladatok:
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## 2. lépés: Határozza meg a Gantt-diagram oszlopait
Határozza meg a Gantt-diagramon megjeleníteni kívánt oszlopokat. Megadhat beépített mezőket, vagy létrehozhat egyéni mezőket:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## 3. lépés: Iterálás oszlopok felett
Iteráljon a meghatározott oszlopokon a tulajdonságaik eléréséhez és információinak megjelenítéséhez:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## 4. lépés: Mentse el a Gantt-diagramot CSV-fájlba
Mentse el a Gantt-diagramot meghatározott oszlopokkal egy CSV-fájlba:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Az alábbi lépések követésével hatékonyan dolgozhat a Gantt-diagram oszlopaival az Aspose.Tasks for .NET-ben, így szükség szerint testreszabhatja és megjelenítheti a feladatadatokat.

## Következtetés
Ha elsajátítja a Gantt-diagram oszlopainak kezelését az Aspose.Tasks for .NET-ben, végtelen lehetőségek nyílnak meg a projektmenedzsment-vizuálok egyedi igényeire szabására. Az oktatóanyagban ismertetett lépések követésével hatékonyan kezelheti a feladatinformációkat, és javíthatja a projekt átláthatóságát és szervezettségét.
## GYIK
### K: Létrehozhatok egyéni oszlopokat az Aspose.Tasks for .NET-ben?
V: Igen, egyedi oszlopokat definiálhat konkrét feladatattribútumok megjelenítéséhez a projekt követelményei szerint.
### K: Az Aspose.Tasks for .NET kompatibilis a Microsoft Project fájlok összes verziójával?
V: Az Aspose.Tasks for .NET támogatja a Microsoft Project fájlok különféle verzióit, így biztosítja a kompatibilitást a különböző projektkörnyezetekkel.
### K: Hogyan kezelhetek összetett projektstruktúrákat az Aspose.Tasks for .NET segítségével?
V: Az Aspose.Tasks for .NET átfogó API-kat és szolgáltatásokat kínál összetett projektstruktúrák kezeléséhez, rugalmasságot és méretezhetőséget kínálva.
### K: Van-e korlátozás a Gantt-diagramhoz hozzáadható oszlopok számára?
V: Az Aspose.Tasks for .NET kiterjedt testreszabási lehetőségeket kínál, lehetővé téve, hogy jelentős számú oszlopot adjon hozzá a Gantt-diagramokhoz korlátozás nélkül.
### K: Hol találok további támogatást és forrásokat az Aspose.Tasks for .NET-hez?
V: Fedezze fel az Aspose.Tasks for .NET által biztosított dokumentációt, közösségi fórumokat és támogatási csatornákat, hogy átfogó forrásokhoz és segítséghez férhessen hozzá.