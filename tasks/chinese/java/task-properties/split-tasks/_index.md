---
date: 2026-02-26
description: 学习如何使用 Aspose.Tasks for Java 拆分任务——关于如何拆分任务、设置项目日历以及创建资源分配的权威指南。
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中拆分任务
url: /zh/java/task-properties/split-tasks/
weight: 29
---

.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中拆分任务

## Introduction
如果您正在寻找在基于 Java 的项目中 **如何拆分任务**，您来对地方了。Aspose.Tasks for Java 为您提供了一种简洁的编程方式，将长时间运行的任务拆分为更小、可管理的部分，这有助于资源均衡、准确报告以及更紧凑的项目时间表。在本教程中，我们将逐步演示整个过程——从设置项目日历、创建资源分配，到最终将任务拆分为多个段落。

## Quick Answers
- **任务拆分是什么？** 将单个任务划分为多个更小的时间间隔，同时保持其总持续时间。  
- **为什么在 Java 中拆分任务？** 它实现了精确的资源分配和更好的进度跟踪。  
- **哪个库提供帮助？** Aspose.Tasks for Java 提供了内置的拆分和时间分段方法。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要许可证。  
- **支持哪个 Java 版本？** 该库支持 Java 8 及更高版本。

## Prerequisites
在深入教程之前，请确保您已具备以下前提条件：
- 已在机器上安装 Java Development Kit (JDK)。  
- 已下载 Aspose.Tasks for Java 库并将其添加到项目中。您可以从 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 下载。

## Import Packages
开始在 Java 项目中导入必要的包：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Step 1: Create a New Project
使用 Aspose.Tasks 库创建一个新项目：

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Step 2: Set Project Calendar
设置 **项目日历** 定义工作日、假期以及整体时间线。这一步对于准确的时间分段计算至关重要。

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Step 3: Add a Root Task
每个项目都需要一个根容器。添加根任务为您提供一个附加所有后续任务的地方。

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Step 4: Add a New Task to Split
创建您打算拆分的任务。这里我们以三天的持续时间为例。

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Step 5: Create a Resource Assignment
**资源分配** 将资源（或占位符）链接到任务。这在生成时间分段数据之前是必需的。

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Step 6: Generate Timephased Data
时间分段数据表示工作在任务持续期间的分布。生成它为任务拆分做好准备。

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Step 7: Split the Task
现在我们 **将任务拆分为多个部分**。在本例中，我们将三天任务拆分为三个一天的段落。

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Why Split Tasks?
拆分任务可以让您对以下方面进行更细粒度的控制：
- **资源均衡：** 为每个段落分配不同的资源。  
- **进度跟踪：** 基于每个段落更新状态。  
- **报告：** 生成更详细的甘特图和报告。

## Common Issues and Solutions
- **缺少日历数据：** 确保在拆分前调用 `timephasedDataFromTaskDuration`。  
- **零时长段落：** 验证每个拆分间隔都有非零时长；否则库会忽略它。  
- **许可证异常：** 未使用有效许可证运行可能会在导出文件中添加水印。

## Frequently Asked Questions
### Can I split tasks with different durations?
是的，您可以调整每个部分的持续时间以符合项目需求。

### Is Aspose.Tasks for Java compatible with all Java versions?
Aspose.Tasks for Java 旨在与 Java 8 及更高版本无缝兼容，确保广泛的兼容性。

### Can I use Aspose.Tasks for Java for free?
Aspose.Tasks for Java 提供免费试用，让您在购买前探索其功能。

### How can I get support for Aspose.Tasks for Java?
访问 [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) 获取帮助并与社区交流。

### Do I need a temporary license for Aspose.Tasks for Java?
您可以通过 [this link](https://purchase.aspose.com/temporary-license/) 获取临时许可证，用于测试和评估。

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}