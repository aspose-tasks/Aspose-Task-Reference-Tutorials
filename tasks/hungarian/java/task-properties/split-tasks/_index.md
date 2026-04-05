---
date: 2026-02-26
description: Tanulja meg, hogyan oszthatja fel a feladatokat az Aspose.Tasks for Java
  segítségével – a feladatok felosztásáról, a projekt naptár beállításáról és az erőforrás-hozzárendelés
  létrehozásáról szóló végleges útmutató.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan osztható fel a feladatok az Aspose.Tasks-ben
url: /hu/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan oszthatók fel a feladatok az Aspose.Tasks-ben

## Bevezetés
Ha **hogyan oszthatók fel a feladatok** Java‑alapú projektben keresed, jó helyen vagy. Az Aspose.Tasks for Java tiszta, programozott módot biztosít egy hosszú futású feladat kisebb, kezelhető részekre bontásához, ami segít az erőforrás kiegyenlítésben, a pontos jelentéskészítésben és a szorosabb projekt ütemezésben. Ebben az útmutatóban végigvezetünk a teljes folyamaton – a projekt naptár beállításától a erőforrás hozzárendelés létrehozásáig, végül a feladat több szegmensre bontásáig.

## Gyors válaszok
- **Mi a feladat felosztás?** Egyetlen feladat több kisebb intervallumra osztása, miközben megőrzi a teljes időtartamát.  
- **Miért oszthatók fel a feladatok Java‑ban?** Lehetővé teszi a pontos erőforrás-elosztást és a jobb előrehaladás‑követést.  
- **Melyik könyvtár segít?** Az Aspose.Tasks for Java beépített módszereket biztosít a felosztáshoz és az idő‑fázisoláshoz.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez használható; a licenc a termeléshez kötelező.  
- **Melyik Java verzió támogatott?** A könyvtár a Java 8‑as és újabb verziókkal működik.

## Előfeltételek
Mielőtt belemerülnél az útmutatóba, győződj meg róla, hogy a következő előfeltételek rendelkezésre állnak:
- Java Development Kit (JDK) telepítve van a gépeden.  
- Aspose.Tasks for Java könyvtár letöltve és hozzáadva a projektedhez. Letöltheted a [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) oldalról.

## Csomagok importálása
Kezdd a szükséges csomagok importálásával a Java projektedbe:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## 1. lépés: Új projekt létrehozása
Kezdd egy új projekt létrehozásával az Aspose.Tasks könyvtár segítségével:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## 2. lépés: Projekt naptár beállítása
A **projekt naptár** beállítása meghatározza a munkanapokat, ünnepnapokat és az ütemezés általános idővonalát. Ez a lépés elengedhetetlen a pontos idő‑fázisos számításokhoz.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## 3. lépés: Gyökér feladat hozzáadása
Minden projektnek szüksége van egy gyökér konténerre. Gyökér feladat hozzáadásával helyet biztosítasz az összes további feladat csatolásához.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## 4. lépés: Új feladat hozzáadása a felosztáshoz
Hozd létre a feladatot, amelyet fel szeretnél osztani. Itt példaként három napos időtartamot állítunk be.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## 5. lépés: Erőforrás hozzárendelés létrehozása
A **resource assignment** összekapcsol egy erőforrást (vagy helyőrzőt) a feladattal. Ez szükséges a idő‑fázisos adatok generálása előtt.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## 6. lépés: Idő‑fázisos adatok generálása
Az idő‑fázisos adatok azt mutatják, hogyan oszlik el a munka a feladat időtartama alatt. Generálása előkészíti a feladatot a felosztáshoz.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## 7. lépés: Feladat felosztása
Most **felosztjuk a feladatot részekre**. Ebben a példában a háromnapos feladatot három egynapos szegmensre bontjuk.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Miért oszthatók fel a feladatok?
A feladatok felosztása finomabb irányítást biztosít a következők felett:
- **Resource leveling:** Különböző erőforrások hozzárendelése minden szegmenshez.
- **Progress tracking:** Állapot frissítése szegmensenként.
- **Reporting:** Részletesebb Gantt-diagramok és jelentések generálása.

## Gyakori problémák és megoldások
- **Missing calendar data:** Győződj meg róla, hogy a felosztás előtt meghívod a `timephasedDataFromTaskDuration` metódust.  
- **Zero‑duration segments:** Ellenőrizd, hogy minden felosztott intervallum nem nulla időtartamú legyen; különben a könyvtár figyelmen kívül hagyja.  
- **License exceptions:** Érvényes licenc nélkül való futtatás vízjelet adhat az exportált fájlokhoz.

## Gyakran ismételt kérdések
### Oszthatok-e fel a feladatokat különböző időtartamokkal?
Igen, minden rész időtartamát a projekt igényeihez igazíthatod.

### Az Aspose.Tasks for Java kompatibilis minden Java verzióval?
Az Aspose.Tasks for Java úgy van tervezve, hogy zökkenőmentesen működjön a Java 8‑as és újabb verziókkal, biztosítva a széles körű kompatibilitást.

### Használhatom ingyen az Aspose.Tasks for Java‑t?
Az Aspose.Tasks for Java ingyenes próba verziót kínál, amely lehetővé teszi a funkciók kipróbálását vásárlás előtt.

### Hogyan kaphatok támogatást az Aspose.Tasks for Java‑hez?
Látogasd meg az [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) oldalt, hogy segítséget kapj és csatlakozz a közösséghez.

### Szükségem van ideiglenes licencre az Aspose.Tasks for Java‑hez?
Ideiglenes licencet szerezhetsz a [this link](https://purchase.aspose.com/temporary-license/) címről tesztelési és értékelési célokra.

---

**Utoljára frissítve:** 2026-02-26  
**Tesztelve:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}