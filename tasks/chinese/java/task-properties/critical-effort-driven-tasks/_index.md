---
date: 2026-09-30
description: 使用 Aspose.Tasks 管理 Java 项目中的关键任务。学习如何处理关键任务和 effort‑driven 任务，下载库并提升您的项目管理工作流。
keywords:
- manage critical tasks java
- effort‑driven tasks Aspose.Tasks
- Java project management
lastmod: 2026-09-30
linktitle: 在 Aspose.Tasks 中管理关键任务和 effort‑driven 任务
og_description: 使用 Aspose.Tasks 处理 Java 开发者面临的关键任务。本指南逐步演示在 Java 项目中处理关键任务和 effort‑driven
  任务的方式（150‑160 字）
og_image_alt: Screenshot of Aspose.Tasks Java API managing critical and effort‑driven
  tasks
og_title: 如何在 Java 中使用 Aspose.Tasks 管理关键任务
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Manage critical tasks Java projects with Aspose.Tasks. Learn to handle
    critical and effort‑driven tasks, download the library and boost your project
    management workflow.
  headline: How to manage critical tasks in Java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is platform‑independent and runs on Windows,
      Linux, and macOS.
    question: Can I use Aspose.Tasks for Java in both Windows and Linux environments?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java on the [Aspose.Tasks
      free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find support for Aspose.Tasks for Java?
  - answer: You can acquire a temporary license on the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: You can purchase Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- critical tasks
- effort‑driven tasks
- Aspose.Tasks
- Java
- project management
title: 如何在 Java 中使用 Aspose.Tasks 管理关键任务
url: /zh/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.Tasks 管理关键任务和工作量驱动任务

## 快速答案
- **主要好处是什么？** 自动标记关键任务并在一次 API 调用中调整工作量驱动的调度。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **支持哪些 Java 版本？** Java 8 至 17，支持 OpenJDK 和 Oracle 发行版。  
- **我可以处理大型项目吗？** 可以——Aspose.Tasks 能高效处理多达 10 000 个任务的项目。  
- **它是跨平台的吗？** 该库可在 Windows、Linux 和 macOS 上运行，无需本机依赖。

## 如何在 Aspose.Tasks for Java 中管理关键任务和工作量驱动任务？
使用 `Project` 类加载项目文件，利用 `ChildTasksCollector` 收集所有任务，然后检查每个任务的 `Critical` 和 `EffortDriven` 属性。通过遍历收集的列表，您可以生成状态报告或自动修改调度规则，只需几行在几秒内执行的 Java 代码。

Aspose.Tasks for Java 支持 **30 多种输入和输出项目格式**（包括 Microsoft Project 2019、2022 和 Primavera P6），并且能够在典型服务器上将内存使用保持在 200 MB 以下的情况下处理 **多达 10 000 个任务** 的文件。这些量化的能力使其适用于企业级规划。

## 先决条件
在开始之前，请确保您拥有：

- **Aspose.Tasks for Java** 库 – 从 [Aspose.Tasks for Java 文档](https://reference.aspose.com/tasks/java/) 下载。  
- **Java Development Kit (JDK)** – 在您的机器上安装 8 版或更高版本。  
- **IDE**（您选择的集成开发环境），如 IntelliJ IDEA、Eclipse、VS Code 等。  
- 用于演示的 XML（或 .mpp）格式示例项目文件。

## 导入包
将所需的命名空间添加到您的 Java 源文件中：

```java
import com.aspose.tasks.*;
import java.util.*;
```

这些导入让您能够访问核心任务管理类，例如 `Project`、`Task` 和实用助手。

## 什么是关键任务？
**关键任务** 是指任何延迟会直接延长项目完成日期的活动，也就是说它位于进度表的关键路径上。在 Aspose.Tasks 中，您可以通过调用 `Task.isCritical()` 方法来判断任务是否关键，当任务影响整体项目完成时间时该方法返回 `true`。

## 什么是工作量驱动任务？
**工作量驱动任务** 在其持续时间更改时会自动重新分配剩余工作量，确保整个进度表中的总工作量保持不变。此行为对以固定速率工作的资源很有用。在 Aspose.Tasks 中，`Task.isEffortDriven()` 属性对表现出此特性的任务返回 `true`。

## 步骤 1：使用 ChildTasksCollector 收集任务
`ChildTasksCollector` 类收集给定父任务下的所有任务。

`ChildTasksCollector` 是一个帮助器，遍历任务层次结构并返回 `Task` 对象的扁平列表。

```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector);
List<Task> allTasks = collector.getTasks();
```

## 步骤 2：遍历收集的任务
遍历列表并打印每个任务的关键性和工作量驱动状态。

```java
for (Task t : allTasks) {
    boolean isCritical = t.get(Tsk.Critical);
    boolean isEffortDriven = t.get(Tsk.EffortDriven);
    System.out.println("Task ID " + t.get(Tsk.Id) + 
        ": critical=" + isCritical + ", effortDriven=" + isEffortDriven);
}
```

这种简单的两步模式为您提供项目调度健康的完整视图。

## 常见问题和故障排除
- **任务属性上的 NullPointerException** – 在访问任务之前确保项目文件已完整加载（`project = new Project("file.mpp")`）。  
- **关键标志不正确** – 确认项目的计算模式设置为 `CalculationMode.Automatic`，以便 Aspose.Tasks 在修改后重新计算关键路径。  
- **大型文件导致变慢** – 使用 `Project.set(Prj.ReadOnly, true)` 以只读模式打开文件，可降低只读分析的内存开销。

## 常见问题

**问：我可以在 Windows 和 Linux 环境中使用 Aspose.Tasks for Java 吗？**  
答：可以，Aspose.Tasks for Java 是平台无关的，可在 Windows、Linux 和 macOS 上运行。

**问：Aspose.Tasks for Java 是否提供免费试用？**  
答：是的，您可以在 [Aspose.Tasks 免费试用下载页面](https://releases.aspose.com/) 获取 Aspose.Tasks for Java 的免费试用。

**问：我在哪里可以找到 Aspose.Tasks for Java 的支持？**  
答：请访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取社区支持和讨论。

**问：我如何获取 Aspose.Tasks for Java 的临时许可证？**  
答：您可以在 [临时许可证请求页面](https://purchase.aspose.com/temporary-license/) 申请临时许可证。

**问：我在哪里可以购买 Aspose.Tasks for Java？**  
答：您可以在 [购买页面](https://purchase.aspose.com/buy) 购买 Aspose.Tasks for Java。

---

**最后更新：** 2026-09-30  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

## 相关教程

- [关键路径 MS Project – Aspose.Tasks Java 教程](/tasks/java/project-management/critical-path/)
- [在 Aspose.Tasks 中创建项目管理任务依赖关系](/tasks/java/task-links/create-task-link/)
- [项目管理 Java：使用 Aspose.Tasks 的任务完成百分比](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}