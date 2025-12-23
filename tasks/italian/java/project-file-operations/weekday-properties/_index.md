---
date: 2025-12-23
description: Scopri come utilizzare Aspose.Tasks per Java per aggiornare il programma
  del progetto, impostare il giorno di inizio della settimana, modificare i giorni
  per mese e personalizzare il calendario del progetto in modo efficiente.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Gestione delle proprietà dei giorni della settimana
url: /it/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Gestione delle proprietà dei giorni della settimana

## Introduction
Aspose.Tasks for Java (aspose tasks java) è un'API robusta che consente agli sviluppatori Java di lavorare con i file Microsoft Project senza la necessità di avere Microsoft Project installato. In questo tutorial imparerai a **caricare un file MPP**, **impostare il giorno di inizio settimana**, **modificare i giorni per mese** e, in generale, **personalizzare il calendario del progetto** — tutti passaggi essenziali per aggiornare il programma di un progetto. Alla fine, sarai in grado di regolare le proprietà dei giorni della settimana programmaticamente e salvare le modifiche nel formato necessario.

## Quick Answers
- **What is the primary class for handling projects?** `Project` from the Aspose.Tasks library.  
- **How do I change the week start day?** Use `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Can I load an existing .mpp file?** Yes—instantiate `Project` with the file path.  
- **Which method saves the project as XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Do I need a license for development?** A free trial works for evaluation; a license is required for production.

## Prerequisites
Before you start, make sure you have the following:

- **Java Development Kit (JDK)** – ultima versione installata.  
- **Aspose.Tasks for Java library** – scaricala [qui](https://releases.aspose.com/tasks/java/).  
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

**Q: Can Aspose.Tasks for Java handle complex project structures?**  
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures with ease.

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project files?**  
A: Absolutely, Aspose.Tasks for Java supports various versions of Microsoft Project files, ensuring compatibility across platforms.

**Q: Can I integrate Aspose.Tasks for Java into my existing Java applications?**  
A: Yes, Aspose.Tasks for Java offers seamless integration capabilities, allowing you to enhance your Java applications with powerful project management features.

**Q: Does Aspose.Tasks for Java provide documentation and support?**  
A: Yes, you can access extensive documentation and community support for Aspose.Tasks for Java on their [website](https://releases.aspose.com/).

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: Yes, you can download a free trial version of Aspose.Tasks for Java from their [website](https://reference.aspose.com/tasks/java/) to explore its features before making a purchase.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}