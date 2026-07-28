---
date: 2026-02-05
description: Tanulja meg, hogyan határozza meg a munkanapokat, és számolja ki a feladat
  időtartamát az MS Project naptárakból származó munkaórák kinyerésével az Aspose.Tasks
  for Java segítségével.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Munkaidőnapok és munkaórák meghatározása az Aspose.Tasks segítségével
url: /hu/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Munkanapok és munkaidő meghatározása az Aspose.Tasks segítségével

## Introduction
A projekt naptárak kezelése a sikeres projekttervezés alapvető része. Ebben az útmutatóban **meghatározod a munkanapokat** bármely feladathoz, és **kinyered a munkaidőt** egy MS Project naptárból az Aspose.Tasks for Java használatával. A végére képes leszel **számítani a feladat időtartamát**, testreszabni a munkaidőt, és megbízhatóan **betölteni egy MPP fájlt**, hogy megszerezd a szükséges adatokat. Emellett megmutatjuk, hogyan **olvashatsz MS Project** fájlokat anélkül, hogy a Microsoft Project telepítve lenne, így az automatizálás bármely platformon lehetséges.

## Quick Answers
- **Mi jelent a “determine working days”?** Ez azt jelenti, hogy azonosítjuk, mely naptári dátumok tekinthetők munkanapoknak egy adott feladat esetén.  
- **Melyik könyvtárat használjam?** Az Aspose.Tasks for Java teljes körű API-t biztosít az MS Project fájlok kezeléséhez.  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10–15 perc egy alapvető kinyeréshez.  
- **Szükségem van licencre?** Elérhető egy ingyenes próba; a termeléshez kereskedelmi licenc szükséges.  
- **Testreszabhatom a munkaidőt?** Igen – módosíthatja a naptárakat, hozzáadhat ünnepnapokat, és beállíthat egyedi munkaidő-intervallumokat.  

## What is “determine working days”?
Amikor egy feladat ütemezésre kerül, a projekt naptár meghatározza, mely napok munkanapok és melyek nem‑munka napok (hétvégék, ünnepnapok). A munkanapok meghatározása azt jelenti, hogy lekérdezzük ezt a naptárat, hogy pontosan tudjuk, mikor végezhető munka, ami elengedhetetlen a pontos **calculate task duration** számításokhoz.

## Why use Aspose.Tasks to retrieve working hours?
- **Microsoft Project nélkül** – közvetlenül Java kódból olvashat MS Project fájlokat.  
- **Teljes naptár támogatás** – tartalmazza az alap, erőforrás és feladat naptárakat.  
- **Nagy teljesítmény** – nagy projekteket gyorsan feldolgoz.  
- **Kiterjedt dokumentáció** – példák és API referencia könnyen elérhető.  

## Prerequisites
Mielőtt elkezdenéd, győződj meg róla, hogy a következőkkel rendelkezel:

1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR-t [itt](https://releases.aspose.com/tasks/java/).  
3. Alap Java programozási ismeretek.  

## Import Packages
Először importáld a fő Aspose.Tasks névteret:

```java
import com.aspose.tasks.*;
```

## How to load an MPP file with Aspose.Tasks?
A projektfájl betöltése az első lépés minden naptárelemzéshez. Az API lehetővé teszi, hogy **betölts egy MPP fájlt** egyetlen kódsorral, a MS Project felhasználói felületének szükségessége nélkül.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Retrieve Task and Calendar Information
Válaszd ki a feladatot, amelyet elemezni szeretnél, és szerezd meg a hozzá tartozó naptárat. Itt **kinyerjük a munkaidőt** a feladathoz:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Define Start and End Dates
Állítsd be azt az időablakot, amelyre **meghatározni szeretnéd a munkanapokat**. A feladat kezdő‑ és befejező dátumainak használata biztosítja, hogy csak a releváns időszakot értékeld.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterate Through Dates
Iterálj végig a feladat időtartamában lévő minden dátumon. Ez a ciklus később segít **testreszabni a munkaidőt**, ha szükséges:

```java
java.util.Calendar tempDate = calStartDate;
```

## Calculate Duration
Az iteráció során ellenőrizzük, hogy egy nap munkanap‑e, összeadjuk a munkaórákat, majd végül kiszámítjuk a feladat időtartamát percben, órában és napban. Ez a lépés bemutatja, hogyan **számítsuk ki a munkanapokat** és **számítsuk ki a feladat időtartamát** programozott módon.

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

## How to customize working hours and holidays
Az Aspose.Tasks lehetővé teszi a naptár munkaidő‑intervallumainak módosítását és kivételek, például ünnepnapok hozzáadását. Hívhatod a `taskCalendar.addWorkingTime()` vagy a `taskCalendar.addException()` metódusokat, hogy a menetrendet a szervezeted szabályaihoz igazítsd. Ez akkor hasznos, ha az alap 9‑5‑ös beosztás nem felel meg a valóságnak.

## Common Issues and Solutions
| Probléma | Megoldás |
|----------|----------|
| **Task returns `null` for calendar** | Győződj meg róla, hogy a feladathoz ténylegesen naptár van rendelve; ellenkező esetben a projekt alapnaptárát örökli. |
| **Incorrect duration because of holidays** | Ellenőrizd, hogy az ünnepnapok definiálva vannak-e a feladat naptárában vagy a projekt alapnaptárában. |
| **Time zone mismatch** | Használd a `java.util.TimeZone`‑t, hogy a naptár időzónáját a rendszereddel egyeztesd, ha szükséges. |

## Frequently Asked Questions
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Igen, az Aspose.Tasks for Java átfogó támogatást nyújt a komplex projektstruktúrák kezeléséhez, beleértve a feladatokat, erőforrásokat és naptárakat.

### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: Teljesen, az Aspose.Tasks for Java különböző MS Project verziókat támogat, biztosítva a kompatibilitást különböző környezetekben.

### Q: Can I customize working hours and holidays in project calendars?
A: Igen, könnyedén testreszabhatod a munkaidőt és az ünnepnapokat a projekt követelményei szerint az Aspose.Tasks for Java API‑k használatával.

### Q: Does Aspose.Tasks for Java offer support and documentation?
A: Igen, az Aspose.Tasks for Java kiterjedt dokumentációt és dedikált támogatási fórumokat biztosít a fejlesztők számára, hogy hatékonyan használhassák a funkciókat.

### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Igen, ingyenes próba verziót érhetsz el az Aspose.Tasks for Java‑ból [itt](https://releases.aspose.com/).

## Conclusion
Ebben az útmutatóban bemutattuk, hogyan **határozzuk meg a munkanapokat**, **nyerjük ki a munkaidőt**, és **számítsuk ki a feladat időtartamát** egy MS Project naptárból az Aspose.Tasks for Java használatával. A fenti lépések követésével automatizálhatod az ütemezés elemzését, testreszabhatod a naptárakat, és naprakészen tarthatod a projektterveket. Most már rendelkezel a **MS Project** adatok **olvasásához**, **MPP fájl betöltéséhez**, és a pontos időtartam‑számítások elvégzéséhez szükséges eszközökkel, Microsoft Project nélkül is.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}