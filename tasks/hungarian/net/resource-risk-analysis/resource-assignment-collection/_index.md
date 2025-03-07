---
title: Erőforrás-hozzárendelések gyűjteménye az Aspose.Tasks-ban
linktitle: Erőforrás-hozzárendelések gyűjteménye az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Ismerje meg, hogyan kezelheti az erőforrás-hozzárendeléseket a Microsoft Projectben az Aspose.Tasks for .NET használatával. Lépésről lépésre bemutató oktatóprogram kódpéldákkal.
weight: 12
url: /hu/net/resource-risk-analysis/resource-assignment-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erőforrás-hozzárendelések gyűjteménye az Aspose.Tasks-ban

## Bevezetés
Üdvözöljük ebben az átfogó oktatóanyagban a Microsoft Project erőforrás-hozzárendeléseinek kezeléséről az Aspose.Tasks for .NET használatával. Ebben az oktatóanyagban lépésről lépésre elmélyülünk a folyamatban, biztosítva, hogy alaposan megértse az erőforrás-hozzárendelések hatékony kezelését. Akár tapasztalt fejlesztő, akár csak most kezdi, ez az útmutató végigvezeti Önt mindenen, amit tudnia kell.
## Előfeltételek
Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy beállította a következőket:
1.  Aspose.Tasks for .NET telepítve: Győződjön meg arról, hogy az Aspose.Tasks for .NET telepítve van a fejlesztői környezetében. Ha nem, letöltheti innen[itt](https://releases.aspose.com/tasks/net/).
2. Alapvető C# ismerete: Ez az oktatóanyag feltételezi, hogy rendelkezik a C# programozási nyelv alapvető ismereteivel.
3. Microsoft Project File: Készítsen egy Microsoft Project fájlt tesztelési célokra. Ha nem rendelkezik ilyennel, létrehozhat egy mintafájlt.

## Névterek importálása
Először is importáljuk a szükséges névtereket:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. lépés: Töltse be a projektfájlt
Kezdje a Microsoft Project fájl betöltésével:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## 2. lépés: Feladat és erőforrás hozzáadása
Most adjunk hozzá egy feladatot és egy erőforrást a projekthez:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## 3. lépés: Rendeljen erőforrást a feladathoz
Ezután hozzárendeljük az erőforrást a feladathoz:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## 4. lépés: Különböző hozzárendeléstípusok kezelése
Dolgozhat olyan feladatokkal is, amelyek egységeket vagy költségeket tartalmaznak:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Állítsa be az egységeket és költségeket tartalmazó hozzárendelések tulajdonságait a 3. lépésben látható módon
```
## 5. lépés: Hozzárendelések nyomtatása
Nyomtassa ki a projekthez tartozó feladatokat:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // A feladat részleteinek nyomtatása
}
```
## 6. lépés: Hozzárendelés lekérése UID alapján
A feladatokat UID alapján kérheti le:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## 7. lépés: Ellenőrizze a Csak olvasható állapotot
Ellenőrizze, hogy az erőforrás-hozzárendelés-gyűjtemény csak olvasható-e:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## 8. lépés: Konvertálja a gyűjteményt listává és ismételje meg
Alakítsa át a gyűjteményt listává, és iteráljon rajta:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Következtetés
Gratulálunk! Megtanulta, hogyan kezelheti az erőforrás-hozzárendeléseket a Microsoft Projectben az Aspose.Tasks for .NET használatával. Ha követi ezeket a lépéseket, hatékonyan kezelheti a feladatokat és az erőforrásokat, így a projektmenedzsment gyerekjáték.
## GYIK
### K: Használhatom az Aspose.Tasks for .NET programot a Microsoft Project fájlok különböző verzióival?
V: Igen, az Aspose.Tasks for .NET támogatja a Microsoft Project fájlok különféle verzióit, beleértve az MPP, MPT és XML formátumokat.
### K: Elérhető-e próbaverzió az Aspose.Tasks .NET-hez való megvásárlása előtt?
 V: Igen, letöltheti az Aspose.Tasks ingyenes próbaverzióját a .NET-hez innen[itt](https://releases.aspose.com/).
### K: Hogyan kaphatok támogatást, ha problémákat tapasztalok az Aspose.Tasks for .NET használata során?
 V: Kérhet támogatást az Aspose.Tasks fórumon[itt](https://forum.aspose.com/c/tasks/15).
### K: Használhatok ideiglenes licenceket az Aspose.Tasks for .NET számára?
 V: Igen, ideiglenes licencek állnak rendelkezésre értékelési célokra. Kaphatsz egyet innen[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol vásárolhatok teljes licencet az Aspose.Tasks for .NET-hez?
 V: Teljes licencet vásárolhat az Aspose online áruházból[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
