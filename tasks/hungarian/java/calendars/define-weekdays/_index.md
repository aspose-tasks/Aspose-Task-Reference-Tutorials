---
date: 2026-08-08
description: Tanulja meg, hogyan állíthatja be a ms project naptárát, határozhatja
  meg a napi munkaórákat, és adhat hozzá hétvégi munkanapokat az Aspose.Tasks for
  Java használatával. Mentse a projektet XML formátumban néhány kódsorral.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Hogyan állítsuk be a ms project naptárát és definiáljuk a hétköznapokat
og_description: Állítsa be a ms project naptárát, definiálja a hétköznapokat, és adjon
  hozzá hétvégi munkanapokat az Aspose.Tasks for Java használatával. Kövesse ezt a
  lépésről‑lépésre útmutatót, és mentse el XML formátumban.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: ms project naptár beállítása az Aspose.Tasks segítségével – Java útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Hogyan állítsuk be a ms project naptárát és definiáljuk a hétköznapokat
url: /hu/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a naptárat az MS Projectben és definiáljuk a hétköznapokat

Ebben az oktatóanyagban megtanulja, **hogyan állítsuk be a naptárat az MS Projectben** programozott módon, definiálja a hétköznapokat, és testreszabott munkanapokat konfiguráljon az Aspose.Tasks Java könyvtár segítségével. Akár ütemező motorral dolgozik, ERP rendszerekkel integrál, vagy egyszerűen csak projekttervet kell generálnia a Microsoft Project megnyitása nélkül, az alábbi lépések megmutatják, hogyan hozhat létre egy naptárat, állíthat be napi munkaórákat, és adhat hozzá hétvégi munkanapokat néhány kódsorral.

## Gyors válaszok
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java.  
- **Hozzáadhatok hétvégi munkanapokat?** Igen – egyszerűen jelölje meg a szombatot és vasárnapot munkanapként.  
- **Hogyan menthetjük a projektet?** Hívja a `prj.save(..., SaveFileFormat.Xml)` metódust.  
- **Szükséges licenc?** Egy ingyenes próba verzió elegendő értékeléshez; a licenc kötelező a termelésben való használathoz.  
- **Melyik Java verzió támogatott?** Java 8 vagy újabb.

## Mi az a naptár beállítása az MS Projectben?
Az MS Project naptárának beállítása meghatározza, mely napok tekinthetők munkanapnak, a napi munkaórák számát, valamint bármilyen különleges kivételt, például ünnepnapokat vagy vállalati leállásokat. Ez az információ irányítja a feladatok ütemezését, az erőforrások elosztását és a projekt teljes idővonalát, biztosítva, hogy a számítások a szervezet valós munkarendjét tükrözzék.

## Miért használjuk az Aspose.Tasks-et a naptárkezeléshez?
Az Aspose.Tasks lehetővé teszi a naptárak programozott vezérlését a Microsoft Project felhasználói felületének indítása nélkül. Bármely, Java‑t támogató operációs rendszeren fut, több mint 50 bemeneti és kimeneti formátumot támogat, és több száz oldalas projekteket képes feldolgozni anélkül, hogy a teljes fájlt a memóriába töltené, így ideális szerveroldali automatizáláshoz.

## Előfeltételek
- **Java Development Kit (JDK) 8+** – letölthető a [Oracle weboldaláról](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – a legújabb JAR letölthető a [Aspose.Tasks letöltési oldaláról](https://releases.aspose.com/tasks/java/).  
- IDE vagy build eszköz (Maven/Gradle) az Aspose.Tasks JAR hozzáadásához a classpath‑hoz.

## Csomagok importálása
Importálja az osztályokat, amelyek hozzáférést biztosítanak projektekhez, naptárakhoz és munkavégzési idő objektumokhoz.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Lépésről‑lépésre útmutató

### 1. lépés: projektpéldány létrehozása
Hozzon létre egy `Project` objektumot, amely a manipulálandó MS Project fájlt képviseli.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### 2. lépés: új naptár definiálása
A `Calendar` egy munkavégzési időket, kivételeket és ünnepnapokat tartalmazó halmazt jelent egy projekthez.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### 3. lépés: szabványos munkanapok hozzáadása (hétfő‑csütörtök)
A `WeekDay` meghatározza egy adott hét napjának munkavégzési idejét.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### 4. lépés: hétvégi munkanapok hozzáadása
Ha a projekt hétvégén is fut, adja hozzá a szombatot és vasárnapot szabályos munkanapként. Ez demonstrálja a **hétvégi munkanapok hozzáadását**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### 5. lépés: egyedi rövid munkanap beállítása (péntek)
Állítsa be a pénteket egy reggeli műszakkal (9 am‑12 pm) és egy délutáni műszakkal (1 pm‑4 pm), hogy bemutassa a **napi munkaórák beállítását** és egy egyedi rövid munkanapot.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### 6. lépés: projekt mentése XML‑ként
A `SaveFileFormat` felsorolja a projekt mentésekor támogatott fájlformátumokat, például XML vagy MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **A munkavégzési idők nem alkalmazódnak** | Győződjön meg róla, hogy a `setDayWorking(true)` minden egyedi `WeekDay`‑nél meghívásra került. |
| **Fájl nem található mentéskor** | Ellenőrizze, hogy a `dataDir` egy létező mappára mutat, és az alkalmazásnak van írási jogosultsága. |
| **A naptár nem jelenik meg a feladatokban** | Rendelje hozzá az újonnan létrehozott naptárat erőforrásokhoz vagy feladatokhoz a `task.setCalendar(cal)` használatával. |

## Gyakran feltett kérdések

**K: Definiálhatok egyedi nem munkanapokat az Aspose.Tasks for Java használatával?**  
V: Igen. Állítsa a `DayWorking` tulajdonságot `false`‑ra bármelyik `WeekDay`‑nél, amelyet nem munkanapként kíván kezelni.

**K: Hogyan adhatok hozzá ünnepnapokat vagy vállalati szintű kivételeket?**  
V: Hozzon létre `CalendarException` objektumokat, adja meg a kivétel dátumait, és adja hozzá a `cal.getExceptions()`‑hez.

**K: Kompatibilis a könyvtár a régebbi MS Project verziókkal?**  
V: Teljesen. Az Aspose.Tasks támogatja az MPP, MPT és XML formátumokat több Project verzióban.

**K: Módosíthatok egy meglévő naptárat egy importált projektben?**  
V: Töltsük be a projektet a `new Project("existing.mpp")`‑vel, szerezze meg a kívánt naptárat, végezze el a módosításokat, majd mentse.

**K: Az Aspose.Tasks kezeli a visszatérő feladatokat is?**  
V: Igen, létrehozhat és szerkeszthet visszatérő feladatokat a `RecurringTask` osztály használatával.

## Összegzés
Most már tudja, **hogyan állítsuk be a naptárat az MS Projectben**, hogyan definiáljon hétköznapokat, adjon hozzá hétvégi munkanapokat, és konfiguráljon egy rövid pénteki ütemezést – mindezt az Aspose.Tasks for Java segítségével. Mentse az eredményt XML‑ként, és integrálja a naptárlogikát bármely Java‑alapú projekt‑menedzsment megoldásba.

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Add Holidays to Calendar and Save as MPP with Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}