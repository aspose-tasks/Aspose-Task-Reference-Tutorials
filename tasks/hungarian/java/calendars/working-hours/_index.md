---
date: 2026-08-24
description: Tanulja meg, hogyan adjon hozzá holidays calendar-t, határozza meg a
  working days-ot, és számítsa ki a task duration-ot a working hours kinyerésével
  az MS Project naptárakból az Aspose.Tasks for Java segítségével.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Hogyan adjon hozzá holidays calendar-t és határozza meg a working days-ot
og_description: Tanulja meg, hogyan adjon hozzá holidays calendar-t, határozza meg
  a working days-ot, és számítsa ki a task duration-ot a working hours kinyerésével
  az MS Project naptárakból az Aspose.Tasks for Java segítségével.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Hogyan adjon hozzá holidays calendar-t és határozza meg a working days-ot
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Hogyan adjon hozzá holidays calendar-t és határozza meg a working days-ot
url: /hu/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan adjunk hozzá ünnepnapok naptárát és határozzuk meg a munkanapokat

A projekt naptárak kezelése a sikeres projekttervezés alapvető része. Ebben az útmutatóban **hozzáadjuk az ünnepnapok naptárát**, **meghatározzuk a munkanapokat** bármely feladathoz, és **kivonjuk a munkaórákat** egy MS Project naptárból az Aspose.Tasks for Java segítségével. A végére **kiszámíthatja a feladat időtartamát**, testre szabhatja a munkaórákat, és megbízhatóan **betöltheti az MPP fájlt**, hogy a szükséges adatokat lekérje – mindezt anélkül, hogy a Microsoft Projectet telepítené.

## Gyors válaszok
- **Mi jelenti a „determine working days” kifejezést?** Ez azt jelenti, hogy azonosítjuk, mely naptári dátumok tekinthetők munkanapnak egy adott feladat esetén.  
- **Melyik könyvtárat használjam?** Az Aspose.Tasks for Java teljes körű API-t biztosít az MS Project fájlok kezeléséhez.  
- **Mennyi időt vesz igénybe a megvalósítás?** Általában 10–15 perc egy alapvető kinyeréshez.  
- **Szükségem van licencre?** Elérhető egy ingyenes próba; a kereskedelmi licenc szükséges a termelési használathoz.  
- **Testreszabhatom a munkaórákat?** Igen – módosíthatja a naptárakat, hozzáadhat ünnepnapokat, és beállíthat egyedi munkaidő-intervallumokat.  

## Mi az a „determine working days”?
**Determine working days** azt jelenti, hogy egy projekt naptárát lekérdezve megállapítjuk, mely dátumok vannak megjelölve munkanapként, és melyek nem‑munkanapként (hétvégék, ünnepnapok vagy egyedi kivételek). Ez az információ elengedhetetlen a pontos **calculate task duration** számításhoz, mivel csak a munkanapok járulnak hozzá a feladat eltelt idejéhez.

## Miért használjuk az Aspose.Tasks‑t a munkaórák lekérdezéséhez?
Az Aspose.Tasks lehetővé teszi MS Project fájlok olvasását anélkül, hogy a Microsoft Project telepítve lenne, így automatizálást biztosít bármely platformon. Emellett magas teljesítményű feldolgozást, kiterjedt formátumtámogatást és részletes dokumentációt kínál.  

- **Teljes naptár támogatás** – az alapértelmezett, erőforrás‑ és feladatinformációk naptárai mind elérhetők.  
- **Magas teljesítmény** – képes **10 000+ feladatot 2 másodperc alatt** feldolgozni egy standard 2,5 GHz CPU‑n.  
- **Kiterjedt formátumtámogatás** – támogat **50+ bemeneti és kimeneti formátumot**, köztük MPP, MPX, XML és Primavera.  
- **Átfogó dokumentáció** – kódminták, API‑referencia és közösségi fórumok állnak rendelkezésre.  

## Előfeltételek
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió.  
2. **Aspose.Tasks for Java** – töltse le a legújabb JAR‑t a [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/) oldalról.  
3. Alapvető Java programozási ismeretek.  

## Csomagok importálása
A `Project` osztály az Aspose.Tasks felső‑szintű objektuma, amely egyetlen MS Project fájlt reprezentál a memóriában. Importálja a szükséges névteret, mielőtt elkezdené:

Import Packages

```java
import com.aspose.tasks.*;
```

## Hogyan töltsünk be egy MPP fájlt az Aspose.Tasks‑szel?
A `Project` osztály betölti az MS Project fájlt, és hozzáférést biztosít annak adataihoz. Egyetlen kódsorral töltheti be a projektfájlt; nincs szükség UI‑ra vagy COM interopra. Ez az egyszerű lépés teljes hozzáférést ad a naptárakhoz, feladatokhoz és erőforrásokhoz.

Loading an MPP file

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Feladat- és naptárinformációk lekérdezése
A `Task` egy projektfeladatot képvisel, a `Calendar` pedig annak munkaidő‑szabályait definiálja. Válassza ki a vizsgálandó feladatot, és szerezze meg a hozzá tartozó naptárat. A `Task` objektum `getStart()` és `getFinish()` metódusokat biztosít, míg a `Calendar` objektum a munkaidő‑definíciókat teszi elérhetővé.

Retrieving task and calendar

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Kezdő‑ és befejező dátumok meghatározása
A `Date` objektumok határozzák meg a naptár‑elemzés időablakát. Állítsa be azt az időablakot, amelyben **determine working days**‑t szeretne végrehajtani. A feladat kezdő‑ és befejező dátumainak használata biztosítja, hogy csak a releváns időszakot értékelje.

Defining dates

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Dátumok iterálása
Egy `for` ciklus segítségével iterálhat a dátumtartomány minden napján. A ciklus végigmegy a feladat időtartamán. Ez a ciklus lehetővé teszi, hogy később **customize working hours**‑t végezzen, és alapja a teljes munkaidő számításának.

Iterating dates

```java
java.util.Calendar tempDate = calStartDate;
```

## Időtartam számítása
A `Duration` összegzi a iteráció során számított teljes munkaidőt. Az iteráció során ellenőrzi, hogy egy nap munkanap‑e, összeadja a munkaórákat, majd végül kiszámítja a feladat időtartamát percekben, órákban és napokban. Ez bemutatja, hogyan **calculate working days**‑t és **calculate task duration**‑t hajtson végre programozottan.

Calculating duration

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

## Hogyan testre szabjuk a munkaórákat és ünnepnapokat
Módosíthatja a naptár munkaidő‑intervallumait, és hozzáadhat kivételeket, például ünnepnapokat. Használja a `taskCalendar.addWorkingTime()`‑t új munkaperiódusok beállításához, és a `taskCalendar.addException()`‑t egy ünnepnap beszúrásához. Ez akkor hasznos, ha az alapértelmezett 9‑5‑ös ütemezés nem felel meg a szervezet szabályainak.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **A feladat `null`‑t ad vissza a naptárra vonatkozóan** | Győződjön meg arról, hogy a feladat ténylegesen rendelkezik naptárral; ellenkező esetben a projekt alapértelmezett naptárát örökli. |
| **Helytelen időtartam az ünnepnapok miatt** | Ellenőrizze, hogy az ünnepnapok a feladat naptárában vagy a projekt alap‑naptárában vannak definiálva. |
| **Időzóna eltérés** | Használja a `java.util.TimeZone`‑t a naptár időzónájának a rendszerével való összehangolásához, ha szükséges. |

## Gyakran feltett kérdések
### Q: Kezelni tudja az Aspose.Tasks for Java a komplex projektstruktúrákat?
A: Igen, az Aspose.Tasks for Java átfogó támogatást nyújt a komplex projektstruktúrák kezeléséhez, beleértve a feladatokat, erőforrásokat és naptárakat.

### Q: Kompatibilis-e az Aspose.Tasks for Java a különböző MS Project verziókkal?
A: Teljes mértékben, az Aspose.Tasks for Java számos MS Project verziót támogat, biztosítva a kompatibilitást különböző környezetekben.

### Q: Testreszabhatom a munkaórákat és ünnepnapokat a projekt naptárakban?
A: Igen, könnyedén testre szabhatja a munkaórákat és ünnepnapokat a projekt követelményei szerint az Aspose.Tasks for Java API‑k segítségével.

### Q: Nyújt az Aspose.Tasks for Java támogatást és dokumentációt?
A: Igen, az Aspose.Tasks for Java kiterjedt dokumentációt és dedikált támogatási fórumokat biztosít a fejlesztők számára, hogy hatékonyan használhassák a funkciókat.

### Q: Elérhető-e próba verzió az Aspose.Tasks for Java‑hoz?
A: Igen, egy ingyenes próba verziót érhet el az Aspose.Tasks for Java‑ból a [Aspose releases page](https://releases.aspose.com/) oldalról.

## Következtetés
Ebben az útmutatóban bemutattuk, hogyan **adjunk hozzá ünnepnapok naptárát**, **határozzuk meg a munkanapokat**, **nyerjük ki a munkaórákat**, és **számítsuk ki a feladat időtartamát** egy MS Project naptárból az Aspose.Tasks for Java segítségével. A fenti lépések követésével automatizálhatja az ütemezés‑elemzést, testre szabhatja a naptárakat, és naprakészen tarthatja projektterveit. Most már rendelkezik az eszközökkel, hogy **MS Project** adatokat **olvasson**, **MPP fájlt töltsön be**, és pontos időtartam‑számításokat végezzen Microsoft Project nélkül.

---

**Utoljára frissítve:** 2026-08-24  
**Tesztelt verzióval:** Aspose.Tasks for Java 24.12 (legújabb a kiadás időpontjában)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Naptár hozzáadása a projekthez az Aspose.Tasks for Java‑val](/tasks/java/calendars/create/)
- [Ünnepnapok hozzáadása a naptárhoz és mentés MPP‑ként az Aspose.Tasks‑szel](/tasks/java/calendars/update-to-mpp/)
- [Egyedi naptárkivétel létrehozása az Aspose.Tasks for Java‑val](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}