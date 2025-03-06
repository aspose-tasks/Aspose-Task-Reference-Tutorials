---
title: Kezelje a szintezési késleltetési tulajdonságokat az Aspose.Tasks-ban
linktitle: Kezelje az Aspose.Tasks erőforrás-hozzárendelések szintezési késleltetési tulajdonságait
second_title: Aspose.Tasks Java API
description: Ezzel az átfogó oktatóanyaggal megtudhatja, hogyan kezelheti a szintezési késleltetési tulajdonságokat az erőforrás-hozzárendelésekhez az Aspose.Tasks for Java programban.
weight: 17
url: /hu/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kezelje a szintezési késleltetési tulajdonságokat az Aspose.Tasks-ban

## Bevezetés
Ebben az oktatóanyagban az Aspose.Tasks for Java erőforrás-hozzárendeléseihez tartozó szintezési késleltetési tulajdonságok kezelésének folyamatát mutatjuk be. Az Aspose.Tasks egy hatékony Java-könyvtár, amely lehetővé teszi a Microsoft Project fájlokkal való munkát anélkül, hogy a Microsoft Project-et telepítenie kellene a rendszerére.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a Java JDK telepítve van a rendszeren. Letöltheti és telepítheti a[weboldal](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Töltse le az Aspose.Tasks for Java könyvtárat a[letöltési oldal](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először is importálja a szükséges csomagokat a Java projektbe az Aspose.Tasks funkciók használatához:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 1. lépés: Hozzon létre egy projektobjektumot
 Példányosítás a`Project` tárgy:
```java
Project prj = new Project();
```
## 2. lépés: Hozzon létre egy feladatot
Adjon hozzá egy feladatot a projekthez:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## 3. lépés: Állítsa be a feladat kezdési dátumát és időtartamát
Állítsa be a feladat kezdési dátumát és időtartamát:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## 4. lépés: Adjon hozzá egy erőforrást
Adjon hozzá egy erőforrást a projekthez:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## 5. lépés: Hozzon létre egy erőforrás-hozzárendelést
Hozzon létre erőforrás-hozzárendelést a feladathoz és az erőforráshoz:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## 6. lépés: Állítsa be a szintezési késleltetést
Állítsa be a szintezési késleltetést a hozzárendeléshez:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## 7. lépés: Eredmények megjelenítése
Nyomtassa ki a szintezési késleltetést és egyéb releváns információkat:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kell kezelni a szintezési késleltetés tulajdonságait az Aspose.Tasks for Java erőforrás-hozzárendeléséhez. Az alábbi lépések követésével hatékonyan kezelheti az erőforrás-hozzárendeléseket a Java-projektekben.
## GYIK
### K: Használhatom az Aspose.Tasks-t más Java könyvtárakkal?

V: Igen, az Aspose.Tasks integrálható más Java-könyvtárakba a projektkezelési képességek javítása érdekében.

### K: Az Aspose.Tasks kompatibilis a Microsoft Project fájlok különböző verzióival?

V: Igen, az Aspose.Tasks támogatja a Microsoft Project fájlok különféle verzióit, így biztosítja a kompatibilitást a különböző környezetekben.

### K: Hol találok további támogatást az Aspose.Tasks számára?

 V: Támogatást és forrásokat találhat a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).

### K: Kipróbálhatom az Aspose.Tasks-t vásárlás előtt?

 V: Igen, beszerezheti az Aspose.Tasks ingyenes próbaverzióját a[kiadások oldala](https://releases.aspose.com/).

### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks számára?

 V: Ideiglenes licencet kérhet a[ideiglenes licenc oldal](https://purchase.aspose.com/temporary-license/) értékelési célokra.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
