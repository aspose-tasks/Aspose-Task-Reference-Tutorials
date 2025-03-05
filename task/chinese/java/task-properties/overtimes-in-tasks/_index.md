---
title: Aspose.Tasks 任务超时
linktitle: Aspose.Tasks 任务超时
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 探索项目任务中的高效加班管理。轻松简化跟踪和资源分配。
type: docs
weight: 23
url: /zh/java/task-properties/overtimes-in-tasks/
---
## 介绍
管理项目任务中的加班对于项目经理和团队领导来说至关重要，以确保准确的跟踪和资源分配。 Aspose.Tasks for Java 提供了一个强大的解决方案来处理项目管理中与加班相关的方面。在本教程中，我们将探讨如何利用 Aspose.Tasks 有效管理和分析项目任务中的加班情况。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- Java 开发环境：确保您的计算机上设置了 Java 开发环境。
-  Aspose.Tasks for Java：下载并安装 Aspose.Tasks 库。您可以找到该库及其文档[这里](https://reference.aspose.com/tasks/java/).
- 项目文件：准备一个项目文件（例如，TaskOvertimes.mpp）以便在教程中使用。
## 导入包
在您的 Java 项目中，导入必要的 Aspose.Tasks 包以利用其功能。添加以下导入语句：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```
## 第 1 步：创建一个新项目
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
//创建一个新项目
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```
## 第 2 步：迭代任务并打印加班详细信息
```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    //设置完成百分比
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```
按照以下步骤有效地利用 Aspose.Tasks for Java 来管理和分析项目任务中的加班情况。您可以根据您的具体项目需求随意定制代码。
## 结论
Aspose.Tasks for Java 简化了项目任务中的加班管理，为开发人员提供了一套强大的工具。通过遵循本指南，您可以将 Aspose.Tasks 无缝集成到您的 Java 项目中，确保高效的项目管理。
## 常见问题解答
### Aspose.Tasks适合大型项目管理吗？
是的，Aspose.Tasks 旨在处理各种规模的项目，从小型项目到大型复杂项目。
### 我可以将 Aspose.Tasks 与其他 Java 框架集成吗？
绝对地！ Aspose.Tasks 与其他 Java 框架无缝集成，增强了其在项目开发中的多功能性。
### 使用 Aspose.Tasks 是否有任何许可注意事项？
是的，您可以找到许可详细信息并获取临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 我可以在哪里寻求帮助或讨论与 Aspose.Tasks 相关的问题？
参观[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)与社区互动并寻求支持。
### Aspose.Tasks 有免费试用版吗？
是的，您可以访问免费试用版[这里](https://releases.aspose.com/).