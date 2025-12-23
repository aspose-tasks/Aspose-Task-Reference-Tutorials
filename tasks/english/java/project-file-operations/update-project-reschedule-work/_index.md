---
title: Update MS Project and Reschedule Work with Aspose.Tasks
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to update MS Project files and reschedule uncompleted work using Aspose.Tasks for Java. Also see how to save MS Project XML.
weight: 23
url: /java/project-file-operations/update-project-reschedule-work/
date: 2025-12-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Update MS Project and Reschedule Work with Aspose.Tasks

## Introduction
Microsoft Project is a widely‑used project‑management tool that helps teams plan, track, and deliver work on time. When schedules shift, you often need to **update MS Project** files programmatically—mark work as complete, move remaining tasks, and keep the project baseline accurate. Aspose.Tasks for Java gives you a clean, type‑safe API to do exactly that without opening the GUI. In this tutorial you’ll see how to update a project, mark work as finished up to a specific date, and then **how to reschedule MS Project** work that is still pending.

## Quick Answers
- **What does “update MS Project” mean?** It marks tasks as completed up to a given date and writes the changes back to the file.  
- **Can I reschedule remaining work automatically?** Yes—use `rescheduleUncompletedWorkToStartAfter` to push unfinished tasks forward.  
- **Which file format is saved?** The examples save the project as XML (`SaveFileFormat.Xml`).  
- **Do I need a license to run the code?** A free trial works for development; a commercial license is required for production.  
- **What Java version is required?** JDK 8 or higher.

## What is “update MS Project” in code?
Updating a project means programmatically changing task dates, durations, or completion percentages and persisting those changes. Aspose.Tasks exposes methods like `updateProjectWorkAsComplete` that apply the changes based on a reference `Date` you provide.

## Why use Aspose.Tasks for Java to update MS Project?
- **No UI dependency** – automate bulk changes across many files.  
- **High fidelity** – the library preserves all native Project data (resources, calendars, custom fields).  
- **Cross‑platform** – run the same code on Windows, Linux, or macOS.  
- **Save MS Project XML** – you can export the updated project to the widely‑supported XML format for downstream tools.

## Prerequisites
1. Java Development Kit (JDK) installed.  
2. Aspose.Tasks for Java library – download it from [here](https://releases.aspose.com/tasks/java/).  
3. Basic familiarity with Java syntax and object‑oriented concepts.

## Import Packages
First, import the necessary Aspose.Tasks classes and Java utilities:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Set up the Project
Create a new `Project` instance, define a few sample tasks, set their durations, and establish dependencies. Then persist the initial state so you can see the before‑and‑after effect.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Step 2: Update Project Work
Mark work as complete up to a specific cutoff date. This is the core of **update MS Project**—the API will adjust task progress and dates automatically.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
After marking completed work, you often need to push the remaining tasks forward. The following call moves any unfinished work to start after the same cutoff date, effectively **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Tasks don’t show updated dates | The project was saved in a different format (e.g., `.mpp`) | Use `SaveFileFormat.Xml` to keep the XML structure intact. |
| `updateProjectWorkAsComplete` appears to do nothing | The reference date is earlier than the project start | Ensure the `Calendar` date is within the project timeline. |
| Rescheduled tasks overlap | No calendar or resource leveling applied | Apply a `Project` calendar or use `Task.setStart` manually after rescheduling. |

## Frequently Asked Questions (Extended)

**Q: Can Aspose.Tasks for Java handle complex project structures?**  
A: Yes, Aspose.Tasks for Java provides robust APIs to manage tasks, dependencies, resources, and other project elements efficiently.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can get a free trial from [here](https://releases.aspose.com/).

**Q: How can I get support for Aspose.Tasks for Java?**  
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries.

**Q: Can I purchase a temporary license for Aspose.Tasks for Java?**  
A: Yes, temporary licenses are available for purchase [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find detailed documentation for Aspose.Tasks for Java?**  
A: You can refer to the documentation [here](https://reference.aspose.com/tasks/java/) for comprehensive guides and API references.

## Conclusion
In this tutorial we walked through the complete process of **updating MS Project** files, marking work as complete, and then **how to reschedule MS Project** tasks that remain unfinished. By saving the project as XML you retain compatibility with other tools and keep a clear audit trail of changes. Use these patterns to automate schedule adjustments in large portfolios, integrate with CI pipelines, or build custom reporting dashboards.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}