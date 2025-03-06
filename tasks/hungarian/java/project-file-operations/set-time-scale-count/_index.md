---
title: Az MS Project Time Scale Count elsajátítása az Aspose.Tasks programban
linktitle: Állítsa be az időskálát az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kezelheti hatékonyan az időskálák számát az MS Projectben az Aspose.Tasks for Java segítségével. Könnyedén optimalizálhatja a projekt vizualizációját és kezelését.
weight: 22
url: /hu/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az MS Project Time Scale Count elsajátítása az Aspose.Tasks programban

## Bevezetés
Az időskálák számának kezelése az MS Projectben jelentősen befolyásolhatja a projekt megjelenítését és kezelését. Az Aspose.Tasks for Java segítségével, amely egy hatékony API a projektmenedzsment feladatok programozott kezelésére, hatékonyan manipulálhatja az időskálák számát, hogy a projektnézeteket az Ön egyedi igényeihez igazítsa.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következők vannak a helyükön:
1. Java fejlesztői környezet: Győződjön meg arról, hogy a Java Development Kit (JDK) telepítve van a rendszerén.
2.  Aspose.Tasks for Java Library: Töltse le és telepítse az Aspose.Tasks for Java könyvtárat. től lehet kapni[itt](https://releases.aspose.com/tasks/java/).
3. Java programozási alapismeretek: A Java programozási nyelv ismerete előnyt jelent.

## Csomagok importálása
Importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 1. lépés: Állítsa be az adatkönyvtárat
Határozza meg annak az adatkönyvtárnak az elérési útját, ahol a projektfájlokat tárolni fogja:
```java
String dataDir = "Your Data Directory";
```
 Cserélje ki`"Your Data Directory"` az adatkönyvtár elérési útjával.
## 2. lépés: Hozzon létre projektpéldányt
 Példányosítson egy újat`Project` tárgy:
```java
Project project = new Project();
```
Ez létrehoz egy új projektobjektumot.
## 3. lépés: A Gantt-diagram nézet konfigurálása
 Hozzon létre egy`GanttChartView` objektum a Gantt-diagram nézet konfigurálásához:
```java
GanttChartView view = new GanttChartView();
```
## 4. lépés: Állítsa be az időskálát az alsó szinthez
Állítsa be a számlálást és a pipák láthatóságát az alsó időskála szinthez:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Ez határozza meg az intervallumok számát, és azt, hogy megjelenjenek-e az alsó szint jelölései.
## 5. lépés: Állítsa be az időskálát a középső szinthez
Hasonlóképpen állítsa be a középső időskálát:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## 6. lépés: Nézet hozzáadása a projekthez
Adja hozzá a konfigurált nézetet a projekthez:
```java
project.getViews().add(view);
```
Ez hozzáadja a testreszabott nézetet a projekthez.
## 7. lépés: Tesztadatok hozzáadása a projekthez
Adjon hozzá néhány tesztadatot a projekthez demonstráció céljából:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Ez két feladatot hoz létre meghatározott időtartammal.
## 8. lépés: Projekt mentése PDF formátumban
Mentse el a projektet PDF fájlként:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Ezzel PDF fájlba menti a projektet az alkalmazott konfigurációkkal.

## Következtetés
Az időskálák számának hatékony kezelése az MS Projectben az Aspose.Tasks for Java segítségével lehetővé teszi a projektnézetek testreszabását a jobb megjelenítés és kezelés érdekében.
## GYIK
### K: Az Aspose.Tasks for Java kezelheti a nagyméretű projektfájlokat?
V: Igen, az Aspose.Tasks for Java hatékonyan képes kezelni a nagyméretű projektfájlokat.
### K: Az Aspose.Tasks for Java kompatibilis a különböző Java IDE-kkel?
V: Igen, az Aspose.Tasks for Java zökkenőmentesen működik a népszerű Java Integrated Development Environment-ekkel (IDE), mint például az Eclipse és az IntelliJ IDEA.
### K: Testreszabhatom a Gantt-diagramok megjelenését az Aspose.Tasks for Java segítségével?
V: Természetesen az Aspose.Tasks for Java kiterjedt lehetőségeket biztosít a Gantt-diagramok megjelenésének testreszabásához az Ön igényei szerint.
### K: Elérhető az Aspose.Tasks for Java próbaverziója?
 V: Igen, ingyenes próbaverziót szerezhet be a webhelyről[itt](https://releases.aspose.com/).
### K: Hol kaphatok támogatást az Aspose.Tasks for Java-hoz?
 V: Támogatást és segítséget az Aspose.Tasks fórumon találhat[itt](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
