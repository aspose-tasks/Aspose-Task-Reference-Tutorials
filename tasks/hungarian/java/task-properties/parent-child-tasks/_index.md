---
title: Szülői és gyermeki feladatok kezelése az Aspose.Tasks alkalmazásban
linktitle: Szülői és gyermeki feladatok kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Növelje a projektmenedzsment hatékonyságát az Aspose.Tasks for Java segítségével. Ismerje meg a szülői és gyermeki feladatokat lépésről lépésre. Kezd el most!
weight: 24
url: /hu/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Szülői és gyermeki feladatok kezelése az Aspose.Tasks alkalmazásban

## Bevezetés
A projektmenedzsment területén a hatékony feladatszervezés kulcsfontosságú. Az Aspose.Tasks for Java robusztus megoldást kínál a szülői és gyermeki feladatok hatékony kezelésére. Ebben az oktatóanyagban végigvezetjük az Aspose.Tasks for Java használatán a projektfeladatok egyszerűsítéséhez.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- A Java programozás alapvető ismerete.
-  Aspose.Tasks for Java könyvtár telepítve. Letöltheti[itt](https://releases.aspose.com/tasks/java/).
- A rendszeren beállított Java Integrated Development Environment (IDE).
## Csomagok importálása
Kezdésként importálja a szükséges csomagokat a Java projektbe. Ezek a csomagok zökkenőmentes integrációt tesznek lehetővé az Aspose.Tasks Java funkciókhoz.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## 1. lépés: Állítsa be a projekt kezdési dátumát
Kezdje a projekt kezdési dátumának és egyéb releváns paramétereinek beállításával.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Itt adható meg további kód a csomagimportáláshoz
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## 2. lépés: Szülői feladat hozzáadása (1. feladat)
Hozzon létre egy „1. feladat” nevű szülőfeladatot, és konfigurálja a tulajdonságait.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## 3. lépés: Adja hozzá a Szülői feladatot (2. feladat) a Gyermekfeladatokkal
Most adjon hozzá egy másik „2. feladat” nevű szülőfeladatot, és vegyen fel gyermekfeladatokat (3. és 4. feladat).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Adjon hozzá gyermekfeladatokat a 2. feladathoz
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// A Task 3 és Task 4 további konfigurációja itt adható meg
```
## 4. lépés: A gyermekfeladatok konfigurálása
Adja meg a kezdési dátumokat, időtartamokat és megszorításokat a 3. és a 4. feladathoz.
```java
// Konfigurálja a 3. feladatot
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Konfigurálja a 4. feladatot
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## 5. lépés: Frissítse a feladat befejezési százalékát
Állítsa be a 3. és 4. feladat teljesítési százalékát.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## 6. lépés: Mentse el a projektet
Végül mentse el a projektet az alkalmazott változtatásokkal.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Ez a részletes útmutató bemutatja, hogyan kezelheti hatékonyan a szülői és gyermeki feladatokat az Aspose.Tasks for Java használatával. Kísérletezzen különböző konfigurációkkal, hogy megfeleljen a projekt követelményeinek.
## Következtetés
Összefoglalva, az Aspose.Tasks for Java felhatalmazza a fejlesztőket a projektfeladatok hatékony kezelésére, biztosítva a zökkenőmentes szervezést és nyomon követést. Hajtsa végre a vázolt lépéseket projektmenedzsment képességeinek fejlesztéséhez.
## GYIK
### Az Aspose.Tasks for Java kompatibilis a különböző projektfájlformátumokkal?
Igen, az Aspose.Tasks for Java különféle projektfájlformátumokat támogat, beleértve az MPP-t és az XML-t.
### Testreszabhatom a feladat tulajdonságait az oktatóanyagon kívül?
Teljesen! Az Aspose.Tasks for Java kiterjedt testreszabási lehetőségeket kínál a feladat tulajdonságaihoz.
### Létezik olyan közösségi fórum az Aspose.Tasks számára, ahol támogatást kérhetek?
 Igen, meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásért.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java számára?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Hol találom az Aspose.Tasks for Java átfogó dokumentációját?
 A dokumentáció elérhető[itt](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
