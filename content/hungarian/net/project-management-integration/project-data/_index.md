---
title: Projektadatok elsajátítása az Aspose.Tasks segítségével
linktitle: Munka a projektadatokkal az Aspose.Tasks programban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti a Microsoft Project adatait az Aspose.Tasks segítségével a .NET-ben. Hozzon létre feladatokat, adjon hozzá erőforrásokat és mentse el a projekteket könnyedén.
type: docs
weight: 16
url: /hu/net/project-management-integration/project-data/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan dolgozhatunk a Microsoft Project adatokkal az Aspose.Tasks könyvtár .NET-hez használatával. Az Aspose.Tasks hatékony funkciókat kínál a projektfájlok kezeléséhez, beleértve a feladatok létrehozását, az erőforrások hozzáadását, a tulajdonságok beállítását és a projektek különféle formátumokban történő mentését.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Az Aspose.Tasks könyvtár telepítése: Töltse le és telepítse az Aspose.Tasks könyvtárat innen[itt](https://releases.aspose.com/tasks/net/).
2. Fejlesztői környezet: Győződjön meg arról, hogy be van állítva .NET fejlesztői környezet.
3. Alapszintű C# ismerete: A C# programozási nyelv ismerete előnyt jelent.

## Névterek importálása
Az Aspose.Tasks használata előtt importálja a szükséges névtereket a projektbe:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1. lépés: Inicializálja a projektobjektumot
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Ez a sor inicializálja a`Project` osztály, amely egy Microsoft Project fájlt képvisel.
## 2. lépés: Állítsa be a projekt tulajdonságait
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Ezek a sorok bemutatják, hogyan lehet beállítani a projekt tulajdonságait, például a munkaformátumot és a feladatkészítési módot.
## 3. lépés: Feladatok hozzáadása
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Itt egy új, „1. feladat” nevű feladat kerül hozzáadásra a projekt gyökérfeladatához.
## 4. lépés: A feladat tulajdonságainak beállítása
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Ezek a sorok állítják be az „1. feladat” kezdő dátumát, időtartamát és befejezési dátumát.
## 5. lépés: Erőforrások hozzáadása
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Ez a rész bemutatja, hogyan lehet munkaerőforrást hozzáadni a projekthez.
## 6. lépés: Erőforrások hozzárendelése a feladatokhoz
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Ezek a sorok azt mutatják, hogyan rendelheti hozzá a korábban hozzáadott munkaerőforrást az „1. feladathoz” meghatározott kezdési, munkavégzési és befejezési dátumokkal.
## 7. lépés: Projekt mentése
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Végül a projekt Microsoft Project XML fájlformátumban kerül mentésre.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell dolgozni a Microsoft Project adatokkal a .NET Aspose.Tasks könyvtárával. A lépésenkénti útmutató követésével kezelheti a projektfájlokat, feladatokat, erőforrásokat adhat hozzá, erőforrásokat rendelhet hozzá, és projekteket menthet különféle formátumokban.
## GYIK
### K: Az Aspose.Tasks kezelni tudja az összetett projektstruktúrákat?
V: Igen, az Aspose.Tasks átfogó támogatást nyújt összetett projektstruktúrákhoz, lehetővé téve a feladatok, erőforrások és hozzárendelések hatékony kezelését.
### K: Az Aspose.Tasks kompatibilis a Microsoft Project különböző verzióival?
V: Az Aspose.Tasks a Microsoft Project verziók széles skáláját támogatja, biztosítva a kompatibilitást a különböző környezetekben.
### K: Integrálhatom az Aspose.Tasks-t más .NET könyvtárakkal?
V: Természetesen az Aspose.Tasks zökkenőmentesen integrálódik más .NET-könyvtárakba, rugalmasságot biztosítva a fejlesztési projektekben.
### K: Az Aspose.Tasks támogatja a projektütemezési algoritmusokat?
V: Igen, az Aspose.Tasks fejlett ütemező algoritmusokat tartalmaz, amelyek segítenek optimalizálni a projektek ütemezését és az erőforrás-felhasználást.
### K: Létezik közösségi fórum az Aspose.Tasks felhasználók számára?
 V: Igen, találhat hasznos forrásokat, és kapcsolatba léphet más Aspose.Tasks-felhasználókkal a webhelyen[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).