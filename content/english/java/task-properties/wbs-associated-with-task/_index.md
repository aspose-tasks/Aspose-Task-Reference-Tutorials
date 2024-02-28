---
title: WBS Associated with Task in Aspose.Tasks
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Master WBS with Aspose.Tasks for Java - Learn to read and renumber task WBS codes. Boost project management efficiency!
type: docs
weight: 36
url: /java/task-properties/wbs-associated-with-task/
---
## Introduction
Welcome to the world of project management with Aspose.Tasks for Java! In this tutorial, we'll delve into the intricacies of Work Breakdown Structure (WBS) associated with tasks using Aspose.Tasks for Java. Whether you're a seasoned developer or just starting, this guide will help you navigate through the essentials of managing WBS codes efficiently.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Java Development Kit (JDK) installed on your machine.
- Aspose.Tasks for Java library downloaded and added to your project. You can get it from [here](https://releases.aspose.com/tasks/java/).
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
Let's start by reading WBS codes associated with tasks. Follow these steps:
## Step 1: Load the Project
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Step 2: Collect Tasks
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Step 3: Parse and Customize
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
This snippet reads and customizes WBS codes associated with tasks in your project.
## Renumber Task WBS Codes
Now, let's explore renumbering WBS codes for tasks:
## Step 1: Load the Project
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Step 2: Select All Tasks
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Step 3: Output Initial WBS Codes
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Step 4: Renumber WBS Codes
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Step 5: Output Updated WBS Codes
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
By following these steps, you'll effectively renumber WBS codes for tasks in your project.
## Conclusion
Congratulations! You've successfully learned how to work with WBS codes using Aspose.Tasks for Java. This knowledge will empower you to efficiently manage and customize your project's task hierarchy.
## FAQs
### Q: Where can I find the official documentation for Aspose.Tasks for Java?
A: The official documentation is available [here](https://reference.aspose.com/tasks/java/).
### Q: How can I download Aspose.Tasks for Java?
A: You can download it [here](https://releases.aspose.com/tasks/java/).
### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can get a free trial [here](https://releases.aspose.com/).
### Q: Where can I get support for Aspose.Tasks for Java?
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for support.
### Q: Can I obtain a temporary license for Aspose.Tasks for Java?
A: Yes, get a temporary license [here](https://purchase.aspose.com/temporary-license/).
