---
date: 2025-12-23
description: 学习如何使用 Aspose.Tasks for Java 在 MS Project 中创建任务依赖关系并计算关键路径。项目管理的逐步指南。
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中创建任务依赖关系并计算关键路径
url: /zh/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中创建任务依赖并计算关键路径

## Introduction
在本教程中，**您将学习如何创建任务依赖**并使用 Aspose.Tasks for Java 计算 MS Project 文件中的关键路径。了解并可视化关键路径有助于您保持项目按计划进行，而正确链接任务可确保任何延迟立即可见。让我们从环境设置到显示最终关键路径，完整演示整个过程。

## Quick Answers
- **第一步是什么？** 设置您的 Java 项目并添加 Aspose.Tasks 库。  
- **必须启用哪种模式？** `CalculationMode.Automatic`（设置自动计算）。  
- **如何链接任务？** 使用 `project.getTaskLinks().add(...)` 创建任务依赖。  
- **如何查看关键路径？** 遍历 `project.getCriticalPath()` 并打印每个任务名称。  
- **是否需要许可证？** 是的，生产环境需要有效的 Aspose.Tasks 许可证。

## What is “create task dependencies”?
创建任务依赖意味着定义任务之间的关系（例如，结束到开始），以便进度表反映现实约束。在 Aspose.Tasks 中，这通过 `TaskLink` 对象实现。

## Why calculate the critical path in MS Project?
MS Project 的**关键路径**显示决定项目最短工期的最长依赖任务序列。通过计算它，您可以快速识别不能延误而不影响整体时间线的任务——这对于有效的 **project management Java** 应用至关重要。

## Prerequisites
在开始之前，请确保您已具备：

1. 已在系统上安装 Java Development Kit (JDK)。  
2. 已下载并将 Aspose.Tasks for Java 库添加到项目中。您可以从 [here](https://releases.aspose.com/tasks/java/) 下载。

## Import Packages
要开始，在 Java 类中导入必要的包：
```java
import com.aspose.tasks.*;
```

## How to set automatic calculation?
如何设置自动计算？

将计算模式设置为自动可确保对任务或链接的任何更改立即更新进度表，包括关键路径。
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
步骤 1：设置数据目录  
定义包含 MS Project 文件的文件夹路径。
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load MS Project File
步骤 2：加载 MS Project 文件  
使用 Aspose.Tasks 加载现有项目文件（例如 *New project 2013.mpp*）。
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Step 3: Add Tasks
步骤 3：添加任务  
创建三个简单的子任务，稍后我们将把它们链接在一起。
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Step 4: Create Task Links (create task dependencies)
步骤 4：创建任务链接（创建任务依赖）  
定义任务之间的依赖关系。这里我们使用最常见的结束到开始链接。
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Step 5: Display Critical Path (display critical path)
步骤 5：显示关键路径（display critical path）  
检索并打印关键路径。`getCriticalPath()` 方法返回形成关键链的任务列表。
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Step 6: Confirm Completion
步骤 6：确认完成  
过程完成后显示友好提示信息。
```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| 问题 | 解决方案 |
|-------|----------|
| **关键路径为空** | 确保在添加链接之前已设置 `CalculationMode.Automatic`。 |
| **任务未链接** | 确认已为每个依赖添加了 `TaskLink` 对象。 |
| **许可证异常** | 在创建 `Project` 实例之前加载有效的 Aspose.Tasks 许可证。 |

## FAQ's
### Q: Can I use Aspose.Tasks for Java with any version of MS Project files?
**问：** 我可以在任何版本的 MS Project 文件中使用 Aspose.Tasks for Java 吗？  
**答：** 是的，Aspose.Tasks for Java 支持多种版本的 MS Project 文件，包括从 MS Project 2003 到 MS Project 2019 的 .mpp 文件。

### Q: Is there a free trial available for Aspose.Tasks for Java?
**问：** 是否提供 Aspose.Tasks for Java 的免费试用？  
**答：** 是的，您可以从 [here](https://releases.aspose.com/) 下载免费试用版。

### Q: Where can I find support for Aspose.Tasks for Java?
**问：** 在哪里可以找到 Aspose.Tasks for Java 的支持？  
**答：** 您可以在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 上获取支持。

### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
**问：** 我可以购买 Aspose.Tasks for Java 的临时许可证吗？  
**答：** 是的，您可以从 [here](https://purchase.aspose.com/temporary-license/) 购买临时许可证。

### Q: How can I buy Aspose.Tasks for Java?
**问：** 我如何购买 Aspose.Tasks for Java？  
**答：** 您可以通过网站 [here](https://purchase.aspose.com/buy) 购买 Aspose.Tasks for Java。

## Conclusion
通过遵循这些步骤，您已经**创建了任务依赖**，设置了**自动计算**，并成功**显示了 MS Project 文件的关键路径**。此工作流让您全面控制进度逻辑，并帮助您使用基于 Java 的 **project management** 代码保持项目进度。

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}