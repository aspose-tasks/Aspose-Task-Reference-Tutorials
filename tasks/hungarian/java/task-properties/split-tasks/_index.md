---
title: Feladatok felosztása az Aspose.Tasks-ban
linktitle: Feladatok felosztása az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Mester feladatkezelés Java nyelven az Aspose.Tasks segítségével! Ismerje meg, hogyan oszthatja fel hatékonyan a feladatokat az optimalizált projektidővonalak érdekében. Letöltés most!
weight: 29
url: /hu/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feladatok felosztása az Aspose.Tasks-ban

## Bevezetés
Nehezen küzd a feladatkezeléssel a Java projektben? Az Aspose.Tasks for Java hatékony megoldást kínál a feladatok hatékony felosztására, javítva a projektkezelési képességeket. Ebben az oktatóanyagban végigvezetjük a feladatok Aspose.Tasks for Java használatával történő felosztásának folyamatán, segítve a projektek ütemezésének és erőforrás-elosztásának optimalizálását.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- Java Development Kit (JDK) telepítve a gépére.
-  Aspose.Tasks a Java könyvtárhoz letöltve és hozzáadva a projekthez. Letöltheti a[Aspose.Tasks a Java dokumentációhoz](https://reference.aspose.com/tasks/java/).
## Csomagok importálása
Kezdje azzal, hogy importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## 1. lépés: Hozzon létre egy új projektet
Kezdje egy új projekt létrehozásával az Aspose.Tasks könyvtár használatával:
```java
// Hozzon létre egy új projektet
Project splitTaskProject = new Project();
```
## 2. lépés: Állítsa be a projekt naptárát
Állítsa be a projekt naptárbeállításait az idővonal létrehozásához:
```java
// Szerezzen be egy szabványos naptárat
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Adja meg a projekt naptárbeállításait
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (folytatás a példával)
```
## 3. lépés: Adjon hozzá egy gyökérfeladatot
Adjon hozzá gyökérfeladatot a projekthez:
```java
// Root feladat
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## 4. lépés: Új feladat hozzáadása a Splithez
Adjon hozzá egy új feladatot a projekthez, amelyet fel szeretne osztani:
```java
// Új feladat hozzáadása
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## 5. lépés: Hozzon létre egy erőforrás-hozzárendelést
Hozzon létre egy új erőforrás-hozzárendelést a feladathoz:
```java
// Hozzon létre egy új erőforrás-hozzárendelést
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## 6. lépés: Időzített adatok létrehozása
Erőforrás-hozzárendelés időfázisos adatok generálása:
```java
// Erőforrás-hozzárendelés időfázisos adatok generálása
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## 7. lépés: Ossza fel a feladatot
Osszuk fel a feladatot több részre:
```java
// Osszuk 3 részre a feladatot
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (folytatás a példával)
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan oszthat fel feladatokat az Aspose.Tasks for Java használatával. Ez a nagy teljesítményű könyvtár leegyszerűsíti a feladatkezelést a Java-projektekben, hatékony megoldásokat kínálva a projektek ütemezésének és erőforrás-elosztásának optimalizálására.
## Gyakran Ismételt Kérdések
### Feloszthatok-e különböző időtartamú feladatokat?
Igen, beállíthatja a feladatok időtartamát a projekt követelményei szerint.
### Az Aspose.Tasks for Java kompatibilis az összes Java-verzióval?
Az Aspose.Tasks for Java úgy lett kialakítva, hogy zökkenőmentesen működjön a különböző Java-verziókkal, biztosítva a kompatibilitást.
### Használhatom ingyenesen az Aspose.Tasks for Java-t?
Az Aspose.Tasks for Java ingyenes próbaverziót kínál, amellyel vásárlás előtt felfedezheti a szolgáltatásait.
### Hogyan kaphatok támogatást az Aspose.Tasks for Java számára?
 Meglátogatni a[Aspose.Tasks for Java támogatási fórum](https://forum.aspose.com/c/tasks/15) segítséget kapni és kapcsolatba lépni a közösséggel.
### Szükségem van ideiglenes licencre az Aspose.Tasks for Java számára?
 Ideiglenes jogosítványt szerezhet be[ez a link](https://purchase.aspose.com/temporary-license/) tesztelési és értékelési célokra.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
