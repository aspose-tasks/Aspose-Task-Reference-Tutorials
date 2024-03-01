---
title: Oldalak nyomtatása külön képként az Aspose.Tasks alkalmazásban
linktitle: Oldalak nyomtatása külön képként az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan nyomtathat oldalakat külön képekhez az Aspose.Tasks for Java programban. Javítsa a projekt vizualizációját ezzel a lépésenkénti útmutatóval.
type: docs
weight: 22
url: /hu/java/project-management/print-pages/
---
## Bevezetés
Ebben az oktatóanyagban végigvezetjük az Aspose.Tasks for Java segítségével oldalak nyomtatásának folyamatán. Ez a funkció különösen akkor lehet hasznos, ha külön kell megjelenítenie a projektelrendezéseket vagy a kritikus feladatokat.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren. Letöltheti innen[itt](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Töltse le és foglalja bele a projektébe az Aspose.Tasks for Java könyvtárat. től lehet kapni[itt](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Ügyeljen arra, hogy a szükséges csomagokat importálja a Java fájl elején:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## 1. lépés: Töltse be a projektadatokat
Először töltse be a projekt adatait az MPP fájlból:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## 2. lépés: Állítsa be a képmentési beállításokat
Adja meg a kép mentésének beállításait, beleértve a kezdő dátumot, a befejezési dátumot, a kritikus feladatokat, a jelmagyarázatot és a rácsvonalakat:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## 3. lépés: A rácsvonalak testreszabása
Testreszabhatja a kép rácsvonalait, megadva a típust, a színt és a mintát:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## 4. lépés: Mentse el a képeket
Mentse el a projekt elrendezését képként, egyetlen fájlként és külön fájlként is:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan nyomtathat oldalakat külön képekre az Aspose.Tasks for Java használatával. A fent vázolt lépések követésével hatékonyan vizualizálhatja a projektelrendezéseket és a kritikus feladatokat az Ön igényei szerint.
## GYIK
### K: Testreszabhatom a képformátumot a projektelrendezések mentésekor?
 V: Igen, az Aspose.Tasks for Java különféle képformátumokat támogat, például PNG, JPEG, BMP stb. A kívánt formátumot a`ImageSaveOptions` osztály.
### K: Az Aspose.Tasks for Java kompatibilis a különböző Java fejlesztői környezetekkel?
V: Igen, az Aspose.Tasks for Java kompatibilis a legtöbb Java fejlesztői környezettel, beleértve az Eclipse-t, az IntelliJ IDEA-t és a NetBeans-t.
### K: Integrálhatom az Aspose.Tasks for Java-t a Maven vagy Gradle projektembe?
V: Igen, az Aspose.Tasks for Java könnyen integrálható Maven vagy Gradle projektjébe, ha hozzáadja a megfelelő függőséget a`pom.xml` vagy`build.gradle` fájlt.
### K: Az Aspose.Tasks for Java támogatja a projektadatok exportálását a képeken kívül más formátumokba is?
V: Igen, az Aspose.Tasks for Java támogatja a projektadatok exportálását különféle formátumokba, például PDF, HTML, XLSX stb., rugalmasságot biztosítva az adatok megjelenítésében és jelentéseiben.
### K: Elérhető közösségi támogatás az Aspose.Tasks for Java számára?
 V: Igen, a webhelyen találhat közösségi támogatást, kérdéseket tehet fel, és kapcsolatba léphet más felhasználókkal[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).