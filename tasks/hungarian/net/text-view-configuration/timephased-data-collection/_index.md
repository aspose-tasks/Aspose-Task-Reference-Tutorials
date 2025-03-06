---
title: Az időfázisú adatgyűjtés elsajátítása az Aspose.Tasks programban
linktitle: Időfázisú adatok gyűjtése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel az időzített adatgyűjtést az Aspose.Tasks for .NET-ben. Lépésről lépésre útmutató, GYIK és egyebek. Fejlessze projektmenedzsment képességeit még ma!
type: docs
weight: 15
url: /hu/net/text-view-configuration/timephased-data-collection/
---
## Bevezetés
Szeretné kihasználni az időfázisú adatok erejét .NET-alkalmazásaiban az Aspose.Tasks használatával? Ne keressen tovább! Ez az átfogó útmutató végigvezeti Önt az Aspose.Tasks for .NET-hez készült időfázisos adatok gyűjtésének folyamatán, így biztosítva, hogy a legtöbbet hozza ki ebből a hatékony könyvtárból.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1.  Aspose.Tasks for .NET Library: Töltse le és telepítse a könyvtárat innen[Aspose.Tasks .NET dokumentáció](https://reference.aspose.com/tasks/net/).
2. .NET fejlesztői környezet: Győződjön meg arról, hogy be van állítva működő .NET fejlesztői környezet.
3. Saját dokumentumkönyvtár: Cserélje le a „Saját dokumentumkönyvtár” helyőrzőt a kódrészletekben a dokumentumkönyvtár elérési útjával.
## Névterek importálása
A .NET-projektben kezdje a szükséges névterek importálásával az Aspose.Tasks funkciók kihasználásához:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Hozzon létre egy projektet és erőforrásokat
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Adjon hozzá feladatokat a projekthez
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Feladat tulajdonságainak beállítása...
var task2 = project.RootTask.Children.Add("Task 2");
// Feladat2 tulajdonságainak beállítása...
```
## 3. Rendeljen erőforrásokat a feladatokhoz
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Hozzárendelés tulajdonságainak beállítása...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//Hozzárendelés2 tulajdonságainak beállítása...
```
## 4. Munkaidőszakos adatokkal
```csharp
// Állítsa be a kontúros munkakontúrt
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Ellenőrizze, hogy az időfázisú adatgyűjtés csak olvasható-e
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Törölje a generált időfázisos adatokat
assignment.TimephasedData.Clear();
// Időfázisos adatok létrehozása és hozzáadása
var td = new TimephasedData
{
    // Időfázisos adattulajdonságok beállítása...
};
assignment.TimephasedData.Add(td);
// Adja hozzá az időzített adatok listáját
var list = new List<TimephasedData>();
// További időfázisú adatelemek hozzáadása a listához...
assignment.TimephasedData.AddRange(list);
// Az időfázisos adatok szűrése típus és dátumtartomány szerint
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Szűrt időfázisos adatok nyomtatása...
```
## 5. Manipulálja az időfázisú adatokat
```csharp
// Helytelen időfázisú adatelem hozzáadása, majd törlése
var td4 = new TimephasedData
{
    // Rossz időfázisú adattulajdonságok beállítása...
};
assignment.TimephasedData.Add(td4);
// Törölje a rossz időfázisú adatelemet
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Ismételje meg az összes időfázisos elemet
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Időfázisos tétel részleteinek nyomtatása...
}
```
## 6. Másolja az időfázisú adatokat egy másik hozzárendelésbe
```csharp
// Időfázisú adatok másolása egy másik hozzárendelésbe
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// A gyűjtemény konvertálása egyszerű listává
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Egyenként távolítsa el az időfázisos adatelemeket
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Következtetés
Összefoglalva, ez az oktatóanyag egy részletes áttekintést nyújt az időfázisú adatok gyűjtéséről az Aspose.Tasks for .NET használatával. Ezen lépések követésével zökkenőmentesen integrálhatja ezt a funkciót projektjeibe, lehetővé téve a hatékony időkövetést és az erőforrás-kezelést.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Tasks for .NET-et más projektmenedzsment eszközökkel?
Igen, az Aspose.Tasks for .NET a népszerű projektmenedzsment eszközökkel való együttműködésre készült, és különféle fájlformátumokat támogat.
### Korlátozott az Aspose.Tasks segítségével kezelhető erőforrások és feladatok száma?
Az Aspose.Tasks különböző méretű projekteket kezel, és nincs szigorú korlát az erőforrások és feladatok számára.
### Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez kapcsolódó problémákhoz vagy kérdésekhez?
 Támogatásért keresse fel a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) kapcsolatba lépni a közösséggel és segítséget kapni.
### Kipróbálhatom az Aspose.Tasks for .NET-et a vásárlás előtt?
 Igen, felfedezheti az Aspose.Tasks for .NET szolgáltatásait, ha eléri a[ingyenes próbaverzió](https://releases.aspose.com/).
### Hol vásárolhatok licencet az Aspose.Tasks for .NET-hez?
Vásárolhat licencet az Aspose.Tasks for .NET számára[itt](https://purchase.aspose.com/buy).