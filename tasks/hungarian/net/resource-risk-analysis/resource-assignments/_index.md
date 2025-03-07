---
title: MS Project erőforrás-hozzárendelések kezelése az Aspose.Tasks-ban
linktitle: Erőforrás-hozzárendelések kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti hatékonyan az MS Project erőforrás-hozzárendeléseit az Aspose.Tasks for .NET használatával. Ez az átfogó útmutató lépésről lépésre nyújt útmutatást a fejlesztők számára.
weight: 11
url: /hu/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project erőforrás-hozzárendelések kezelése az Aspose.Tasks-ban

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan kezeljük hatékonyan a Microsoft Project erőforrás-hozzárendeléseit az Aspose.Tasks for .NET használatával. Az Aspose.Tasks egy hatékony API, amely lehetővé teszi a fejlesztők számára, hogy programozottan kezeljék a Microsoft Project fájlokat. Az alábbi lépések követésével megtanulhatja, hogyan kezelheti hatékonyan az erőforrás-hozzárendeléseket .NET-alkalmazásaiban.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

## Névterek importálása
Először is importálnia kell a szükséges névtereket az Aspose.Tasks funkciók használatához a .NET-projektben. Ebbe beletartozik:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Most bontsuk le a példát több lépésre, hogy átfogó képet kapjunk arról, hogyan kell kezelni az MS Project erőforrás-hozzárendeléseit az Aspose.Tasks használatával.
## 1. lépés: Állítsa be a projekt- és naptárbeállításokat
kezdéshez hozzon létre egy új projektpéldányt, és állítsa be a projekt naptárbeállításait:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## 2. lépés: Adjon hozzá egy feladatot a projekthez
Ezután adjon hozzá egy új feladatot a projekt gyökérfeladatához:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## 3. lépés: Erőforrás-hozzárendelés létrehozása és időfázisú adatok generálása
Most hozzon létre egy új erőforrás-hozzárendelést a feladathoz, és állítson elő időfázisú adatokat:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## 4. lépés: Ossza fel a feladatot
Oszd fel a feladatot több részre a kezdési és befejezési dátumok megadásával:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## 5. lépés: Állítsa be a munkakontúrt
Állítsa be a munkakörvonal típusát a feladathoz:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## 6. lépés: Mentse el a projektet
Végül mentse el a projektfájlt a változtatásokkal:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Következtetés
Összefoglalva, a Microsoft Project erőforrás-hozzárendelések kezelése az Aspose.Tasks for .NET használatával egyszerű folyamat. Az oktatóanyagban ismertetett lépések követésével hatékonyan kezelheti az erőforrás-hozzárendeléseket .NET-alkalmazásaiban.
## GYIK
### Az Aspose.Tasks képes kezelni az összetett projektstruktúrákat?
Igen, az Aspose.Tasks átfogó funkciókat kínál az összetett projektstruktúrák hatékony kezeléséhez.
### Az Aspose.Tasks kompatibilis a Microsoft Project különböző verzióival?
Igen, az Aspose.Tasks támogatja a Microsoft Project különféle verzióit, biztosítva a kompatibilitást a különböző környezetekben.
### Testreszabhatom az erőforrás-hozzárendeléseket konkrét követelmények alapján?
Természetesen az Aspose.Tasks kiterjedt testreszabási lehetőségeket kínál az erőforrás-hozzárendelésekhez, hogy megfeleljen a konkrét projektigényeknek.
### Az Aspose.Tasks támogatja a projektadatok exportálását más formátumokba?
Igen, az Aspose.Tasks lehetővé teszi a projektadatok exportálását különféle formátumokba, például XML-be, PDF-be és HTML-be.
### Elérhető technikai támogatás az Aspose.Tasks felhasználók számára?
Igen, az Aspose speciális technikai támogatást nyújt fórumán és más csatornákon keresztül, hogy segítséget nyújtson a felhasználóknak bármilyen kérdésben vagy problémában.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
