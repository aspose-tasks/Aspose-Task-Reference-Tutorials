---
date: 2026-02-23
description: 学习如何使用 Aspose.Tasks for Java 设置项目开始日期、设置任务持续时间，并将项目保存为 MPP。高效管理父任务和子任务。
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中设置项目开始日期并管理父子任务
url: /zh/java/task-properties/parent-child-tasks/
weight: 24
---

.

Let's construct final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 设置项目开始日期并管理 Aspose.Tasks 中的父子任务

## 介绍
有效的任务组织是成功项目管理的基石，**setting the project start date** 正确设置是构建结构化进度表的第一步。在本教程中，您将了解如何 **set project start date**、配置任务持续时间，以及使用 Aspose.Tasks for Java 管理父子关系。完成后，您将能够 **save project as MPP**、更新任务完成百分比，并自定义任务属性以适应任何实际场景。

## 快速答案
- **如何设置项目开始日期？** 使用 `proj.set(Prj.START_DATE, startDate);` 在初始化 `Project` 对象后。  
- **我可以在父任务下添加子任务吗？** 可以 – 调用 `parentTask.getChildren().add("Child Task")`。  
- **Aspose.Tasks 将文件保存为何种格式？** 使用 `SaveFileFormat.Mpp` 来 **save project as MPP**。  
- **如何更新任务完成度？** 在任务对象上设置 `Tsk.PERCENT_COMPLETE`。  
- **在哪里可以获取临时许可证？** 请访问常见问题中链接的临时许可证页面。

## 前置条件
在深入教程之前，请确保具备以下前置条件：
- 对 Java 编程的基本了解。  
- 已安装 Aspose.Tasks for Java 库。您可以在[此处](https://releases.aspose.com/tasks/java/)下载。  
- 在系统上已设置 Java 集成开发环境（IDE）。

## 导入包
首先，将必要的包导入到您的 Java 项目中。这些包可实现与 Aspose.Tasks for Java 功能的无缝集成。
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## 步骤 1：设置项目开始日期
首先设置项目的开始日期以及其他相关参数。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## 步骤 2：添加父任务（任务 1）
创建一个名为 “Task 1” 的父任务并配置其属性，包括 **set task duration**。
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## 步骤 3：添加父任务（任务 2）及子任务
现在，添加另一个名为 “Task 2” 的父任务，并包含子任务（Task 3 和 Task 4）。
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## 步骤 4：配置子任务
为 Task 3 和 Task 4 指定开始日期、持续时间和约束条件。
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## 步骤 5：更新任务完成百分比
调整 Task 3 和 Task 4 的完成百分比 – 这就是 **update task completion** 的方式。
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## 步骤 6：保存项目
最后，使用 **save project as MPP** 保存带有已应用更改的项目。
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

本分步指南演示了如何使用 Aspose.Tasks for Java 有效管理父子任务。请尝试不同的配置以满足项目需求。

## 为什么要自定义任务属性？
自定义任务属性（如开始日期、持续时间、约束条件和完成百分比）可让您对进度行为进行细粒度控制。无论是需要将任务与资源可用性对齐，还是强制业务规则，Aspose.Tasks 都能让您 **customize task properties** 编程实现。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **开始日期未生效** | 确保在创建 `Project` 对象后、添加任务之前 **调用** `proj.set(Prj.START_DATE, …)`。 |
| **子任务继承了错误的约束** | 如步骤 4 所示，显式设置每个子任务的 `ConstraintType` 和 `ConstraintDate`。 |
| **保存的文件无法在 MS Project 中打开** | 确认使用的是最新的 Aspose.Tasks 版本，并使用 `SaveFileFormat.Mpp` 保存。 |
| **百分比在 UI 中未显示** | 在设置 `Tsk.PERCENT_COMPLETE` 后，如果需要重新计算日期，请调用 `proj.calculateTaskSchedule()`。 |

## 常见问答
### Aspose.Tasks for Java 是否兼容不同的项目文件格式？
是的，Aspose.Tasks for Java 支持多种项目文件格式，包括 MPP 和 XML。

### 我可以自定义任务属性，超出本教程的范围吗？
当然！Aspose.Tasks for Java 提供了广泛的任务属性自定义选项。

### 是否有 Aspose.Tasks 社区论坛可供我寻求支持？
是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)获取社区支持。

### 如何获取 Aspose.Tasks for Java 的临时许可证？
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### 在哪里可以找到 Aspose.Tasks for Java 的完整文档？
文档可在[此处](https://reference.aspose.com/tasks/java/)获取。

**附加问答**

**Q:** 如何以编程方式获取临时许可证？  
**A:** Load the temporary license file using `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q:** 我可以更改默认的任务持续时间单位吗？  
**A:** Yes – modify the `TimeUnitType` argument in `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q:** 使用 `SaveFileFormat.Mpp` 需要哪个版本的 Aspose.Tasks？  
**A:** All recent versions (2022‑2026) support saving as MPP; check the release notes for any breaking changes.

---

**最后更新：** 2026-02-23  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}