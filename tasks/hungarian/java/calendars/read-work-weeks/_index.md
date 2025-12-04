---
date: 2025-12-03
description: Tanulja meg, hogyan olvassa be a munkahét adatokat Java-ban egy Microsoft
  Project naptárból az Aspose.Tasks használatával. Kövesse a lépésről‑lépésre útmutatót
  teljes kódrészletekkel.
language: hu
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Munkahét olvasása Java-val az MS Project naptárból – Aspose.Tasks
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Munkahét olvasása Java-val MS Project naptárból – Aspose.Tasks

## Introduction
Ebben az útmutatóban **read work weeks Java**-t fogsz olvasni egy Microsoft Project naptárból az Aspose.Tasks könyvtár segítségével. Akár jelentéskészítő eszközt építesz, ütemterveket szinkronizálsz, vagy automatizálod a projektadatok kinyerését, a munkahét‑definíciók programozott elérése rengeteg manuális órát takarít meg. Végigvezetünk a szükséges beállításokon, megmutatjuk a pontos kódot a munkahét részleteinek lekéréséhez, és minden lépést elmagyarázunk, hogy a megoldást saját projektjeidhez is adaptálhasd.

## Quick Answers
- **What does “read work weeks java” mean?** It refers to extracting work‑week definitions from a Project file using Java code.  
- **Which library is required?** Aspose.Tasks for Java (free trial available).  
- **Do I need a license for development?** A trial works for testing; a commercial license is needed for production.  
- **What file formats are supported?** Both *.mpp* and Project XML files are handled.  
- **How long does the implementation take?** Typically under 10 minutes once the library is set up.

## What is “read work weeks java”?
A munkahét olvasása Java-ban azt jelenti, hogy az Aspose.Tasks API‑t használva hozzáférünk egy naptár objektum `WorkWeekCollection`‑jéhez egy Microsoft Project fájlban. Minden `WorkWeek` tartalmazza a kezdő/lezáró dátumokat és a napi munkaidő‑definíciókat, amelyek meghatározzák, hogyan ütemeződnek a források.

## Why read work weeks java from a Microsoft Project calendar?
- **Automation:** Elkerülhető a manuális ütemezési adatok másolása.  
- **Integration:** A munkahét információk betáplálhatók ERP, HR vagy egyedi jelentéskészítő rendszerekbe.  
- **Consistency:** Biztosítható, hogy minden downstream eszköz ugyanazokat a naptárszabályokat használja, amelyek a Project fájlban vannak definiálva.

## Prerequisites
Mielőtt a kódba merülnél, győződj meg róla, hogy a következők rendelkezésre állnak:

1. **Java Development Kit (JDK)** – 8-as vagy újabb verzió telepítve.  
2. **Aspose.Tasks for Java** – a legújabb JAR letöltése a hivatalos oldalról: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Egy **minta Project fájl** (`ReadWorkWeeksInformation.mpp`) egy ismert mappában elhelyezve.

## Import Packages
First, import the classes we’ll need to interact with calendars and work weeks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Step 1: Set Up Your Data Directory
Define the folder that contains the `.mpp` file. Replace the placeholder with the actual path on your machine:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Create a Project Instance and Access the Calendar
Instantiate a `Project` object, pick the calendar you want (by UID), and obtain its `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** If you’re not sure about the calendar UID, you can iterate through `project.getCalendars()` and print each calendar’s name and UID.

## Step 3: Iterate Through Work Weeks
Loop through each `WorkWeek` to display its name, start/end dates, and the daily working times:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**What you’ll see:** The console prints each work‑week’s label (e.g., “Standard”), its effective date range, and you can drill down to the exact working hours for each day.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Wrong UID or calendar does not exist | Verify the UID with `project.getCalendars().size()` and list available calendars first. |
| No output for work weeks | The selected calendar has no custom work weeks (uses default) | Use the default calendar (`project.getDefaultCalendar()`) or create a work week programmatically. |
| Date format looks odd | `System.out.println` uses default `java.util.Date` format | Apply a `SimpleDateFormat` to format dates as needed. |

## Frequently Asked Questions

**Q: Can I modify the work weeks information using Aspose.Tasks for Java?**  
A: Yes. The API provides methods such as `addWorkWeek()`, `removeWorkWeek()`, and property setters to change names, dates, and working times.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?**  
A: Absolutely. It supports MPP files from Project 98 up to the latest versions, as well as Project XML files.

**Q: Can I integrate Aspose.Tasks with other Java frameworks?**  
A: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta EE, or any other framework.

**Q: Is there a trial version available for Aspose.Tasks?**  
A: Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Most már elsajátítottad a **read work weeks java** használatát az Aspose.Tasks segítségével. A fenti lépések követésével programozottan lekérheted a munkahét‑definíciókat bármely MS Project naptárból, integrálhatod az adatokat alkalmazásaidba, és automatizálhatod az ütemezéssel kapcsolatos munkafolyamatokat. Nyugodtan kísérletezz új munkahét létrehozásával vagy módosításával – az Aspose.Tasks ezt egyszerűvé teszi.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}