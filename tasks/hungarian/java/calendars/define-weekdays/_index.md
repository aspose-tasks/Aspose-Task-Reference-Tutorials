---
date: 2025-12-02
description: Ismerje meg, hogyan állíthat be naptárat, definiálhatja a hét napjait
  az MS Projectben, és állíthat be egyéni munkanapokat az Aspose.Tasks for Java használatával.
  Mentse a projektet XML formátumban néhány sor kóddal.
language: hu
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan állítsunk be naptárat és definiáljuk a hét napjait az MS Projectben
  az Aspose.Tasks segítségével
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsunk be naptárat és határozzuk meg a hét napjait az MS Projectben az Aspose.Tasks segítségével

## Introduction
Ebben az útmutatóban megtanulja, hogyan állíthat be programozottan **naptár beállításokat** és határozhatja meg a hét napjait egy Microsoft Project fájlban az Aspose.Tasks Java könyvtár segítségével. Akár egy szabványos munkahét létrehozására, hétvégi munkanapok hozzáadására, vagy egy rövid pénteki ütemezés beállítására van szüksége, ez az útmutató minden lépésen végigvezet – a projekt létrehozásától a fájl XML formátumban történő mentéséig.

## Quick Answers
- **What library is needed?** Aspose.Tasks for Java  
- **Can I add weekend working days?** Yes – just add Saturday and Sunday as working days.  
- **How do I save the project?** Use `prj.save(..., SaveFileFormat.Xml)`.  
- **Do I need a license?** A free trial works for evaluation; a license is required for production.  
- **What Java version is required?** Java 8 or higher.

## What is “how to set calendar” in the context of MS Project?
A naptár beállítása az MS Projectben azt jelenti, hogy meghatározzuk, mely napok munkanapok, a napi munkaidő, valamint az esetleges kivételek, például ünnepnapok. Ez a naptár irányítja a feladatok ütemezését, az erőforrások kiosztását és a projekt teljes idővonalát.

## Why use Aspose.Tasks for calendar manipulation?
- **Full control** – programmatically create, modify, or delete calendars without opening the UI.  
- **Cross‑platform** – works on any OS that supports Java.  
- **Supports all file formats** – MPP, MPT, and XML, so you can *save project as XML* for easy integration with other systems.  
- **No COM dependencies** – unlike the Microsoft Project Interop library.

## Prerequisites
Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

1. **Java Development Kit (JDK) 8+** – letölthető a [Oracle weboldaláról](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – a legújabb JAR letölthető az [Aspose.Tasks letöltési oldaláról](https://releases.aspose.com/tasks/java/).  
3. Egy IDE vagy build eszköz (Maven/Gradle), amely hozzáadja az Aspose.Tasks JAR‑t a projekt classpath‑jához.

## Import Packages
Először importálja a szükséges osztályokat. Ezek az importok hozzáférést biztosítanak a projekt, naptár és munkavégzési idő objektumokhoz.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Project Instance
Hozzon létre egy új `Project` objektumot. Ez az objektum képviseli azt az MS Project fájlt, amelyet szerkeszteni fog.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Step 2: Define a New Calendar
Adjon hozzá egy új naptárat a projekthez. Egy egyértelmű név megadása segít, ha több naptárat használ.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Step 3: Add Standard Working Days (Monday‑Thursday)
Használja a beépített segédfüggvényt `WeekDay.createDefaultWorkingDay`, hogy beállítsa az alapértelmezett 9 am‑5 pm ütemezést a fő munkahétre.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Step 4: Add Weekend Working Days
Ha a projekt hétvégén is fut, egyszerűen adja hozzá a szombatot és vasárnapot rendszeres munkanapként. Ez bemutatja a **add weekend working days** funkciót.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Step 5: Set a Custom Short Working Day (Friday)
Itt **set custom working days** a péntekre: egy reggeli műszak (9 am‑12 pm) és egy délutáni műszak (1 pm‑4 pm).

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

### Step 6: Save the Project as XML
Végül mentse el a módosításokat. A `SaveFileFormat.Xml` opció lehetővé teszi a **save project as XML** műveletet, ami hasznos az egyéb eszközökkel való integrációhoz.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues & Solutions
| Probléma | Megoldás |
|----------|----------|
| **A munkavégzési idők nem alkalmazva** | Győződjön meg arról, hogy a `setDayWorking(true)` hívás megtörtént az egyedi `WeekDay` objektumon. |
| **A fájl nem található mentéskor** | Ellenőrizze, hogy a `dataDir` egy létező mappára mutat, és hogy az alkalmazásnak van írási joga. |
| **A naptár nem jelenik meg a feladatokban** | Rendelje hozzá az újonnan létrehozott naptárat az erőforrásokhoz vagy feladatokhoz a `task.setCalendar(cal)` használatával. |

## Frequently Asked Questions

**Q: Definiálhatok egyedi nem‑munka napokat az Aspose.Tasks for Java‑val?**  
A: Igen. Állítsa a `DayWorking` tulajdonságot `false`‑ra bármelyik `WeekDay` esetén, amelyet nem‑munka napként kíván kezelni.

**Q: Hogyan adhatok hozzá ünnepnapokat vagy vállalati szintű kivételeket?**  
A: Hozzon létre `CalendarException` objektumokat, adja meg a kivétel dátumait, majd adja hozzá őket a `cal.getExceptions()` gyűjteményhez.

**Q: A könyvtár kompatibilis-e a régebbi MS Project verziókkal?**  
A: Teljes mértékben. Az Aspose.Tasks támogatja az MPP, MPT és XML formátumokat több Project verzióban is.

**Q: Módosíthatok egy meglévő naptárat egy importált projektben?**  
A: Töltse be a projektet a `new Project("existing.mpp")` segítségével, szerezze meg a kívánt naptárat, végezze el a módosításokat, majd mentse el.

**Q: Az Aspose.Tasks kezeli a visszatérő feladatokat is?**  
A: Igen, visszatérő feladatokat hozhat létre és szerkeszthet a `RecurringTask` osztály segítségével.

## Conclusion
Most már tudja, hogyan állítsa be a **naptár beállításokat**, **határozza meg a hét napjait az MS Projectben**, adjon hozzá hétvégi munkanapokat, és hozzon létre egy rövid pénteki ütemezést – mindezt az Aspose.Tasks for Java‑val. Mentse az eredményt XML‑ként, és integrálja a naptárlogikát bármely Java‑alapú projektmenedzsment megoldásba.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}