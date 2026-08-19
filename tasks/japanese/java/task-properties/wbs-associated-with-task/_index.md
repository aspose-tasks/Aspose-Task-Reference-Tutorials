---
date: 2026-03-03
description: Aspose.Tasks for JavaでWBSの番号付けを変更する方法を学び、作業分解を管理し、ステップバイステップの例でWBSコードを効率的にカスタマイズします。
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for JavaでWBSを再番号付けする方法
url: /ja/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java で WBS を再番号付けする方法

## Introduction
If you need to **how to renumber WBS** in a Microsoft Project file using Aspose.Tasks for Java, you’re in the right place. This tutorial walks you through reading existing WBS codes, customizing them, and then renumbering the hierarchy so your project stays organized. Whether you’re cleaning up a legacy schedule or building a new one from scratch, mastering these steps will help you **manage work breakdown** structures with confidence.

## Quick Answers
- **What does renumbering WBS do?** It recalculates the hierarchical numbering of tasks to reflect any structural changes.  
- **Which class performs the renumbering?** `Project.renumberWBSCode`.  
- **Do I need a license to run the code?** A valid Aspose.Tasks license is required for production use.  
- **Can I customize the WBS format?** Yes—use `Task.set(Tsk.WBS, "...")` to assign any string you like.  
- **What are the main prerequisites?** Java JDK, Aspose.Tasks for Java library, and a valid project file (.mpp).

## What is a Work Breakdown Structure (WBS)?
Work Breakdown Structure (WBS) は、プロジェクトの成果物やタスクを階層的に表現したものです。各タスクにはコード（例: 1.2.3）が付与され、階層上の位置を示します。タスクの追加・削除・並び替えが行われた際に、コードを論理的かつ読みやすく保つために再番号付けが必要になります。

## Why manage work breakdown and customize WBS codes?
- **Clarity:** Clear WBS codes make it simple for stakeholders to locate tasks.  
- **Reporting:** Many reporting tools rely on consistent numbering.  
- **Flexibility:** Custom codes let you align the project structure with internal standards.  

## Prerequisites
Before we dive into the code, confirm you have the following:

- Java Development Kit (JDK) installed on your machine.  
- Aspose.Tasks for Java library added to your project. You can get it from [here](https://releases.aspose.com/tasks/java/).  

## Import Packages
Ensure you import the necessary packages to kickstart your project:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Read WBS Codes
First, we’ll read the existing WBS codes so you can see what you’re working with.

### Step 1: Load the Project
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Step 2: Collect Tasks
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Step 3: Parse and Customize
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

The snippet above prints each task’s current WBS and level, then demonstrates **customize wbs codes** by assigning a new string.

## Renumber Task WBS Codes
Now let’s actually renumber the WBS hierarchy.

### Step 1: Load the Project (Renumber Example)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Step 2: Select All Tasks
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Step 3: Output Initial WBS Codes
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Step 4: Renumber WBS Codes
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Step 5: Output Updated WBS Codes
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

By following these steps, you’ll effectively **how to renumber wbs** for any set of tasks in your project file.

## Common Issues and Solutions
- **WBS not changing after `set` call:** Ensure you are working with the correct task instance and that the project is saved after modifications.  
- **`renumberWBSCode` throws an exception:** Verify that the list of IDs matches the number of top‑level tasks; otherwise the method cannot map new numbers correctly.  
- **Missing WBS values:** Some tasks may have a `null` WBS if they were imported from a file that didn’t define one. Use a fallback value before printing.

## Frequently Asked Questions

**Q: Where can I find the documentation for Aspose.Tasks for Java?**  
A: The documentation is available [here](https://reference.aspose.com/tasks/java/).

**Q: How can I download Aspose.Tasks for Java?**  
A: You can download it [here](https://releases.aspose.com/tasks/java/).

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: Yes, you can get a free trial [here](https://releases.aspose.com/).

**Q: Where can I get support for Aspose.Tasks for Java?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for support.

**Q: Can I obtain a temporary license for Aspose.Tasks for Java?**  
A: Yes, get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Can I rename the WBS format after renumbering?**  
A: Absolutely. After calling `renumberWBSCode`, you can iterate over the tasks and apply `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` to suit your naming conventions.

**Q: Does renumbering affect task dependencies?**  
A: No. The method only updates the WBS string; task links and constraints remain unchanged.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}