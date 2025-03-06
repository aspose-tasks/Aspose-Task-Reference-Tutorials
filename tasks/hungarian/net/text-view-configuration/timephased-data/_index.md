---
title: Master Timephased Data Handling Aspose.Tasks for .NET
linktitle: Időfázisú adatok kezelése az Aspose.Tasks-ban
second_title: Aspose.Tasks .NET API
description: Fedezze fel az Aspose.Tasks for .NET-et az időfázisos adatok egyszerű kezeléséhez, a projekttervezés javításához és az erőforrás-kezelés optimalizálásához. #Aspose #Tasks #MS Project
weight: 14
url: /hu/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master Timephased Data Handling Aspose.Tasks for .NET

## Bevezetés
A projektmenedzsment világában az időfázisos adatok hatékony kezelése kulcsfontosságú az erőforrások elosztása, a költségbecslés és az átfogó projekttervezés szempontjából. Az Aspose.Tasks for .NET hatékony megoldást kínál az egyéni időfázisú adatok zökkenőmentes kezelésére. Ez az oktatóanyag végigvezeti az időfázisos adatok Aspose.Tasks használatával történő kezelésének folyamatán, lehetővé téve az erőforrás-kezelés optimalizálását a projektekben.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- A projektmenedzsment fogalmainak alapvető ismerete.
-  Aspose.Tasks telepítve a .NET-hez. Letöltheti[itt](https://releases.aspose.com/tasks/net/).
- Egy kódszerkesztő, például a Visual Studio, a megadott példák megvalósításához.
## Névterek importálása
.NET-projektben feltétlenül importálja a szükséges névtereket az Aspose.Tasks funkciók kihasználásához. Adja hozzá a következő sorokat a kódfájl elejéhez:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Most bontsuk fel a megadott példát több lépésre, hogy végigvezetjük az időfázisos adatok kezelésén az Aspose.Tasks segítségével:
## 1. lépés: Állítsa be a projektet
```csharp
// A dokumentumok könyvtárának elérési útja.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Itt inicializálunk egy új projektet, és beállítjuk a számítási módot.
## 2. lépés: Erőforrások és feladatok meghatározása
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Hozzon létre munka- és költségforrásokat, valamint egy feladatot a projektstruktúra szimulálásához.
## 3. lépés: Rendeljen erőforrásokat a feladathoz
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Rendeljen munka- és költségforrásokat a feladathoz.
## 4. lépés: Adjon hozzá egyéni időfázisos adatokat
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Hasonló lépések a costAssignment esetében
costAssignment.TimephasedData.Clear();
```
Adjon hozzá egyéni időfázisú adatokat a munka- és költség-hozzárendelésekhez.
## 5. lépés: Időfázisos adatok megjelenítése
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Jelenítse meg a releváns információkat minden egyes időfázisú adatbevitelről
    }
}
```
Végül jelenítse meg az egyes feladatok időfázisos adatait.
#
## Következtetés
Az időfázisos adatok hatékony kezelése az Aspose.Tasks-ban új lehetőségeket nyit meg a részletes projekttervezésben és az erőforrás-kezelésben. Ennek a lépésenkénti útmutatónak a követésével megtanulta, hogyan kezelheti az időfázisos adatokat, hogy megfeleljen a projektek speciális igényeinek.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Tasks for .NET-et más projektmenedzsment eszközökkel?
Az Aspose.Tasks elsősorban .NET fejlesztésre készült. Funkciói azonban kiegészíthetik a különféle projektmenedzsment eszközöket.
### Létezik ingyenes próbaverzió az Aspose.Tasks for .NET számára?
 Igen, felfedezheti az ingyenes próbaverziót[itt](https://releases.aspose.com/).
### Hogyan kaphatok támogatást az Aspose.Tasks for .NET-hez?
 Meglátogatni a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásért.
### Mi az az ideiglenes engedély, és hogyan szerezhetem meg?
 További információ az ideiglenes licencekről[itt](https://purchase.aspose.com/temporary-license/).
### Hol találom az Aspose.Tasks for .NET dokumentációját?
 Lásd az átfogó[dokumentáció](https://reference.aspose.com/tasks/net/) részletes információkért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
