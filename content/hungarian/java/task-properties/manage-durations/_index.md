---
title: A feladatok időtartamának kezelése az Aspose.Tasks alkalmazásban
linktitle: A feladatok időtartamának kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Fedezze fel az Aspose.Tasks for Java alkalmazást, és tanulja meg könnyedén kezelni a feladatok időtartamát. Kövesse lépésről lépésre útmutatónkat a hatékony projekttervezés és -végrehajtás érdekében.
type: docs
weight: 20
url: /hu/java/task-properties/manage-durations/
---
## Bevezetés
Az Aspose.Tasks for Java robusztus megoldást kínál a projektfeladatok és -időtartamok hatékony kezelésére. Ebben az oktatóanyagban megvizsgáljuk, hogyan kezelheti a feladatok időtartamát az Aspose.Tasks segítségével, és végigvezeti Önt az egyes lépéseken. Legyen szó tapasztalt fejlesztőről vagy kezdőről, ez az útmutató segít megérteni a projektekben a feladatok időtartamával történő munkavégzés lényegét.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
-  Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a gépen. Letöltheti[itt](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks könyvtár: Töltse le és foglalja bele a projektbe az Aspose.Tasks könyvtárat. Megtalálhatod a könyvtárat[itt](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
Java projektjében importálja a szükséges csomagokat az Aspose.Tasks használatához:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 1. lépés: Állítsa be projektjét
```java
// Hozzon létre egy új projektet
Project project = new Project();
```
## 2. lépés: Új feladat hozzáadása
```java
// Adjon hozzá egy új feladatot a projekthez
Task task = project.getRootTask().getChildren().add("Task");
```
## 3. lépés: A feladat időtartamának lekérése és konvertálása
```java
// Feladat időtartamának lekérése napokban (alapértelmezett időegység)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Az időtartam konvertálása óra időegységre
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## 4. lépés: Frissítse a feladat időtartamát 1 hétre
```java
// Növelje a feladat időtartamát 1 hétre
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## 5. lépés: Csökkentse a feladat időtartamát
```java
// Csökkentse a feladat időtartamát
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Az alábbi lépések követésével sikeresen kezelte a feladatok időtartamát az Aspose.Tasks for Java projektben.
## Következtetés
Ebben az oktatóanyagban a feladatok időtartamának kezelésének alapjait ismertetjük az Aspose.Tasks for Java használatával. Most már magabiztosan beépítheti ezeket a technikákat projektjeibe a hatékony feladatidő-kezelés érdekében.
## GYIK
### Az Aspose.Tasks kompatibilis az összes Java-verzióval?
Az Aspose.Tasks kompatibilis a Java 6 és újabb verzióival.
### Használhatom az Aspose.Tasks-t kereskedelmi projektekhez?
 Igen, használhatja az Aspose.Tasks-t személyes és kereskedelmi projektekhez egyaránt. Látogatás[itt](https://purchase.aspose.com/buy) az engedélyezési részletekért.
### Hol találhatok további támogatást és forrásokat?
 Meglátogatni a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásra és beszélgetésekre.
### Hogyan szerezhetek ideiglenes licencet tesztelési célból?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/) teszteléshez és értékeléshez.
### Elérhető az Aspose.Tasks ingyenes próbaverziója?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/) hogy fedezze fel az Aspose.Tasks-t vásárlás előtt.