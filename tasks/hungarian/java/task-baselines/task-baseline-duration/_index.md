---
title: Task Baseline Duration Management in Aspose.Tasks
linktitle: Task Baseline Duration Management in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kezelheti hatékonyan az alapfeladatokat az MS Projectben az Aspose.Tasks for Java használatával. Ez az oktatóanyag lépésről lépésre végigvezeti a folyamaton.
weight: 12
url: /hu/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Task Baseline Duration Management in Aspose.Tasks

## Bevezetés
A feladatok alaphelyzeteinek kezelése az MS Projectben kulcsfontosságú a projekttervezés és -követés szempontjából. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet hatékonyan kezelni a feladatok alapidőtartamát az Aspose.Tasks for Java használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java fejlesztői környezet: Győződjön meg arról, hogy a Java Development Kit (JDK) telepítve van a rendszerén.
2.  Aspose.Tasks Library: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat innen[itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először importálja a Java projekthez szükséges csomagokat:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## 1. lépés: Hozzon létre egy projektpéldányt
Inicializáljon egy új projektpéldányt a következő kóddal:
```java
Project project = new Project();
```
## 2. lépés: Hozzon létre egy feladatbázist
Hozzon létre egy új feladatot, és állítsa be az alapvonalat a következő kóddal:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## 3. lépés: Jelenítse meg a Feladat alapinformációit
A feladat alapinformációinak lekérése és megjelenítése, például időtartam, kezdési dátum, befejezési dátum és egyebek:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## 4. lépés: Ellenőrizze az ideiglenes kiindulási és fix költségeket
Ellenőrizze, hogy az alapvonal köztes alapvonal-e, és kérje le a hozzá kapcsolódó fix költségeket:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## 5. lépés: Időfázisos adatok nyomtatása
A feladat alapvonalához tartozó időfázisos adatok nyomtatása:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Az alábbi lépések követésével hatékonyan kezelheti a feladatok alapidőtartamát az MS Projectben az Aspose.Tasks for Java segítségével.

## Következtetés
A feladatok alaphelyzeteinek kezelése elengedhetetlen a projektmenedzsmenthez, lehetővé téve a tervezett ütemezéstől való eltérések nyomon követését. Az Aspose.Tasks for Java segítségével ez a folyamat egyszerűbbé és hatékonyabbá válik, lehetővé téve a projektek jobb vezérlését és kézbesítését.
## GYIK
### Mi az alapfeladat az MS Projectben?
Az MS Projectben a feladat alapvonala egy feladat kezdeti tervezett ütemezésének pillanatképe, beleértve a kezdő dátumot, a befejezési dátumot és az időtartamot.
### Miért fontos az alapfeladatok kezelése?
A feladatok alaphelyzeteinek kezelése segít a tervezett ütemezés és a projekt tényleges előrehaladásának összehasonlításában, megkönnyítve a nyomon követést és a döntéshozatalt.
### Módosíthatom a feladat alapvonalát, miután beállította?
Igen, módosíthatja a feladatok alapvonalait az MS Projectben, hogy tükrözze a projektterv változásait. Mindazonáltal elengedhetetlen az eredeti alapvonaltól való eltérések dokumentálása.
### Az Aspose.Tasks támogat más projektmenedzsment funkciókat?
Igen, az Aspose.Tasks funkciók széles skáláját kínálja a projektmenedzsmenthez, beleértve a feladatütemezést, az erőforrások elosztását és a Gantt-diagram generálását.
### Hol találok támogatást az Aspose.Tasks számára?
 Az Aspose.Tasks támogatást itt találja[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15), ahol kérdéseket tehet fel, és kapcsolatba léphet más felhasználókkal.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
