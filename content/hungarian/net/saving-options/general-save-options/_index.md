---
title: Az Aspose.Tasks MS Project mentési opcióinak elsajátítása
linktitle: Az Aspose.Tasks általános mentési beállításai
second_title: Aspose.Tasks .NET API
description: Ismerje meg az MS Project fájlok hatékony mentését az Aspose.Tasks for .NET használatával. A kimeneti lehetőségeket könnyedén testreszabhatja projektjeihez.
type: docs
weight: 17
url: /hu/net/saving-options/general-save-options/
---
## Bevezetés
Az Aspose.Tasks for .NET hatékony szolgáltatásokat kínál a Microsoft Project fájlok programozott kezeléséhez. Ebben az oktatóanyagban az MS Project fájlok Aspose.Tasks által biztosított különféle lehetőségekkel történő mentésének bonyolultságába fogunk bele. Konkrétan az Aspose.Tasks számára elérhető általános mentési lehetőségekre összpontosítunk, amelyek lehetővé teszik, hogy a kimenetet az Ön egyedi igényeihez igazítsa.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Az Aspose.Tasks for .NET telepítése: Töltse le és telepítse az Aspose.Tasks for .NET webhelyről[letöltési link](https://releases.aspose.com/tasks/net/).
2. .NET-keretrendszer alapvető ismerete: A .NET programozási koncepciók ismerete előnyös.

## Névterek importálása
Mielőtt belemerülne a kódba, feltétlenül importálja a szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## 1. lépés: Töltse be a projektfájlt
Először is be kell töltenie az MS Project fájlt az Aspose.Tasks segítségével:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## 2. lépés: Adja meg a mentési beállításokat
 Határozza meg a mentési lehetőségeket igényei szerint. Ebben a példában azt használjuk`Spreadsheet2003SaveOptions`,
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## 3. lépés: A nézetoszlopok testreszabása
Testreszabhatja a nézetoszlopokat, például a Gantt-diagramot, az erőforrás-nézetet és a hozzárendelési nézetet. A következőképpen adhat hozzá oszlopokat mindegyikhez:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## 4. lépés: Mentse el a projektet az opciókkal
Végül mentse a projektet a megadott opciókkal:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Következtetés
Az általános MS Project mentési opciók elsajátítása az Aspose.Tasks for .NET segítségével lehetővé teszi a kimeneti formátum hatékony testreszabását projektje igényei szerint.
## GYIK
### K: Az Aspose.Tasks kompatibilis az MS Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks támogatja az MS Project fájlok különféle verzióit, biztosítva a kompatibilitást a különböző környezetekben.
### K: Kipróbálhatom az Aspose.Tasks-t vásárlás előtt?
 V: Igen, az Aspose.Tasks szolgáltatást ingyenes próbaverzióval fedezheti fel[itt](https://releases.aspose.com/).
### K: Hol találom az Aspose.Tasks dokumentációját?
V: A részletes dokumentáció megtalálható[itt](https://reference.aspose.com/tasks/net/), amely átfogó útmutatást nyújt az Aspose.Tasks funkciók használatához.
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks számára?
 V: Ideiglenes licencek állnak rendelkezésre értékelési célokra.[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol kérhetek támogatást az Aspose.Tasks-hoz kapcsolódó lekérdezésekhez?
 V: Csatlakozhat az Aspose.Tasks közösségi fórumhoz[itt](https://forum.aspose.com/c/tasks/15) szakértőktől és fejlesztőtársaktól kérhet segítséget.