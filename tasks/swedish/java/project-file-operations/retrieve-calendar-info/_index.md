---
date: 2026-03-27
description: Lär dig hur du använder Aspose och Aspose.Tasks för att extrahera projektkalenderdetaljer
  från Microsoft Project‑filer med Java. Steg‑för‑steg‑guide med kodexempel.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man använder Aspose.Tasks för att hämta kalenderinformation i MS Project
url: /sv/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder Aspose.Tasks för att hämta kalenderinformation från MS Project

## Introduction
I den här handledningen kommer du att upptäcka hur du använder Aspose.Tasks för att programatiskt hämta kalenderinformation från Microsoft Project‑filer. Att få åtkomst till kalenderdata såsom arbetsdagar, timmar och undantag är viktigt när du behöver extrahera projektkalenderdetaljer för rapportering, integration eller anpassad schemaläggningslogik. Låt oss gå igenom processen steg för steg, och du kommer att se exakt hur du använder Aspose för att hämta dessa data ur en *.mpp*-fil.

## Quick Answers
- **What library does this tutorial use?** Aspose.Tasks for Java.  
- **Which primary keyword is covered?** *how to use aspose*.  
- **What can you extract?** Project calendars, including working days and hours.  
- **Do I need a license?** A free trial is available; a license is required for production.  
- **What Java version is supported?** Java 8 or higher.

## What is Aspose.Tasks and Why Use It?
Aspose.Tasks är ett kraftfullt Java‑API som låter utvecklare läsa, skriva och manipulera Microsoft Project‑filer utan att behöva Microsoft Project själv. Genom att använda Aspose.Tasks kan du **how to extract calendar**‑information, automatisera schemaläggningsberäkningar och integrera projektdata med andra företagsystem – allt från ren Java‑kod.

## Why extract project calendar information?
Projektkalendrar styr uppgiftens datum, resursallokeringar och övergripande tidslinjebereäkningar. Genom att extrahera dessa data kan du:
- Generera anpassade rapporter som speglar faktiska arbetsscheman.  
- Synkronisera Microsoft Project‑tidslinjer med externa system (ERP, BI, etc.).  
- Utföra vad‑om‑analyser genom att programatiskt ändra kalenderinställningar.  
- **Extract MS Project calendar**‑data för migrering till andra planeringsverktyg.

## Prerequisites
Innan vi börjar, se till att du har:

- Grundläggande kunskaper i Java‑programmering.  
- Java Development Kit (JDK) installerat på ditt system.  
- Aspose.Tasks for Java‑biblioteket. Du kan ladda ner det [here](https://releases.aspose.com/tasks/java/).

## Import Packages
First, import the necessary Aspose.Tasks classes into your Java project.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
Define the folder that contains your *.mpp* file.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path to the folder where **project.mpp** resides.

## Step 2: Define Time Units
Create constants that help convert the internal time representation to human‑readable hours.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

These values are expressed in microseconds, which is how Aspose.Tasks stores time internally.

## Step 3: Create Project Instance
Load the Microsoft Project file into a `Project` object.

```java
Project project = new Project(dataDir + "project.mpp");
```

The `Project` constructor parses the *.mpp* file and makes all project data, including calendars, accessible through the API.

## Step 4: Retrieve Calendars Information
Obtain the collection of calendars defined in the project.

```java
CalendarCollection alCals = project.getCalendars();
```

A project can contain multiple calendars (standard, resource, and custom calendars). This collection gives you access to each one.

## Step 5: Iterate Through Calendars
Loop through every calendar, display its UID, name, and the working days with corresponding hours.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

The inner loop checks each `WeekDay` object. If the day is marked as working, it prints the day type (Monday, Tuesday, …) together with the calculated working hours.

## Step 6: Display Completion Message
Signal that the extraction process has finished.

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| **Inga kalendrar returnerade** | Projektfilen kanske inte innehåller några anpassade kalendrar. | Verifiera att *.mpp* faktiskt definierar kalendrar eller öppna den i Microsoft Project för att bekräfta. |
| **Felaktiga arbetstimmar** | Tidskonverteringskonstanterna är felaktiga för en annan Project‑version. | Justera `OneSec`, `OneMin`, `OneHour` om du använder en nyare version av Aspose.Tasks som ändrar den interna tidsenheten. |
| `NullPointerException` på `cal.getName()` | Vissa kalenderobjekt kan vara null. | Lägg till en null‑kontroll innan du kommer åt egenskaper (redan demonstrerat). |

## Frequently Asked Questions

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks stöder flera plattformar och programmeringsspråk, inklusive .NET, C++, Python och Java.

**Q: Finns det en gratis provversion av Aspose.Tasks?**  
A: Ja, du kan ladda ner en gratis provversion [here](https://releases.aspose.com/).

**Q: Hur får jag support för Aspose.Tasks?**  
A: Du kan få support via Aspose.Tasks‑community‑forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Kan jag köpa en tillfällig licens för Aspose.Tasks?**  
A: Ja, tillfälliga licenser finns att köpa [here](https://purchase.aspose.com/temporary-license/).

**Q: Var hittar jag detaljerad dokumentation för Aspose.Tasks?**  
A: Du kan hänvisa till dokumentationen [here](https://reference.aspose.com/tasks/java/).

## Conclusion
Genom att följa dessa steg **vet du nu hur du använder Aspose.Tasks för att extrahera projektkalender**‑information från en MS Project‑fil med Java. Du kan integrera denna logik i större applikationer, automatisera rapportering eller synkronisera scheman med andra företagsystem. Kom ihåg att behärska **how to use aspose** öppnar dörren till många avancerade projekt‑hanterings‑automatiseringsscenarier.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}