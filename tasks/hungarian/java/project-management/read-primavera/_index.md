---
title: Olvassa el a Primavera MS Projectjét az Aspose.Tasks for Java segítségével
linktitle: Olvassa el a Primavera projektjét az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan olvashat zökkenőmentesen MS Project fájlokat a Primavera XML-ből az Aspose.Tasks for Java segítségével. Növelje projektmenedzsmentjének hatékonyságát.
type: docs
weight: 20
url: /hu/java/project-management/read-primavera/
---
## Bevezetés
projektmenedzsmentben a különböző szoftverplatformok közötti interoperabilitás kulcsfontosságú a zökkenőmentes munkafolyamat érdekében. Az Aspose.Tasks for Java robusztus funkcionalitást biztosít a Microsoft Project fájlok Primavera XML-ből való olvasásához. Ez az oktatóanyag végigvezeti Önt a Primavera MS Project fájlok Aspose.Tasks for Java segítségével történő olvasásának folyamatán, lehetővé téve a feladatok Primavera-specifikus tulajdonságainak hatékony vizsgálatát.
## Előfeltételek
Mielőtt folytatná, győződjön meg arról, hogy a következő előfeltételek telepítve és be vannak állítva:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Tasks for Java: Töltse le és telepítse az Aspose.Tasks for Java-t innen[itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## 1. lépés: A Data Directory beállítása
```java
String dataDir = "Your Data Directory";
```
 Biztosítsa a cserét`"Your Data Directory"` az adatkönyvtár tényleges elérési útjával.
## 2. lépés: Olvassa be a projektet a Primavera XML-ből
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Biztosítsa a cserét`"PrimaveraProject.xml"` a Primavera XML-fájl tényleges nevével.
## 3. lépés: Ismételje meg a feladatokat, és állítsa le a Primavera-specifikus tulajdonságokat
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Ez a kód a projekt minden egyes feladatán keresztül iterál, és kinyomtatja a megfelelő Primavera-specifikus tulajdonságokat.

## Következtetés
Ebben az oktatóanyagban megtanulta, hogyan kell MS Project fájlokat olvasni a Primavera XML-ből az Aspose.Tasks for Java segítségével. Ez a funkció lehetővé teszi a projektadatok zökkenőmentes integrációját és elemzését a különböző platformokon, javítva a projektmenedzsment általános hatékonyságát.
## GYIK
### K: Módosíthatom a feladatok Primavera-specifikus tulajdonságait az Aspose.Tasks for Java használatával?
V: Igen, az Aspose.Tasks for Java API-kat biztosít a feladatok Primavera-specifikus tulajdonságainak igény szerinti módosításához.
### K: Az Aspose.Tasks for Java támogatja más projektfájlformátumok olvasását?
V: Igen, az Aspose.Tasks for Java támogatja a különféle projektfájlformátumok, köztük az MPP, XML és Primavera XML olvasását.
### K: Az Aspose.Tasks for Java alkalmas vállalati szintű projektmenedzsment alkalmazásokhoz?
V: Az Aspose.Tasks for Java robusztus szolgáltatásokat és méretezhetőséget kínál, így alkalmas vállalati szintű projektmenedzsment alkalmazásokhoz.
### K: Kinyerhetem az erőforrás-információkat a Primavera projektekből az Aspose.Tasks for Java használatával?
V: Igen, az Aspose.Tasks for Java lehetővé teszi az erőforrás-információk és a feladatok részleteinek kinyerését a Primavera projektekből.
### K: Hol találok további támogatást vagy dokumentációt az Aspose.Tasks for Java-hoz?
 V: A webhelyen átfogó dokumentációt és támogatási fórumokat találhat[Aspose.Tasks a Java dokumentációhoz](https://reference.aspose.com/tasks/java/) oldalon.