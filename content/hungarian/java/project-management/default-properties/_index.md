---
title: Hatékonyan kezelheti az MS projekt tulajdonságait az Aspose.Tasks alkalmazásban
linktitle: Az alapértelmezett projekttulajdonságok kezelése az Aspose.Tasks alkalmazásban
second_title: Aspose.Tasks Java API
description: Ismerje meg, hogyan kezelheti az alapértelmezett MS Project-tulajdonságokat az Aspose.Tasks for Java használatával. Egyszerűsítse a projektmenedzsment munkafolyamatát könnyedén.
type: docs
weight: 11
url: /hu/java/project-management/default-properties/
---
## Bevezetés
Szeretné leegyszerűsíteni projektkezelési folyamatát az Aspose.Tasks for Java segítségével? A Microsoft Project fájlok alapértelmezett tulajdonságainak kezelése jelentősen növelheti a hatékonyságot. Ebben az oktatóanyagban lépésről lépésre végigvezetjük az alapértelmezett MS Project tulajdonságok kezelését az Aspose.Tasks használatával.
## Előfeltételek
Mielőtt belemerülnénk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
### 1. Java fejlesztőkészlet (JDK)
   - Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
   -  Letöltheti innen[itt](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks for Java Library
   - Töltse le és foglalja bele a projektbe az Aspose.Tasks for Java könyvtárat.
   -  Letöltheti a[weboldal](https://releases.aspose.com/tasks/java/).
## Csomagok importálása
Először is importálja a szükséges csomagokat a Java fájlba:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Bontsuk fel a folyamatot kezelhető lépésekre:
## 1. lépés: Töltse be a projektfájlt
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 2. lépés: Az alapértelmezett tulajdonságok megjelenítése
```java
// Az alapértelmezett tulajdonságok megjelenítése
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## 3. lépés: Állítsa be az alapértelmezett tulajdonságokat
```java
// Állítsa be az alapértelmezett tulajdonságokat
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## 4. lépés: Projekt mentése XML formátumba
```java
// Mentse a projektet XML formátumba
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## 5. lépés: Eredmény megjelenítése
```java
// Konverzió eredményének megjelenítése.
System.out.println("Process completed Successfully");
```
Az alábbi lépések követésével hatékonyan kezelheti az alapértelmezett MS Project tulajdonságait az Aspose.Tasks for Java segítségével.
## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kezelheti az alapértelmezett MS Project-tulajdonságokat az Aspose.Tasks for Java használatával. Ezen technikák használatával optimalizálhatja projektmenedzsment munkafolyamatait, javítva a termelékenységet és a szervezettséget.
## GYIK
### 1. kérdés: Használhatom az Aspose.Tasks-t más programozási nyelvekkel?
1. válasz: Igen, az Aspose.Tasks különféle programozási nyelveket támogat, mint például a .NET, a Python és a Java.
### 2. kérdés: Az Aspose.Tasks alkalmas személyes és vállalati használatra is?
A2: Abszolút! Akár kisebb személyes projekteket, akár nagyszabású vállalati kezdeményezéseket kezel, az Aspose.Tasks mindenkit kielégít.
### 3. kérdés: Az Aspose.Tasks kínál ügyfélszolgálatot?
V3: Igen, segítséget és közösségi támogatást találhat a webhelyen[Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15).
### 4. kérdés: Kipróbálhatom az Aspose.Tasks-t vásárlás előtt?
 A4: Természetesen! Ingyenes próbaverziót vehet igénybe a[weboldal](https://releases.aspose.com/).
### 5. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.Tasks számára?
 V5: Ideiglenes engedélyt kaphat a[vásárlási oldal](https://purchase.aspose.com/temporary-license/) tesztelési és értékelési célokra.