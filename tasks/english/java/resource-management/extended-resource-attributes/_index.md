---
title: How to create extended attribute in Java with Aspose.Tasks
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to create extended attribute in Java, load a Microsoft Project file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
weight: 11
url: /java/resource-management/extended-resource-attributes/
date: 2026-06-10
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
schemas:
- type: TechArticle
  headline: How to create extended attribute in Java with Aspose.Tasks
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  dateModified: '2026-06-10'
  author: Aspose
- type: HowTo
  name: How to create extended attribute in Java with Aspose.Tasks
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
- type: FAQPage
  questions:
  - question: Can I create custom attributes for tasks as well as resources?
    answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
  - question: Is it possible to add multiple custom attributes at once?
    answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
  - question: What formats can I save the project in?
    answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
  - question: Do I need a license for development builds?
    answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
  - question: How do I read back the custom attribute values later?
    answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create extended attribute in Java with Aspose.Tasks

## Introduction
In this hands‑on guide you’ll **create extended attribute in Java** for a Microsoft Project file using Aspose.Tasks. We’ll walk through loading an existing project, defining a new numeric attribute, assigning a value to a resource, and finally persisting the changes as an XML file. By the end you’ll have a reusable code pattern that can be dropped into any Java‑based project‑management solution.

## Quick Answers
- **What is an extended attribute?**  
  A user‑defined field (e.g., Age, Skill Level) that stores extra data for resources or tasks.  
- **Which API creates it?**  
  Aspose.Tasks for Java provides the `ExtendedAttributeDefinition` class to define and manage custom attributes.  
- **Do I need a license?**  
  A temporary evaluation license works for development; a full license is required for production deployments.  
- **Can I store numbers?**  
  Yes – use `setNumericValue(BigDecimal)` to assign precise decimal values.  
- **How do I persist the changes?**  
  Call `project.save("output.xml", SaveFileFormat.Xml)` to write the updated project in XML format.

## What is a custom attribute?
A **custom attribute** (also known as an extended attribute) is an additional column you can add to resources or tasks in Microsoft Project. It lets you capture data that isn’t covered by the built‑in fields, such as employee age, certification level, or any business‑specific metric.

## Why create an extended attribute in Java?
Creating an extended attribute in Java lets you programmatically enrich project data, ensuring consistency across files and enabling automated reporting. By defining the attribute once, you can apply it to any number of resources or tasks without manual entry, saving time and reducing errors.

- **Tailor data to your organization** – store any metric that matters to you without manual Excel workarounds.  
- **Enable richer reporting** – query the custom field later for dashboards or analytics.  
- **Maintain consistency** – programmatically apply the same definition across dozens of projects, eliminating human error.  
- **Performance‑tested** – Aspose.Tasks processes projects with up to 10,000 tasks and 5,000 resources without loading the entire file into memory, according to the product benchmarks.

## Prerequisites
Before you start, ensure you have:

1. **Java Development Kit** – JDK 8 or newer installed.  
2. **Aspose.Tasks for Java** – download the latest release from [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, or any Java‑compatible development environment.  

## How to create an extended attribute in Java?
Load your project, define the attribute, attach it to a resource, and save the file – all in a few straightforward steps. The following sections break each step into a concise explanation followed by the placeholder where your actual code lives.

### Step‑by‑Step Guide

#### Import Packages
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource`, and related classes reside in the `com.aspose.tasks` namespace. Import them at the top of your Java file.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Step 1: Define Data Directory
`Paths` is a utility class that provides methods to obtain a file system path in a platform‑independent way.

```java
String dataDir = "Your Data Directory";
```

#### Step 2: Load Microsoft Project File
`Project` represents a Microsoft Project file in memory, allowing read and write access to its contents.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Step 3: Define the Custom Attribute
`ExtendedAttributeDefinition` defines the schema of a new custom field that can be attached to resources or tasks.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Step 4: Set Numeric Value in Java
`ExtendedAttributeResource` holds the value of a custom attribute for a specific resource instance.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Step 5: Add Resource and Attach the Custom Attribute
`Resource` models a project resource such as a person, equipment, or material.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Step 6: Save Project as XML
`SaveFileFormat` enumerates the supported output formats for saving a project, including XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Step 7: Display Result
`System.out.println` prints a line of text to the standard console output.

```java
System.out.println("Process completed Successfully");
```

## Common Pitfalls & Tips
- **Attribute ID conflicts:** Always call `project.getExtendedAttributes().getById(id)` before creating a new definition to prevent duplicate identifiers.  
- **Precision handling:** Prefer `BigDecimal` over `float`/`double` for exact numeric values; this avoids rounding errors in reporting.  
- **File path reliability:** Use `Paths.get(...).toAbsolutePath()` or configure your IDE’s working directory to eliminate `FileNotFoundException`.  

## Frequently Asked Questions

**Q: Can I create custom attributes for tasks as well as resources?**  
A: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource` when defining the attribute schema.

**Q: Is it possible to add multiple custom attributes at once?**  
A: Absolutely. Create separate `ExtendedAttributeDefinition` objects for each attribute and attach them to the desired resources or tasks.

**Q: What formats can I save the project in?**  
A: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional formats. In this example we used `SaveFileFormat.Xml`.

**Q: Do I need a license for development builds?**  
A: A temporary evaluation license is sufficient for testing. For any production deployment, a full commercial license is required.

**Q: How do I read back the custom attribute values later?**  
A: Call `resource.getExtendedAttributes()` and iterate over the collection; retrieve the stored value with `getNumericValue()` or `getTextValue()`.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [How to Create Resources – Resource Management with Aspose.Tasks for Java](/tasks/java/resource-management/)
- [Create custom field Aspose - Handle extended attributes](/tasks/java/project-management/extended-attributes/)
- [How to Create Project – Set New Task Attributes with Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}