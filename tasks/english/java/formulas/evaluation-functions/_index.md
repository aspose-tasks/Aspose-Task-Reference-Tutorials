---
date: 2026-10-10
description: Learn how to add extended attribute in Aspose.Tasks, use evaluation functions,
  and generate project reports with this Java project management library.
images:
- /java/formulas/evaluation-functions/og-image.png
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
og_description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
  functions, and generate project reports with this Java project management library.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: How to add extended attribute in Aspose.Tasks formulas
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: How to add extended attribute in Aspose.Tasks formulas
url: /java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to add extended attribute in Aspose.Tasks formulas

## Introduction
Aspose.Tasks for Java is a **Java project management library** that lets you generate project reports by creating a `Project` object in Java and evaluating Microsoft Project functions directly inside your code. By embedding these formulas, you can run sophisticated calculations, generate custom reports, and automate project analysis without leaving your development environment. In this tutorial we’ll walk through creating a project object, adding an extended attribute, and using evaluation functions to **add custom field task** data.

## Quick answers
- **What does “create project object java” mean?** It creates an in‑memory `Project` instance that you can manipulate programmatically.  
- **Which library is required?** Aspose.Tasks for Java (download from the official site).  
- **Do I need a license?** A temporary or full Aspose.Tasks license is required for production use; a free trial is available.  
- **Can I use custom fields?** Yes – you can **add extended attribute** to tasks and treat them as custom fields.  
- **Is this compatible with all Project file formats?** Aspose.Tasks supports 3 major formats (MPP, MPT, XML) and over 50 additional input/output formats.

## Prerequisites
Before getting started, make sure you have:

1. **Java Development Environment** – JDK 8+ and an IDE such as IntelliJ IDEA or Eclipse.  
2. **Aspose.Tasks for Java Library** – Download and include the library from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Import packages
Add the Aspose.Tasks namespace to your Java class so you can work with projects, tasks, and extended attributes:

```java
import com.aspose.tasks.*;
```

## Generate project report – create project object java
The `Project` class represents a Microsoft Project file in memory, exposing tasks, resources, and custom data. Instantiating this class gives you a container for all project elements you’ll define.

```java
Project project = new Project();
```

The line above **creates project object java** that starts out empty and ready for customization.

## How to add extended attribute
The `ExtendedAttributeDefinition` class defines a custom field that can be attached to tasks. To add an extended attribute, create an instance of this class with type `Number`, assign it an alias such as “Sine”, add it to the project's `ExtendedAttributes` collection, and then link it to each task that requires the custom field.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Here we **add extended attribute** of type `Number` named “Sine” and associate it with tasks.

## Add the extended attribute to the project
Register the attribute definition with the project so every task can reference it.

```java
project.getExtendedAttributes().add(attr);
```

## Create a new task
`Task` represents a work item in the project and can contain custom fields.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Add custom field task to the project
Link the previously defined extended attribute to the newly created task, giving the task a custom “Sine” field that you can use in formulas or calculations.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Now the task holds a custom “Sine” field that you can use in formulas or calculations. This is also how you **add custom field task** data programmatically.

## Why use evaluation functions?
Evaluation functions let you embed native Microsoft Project formulas (e.g., `Sin([Start])`) directly in Aspose.Tasks, enabling on‑the‑fly calculations without external processing. This keeps all project logic in one place, reduces data‑sync errors, and speeds up report generation. Aspose.Tasks supports evaluation of over 100 MS Project functions, providing a comprehensive calculation engine inside Java.

## Common issues and solutions
| Issue | Solution |
|-------|----------|
| **Formula returns `NaN`** | Verify that the custom field type matches the expected numeric type. |
| **Extended attribute not visible** | Ensure the attribute definition is added to the project **before** creating tasks. |
| **License exception** | Install a temporary or full **Aspose.Tasks license**; trial mode may limit certain features. |
| **Missing temporary license** | Obtain a **temporary Aspose license** from the Aspose website. |

## Frequently asked questions

**Q: Can Aspose.Tasks for Java handle complex MS Project formulas?**  
A: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project functions, allowing for complex calculations within Java applications.

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project files?**  
A: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project files, including MPP, MPT, and XML formats.

**Q: Can I try Aspose.Tasks for Java before purchasing?**  
A: Yes, you can download a free trial version of Aspose.Tasks for Java from the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: How can I get support for Aspose.Tasks for Java?**  
A: You can get support from the Aspose.Tasks community forum [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Is there a temporary license available for Aspose.Tasks for Java?**  
A: Yes, you can obtain a temporary license for testing purposes from the Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Conclusion
By following these steps you’ve learned how to **create project object**, **add extended attribute**, and leverage evaluation functions to **generate project report** automatically. You can now extend this foundation to build richer project analytics, custom dashboards, or automated scheduling tools—all powered by Aspose.Tasks for Java.

---

**Last Updated:** 2026-10-10  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose

## Related Tutorials

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}