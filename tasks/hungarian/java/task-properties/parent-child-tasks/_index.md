---
date: 2026-02-23
description: Tanulja meg, hogyan állíthatja be a projekt kezdő dátumát, a feladat
  időtartamát, és mentheti a projektet MPP formátumban az Aspose.Tasks for Java használatával.
  Kezelje hatékonyan a szülő‑ és gyermekfeladatokat.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projekt kezdő dátumának beállítása és szülő‑ és gyermekfeladatok kezelése az
  Aspose.Tasks‑ben
url: /hu/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a projekt kezdő dátumát és kezelje a szülő‑ és gyermekfeladatokat az Aspose.Tasks‑ben

## Bevezetés
A hatékony feladat szervezés a sikeres projektmenedzsment gerince, és a **projekt kezdő dátumának** helyes beállítása az első lépés egy jól felépített ütemterv felé. Ebben az útmutatóban megmutatjuk, hogyan **állítsa be a projekt kezdő dátumát**, konfigurálja a feladat időtartamokat, és kezelje a szülő‑gyermek kapcsolatokat az Aspose.Tasks for Java segítségével. A végére készen áll majd a **projekt mentésére MPP‑ként**, a feladat befejezési százalékok frissítésére, valamint a feladat tulajdonságok testreszabására bármely valós helyzethez.

## Gyors válaszok
- **Hogyan állíthatom be a projekt kezdő dátumát?** Használja a `proj.set(Prj.START_DATE, startDate);` hívást a `Project` objektum inicializálása után.  
- **Hozzáadhatok gyermekfeladatokat egy szülő feladathoz?** Igen – hívja a `parentTask.getChildren().add("Child Task")` metódust.  
- **Milyen formátumban menti a fájlt az Aspose.Tasks?** Használja a `SaveFileFormat.Mpp` értéket a **projekt mentéséhez MPP‑ként**.  
- **Hogyan frissíthetem a feladat befejezést?** Állítsa be a `Tsk.PERCENT_COMPLETE` értéket a feladat objektumon.  
- **Hol szerezhetek ideiglenes licencet?** Látogassa meg a gyakran ismételt kérdésekben szereplő ideiglenes licenc oldalát.

## Előfeltételek
- Alapvető Java programozási ismeretek.  
- Aspose.Tasks for Java könyvtár telepítve. Letöltheti [innen](https://releases.aspose.com/tasks/java/).  
- Java integrált fejlesztőkörnyezet (IDE) telepítve a rendszerén.

## Csomagok importálása
A kezdethez importálja a szükséges csomagokat a Java projektjébe. Ezek a csomagok lehetővé teszik az Aspose.Tasks for Java funkcióival való zökkenőmentes integrációt.
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

## 1. lépés: Projekt kezdő dátumának beállítása
Kezdje a projekt kezdő dátumának és egyéb releváns paraméterek beállításával.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## 2. lépés: Szülő feladat hozzáadása (Feladat 1)
Hozzon létre egy „Task 1” nevű szülő feladatot, és konfigurálja annak tulajdonságait, beleértve a **feladat időtartam beállítását**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## 3. lépés: Szülő feladat hozzáadása (Feladat 2) gyermekfeladatokkal
Most adjon hozzá egy másik szülő feladatot „Task 2” néven, és tartalmazzon gyermekfeladatokat (Task 3 és Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## 4. lépés: Gyermekfeladatok konfigurálása
Adja meg a kezdő dátumokat, időtartamokat és korlátozásokat a Task 3 és Task 4 számára.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## 5. lépés: Feladat befejezési százalékának frissítése
Állítsa be a befejezési százalékot a Task 3 és Task 4 esetén – ez a módja a **feladat befejezésének frissítésére**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## 6. lépés: Projekt mentése
Végül **mentse a projektet MPP‑ként** a végrehajtott módosításokkal.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Ez a lépésről‑lépésre útmutató bemutatja, hogyan kezelje hatékonyan a szülő‑ és gyermekfeladatokat az Aspose.Tasks for Java segítségével. Kísérletezzen különböző beállításokkal, hogy megfeleljen a projekt követelményeinek.

## Miért testre szabjuk a feladat tulajdonságait?
A feladat tulajdonságok, például a kezdő dátumok, időtartamok, korlátozások és befejezési százalékok testreszabása finomhangolt irányítást biztosít az ütemezés viselkedése felett. Akár erőforrás‑elérhetőséghez kell igazítani a feladatokat, akár üzleti szabályokat kell érvényesíteni, az Aspose.Tasks lehetővé teszi a **feladat tulajdonságok programozott testreszabását**.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **A kezdő dátum nem alkalmazódik** | Győződjön meg róla, hogy a `proj.set(Prj.START_DATE, …)` hívást **a** `Project` objektum létrehozása **után** és a feladatok hozzáadása **előtt** hajtja végre. |
| **A gyermekfeladatok rossz korlátozásokat örökölnek** | Állítsa be minden gyermek `ConstraintType` és `ConstraintDate` értékét explicit módon, ahogyan a 4. lépésben látható. |
| **A mentett fájl nem nyitható meg MS Projectben** | Ellenőrizze, hogy a legújabb Aspose.Tasks verziót használja, és mentse `SaveFileFormat.Mpp` formátummal. |
| **A százalék nem jelenik meg a felhasználói felületen** | A `Tsk.PERCENT_COMPLETE` beállítása után hívja meg a `proj.calculateTaskSchedule()` metódust, ha újraszámolt dátumokra van szükség. |

## GyIK
### Az Aspose.Tasks for Java kompatibilis különböző projektfájl formátumokkal?
Igen, az Aspose.Tasks for Java számos projektfájl formátumot támogat, többek között az MPP‑t és az XML‑t.

### Testreszabhatom a feladat tulajdonságait a bemutatottakon túl?
Természetesen! Az Aspose.Tasks for Java kiterjedt testreszabási lehetőségeket kínál a feladat tulajdonságokhoz.

### Van közösségi fórum az Aspose.Tasks‑hez, ahol segítséget kaphatok?
Igen, a [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) felkeresésével közösségi támogatást kaphat.

### Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks for Java‑hoz?
Ideiglenes licencet szerezhet [innen](https://purchase.aspose.com/temporary-license/).

### Hol találhatom meg az Aspose.Tasks for Java átfogó dokumentációját?
A dokumentáció elérhető [innen](https://reference.aspose.com/tasks/java/).

**További kérdések és válaszok**

**K: Hogyan szerezhetem meg programozottan az ideiglenes licencet?**  
A: Töltse be az ideiglenes licencfájlt a következő kóddal: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**K: Megváltoztathatom az alapértelmezett feladat időtartam egységet?**  
A: Igen – módosítsa a `TimeUnitType` argumentumot a `proj.getDuration(value, TimeUnitType.YourChoice)` hívásban.

**K: Melyik Aspose.Tasks verzió szükséges a `SaveFileFormat.Mpp` használatához?**  
A: Minden legújabb verzió (2022‑2026) támogatja a mentést MPP‑ként; ellenőrizze a kiadási megjegyzéseket az esetleges változásokért.

**Utoljára frissítve:** 2026-02-23  
**Tesztelve:** Aspose.Tasks for Java 24.11  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}