---
title: 在 Aspose.Tasks 中管理父任务和子任务
linktitle: 在 Aspose.Tasks 中管理父任务和子任务
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 提高项目管理效率。学习逐步管理父级和子级任务。现在就开始！
type: docs
weight: 24
url: /zh/java/task-properties/parent-child-tasks/
---
## 介绍
在项目管理领域，有效的任务组织至关重要。 Aspose.Tasks for Java 提供了一个强大的解决方案来有效管理父任务和子任务。在本教程中，我们将指导您完成使用 Aspose.Tasks for Java 来简化项目任务的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- 对 Java 编程有基本的了解。
- 安装了 Java 库的 Aspose.Tasks。你可以下载它[这里](https://releases.aspose.com/tasks/java/).
- 在您的系统上设置 Java 集成开发环境 (IDE)。
## 导入包
首先，将必要的包导入到您的 Java 项目中。这些包有助于与 Aspose.Tasks for Java 功能无缝集成。
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
## 第 1 步：设置项目开始日期
首先设置项目的开始日期和其他相关参数。
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
//可以在此处添加用于包导入的附加代码
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## 步骤 2：添加父任务（任务 1）
创建名为“任务 1”的父任务并配置其属性。
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## 步骤 3：添加父任务（任务 2）和子任务
现在，添加另一个名为“任务 2”的父任务并包含子任务（任务 3 和任务 4）。
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
//将子任务添加到任务 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
//可以在此处添加任务 3 和任务 4 的其他配置
```
## 步骤 4：配置子任务
指定任务 3 和任务 4 的开始日期、持续时间和限制。
```java
//配置任务 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
//配置任务 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## 步骤 5：更新任务完成百分比
调整任务 3 和任务 4 的完成百分比。
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## 第 6 步：保存项目
最后，保存应用了更改的项目。
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
本分步指南演示了如何使用 Aspose.Tasks for Java 有效管理父任务和子任务。尝试不同的配置以满足您的项目要求。
## 结论
总之，Aspose.Tasks for Java 使开发人员能够高效地处理项目任务，确保无缝组织和跟踪。实施概述的步骤来增强您的项目管理能力。
## 常见问题解答
### Aspose.Tasks for Java 是否与不同的项目文件格式兼容？
是的，Aspose.Tasks for Java 支持各种项目文件格式，包括 MPP 和 XML。
### 我可以自定义超出本教程涵盖范围的任务属性吗？
绝对地！ Aspose.Tasks for Java 为任务属性提供了广泛的自定义选项。
### 是否有 Aspose.Tasks 社区论坛可供我寻求支持？
是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持。
### 如何获得 Aspose.Tasks for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以找到 Aspose.Tasks for Java 的综合文档？
文档可用[这里](https://reference.aspose.com/tasks/java/).