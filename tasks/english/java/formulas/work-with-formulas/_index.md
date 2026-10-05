---
date: 2026-10-05
description: Learn how to create test project and calculate days between dates using
  Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
images:
- /java/formulas/work-with-formulas/og-image.png
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Work with formulas in Aspose.Tasks
og_description: Create test project and calculate days between dates using Aspose.Tasks
  for Java. This guide shows how to add a custom field, set task deadlines, and save
  the project as an MPP file.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Create test project and calculate days between dates
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Create test project and calculate days between dates
url: /java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create test project and calculate days between dates

In this tutorial you’ll **create test project** and **calculate days between dates** by adding a custom field, defining an extended attribute, and applying a Microsoft Project formula through the Aspose.Tasks library for Java. Whether you need to generate schedules, compute deadlines, or automate reporting, Aspose.Tasks lets you manipulate Project data programmatically without a desktop installation, supporting 50+ input and output formats and handling multi‑hundred‑page files in memory‑efficient mode.

## Quick answers
- **What does the tutorial cover?** It shows how to create a test project, define an extended attribute, set a task deadline, and use a formula to calculate days between dates.  
- **Which library is required?** Aspose.Tasks for Java (latest version).  
- **Do I need a license?** A free trial works for development; a commercial license is required for production use.  
- **What IDE can I use?** Any Java IDE (IntelliJ IDEA, Eclipse, VS Code) that supports JDK 8+.  
- **How long does the implementation take?** Roughly 10‑15 minutes to copy the code and run it.

## What is “calculate days between dates” in Aspose.Tasks?
In Aspose.Tasks, a formula is a string that can reference task fields and perform calculations. `[Deadline] - [Finish]` is the formula syntax Aspose.Tasks uses to return the numeric difference in days between two date fields. The result is stored as a numeric value representing whole days, which you can display in a custom field or use in further calculations.

## Why use Aspose.Tasks to calculate days between dates?
Aspose.Tasks provides **full API coverage** for every Project, Task, and Resource property, runs on Windows, Linux, and macOS, and does **not require Microsoft Project or Office** to be installed. The engine can process projects with **500+ tasks** in under a second on typical server hardware, making it ideal for CI pipelines, Docker containers, and high‑volume batch processing.

## How to set deadline for a task
java.util.Calendar is a Java class that represents a specific moment in time. You set a deadline by assigning a `java.util.Calendar` value to the `Tsk.DEADLINE` field of a task. After creating the Calendar instance, set its year, month, and day to the desired deadline, then call `task.set(Tsk.DEADLINE, calendar);`. The deadline is stored in the project file and can be used in formulas such as `[Deadline] - [Finish]`.

## How to define extended attribute
An extended attribute is a custom field that stores the result of your formula. You create it once, give it a friendly alias, and attach the `[Deadline] - [Finish]` expression so every task can automatically compute the interval. Create it by instantiating `ExtendedAttribute`, setting its Alias, assigning the formula, and adding it to the project's collection.

## Prerequisites
Before you start, make sure you have the following:

- **Java Development Kit (JDK) 8+** – download from the Oracle website or adopt OpenJDK.  
- **Aspose.Tasks for Java** – obtain the latest JAR from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) and add it to your project’s classpath or Maven/Gradle dependencies.

## Import packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step‑by‑step guide

### Step 1: Create a test project with a custom field
We begin by **creating a test project** and adding a custom field that will later hold our formula result.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` is a helper method that builds a minimal schedule and registers an extended attribute ready for formula assignment.

### Step 2: Define an extended attribute (add custom field)
Next, we **define an extended attribute** – essentially the custom field – and give it a friendly alias. This is where we **add custom field** logic.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** makes the field readable in Project.  
- **Formula** calculates the number of days between a task’s *Finish* date and its *Deadline* – the core of *calculate days between dates*.

### Step 3: Set deadline for a task (add deadline task & set task deadline)
Now we **add deadline task** data by setting the *Deadline* property on a specific task.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- The `Calendar` instance defines the exact deadline moment.  
- `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.

### Step 4: Save the project (manipulate Microsoft Project file)
Finally, we **manipulate Microsoft Project** by persisting the changes to an MPP file.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

You can open `SaveFile.mpp` in Microsoft Project to see the custom field, formula result, and deadline reflected in the schedule.

## Common issues and solutions
| Issue | Solution |
|-------|----------|
| **Formula not evaluating** | Ensure the attribute’s `Formula` string uses correct field names (e.g., `[Deadline]`, `[Finish]`). |
| **Task not found** | Verify the task ID (`1` in the example) exists; use `project.getRootTask().getChildren().size()` to debug. |
| **License exception** | Apply a valid Aspose.Tasks license before calling any API methods (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently asked questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing you to manipulate Microsoft Project files in the language of your choice.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Absolutely. Download a fully functional trial from the [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: How can I get support for Aspose.Tasks?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to ask questions and share experiences with the community.

**Q: Do I need a temporary license for evaluation?**  
A: A temporary license is available for short‑term testing; you can request one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-10-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [How to create extended attribute in Java with Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}