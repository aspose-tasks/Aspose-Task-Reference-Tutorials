---
title: How to Set Link Types in Aspose.Tasks for Java
linktitle: How to Set Link Types in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
description: Learn how to set link types and manage task dependencies with Aspose.Tasks for Java in a step‑by‑step tutorial.
weight: 13
url: /java/task-links/define-link-type/
date: 2026-01-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Link Types in Aspose.Tasks for Java

## Introduction
If you're wondering **how to set link** between tasks while you *manage task dependencies* in a project, you’ve come to the right place. In this tutorial we’ll walk through creating a new project, adding tasks, and defining the link type (Start‑to‑Start, Finish‑to‑Start, etc.) using Aspose.Tasks for Java. By the end you’ll feel confident customizing task relationships to match your real‑world scheduling needs.

## Quick Answers
- **What is the primary class for links?** `TaskLink` in the Aspose.Tasks library.  
- **Which enum defines link types?** `TaskLinkType` (e.g., `StartToStart`).  
- **Can I read existing link types?** Yes, iterate `Project.getTaskLinks()` and call `getLinkType()`.  
- **Do I need a license for this code?** A temporary license works for testing; a full license is required for production.  
- **Is this compatible with Java 8+?** Absolutely – Aspose.Tasks supports modern Java runtimes.

## Prerequisites
Before we dive in, ensure you have the following:

- **Java Development Environment** – JDK 8 or newer installed and configured.  
- **Aspose.Tasks Library** – Download the latest JAR from the [download link](https://releases.aspose.com/tasks/java/).  
- **Document Directory** – Create a folder on your machine where you’ll keep the sample project files.

## Import Packages
We start by importing the essential Aspose.Tasks classes. This prepares the IDE to recognize the API calls we’ll use later.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## How to Set Link Types in Aspose.Tasks
Below we break the process into two clear steps: creating a link with a specific type, and then reading that type back from an existing project.

### Step 1: Setting a Link Type
In this step we create a fresh project, add two tasks, and link them using the **Start‑to‑Start** relationship. This demonstrates **how to set link** programmatically.

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

### Step 2: Getting a Link Type
Now we load an existing project file (`project.xml`) and enumerate all links to see which type each one uses. This is useful for auditing or modifying existing schedules.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

The console will output values such as `StartToStart`, `FinishToStart`, etc., confirming the link type you previously set.

## Common Issues & Solutions
- **NullPointerException when adding links** – Ensure both predecessor and successor tasks are added to the project before creating a `TaskLink`.  
- **Incorrect link type after saving** – Always call `project.save("output.mpp")` (or another supported format) after setting the link type to persist changes.  
- **License not found** – Place your Aspose.Tasks license file in the project’s classpath and load it with `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Frequently Asked Questions

### Q: Is Aspose.Tasks compatible with different Java environments?
A: Yes, Aspose.Tasks is designed to seamlessly integrate with various Java development environments.

### Q: Can I customize link types based on my project requirements?
A: Absolutely! Aspose.Tasks provides flexibility, allowing you to define and customize link types to suit your project needs.

### Q: Where can I find detailed documentation for Aspose.Tasks for Java?
A: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) for in‑depth guidance.

### Q: How can I obtain a temporary license for Aspose.Tasks?
A: Visit [this link](https://purchase.aspose.com/temporary-license/) to acquire a temporary license for testing purposes.

### Q: Where can I get support for Aspose.Tasks-related queries?
A: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15) for assistance and discussions.

### Q: Can I change a link type after the project is saved?
A: Yes. Load the project, retrieve the `TaskLink`, call `setLinkType()` with the new enum value, and save the project again.

### Q: Does Aspose.Tasks support reading Microsoft Project (MPP) files?
A: It does. Use `new Project("file.mpp")` to load MPP files and work with their task links just like the XML example above.

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}