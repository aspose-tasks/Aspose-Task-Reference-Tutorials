---
title: Add custom column with Aspose.Tasks: Handle extended attributes
linktitle: Add custom column with Aspose.Tasks: Handle extended attributes
second_title: Aspose.Tasks Java API
description: Learn how to add custom column and create custom field in Aspose.Tasks projects using Java, handling extended attributes efficiently.
weight: 13
url: /java/project-management/extended-attributes/
date: 2026-05-31
keywords:
- add custom column
- custom field task
- java extended attributes
- create custom field
- define extended attribute
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add custom column with Aspose.Tasks: Handle extended attributes

In modern project‑management solutions you often need to **add custom column** data that isn’t covered by the out‑of‑the‑box MS Project fields. Aspose.Tasks for Java gives you a clean API to **create custom field** definitions, attach them to tasks, and persist the changes back to the project file. In this hands‑on guide we’ll walk through every step—from defining the extended attribute to saving the project—so you can start customizing your schedules today.

## Quick Answers
- **What does “add custom column” mean?**  
  It means defining a new extended attribute (custom field) that appears as an extra column in the project view.  
- **Which library is required?**  
  Aspose.Tasks for Java (any recent release supports the full feature set).  
- **Do I need a license for this example?**  
  A free trial works for development; a commercial license is required for production deployments.  
- **Can I assign the custom column to a task?**  
  Yes – the tutorial shows how to add the custom field to a specific task.  
- **What file formats can I save to?**  
  XML, MPP, and more than 30 other formats via `SaveFileFormat`.

## What is add custom column?
`add custom column` is the process of creating an **ExtendedAttributeDefinition** that defines a new column’s data type, alias, and unique field ID, then attaching an **ExtendedAttribute** instance to a task or resource. This column behaves like any built‑in field in Microsoft Project and is fully round‑trippable.

## Why handle extended attributes?
Adding custom columns gives you **flexibility**, **reporting power**, and **integration safety**. Aspose.Tasks supports **30+** built‑in attribute types and can manage projects with **up to 10,000 tasks** while keeping memory usage under 200 MB, so performance remains smooth even for large schedules. These attributes can also be leveraged in custom reports and exported to other tools without data loss.

## Prerequisites
- Familiarity with Java syntax and object‑oriented concepts.  
- JDK 8 or newer installed on your workstation.  
- Aspose.Tasks for Java JAR added to your project’s classpath (Maven, Gradle, or manual copy).

## Import Packages
The following imports give you access to the core project manipulation classes.

The `Project` class is the entry point for loading and saving MS Project files.  
`ExtendedAttributeDefinition` defines the schema of a custom column.  
`ExtendedAttribute` holds the actual value for a particular task.  

```java
import java.util.Date;
import com.aspose.tasks.*;
```

## Step 1: Define Data Directory
First, tell the program where your source files live.

The `dataDir` string points to the folder that contains `project5.mpp`. Using an absolute path or a well‑structured relative path prevents `FileNotFoundException` at runtime.  

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Keep all project assets (templates, resources, and output files) under a single `data` folder to simplify path management.

## Step 2: Load Project File
Load the existing project so you can modify it.

The `Project` class represents the whole project in memory; calling its constructor with the file path parses the MPP file and builds a full object model.  

```java
Project prj = new Project(dataDir + "project5.mpp");
```

## Step 3: Access Extended Attribute Definitions
Retrieve the collection that holds all custom field definitions.

`prj.getExtendedAttributes()` returns a live collection you can query, add to, or iterate over.  

```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```

## Step 4: Create Extended Attribute Definition
Define the new custom column “Start 7” as a start‑date field for tasks.

`ExtendedAttributeDefinition` specifies the schema of a custom field, including its type, alias, and unique ID.  

```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```

## Step 5: Add Definition to Project
Insert the new definition into the project’s global collection.

Adding the definition to `prj.getExtendedAttributes()` makes it available for any task, resource, or assignment in the file.  

```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```

## Step 6: Access Task and Extended Attributes
Select a task (ID = 1) and fetch its current extended attributes.

`Task` represents an individual work item in the project schedule.  

```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```

## Step 7: Create Extended Attribute Instance
Create an instance of the definition for the chosen task.

`ExtendedAttribute` holds the actual value for a custom field attached to a task, resource, or assignment.  

```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```

## Step 8: Set Attribute Value
Assign today’s date to the new custom column.

`setDateValue` assigns a Date object to the attribute, storing it as a date‑type custom field.  

```java
Date date = new Date();
ea.setDateValue(date);
```

## Step 9: Add Attribute to Task
Attach the populated custom field to the task’s collection.

`add` inserts the ExtendedAttribute into the task’s attribute list, making it part of the project data.  

```java
eas.add(ea);
```

## Step 10: Save Project
Persist the changes back to disk.

`SaveFileFormat` enumerates the supported output formats such as XML, MPP, and PDF.  

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **`NullPointerException` when accessing task** | Verify that the task ID exists (`getById(1)` assumes a task with ID 1). Use `prj.getRootTask().getChildren().size()` to list available IDs. |
| **Custom column does not appear in Microsoft Project** | Save in a format that retains custom fields (e.g., `.mpp` or `.xml`). Open the file in MS Project and insert the column via “Insert Column”. |
| **Date value shows as 01/01/1970** | Ensure the `Date` object is correctly instantiated; avoid deprecated constructors and set the timezone if needed. |

## FAQ's
**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks provides APIs for Java, .NET, and C++.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Absolutely. You can download a fully functional trial from the Aspose.Tasks website.

**Q: Can I customize the type of an extended attribute?**  
A: Yes, you can define custom fields of type Date, Text, Cost, Number, Flag, and many more.

**Q: Where can I find the official documentation?**  
A: Comprehensive API docs are available at the Aspose.Tasks [documentation](https://reference.aspose.com/tasks/java/) site.

**Q: Is technical support offered for Aspose.Tasks users?**  
A: Yes, the Aspose.Tasks community forum provides prompt assistance: [website](https://forum.aspose.com/c/tasks/15).

## Additional Frequently Asked Questions
**Q: Does adding a custom column affect project performance?**  
A: Adding a few custom columns has a negligible impact; performance degradation only becomes noticeable when thousands of custom fields are created in a single project.

**Q: Can I copy custom columns between projects?**  
A: Yes, export the `ExtendedAttributeDefinition` from one project and import it into another using the same API calls.

**Q: Are custom columns version‑compatible?**  
A: Custom columns saved in newer Aspose.Tasks versions remain readable by older versions as long you use a supported file format such as XML.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose

## Related Tutorials

- [Add Extended Attributes to Tasks in Aspose.Tasks](/tasks/java/task-properties/add-extended-attributes/)
- [How to Create Project – Set New Task Attributes with Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [How to Create View - Custom MS Project Views in Aspose.Tasks](/tasks/java/project-file-operations/custom-views/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}