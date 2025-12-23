---
date: 2025-12-23
description: Dowiedz się, jak używać Aspose.Tasks for Java do aktualizacji harmonogramu
  projektu, ustawiania pierwszego dnia tygodnia, zmiany liczby dni w miesiącu oraz
  efektywnego dostosowywania kalendarza projektu.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Zarządzanie właściwościami dni tygodnia
url: /pl/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Zarządzanie właściwościami dni tygodnia

## Introduction
Aspose.Tasks for Java (aspose tasks java) to solidne API, które umożliwia programistom Java pracę z plikami Microsoft Project bez konieczności instalacji Microsoft Project. W tym samouczku dowiesz się, jak **wczytać plik MPP**, **ustawić dzień rozpoczęcia tygodnia**, **zmienić liczbę dni w miesiącu** oraz **dostosować kalendarz projektu** — wszystkie niezbędne kroki do aktualizacji harmonogramu projektu. Po zakończeniu będziesz mógł programowo modyfikować właściwości dni tygodnia i zapisywać zmiany w wymaganym formacie.

## Quick Answers
- **Jaka jest podstawowa klasa do obsługi projektów?** `Project` from the Aspose.Tasks library.  
- **Jak zmienić dzień rozpoczęcia tygodnia?** Use `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Czy mogę wczytać istniejący plik .mpp?** Yes—instantiate `Project` with the file path.  
- **Która metoda zapisuje projekt jako XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Czy potrzebna jest licencja do rozwoju?** A free trial works for evaluation; a license is required for production.

## Prerequisites
Before you start, make sure you have the following:

- **Java Development Kit (JDK)** – latest version installed.  
- **Aspose.Tasks for Java library** – download it [tutaj](https://releases.aspose.com/tasks/java/).  
- **An IDE** such as IntelliJ IDEA, Eclipse, or NetBeans.  

## Import Packages
To begin, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Now let’s walk through each step of managing weekday properties.

## Step 1: Load an MPP File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Here we **load an existing .mpp file** (`load mpp file`) so we can inspect and modify its calendar settings.*

## Step 2: Display Current Weekday Properties
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
This code prints the current **week start day**, **days per month**, **minutes per day**, and **minutes per week**—the core elements you’ll often need to **customize project calendar**.

## Step 3: Set New Weekday Properties
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
In this step we **set week start day** to Monday, **change days per month** to 24, and adjust daily and weekly minute counts. These settings are typical when you need to **update project schedule** to match a non‑standard working calendar.

## Step 4: Save the Updated Project
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
The modified project is saved as an XML file, making it easy to share or import into other tools.

## Step 5: Confirm the Operation
```java
System.out.println("Process completed Successfully");
```
A simple console message lets you know the workflow finished without errors.

## Common Issues & Tips
- **Incorrect file path** – Verify `dataDir` ends with a slash or use `Paths.get(...)` for platform‑independent paths.  
- **License not set** – In a production environment, call `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` before creating `Project`.  
- **Unexpected week start day** – Ensure you use the correct `DayType` enum value (e.g., `DayType.Sunday`).  

## Frequently Asked Questions

**Q: Czy Aspose.Tasks for Java radzi sobie ze złożonymi strukturami projektów?**  
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures with ease.

**Q: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
A: Absolutely, Aspose.Tasks for Java supports various versions of Microsoft Project files, ensuring compatibility across platforms.

**Q: Czy mogę zintegrować Aspose.Tasks for Java z istniejącymi aplikacjami Java?**  
A: Yes, Aspose.Tasks for Java offers seamless integration capabilities, allowing you to enhance your Java applications with powerful project management features.

**Q: Czy Aspose.Tasks for Java udostępnia dokumentację i wsparcie?**  
A: Yes, you can access extensive documentation and community support for Aspose.Tasks for Java on their [strona internetowa](https://releases.aspose.com/).

**Q: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks for Java?**  
A: Yes, you can download a free trial version of Aspose.Tasks for Java from their [strona internetowa](https://reference.aspose.com/tasks/java/) to explore its features before making a purchase.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}