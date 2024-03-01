---
title: Állítsa le és folytassa a feladatot az Aspose.Tasks alkalmazásban
linktitle: Állítsa le és folytassa a feladatot az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Fedezze fel az Aspose.Tasks for Java erejét a feladatok leállításáról és folytatásáról szóló, lépésenkénti útmutatónkkal. Javítsa a projektmenedzsmentet zökkenőmentesen!
type: docs
weight: 30
url: /hu/java/task-properties/stop-resume-task/
---
## Bevezetés
A Java fejlesztés területén a feladatok hatékony kezelése a projektvégrehajtás kulcsfontosságú szempontja. Az Aspose.Tasks for Java robusztus megoldást kínál a feladatok kezeléséhez hatékony funkcióival. Ebben az oktatóanyagban egy konkrét funkcióval foglalkozunk – a feladatok leállításával és folytatásával. Ennek a lépésről-lépésre szóló útmutatónak a követésével zökkenőmentesen integrálhatja ezt a funkciót Java-projektjeibe.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- A Java programozás alapvető ismerete.
- Java Development Kit (JDK) telepítve a rendszerére.
- Aspose.Tasks a Java könyvtárhoz letöltve és hozzáadva a projekthez. től szerezheti be[itt](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
A folyamat elindításához feltétlenül importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## 1. lépés: Inicializálás
 Kezdje a projekt inicializálásával és a létrehozásával`ChildTasksCollector` példa az összes feladat összegyűjtésére.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 2. lépés: Állítsa be a minimális dátumot
Határozzon meg egy minimális dátumot a leállítandó vagy folytatandó feladatok szűrésére.
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## 3. lépés: A feladatok leállítása és folytatása
Ismételje meg a feladatokat, ellenőrizze és nyomtassa ki a leállítási és folytatási dátumokat.
```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```
Ismételje meg ezeket a lépéseket a Java projektben, hogy zökkenőmentesen integrálja a leállítás és folytatás funkciót az Aspose.Tasks for Java segítségével.
## Következtetés
Ebben az oktatóanyagban a feladatok leállításának és folytatásának folyamatát vizsgáltuk az Aspose.Tasks for Java használatával. A fent vázolt lépések követésével javíthatja projektkezelési képességeit és egyszerűsítheti a feladatok végrehajtását.
## Gyakran Ismételt Kérdések
### Az Aspose.Tasks for Java alkalmas nagyszabású projektekhez?
Teljesen! Az Aspose.Tasks for Java különböző méretű projektek kezelésére készült, így biztosítva a hatékonyságot és a megbízhatóságot.
### Testreszabhatom a feladatok leállításának és folytatásának dátumát?
Igen, a bemutatott példa rugalmasságot tesz lehetővé a minimális dátum beállításában a projekt követelményei szerint.
### Hol találok további támogatást az Aspose.Tasks for Java számára?
 Meglátogatni a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) közösségi támogatásra és beszélgetésekre.
### Létezik ingyenes próbaverzió az Aspose.Tasks for Java számára?
 Igen, hozzáférhet a[ingyenes próbaverzió](https://releases.aspose.com/) hogy vásárlás előtt fedezze fel a funkciókat.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java számára?
 Ideiglenes jogosítványt szerezhet[itt](https://purchase.aspose.com/temporary-license/) tesztelési célokra.