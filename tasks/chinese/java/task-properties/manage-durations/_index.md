---
title: 在 Aspose.Tasks 中管理任务的持续时间
linktitle: 在 Aspose.Tasks 中管理任务的持续时间
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 并学习轻松管理任务持续时间。按照我们的分步指南进行有效的项目规划和执行。
weight: 20
url: /zh/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理任务的持续时间

## 介绍
Aspose.Tasks for Java 提供了一个强大的解决方案来有效管理项目任务和工期。在本教程中，我们将探索如何使用 Aspose.Tasks 管理任务的持续时间，指导您完成每个步骤。无论您是经验丰富的开发人员还是初学者，本指南都将帮助您掌握在项目中处理任务持续时间的要点。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
-  Java 开发工具包 (JDK)：确保您的计算机上安装了 Java。你可以下载它[这里](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks 库：下载 Aspose.Tasks 库并将其包含在您的项目中。你可以找到图书馆[这里](https://releases.aspose.com/tasks/java/).
## 导入包
在您的 Java 项目中，导入使用 Aspose.Tasks 所需的包：
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 第 1 步：设置您的项目
```java
//创建一个新项目
Project project = new Project();
```
## 第 2 步：添加新任务
```java
//向项目添加新任务
Task task = project.getRootTask().getChildren().add("Task");
```
## 第 3 步：获取并转换任务持续时间
```java
//获取任务持续时间（以天为单位）（默认时间单位）
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
//将持续时间转换为小时时间单位
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## 步骤 4：将任务持续时间更新为 1 周
```java
//将任务持续时间增加至 1 周
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## 第 5 步：减少任务持续时间
```java
//减少任务持续时间
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
通过执行这些步骤，您已成功管理 Aspose.Tasks for Java 项目中任务的持续时间。
## 结论
在本教程中，我们介绍了使用 Aspose.Tasks for Java 管理任务持续时间的基础知识。现在，您可以自信地将这些技术融入您的项目中，以实现有效的任务工期管理。
## 常见问题解答
### Aspose.Tasks 与所有 Java 版本兼容吗？
Aspose.Tasks 与 Java 6 及更高版本兼容。
### 我可以将 Aspose.Tasks 用于商业项目吗？
是的，您可以将 Aspose.Tasks 用于个人和商业项目。访问[这里](https://purchase.aspose.com/buy)了解许可详细信息。
### 我在哪里可以找到额外的支持和资源？
参观[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持和讨论。
### 我如何获得用于测试目的的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/)用于测试和评估。
### Aspose.Tasks 是否有免费试用版？
是的，您可以免费试用[这里](https://releases.aspose.com/)在购买之前探索 Aspose.Tasks。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
