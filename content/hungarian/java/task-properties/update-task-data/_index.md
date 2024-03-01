---
title: Frissítse a feladatadatokat MPP formátumra az Aspose.Tasks alkalmazásban
linktitle: Frissítse a feladatadatokat MPP formátumra az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan frissítheti a feladatadatokat MPP formátumra az Aspose.Tasks for Java segítségével. Kövesse lépésről lépésre útmutatónkat a hatékony projektmenedzsment érdekében.
type: docs
weight: 35
url: /hu/java/task-properties/update-task-data/
---
## Bevezetés
Üdvözöljük lépésenkénti útmutatónkban a feladatadatok MPP formátumra történő frissítéséről az Aspose.Tasks for Java használatával. Ebben az oktatóanyagban végigvezetjük a folyamaton, biztosítva, hogy minden lépést világosan megértsen. Az Aspose.Tasks for Java robusztus megoldást kínál a Microsoft Project fájlokkal való munkavégzéshez, és ennek az útmutatónak a végére képes lesz hatékonyan frissíteni a feladatok adatait MPP formátumban.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
-  Aspose.Tasks for Java: Győződjön meg arról, hogy telepítve van az Aspose.Tasks könyvtár. Letöltheti a[kiadási oldal](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszeren.
- Integrált fejlesztőkörnyezet (IDE): Használjon tetszőleges IDE-t a Java fejlesztéshez.
## Csomagok importálása
Kezdje azzal, hogy importálja a szükséges csomagokat a Java projektbe. A következő részlet bemutatja a csomagok importálását:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Hozza létre és konfigurálja a kezdeti feladatot
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Folytatás a kód többi részével)
```
## 2. Állítsa be a kezdési dátumot és az időtartamot
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Folytatás a kód többi részével)
```
## 3. Hozzon létre egy összefoglaló feladatot
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Folytatás a kód többi részével)
```
## 4. Állítsa be a határidőt és a feladatmegjegyzéseket
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Folytatás a kód többi részével)
```
## 5. Állítsa be a feladatkényszereket
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Folytatás a kód többi részével)
```
## 6. Hozzon létre további feladatokat
```java
//Hozzon létre 10 új feladatot
for (int i = 0; i < 10; i++) {
    //... (Folytatás a kód többi részével)
}
//... (Folytatás a kód többi részével)
```
## 7. Mentse a projektet
```java
// Mentse el a projektet
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Az alábbi lépések végrehajtásával sikeresen frissítette a feladatadatokat MPP formátumra az Aspose.Tasks for Java segítségével.
## Következtetés
Gratulálunk! Elkészített egy átfogó útmutatót a feladatadatok MPP formátumú frissítéséről az Aspose.Tasks for Java használatával. Ez a hatékony könyvtár leegyszerűsíti a projektkezelési feladatokat, így értékes eszköz a Java fejlesztők számára.
## GYIK
### K: Hol találom az Aspose.Tasks for Java dokumentációt?
 V: A dokumentáció elérhető[itt](https://reference.aspose.com/tasks/java/).
### K: Hogyan tölthetem le az Aspose.Tasks for Java-t?
 V: Letöltheti a[kiadási oldal](https://releases.aspose.com/tasks/java/).
### K: Van ingyenes próbaverzió?
 V: Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### K: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?
 V: Látogassa meg a támogatási fórumot[itt](https://forum.aspose.com/c/tasks/15).
### K: Kínál ideiglenes licenceket tesztelési célokra?
 V: Igen, beszerezhet ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).