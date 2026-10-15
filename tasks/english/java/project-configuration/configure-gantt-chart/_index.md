---
date: 2026-10-15
description: Learn how to create activity, set the data directory, customize table
  fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide for
  Java developers.
images:
- /java/project-configuration/configure-gantt-chart/og-image.png
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: How to create activity and set data directory using Aspose.Tasks for Java
og_description: How to create activity, customize table fields and save project as
  MPP using Aspose.Tasks for Java. Follow this detailed guide for fast implementation.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: How to create activity and set data directory in Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: How to create activity and set data directory using Aspose.Tasks for Java
url: /java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create activity and set data directory using Aspose.Tasks for Java

## Introduction
In this tutorial you’ll discover **how to create activity** programmatically, configure the **data directory**, and **save project as MPP** while also **customizing table fields** in a Gantt chart view. Aspose.Tasks for Java is a powerful API that supports over 30 input and output formats and can process projects with up to 10 000 tasks without loading the entire file into memory. By the end of the guide you’ll be able to automate project creation, enrich tasks with custom attributes, and produce a ready‑to‑open MPP file for Microsoft Project.

## Quick answers
- **What is the first step?** Set the data directory path where your project files reside.  
- **Which library is required?** Aspose.Tasks for Java (downloadable from the official site).  
- **Can I add custom attributes?** Yes – you can define extended attributes and show them in the Gantt chart.  
- **Do I need a license for testing?** A temporary license is available for evaluation purposes.  
- **Which IDE works best?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) will work.

## What is “set data directory” and why does it matter?
Setting the data directory tells Aspose.Tasks where to read and write project files. Without a correct path the API cannot locate your `.mpp` files, leading to `FileNotFoundException` errors. Defining this directory at the start of your code makes the workflow repeatable and isolates file‑system concerns from business logic.

## Why customize table fields in a Gantt chart?
Custom table fields let you surface additional information—such as custom attributes, resource data, or project‑specific notes—directly in the Gantt view. This reduces the need for separate reports and gives stakeholders a single, data‑rich visual that can improve decision‑making speed by up to 30 %.

## How to create new activity?
You create a new activity (task) by instantiating a `Task` object and adding it to the project’s root task collection. This approach lets you generate large schedules automatically, pull task data from external systems, or apply bulk updates without manual editing.

## Prerequisites
Before you begin, ensure you have:

1. **Java Development Kit (JDK)** – version 8 or newer.  
2. **Aspose.Tasks for Java** – download it from the **Aspose.Tasks Java release page**.  
3. **IDE** – IntelliJ IDEA, Eclipse, or any Java‑compatible editor you prefer.  

## Import packages
The `com.aspose.tasks` namespace contains all the classes you’ll need for project manipulation. Importing it gives you access to `Project`, `Task`, `ExtendedAttributeDefinition`, and other core types.

```java
import com.aspose.tasks.*;
```

## Maven dependency (optional)
If you manage your project with Maven, add the Aspose.Tasks dependency to `pom.xml`. This ensures the library is resolved automatically during the build.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Step‑by‑step guide

### Step 1: set up data directory
Define the folder that contains your project files. The `dataDir` variable holds the absolute path and is reused throughout the tutorial.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the full path to the folder where `project.mpp` lives, for example `C:/Projects/MyGantt`.

### Step 2: load project file
`Project` is Aspose.Tasks' top‑level object that represents a single Microsoft Project file in memory. Loading an existing file gives you access to its tasks, resources, and tables.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: add new activity
`Task` represents an individual activity in the schedule. Adding a task to the root task collection inserts it at the top level of the project hierarchy.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Step 4: define custom attribute
`ExtendedAttributeDefinition` lets you create a reusable custom field that can be attached to any task, resource, or assignment.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Step 5: add custom attribute to task
`ExtendedAttribute` is the concrete instance of a custom attribute that you assign to a specific task.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Step 6: customize table – add custom attribute as a column
`TableField` describes a column in a Gantt chart table. By adding a `TableField` that references the custom attribute, you make the attribute visible in the chart view.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Step 7: save project
Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP` constant tells Aspose.Tasks to write the file in Microsoft Project’s native binary format.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Common issues and solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** when loading the project | The **set data directory** path is incorrect or missing a trailing slash. | Verify `dataDir` points to the exact folder and include the proper file separator (`/` or `\\`). |
| Custom attribute not visible in Gantt view | The table field was added at the wrong index or the column width is too small. | Ensure `table.getTableFields().add(3, attrField);` uses a valid index and adjust `setWidth` as needed. |
| LicenseException on save | No valid license was applied for production use. | Apply a temporary or permanent license before calling `project.save()`. |

## Frequently asked questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks is available for .NET, Java, and C++.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Yes, you can download a free trial from the **Aspose.Tasks free trial download page**.

**Q: Where can I find support for Aspose.Tasks?**  
A: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: How do I purchase a license for Aspose.Tasks?**  
A: You can purchase a license from the **Aspose.Tasks purchase page**.

**Q: Do I need a temporary license for testing purposes?**  
A: Yes, you can obtain a temporary license from the **temporary license request page**.

## Conclusion
You now know **how to create activity**, set the data directory, define and attach a custom attribute, and **save project as MPP** while **customizing table fields** in a Gantt chart view using Aspose.Tasks for Java. These capabilities give you full programmatic control over project data, enabling automated schedule generation and richer visual reporting for your stakeholders.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose

## Related Tutorials

- [How to Create Empty Project File in Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}