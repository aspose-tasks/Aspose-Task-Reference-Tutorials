---
date: 2026-08-29
description: Learn how to set link types and manage task dependencies with Aspose.Tasks
  for Java in a step‑by‑step tutorial.
images:
- /java/task-links/define-link-type/og-image.png
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: How to Set Link Types in Aspose.Tasks for Java
og_description: Learn how to set link types and manage task dependencies with Aspose.Tasks
  for Java. Step‑by‑step guide for developers.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: How to set link types in Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: How to Set Link Types in Aspose.Tasks for Java
url: /java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set link types in Aspose.Tasks for Java

## Introduction
If you're wondering **how to set link** between tasks while you *manage task dependencies* in a project, you’ve come to the right place. In this tutorial we’ll walk through creating a new project, adding tasks, and defining the link type (Start‑to‑Start, Finish‑to‑Start, etc.) using Aspose.Tasks for Java. By the end you’ll feel confident customizing task relationships to match real‑world scheduling needs and you’ll see how the API handles large‑scale plans with up to 10,000 tasks.

## Quick answers
- **What class represents a dependency?** `TaskLink` is the core object that models a link between two tasks.  
- **Which enum defines the relationship type?** `TaskLinkType` (e.g., `StartToStart`, `FinishToStart`).  
- **Can I read existing link types?** Yes – iterate `Project.getTaskLinks()` and call `getLinkType()`.  
- **Do I need a license for this code?** A temporary license works for testing; a full license is required for production.  
- **Is this compatible with Java 8+?** Absolutely – Aspose.Tasks supports Java 8 through Java 21, covering 13 major releases.

## What is a task link?
A **task link** models a dependency between two tasks in a project schedule.  
You can create, modify, or delete a `TaskLink` to reflect predecessor‑successor relationships, enabling the scheduler to calculate start and finish dates automatically.

## Why use Aspose.Tasks link types?
Aspose.Tasks supports **30+ input and output formats** and can process projects containing **up to 10,000 tasks** without loading the entire file into memory. This quantified capability ensures fast performance even for enterprise‑scale plans, and the library preserves all Microsoft Project features such as custom fields and resource assignments.

## Prerequisites
- **Java Development Environment** – JDK 8 or newer installed and configured.  
- **Aspose.Tasks Library** – Download the latest JAR from the [download link](https://releases.aspose.com/tasks/java/).  
- **Document Directory** – Create a folder on your machine where you’ll keep the sample project files.

## Import packages
We start by importing the essential Aspose.Tasks classes. This prepares the IDE to recognize the API calls we’ll use later.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## How to set link types in Aspose.Tasks for Java?
Load a fresh `Project` instance, add two tasks, and then create a `TaskLink` with the desired `TaskLinkType`. This two‑step pattern lets you define any of the four standard dependency types in a single call. `Project` represents the entire project file and its schedule. `Task` is an individual work item within the project. `TaskLink` connects a predecessor task to a successor task. `TaskLinkType` is an enumeration that specifies the relationship (Start‑to‑Start, Finish‑to‑Start, etc.).

### Step 1: setting a link type
`TaskLink` represents a dependency between two tasks, while `TaskLinkType` enumerates the possible relationship types such as `StartToStart`. In this step we create a fresh project, add two tasks, and link them using the **Start‑to‑Start** relationship.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Pro tip:** You can replace `StartToStart` with `FinishToStart`, `StartToFinish`, or `FinishToFinish` depending on the dependency you need to **manage task dependencies**.

### Step 2: getting a link type
`Project.getTaskLinks()` returns a collection of all `TaskLink` objects in the schedule. By iterating this collection you can read each link’s `TaskLinkType` and verify that the correct relationship was persisted.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

The console will output values such as `StartToStart`, `FinishToStart`, etc., confirming the link type you previously set.

## Common issues & solutions
- **NullPointerException when adding links** – Ensure both predecessor and successor tasks are added to the project before creating a `TaskLink`.  
- **Incorrect link type after saving** – Always call `project.save("output.mpp")` (or another supported format) after setting the link type to persist changes.  
- **License not found** – Place your Aspose.Tasks license file in the project’s classpath and load it with `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Frequently asked questions

**Q: Is Aspose.Tasks compatible with different Java environments?**  
A: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android development kits without additional dependencies.

**Q: Can I customize link types based on my project requirements?**  
A: Absolutely. The `TaskLinkType` enum provides four standard types, and you can combine them with lag values to model complex schedules.

**Q: Where can I find detailed documentation for Aspose.Tasks for Java?**  
A: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) for in‑depth guidance, API reference, and code samples.

**Q: How can I obtain a temporary license for Aspose.Tasks?**  
A: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/) to acquire a temporary license for testing purposes.

**Q: Where can I get support for Aspose.Tasks‑related queries?**  
A: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15) for assistance and discussions.

**Q: Can I change a link type after the project is saved?**  
A: Yes. Load the project, retrieve the `TaskLink`, call `setLinkType()` with the new enum value, and save the project again.

**Q: Does Aspose.Tasks support reading Microsoft Project (MPP) files?**  
A: It does. Use `new Project("file.mpp")` to load MPP files and work with their task links just like the XML example above.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [Create Cross-Project Task Link in Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Load MPP File Java - Manage Project Properties with Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}