---
title: Manage Durations of Tasks in Aspose.Tasks
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Explore Aspose.Tasks for Java and learn to manage task durations effortlessly. Follow our step-by-step guide for effective project planning and execution.
type: docs
weight: 20
url: /java/task-properties/manage-durations/
---
## Introduction
Aspose.Tasks for Java provides a robust solution for managing project tasks and durations efficiently. In this tutorial, we will explore how to manage durations of tasks using Aspose.Tasks, guiding you through each step. Whether you are a seasoned developer or a beginner, this guide will help you grasp the essentials of working with task durations in your projects.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- Java Development Kit (JDK): Ensure that you have Java installed on your machine. You can download it [here](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: Download and include the Aspose.Tasks library in your project. You can find the library [here](https://releases.aspose.com/tasks/java/).
## Import Packages
In your Java project, import the necessary packages to work with Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Step 1: Set Up Your Project
```java
// Create a new project
Project project = new Project();
```
## Step 2: Add a New Task
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```
## Step 3: Get and Convert Task Duration
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Step 4: Update Task Duration to 1 Week
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Step 5: Decrease Task Duration
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
By following these steps, you've successfully managed the durations of tasks in your Aspose.Tasks for Java project.
## Conclusion
In this tutorial, we've covered the basics of managing task durations using Aspose.Tasks for Java. Now, you can confidently incorporate these techniques into your projects for effective task duration management.
## FAQs
### Is Aspose.Tasks compatible with all Java versions?
Aspose.Tasks is compatible with Java 6 and later versions.
### Can I use Aspose.Tasks for commercial projects?
Yes, you can use Aspose.Tasks for both personal and commercial projects. Visit [here](https://purchase.aspose.com/buy) for licensing details.
### Where can I find additional support and resources?
Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support and discussions.
### How can I obtain a temporary license for testing purposes?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing and evaluation.
### Is there a free trial available for Aspose.Tasks?
Yes, you can access the free trial [here](https://releases.aspose.com/) to explore Aspose.Tasks before making a purchase.
