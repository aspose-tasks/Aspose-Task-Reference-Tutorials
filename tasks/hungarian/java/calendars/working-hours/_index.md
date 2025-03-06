---
title: Szerezzen be munkaidőt a naptárból az Aspose.Tasks segítségével
linktitle: Szerezzen be munkaidőt a naptárból az Aspose.Tasks segítségével
second_title: Aspose.Tasks Java API
description: Az Aspose.Tasks for Java segítségével egyszerűen kivonhatja a munkaidőt az MS Project naptáraiból. A projektmenedzsment feladatok egyszerűsítése.
weight: 13
url: /hu/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Szerezzen be munkaidőt a naptárból az Aspose.Tasks segítségével

## Bevezetés
projektnaptárak kezelése és a munkaidő-kivonás elengedhetetlen a hatékony projektmenedzsmenthez. Az Aspose.Tasks for Java robusztus funkcionalitást biztosít a munkaidő könnyű lekéréséhez az MS Project naptáraiból. Ebben az oktatóanyagban lépésről lépésre végigvezetjük a folyamaton.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Tasks a Java könyvtárhoz letöltve és hozzáadva a projekthez. Letöltheti innen[itt](https://releases.aspose.com/tasks/java/).
3. A Java programozási nyelv alapvető ismerete.
## Csomagok importálása
Először is importálja a szükséges csomagokat az Aspose.Tasks for Java használatához:
```java
import com.aspose.tasks.*;
```
## 1. lépés: Töltse be a projektfájlt
Kezdje az MS Project fájl betöltésével:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 2. lépés: A feladat és a naptár adatainak lekérése
Feladat és naptár részleteinek kinyerése a projektből:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## 3. lépés: Határozza meg a kezdési és befejezési dátumot
Állítsa be a feladat kezdő és befejező dátumát:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## 4. lépés: Ismétlés dátumokon keresztül
Ismételje meg a dátumokat a feladat időtartamán belül:
```java
java.util.Calendar tempDate = calStartDate;
```
## 5. lépés: Az időtartam kiszámítása
Számítsa ki az időtartamot percekben, órákban és napokban:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan lehet lekérni a munkaórákat egy MS Project naptárból az Aspose.Tasks for Java segítségével. Ezen lépések követésével hatékonyan kezelheti a projekt ütemezését és könnyedén kiszámíthatja a feladatok időtartamát.
## GYIK
### K: Az Aspose.Tasks for Java kezelheti az összetett projektstruktúrákat?
V: Igen, az Aspose.Tasks for Java átfogó támogatást nyújt összetett projektstruktúrák kezeléséhez, beleértve a feladatokat, erőforrásokat és naptárakat.
### K: Az Aspose.Tasks for Java kompatibilis az MS Project különböző verzióival?
V: Természetesen az Aspose.Tasks for Java támogatja az MS Project különféle verzióit, biztosítva a kompatibilitást a különböző környezetekben.
### K: Testreszabhatom a munkaidőt és az ünnepnapokat a projektnaptárban?
V: Igen, az Aspose.Tasks for Java API-k segítségével könnyedén testreszabhatja a munkaidőt és az ünnepnapokat a projekt követelményei szerint.
### K: Az Aspose.Tasks for Java kínál támogatást és dokumentációt?
V: Igen, az Aspose.Tasks for Java kiterjedt dokumentációval és dedikált támogatási fórumokkal segíti a fejlesztőket a funkcióinak hatékony kihasználásában.
### K: Elérhető az Aspose.Tasks for Java próbaverziója?
 V: Igen, elérheti az Aspose.Tasks Java ingyenes próbaverzióját innen[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
