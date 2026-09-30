---
date: 2026-09-30
description: Learn how to create task extended attribute using Aspose.Tasks for Java,
  the leading java project management library for adding custom task fields.
images:
- /java/task-properties/add-extended-attributes/og-image.png
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: How to create task extended attribute with Aspose.Tasks Java
og_description: Learn how to create task extended attribute using Aspose.Tasks for
  Java, the leading java project management library for adding custom task fields.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: How to create task extended attribute with Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: How to create task extended attribute with Aspose.Tasks Java
url: /java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create task extended attribute with Aspose.Tasks Java

## Introduction
In this tutorial you’ll learn how to **create task extended attribute** in a Microsoft Project file by using Aspose.Tasks for Java. Adding custom fields lets you capture project‑specific data that isn’t covered by the built‑in columns, giving you finer‑grained control over reporting and resource planning. By the end of the guide you’ll be able to add plain‑text, lookup‑enabled, and duration attributes to any task.

## Quick answers
- **What does “extended attribute” mean?** It is a custom field that you define and attach to tasks, resources, or assignments.  
- **Which library adds this capability?** Aspose.Tasks for Java, a java project management library.  
- **Do I need a license to try it?** Yes – a free 30‑day trial is available from the Aspose website.  
- **Can I add lookup values?** Absolutely; you can supply a list of allowed values for text or duration fields.  
- **Is the API compatible with Java 8 and later?** Yes, it supports Java 8+ and runs on all major operating systems.

## What is a task extended attribute?
A task extended attribute is a user‑defined column that stores additional information for each task in a Project file. It behaves like a built‑in field but can hold any data type you need, such as text, numbers, dates, or durations.

## Why use Aspose.Tasks for Java?
Aspose.Tasks supports **50+ file formats** and can process projects with **10,000+ tasks** without requiring Microsoft Project to be installed. The library works completely offline, guaranteeing data privacy and deterministic performance for enterprise‑scale solutions.

## Prerequisites
Before you start, make sure you have:

- Basic Java programming knowledge.  
- The Aspose.Tasks for Java library installed. You can download it from the [website](https://releases.aspose.com/tasks/java/).  
- A Java IDE (IntelliJ IDEA, Eclipse, or VS Code) set up on your machine.

## Import packages
The `import` statements give you access to the core classes you’ll need, such as `Project`, `ExtendedAttributeDefinition`, and `ExtendedAttribute`.  

`Project` represents a Microsoft Project file and provides methods to read, modify, and save it.  
`ExtendedAttributeDefinition` defines a custom field that can be attached to tasks, resources, or assignments.  
`ExtendedAttribute` is an instance of a definition that holds the actual value for a specific entity.

## How do you add a plain‑text extended attribute to a task?
To add a plain‑text extended attribute, you first load the project, then create a definition of type Text, add it to the project's collection, create a task, instantiate the attribute from the definition, set its text value, attach it to the task, and finally save the project.

### 1. Set the document directory path
Specify where your source and output files live.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Create a new project
Instantiate a `Project` object, optionally loading an existing .mpp file.

```java
String dataDir = "Your Document Directory";
```

### 3. Create an extended attribute definition of Text1 type
Define the custom field as a plain‑text column named “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Add the definition to the project's extended attributes collection
Register the new definition so the project recognises it.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Add a task to the project
Create a task that will receive the custom field.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Create an extended attribute from the attribute definition
Generate an instance that you can bind to a specific task.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Assign a value to the generated extended attribute
Set the actual text you want to store, e.g., “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Add the extended attribute to the task
Attach the attribute instance to the task’s `ExtendedAttributes` collection.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Save the project
Write the updated project back to disk in the desired format.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## How do you add a text attribute with a lookup option?
When adding a text attribute with a lookup, you follow the same steps as for a plain‑text attribute, but before adding the definition you populate its `LookupValues` collection with the permitted strings. These values appear as a drop‑down list in Microsoft Project, ensuring data consistency.

## How do you add a duration attribute with a lookup option?
To add a duration attribute with a lookup, replace the `Text1` type with `Duration2` when creating the definition, then fill the `LookupValues` collection with duration strings such as “1 day”, “2 days”, etc. After the definition is added to the project, create the attribute instance, set a duration value, attach it to a task, and save the file.

## Common issues and troubleshooting
- **Lookup values not appearing** – Ensure you add each lookup entry to the `LookupValues` collection *before* calling `project.getExtendedAttributes().add(definition)`.  
- **Attribute value not saved** – Verify that you add the `ExtendedAttribute` instance to the task *after* setting its value.  
- **File size grows unexpectedly** – When working with very large projects, consider calling `project.setSaveOptions(new ProjectSaveOptions())` to enable incremental saving.

## Frequently asked questions

**Q: Can I use Aspose.Tasks for Java with other Java libraries?**  
A: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem, including Spring, Hibernate, and Apache POI.

**Q: Is Aspose.Tasks for Java suitable for large‑scale project management applications?**  
A: Absolutely. The library is engineered to handle multi‑thousand‑task projects and supports streaming to keep memory usage low.

**Q: Are there any licensing considerations for using Aspose.Tasks for Java in a commercial project?**  
A: Yes, you need a valid commercial license. You can review the details on the [Aspose.Tasks website](https://purchase.aspose.com/buy).

**Q: How can I get support or assistance with Aspose.Tasks for Java?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community help, or open a support ticket through your Aspose account.

**Q: Can I try Aspose.Tasks for Java before purchasing?**  
A: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/) page.

---

**Last updated:** 2026-09-30  
**Tested with:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Related Tutorials

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}