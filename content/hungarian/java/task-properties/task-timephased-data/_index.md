---
title: Feladat időfázisú adatok az Aspose.Tasks-ban
linktitle: Feladat időfázisú adatok az Aspose.Tasks-ban
second_title: Aspose.Tasks Java API
description: Fedezze fel az Aspose.Tasks for Java-t és a főfeladat időfázisú adatkezelését. Töltse le a könyvtárat, élvezze az ingyenes próbaverziót, és egyszerűsítse projektje nyomon követését.
type: docs
weight: 34
url: /hu/java/task-properties/task-timephased-data/
---
## Bevezetés
projektmenedzsment területén a feladatok időfázisos adatainak pontos nyomon követése elengedhetetlen a hatékony projektvégrehajtáshoz. Az Aspose.Tasks for Java hatékony eszköz a folyamat egyszerűsítésére, robusztus szolgáltatásokat és rugalmasságot kínálva. Ez az oktatóanyag végigvezeti Önt az Aspose.Tasks for Java használatán a feladatok időfázisos adatainak hatékony kezeléséhez.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Java fejlesztői környezet: Győződjön meg arról, hogy a Java telepítve van a rendszeren.
-  Aspose.Tasks for Java Library: Töltse le és foglalja bele az Aspose.Tasks könyvtárat a projektbe. Megtalálhatod a könyvtárat[itt](https://releases.aspose.com/tasks/java/).
- Dokumentumkönyvtár: Állítson be egy könyvtárat a projektdokumentumokhoz.
## Csomagok importálása
Java projektjében importálja az Aspose.Tasks szükséges csomagjait:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## 1. lépés: Állítsa be a projekt kezdési dátumát
```java
Project project = new Project(dataDir + "project.xml");
// Kiegészítő kód a csomagok importálásához
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Magyarázat: Inicializáljon egy naptárobjektumot, állítsa be a kezdési dátumot, és alkalmazza a projektre.
## 2. lépés: Határozza meg a feladatot és az erőforrást
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Magyarázat: Hozzon létre egy feladatot és erőforrást, állítsa be a normál és a túlórák díjait.
## 3. lépés: Állítsa be a feladat időtartamát
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Magyarázat: Határozza meg a feladat időtartamát (pl. 6 nap).
## 4. lépés: Rendeljen erőforrást a feladathoz
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Magyarázat: Rendelje hozzá az erőforrást a feladathoz.
## 5. lépés: Erőforrás-hozzárendelés konfigurálása
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Magyarázat: Állítsa be az erőforrás-hozzárendelés paramétereit, például leállítást, folytatást és munkakontúrt.
## 6. lépés: Állítsa be az alapvonalat
```java
project.setBaseline(BaselineType.Baseline);
```
Magyarázat: Állítsa be a projekt alapértékét.
## 7. lépés: Frissítse a Feladat befejezését
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Magyarázat: Adja meg a feladat teljesítési százalékát.
## 8. lépés: Időfázisos adatok lekérése
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Magyarázat: Az időfázisos adatok lekérése a hozzárendelés hátralévő munkájához.
## 9. lépés: Időfázisos adatok megjelenítése
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Kiegészítő kód más értékek megjelenítéséhez
```
Magyarázat: Az időfázisos adatok kiadása és megjelenítése.
## Következtetés
feladatok időfázisos adatainak hatékony kezelése elengedhetetlen a projekt sikeréhez. Az Aspose.Tasks for Java leegyszerűsíti ezt a folyamatot, és átfogó funkciókat biztosít. Ennek az oktatóanyagnak a követésével zökkenőmentesen integrálhatja az Aspose.Tasks-t Java-projektjébe, így biztosítva a projekt idővonalainak és az erőforrások elosztásának pontos vezérlését.
## Gyakran Ismételt Kérdések
### K: Használhatom az Aspose.Tasks for Java-t bármely Java projektben?
V: Igen, az Aspose.Tasks for Java minden Java-alapú projekttel kompatibilis.
### K: Hol találok további támogatást az Aspose.Tasks for Java számára?
 V: Látogassa meg a[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) támogatásért és megbeszélésekért.
### K: Elérhető az Aspose.Tasks for Java ingyenes próbaverziója?
 V: Igen, felfedezheti az ingyenes próbaverziót[itt](https://releases.aspose.com/).
### K: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java számára?
 V: Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### K: Hol vásárolhatom meg az Aspose.Tasks for Java-t?
 V: Megvásárolhatja az Aspose.Tasks-t Java-hoz[itt](https://purchase.aspose.com/buy).