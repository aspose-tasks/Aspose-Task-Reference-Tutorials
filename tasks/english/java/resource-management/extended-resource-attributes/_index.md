---
title: How to Create Custom Attribute in MS Project using Aspose.Tasks
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to create custom attribute, load Microsoft Project file, set numeric value Java, and save project as XML with Aspose.Tasks for Java.
weight: 11
url: /java/resource-management/extended-resource-attributes/
date: 2026-01-13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Create Custom Attribute in MS Project using Aspose.Tasks

## Introduction
In this tutorial, **you’ll discover how to create custom attribute** for resources in a Microsoft Project file using Aspose.Tasks for Java. We'll walk through loading a Microsoft Project file, defining a new numeric attribute, assigning a value, and finally saving the project as XML. By the end, you’ll have a clear, hands‑on example you can adapt to your own project‑management solutions.

## Quick Answers
- **What does “custom attribute” mean?**  
  A user‑defined field that stores extra information (e.g., Age, Skill Level) for a resource or task.  
- **Which library handles this?**  
  Aspose.Tasks for Java provides a fluent API to create and manage custom attributes.  
- **Do I need a license?**  
  A free temporary license works for evaluation; a full license is required for production.  
- **Can I set numeric values?**  
  Yes – use `setNumericValue` with a `BigDecimal` (e.g., `30.5345`).  
- **How is the project saved?**  
  The modified file can be saved as XML using `SaveFileFormat.Xml`.

## What is a Custom Attribute?
A **custom attribute** (also called an extended attribute) is an additional column you can add to resources or tasks in Microsoft Project. It lets you capture data that isn’t covered by the built‑in fields, such as employee age, certification level, or any business‑specific metric.

## Why Create a Custom Attribute in MS Project?
- **Tailor project data** to your organization’s needs.  
- **Enable advanced reporting** by storing values that can be queried later.  
- **Maintain consistency** across multiple projects by programmatically applying the same attribute definition.

## Prerequisites
Before you start, make sure you have:

1. **Java Development Environment** – JDK 8 or higher installed.  
2. **Aspose.Tasks for Java** – Download the latest version from [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, or any Java‑compatible IDE.  

## Step‑by‑Step Guide

### Import Packages
First, import the Aspose.Tasks classes you’ll need. These provide the core functionality for handling projects, resources, and extended attributes.

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

### Step 1: Define Data Directory
Set the folder where your source project file lives and where the output will be written.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load Microsoft Project File
Create a `Project` instance by loading the existing file. This is the **load Microsoft project file** step that gives you full access to its contents.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Step 3: Define the Custom Attribute
We’ll define a new numeric attribute called **Age**. The API checks whether the definition already exists; if not, it creates one.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Step 4: Set Numeric Value in Java
Create an instance of the attribute for a specific resource and assign a numeric value using `setNumericValue`. This demonstrates **set numeric value java** in action.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Step 5: Add Resource and Attach the Custom Attribute
Add a new resource named **R1** and attach the previously created custom attribute to it.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Step 6: Save Project as XML
Finally, persist the changes by saving the project. This is the **save project as xml** step, which produces a clean XML representation of the updated file.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Step 7: Display Result
Print a friendly confirmation so you know the process completed without errors.

```java
System.out.println("Process completed Successfully");
```

By following these steps, you’ve successfully **created a custom attribute**, loaded a Microsoft Project file, set a numeric value using Java, and saved the project as XML.

## Common Pitfalls & Tips
- **Attribute ID conflicts:** Always check `getById` before creating a new definition to avoid duplicate IDs.  
- **Precision handling:** `BigDecimal` preserves decimal precision; avoid using `float` or `double` for exact values.  
- **File paths:** Use absolute paths or configure your IDE’s working directory to prevent `FileNotFoundException`.  

## Frequently Asked Questions

**Q: Can I create custom attributes for tasks as well as resources?**  
A: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource` when defining the attribute.

**Q: Is it possible to add multiple custom attributes at once?**  
A: Absolutely. Create separate `ExtendedAttributeDefinition` objects for each attribute and attach them to the desired resources or tasks.

**Q: What formats can I save the project in?**  
A: Aspose.Tasks supports XML, MPP, and several other formats like PDF and HTML. In this example we used `SaveFileFormat.Xml`.

**Q: Do I need to license Aspose.Tasks for development builds?**  
A: A temporary license is sufficient for evaluation. For production deployments, a full license is required.

**Q: How do I read back the custom attribute values later?**  
A: Use `resource.getExtendedAttributes()` to iterate over attached attributes and retrieve their values with `getNumericValue()` or `getTextValue()`.

## Conclusion
Creating a **custom attribute** in Microsoft Project with Aspose.Tasks for Java is straightforward once you understand the workflow: load the project, define the attribute, set its value, attach it to a resource, and save the file. This approach empowers you to extend project data models programmatically, enabling richer reporting and tighter integration with your business processes.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}