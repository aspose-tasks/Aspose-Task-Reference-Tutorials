---
date: 2025-12-04
description: Ismerje meg, hogyan állíthatja be a projekt naptárát és kezelheti az
  MS Project naptár tulajdonságait Java-ban az Aspose.Tasks segítségével. Lépésről‑lépésre
  útmutató a naptár munkavégzési óráinak megjelenítéséhez és az ütemezések testreszabásához.
language: hu
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hogyan állítsuk be a projekt naptárát az Aspose.Tasks for Java segítségével
url: /java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a projekt naptárát az Aspose.Tasks for Java segítségével

## Introduction
Ebben az oktatóanyagról megtudhatja, **hogyan állítsuk be a projekt naptárát** programozott módon az Aspose.Tasks Java könyvtár segítségével. A naptár tulajdonságainak vezérlése lehetővé teszi a **naptár munkavégzési óráinak megjelenítését**, egyedi munkanapok definiálását, valamint a projekt ütemezésének összehangolását a valós világ korlátaival. Lépésről‑lépésre végigvezetjük a folyamaton – a környezet beállításától a naptárak bejárásáig és tulajdonságaik kiolvasásáig – hogy magabiztosan kezelhesse az MS Project naptárakat alkalmazásaiban.

## Quick Answers
- **Mi jelent a „projekt naptár beállítása”?** Azt jelenti, hogy egy naptár munkavégzési időit, alapszintű naptárát és nap típusait hozza létre vagy frissíti egy MS Project fájlban.  
- **Melyik könyvtár szükséges?** Aspose.Tasks for Java (bármelyik legújabb verzió).  
- **Szükségem van licencre?** A fejlesztéshez ingyenes próba verzió is működik; a termeléshez kereskedelmi licenc szükséges.  
- **Meg tudom jeleníteni a naptár munkavégzési óráit?** Igen – a `WeekDay` elemek olvasásával kiírhatja az órákat minden nap típusra.  
- **Kompatibilis-e a Maven/Gradle‑lal?** Teljesen – adja hozzá az Aspose.Tasks JAR‑t függőségként.

## What Is a Project Calendar?
A projekt naptár meghatározza feladatok, erőforrások és a teljes projekt idővonalának munkanapjait és munkaidőit. Az MS Projectben a naptárak örökölhetnek egy alapszintű naptárból, és minden nap típus (például **Standard**, **Non‑working**) saját munkavégzési idővel rendelkezhet. Ezeknek a beállításoknak a programozott kezelése lehetővé teszi a dinamikus ütemezés‑állításokat manuális szerkesztés nélkül.

## Why Manage MS Project Calendar Programmatically?
- **Automatizálás:** Naptárak módosítása számos projektben egyetlen szkript segítségével.  
- **Következetesség:** Szervezeti szintű munkaidő‑szabályok érvényesítése.  
- **Integráció:** Naptárak szinkronizálása külső rendszerekkel (HR, ERP).  
- **Átláthatóság:** Gyors **naptár munkavégzési órák megjelenítése** jelentésekhez vagy hibakereséshez.

## Prerequisites
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik:

- **Java Development Kit (JDK) 8+** telepítve van, és a `JAVA_HOME` be van állítva.  
- **Aspose.Tasks for Java** könyvtár letöltve a [letöltési oldalról](https://releases.aspose.com/tasks/java/). Adja hozzá a JAR‑t a projekt osztályútvonalához vagy Maven/Gradle függőségekhez.  

## Import Packages
First, import the core Aspose.Tasks classes that we’ll use throughout the tutorial:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
Define the folder that contains your project files. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
Working times are expressed in milliseconds. Defining reusable constants makes the code easier to read.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
Create a `Project` instance by loading an existing MS Project XML file (`.xml` or `.mpp`). This gives us access to all calendars stored in the file.

```java
Project project = new Project(dataDir + "project.xml");
```

## Step 4: Iterate Through Calendars and Display Working Hours
Now we loop through every calendar, print its unique identifier, name, base calendar, and the working hours for each day type. This demonstrates **how to set project calendar** values and also how to **display calendar working hours**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### What This Code Does
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
- **Prints UID and name** – useful for identifying the calendar later.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`).  

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | Calendar is a base calendar itself (`isBaseCalendar()` returns `true`). | Use the ternary check as shown (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | The project file uses a different time unit (ticks). | Verify the file format; Aspose.Tasks normalizes to milliseconds, but ensure you’re loading the correct file type. |
| Unable to locate `project.xml` | Incorrect `dataDir` path. | Use an absolute path or `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently Asked Questions

**Q: Can I modify calendar properties programmatically using Aspose.Tasks?**  
A: Yes, the API provides full read/write access to calendars, allowing you to add, edit, or delete working times, exceptions, and base calendar relationships.

**Q: Are there any limitations to calendar customization with Aspose.Tasks?**  
A: The library mirrors the capabilities of Microsoft Project, so you can customize virtually all calendar aspects. Only very old Project file versions may have minor compatibility quirks.

**Q: Can I integrate calendar management into existing Java projects?**  
A: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use the same code patterns shown here.

**Q: Does Aspose.Tasks support other project management functionalities besides calendar management?**  
A: Yes, it covers tasks, resources, assignments, outlines, baselines, and more—making it a comprehensive solution for Java‑based project automation.

**Q: Is technical support available for developers using Aspose.Tasks?**  
A: Yes, Aspose provides dedicated forums, email support, and extensive documentation for all licensed users.

## Conclusion
By following this guide you now know **how to set project calendar** values, read and **display calendar working hours**, and integrate these capabilities into any Java application using Aspose.Tasks. This empowers you to automate schedule adjustments, enforce consistent working policies, and build richer project‑management solutions.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}