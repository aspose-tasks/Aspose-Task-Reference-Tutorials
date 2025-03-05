---
title: Időfázisú adatok létrehozása az Aspose.Tasks programban
linktitle: Időfázisú adatokat generál az Aspose.Tasks erőforrás-hozzárendeléseihez
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan hozhat létre időfázisú adatokat erőforrás-hozzárendelésekhez az Aspose.Tasks for Java használatával. Növelje a projektmenedzsment hatékonyságát ezzel az átfogó útmutatóval.
type: docs
weight: 24
url: /hu/java/resource-assignments/timephased-data-generation/
---
## Bevezetés
Ebben az oktatóanyagban az Aspose.Tasks for Java segítségével történő erőforrás-hozzárendelésekhez való időfázisos adatok generálásának folyamatát mutatjuk be. Az időzített adatok értékes betekintést nyújtanak az erőforrások időbeli elosztásába a projekten belül, segítve a projektmenedzsereket megalapozott döntések meghozatalában.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren. A JDK-t letöltheti és telepítheti innen[itt](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java Library: rendelkeznie kell az Aspose.Tasks for Java könyvtárral. Letöltheti a[weboldal](https://releases.aspose.com/tasks/java/).

## Csomagok importálása
Először is importáljuk a szükséges csomagokat az Aspose.Tasks használatához:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## 1. lépés: Olvassa el az MPP forrásfájlt
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
// Olvassa el a forrás MPP fájlt
Project project = new Project(dataDir + "project.mpp");
```
## 2. lépés: Feladat- és erőforrás-hozzárendelés lekérése
```java
// Szerezd meg a Projekt első feladatát
Task task = project.getRootTask().getChildren().getById(1);
// Szerezze meg a projekt első erőforrás-hozzárendelését
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## 3. lépés: Hozzon létre időfázisú adatokat lapos kontúrral
```java
// A lapos kontúr az alapértelmezett kontúr
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 4. lépés: Változtassa meg a Kontúrt Teknősre
```java
// Változtassa meg a kontúrt Teknősre
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 5. lépés: A Contour módosítása BackLoaded értékre
```java
// Változtassa meg a kontúrt BackLoaded-re
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 6. lépés: A Contour módosítása FrontLoaded-re
```java
// Változtassa meg a kontúrt FrontLoaded-re
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 7. lépés: Változtassa meg a kontúrt Csengőre
```java
// Változtassa meg a kontúrt Bell-re
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 8. lépés: Változtassa meg a kontúrt EarlyPeak-re
```java
// Változtassa meg a kontúrt EarlyPeak-re
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 9. lépés: Változtassa meg a kontúrt LatePeak-re
```java
// Változtassa meg a kontúrt LatePeak-re
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## 10. lépés: Változtassa meg a kontúrt DoublePeak-re
```java
// Változtassa meg a kontúrt DoublePeak-re
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan állíthat elő időfázisú adatokat az erőforrás-hozzárendelésekhez az Aspose.Tasks for Java használatával. A különböző munkakontúrok megértése segíthet a projektmenedzsereknek hatékonyan kezelni az erőforrások elosztását és ütemezését projektjeikben.
## GYIK
### Használhatom az Aspose.Tasks-t más Java könyvtárakkal?
Igen, az Aspose.Tasks integrálható más Java-könyvtárakba a projektkezelési képességek javítása érdekében.
### Az Aspose.Tasks alkalmas nagyvállalati projektekre?
Természetesen az Aspose.Tasks minden méretű projekt kezelésére készült, beleértve a nagyvállalati projekteket is.
### Az Aspose.Tasks támogatja a különböző projektfájlformátumokat?
Igen, az Aspose.Tasks különféle projektfájlformátumokat támogat, beleértve az MPP-t, az XML-t és az MPX-et.
### Testreszabhatom a munkakontúrokat a projekt követelményei szerint?
Igen, az Aspose.Tasks lehetővé teszi a felhasználók számára, hogy egyedi munkakontúrokat határozzanak meg, hogy megfeleljenek konkrét projektszükségleteiknek.
### Van olyan közösségi fórum, ahol segítséget kaphatok az Aspose.Tasks-szal kapcsolatban?
 Igen, meglátogathatja a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) támogatásért és megbeszélésekért.