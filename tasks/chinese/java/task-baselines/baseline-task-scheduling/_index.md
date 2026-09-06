---
date: 2026-08-29
description: 了解如何使用 Aspose.Tasks for Java 读取基准数据并安排任务，从而高效比较计划进度与实际进度。
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Aspose.Tasks 中的基准任务调度
og_description: 了解如何使用 Aspose.Tasks for Java 读取基准数据并安排任务，实现对计划进度与实际进度的精确比较。
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: 如何使用 Aspose.Tasks 读取基准并安排任务
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: 如何使用 Aspose.Tasks 读取基准并安排任务
url: /zh/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何读取基准并使用 Aspose.Tasks 安排任务

在本指南中，您将了解 **如何读取基准** 信息并使用 Aspose.Tasks for Java 以编程方式安排任务。教程结束时，您将能够捕获原始项目计划，将其与实际进度进行比较，并生成差异报告——无需安装 Microsoft Project。

## 项目管理基准简介

管理 **项目管理基准** 是有效项目管理的基石。它让您捕获原始计划，随后比较 **计划进度与实际进度**，以便及早发现偏差。在本教程中，我们将演示如何使用 Aspose.Tasks for Java 安排任务基准，为您提供自信 **管理项目基准** 的工具，确保项目保持正轨。

## 快速答案

- **项目管理基准代表什么？**  
  它记录了项目启动时批准的进度、成本和范围，提供用于差异分析的参考。  
- **哪个库在 Java 中处理基准调度？**  
  Aspose.Tasks for Java 提供纯 Java API，支持 45+ 输入和输出格式，且可处理多达 100 000 个任务的项目。  
- **运行代码是否需要许可证？**  
  免费试用可用于测试；生产使用需要商业许可证。  
- **主要前提条件是什么？**  
  Java Development Kit (JDK) 11+ 和 Aspose.Tasks for Java 库。  
- **设置基准后我可以查看基准日期吗？**  
  可以——使用 `TaskBaseline` 对象读取开始、结束和持续时间值。

## 什么是项目管理基准？

项目管理基准记录了执行开始时批准的进度、预算和范围。它作为衡量绩效和识别整个项目生命周期中偏差的参考点。它包括计划的开始和结束日期、总成本以及范围细节，提供用于未来比较的完整快照。

## 为什么使用 Aspose.Tasks 进行基准调度？

Aspose.Tasks 提供纯 Java API，无需安装 Microsoft Project 即可使用。它支持 **45+ 输入和输出格式**，能够在内存高效模式下处理 **多达 100 000 个任务** 的项目，并提供内置方法读取和写入基准数据——使自动化报告和集成变得简便。

## 前提条件

- **Java Development Kit (JDK)** – 安装 JDK 11 或更高版本。您可以从 [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下载。  
- **Aspose.Tasks for Java 库** – 从 [download page](https://releases.aspose.com/tasks/java/) 下载最新版本，并将 JAR 添加到项目的类路径中。

## 导入包

`Project`、`Task` 和 `TaskBaseline` 类位于 `com.aspose.tasks` 命名空间。请在源文件顶部导入它们：

`Project` 类是 Aspose.Tasks 的顶层对象，表示内存中的单个项目文件。它提供对任务、资源和基准集合的访问。

## 如何读取基准？

加载项目后，查询每个任务的 `TaskBaseline` 集合。`TaskBaseline` 对象返回在调用 `setBaseline` 时捕获的基准开始、结束和持续时间。此直接方法让您无需解析 XML 或二进制文件即可读取基准值。

## 步骤 1：创建新项目实例

`Project` 类表示内存中的整个项目文件。
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## 步骤 2：定义任务并设置基准

`Task` 表示单个工作项，`setBaseline` 将其当前进度捕获为基准。
```java
Project project = new Project();
```

## 步骤 3：访问基准信息

`TaskBaseline` 保存基准的开始、结束和持续时间值。
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 步骤 4：显示基准持续时间

`Duration` 表示任务或基准的时间长度。
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## 步骤 5：显示基准开始日期

`Start` 是基准的计划开始日期。
```java
System.out.println(baseline.getDuration().toString());
```

## 步骤 6：显示基准结束日期

`Finish` 是基准的计划完成日期。
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## 常见问题及解决方案

- **基准未设置：** 确保在添加任务 **之后** 调用 `project.setBaseline(BaselineType.Baseline)`；否则基准集合将为空。  
- **空值：** 如果 `task.getBaselines()` 返回空列表，请确认在设置基准之前已将任务添加到项目层次结构中。  
- **日期格式：** `getStart()` 和 `getFinish()` 方法返回 `java.util.Date` 对象。如需自定义显示格式，请使用 `SimpleDateFormat`。

## 常见问题

**Q: 如何在 Aspose.Tasks 中创建新项目实例？**  
A: 实例化 `Project` 类 (`Project project = new Project();`)。这将创建一个准备好用于任务和基准的全新项目文件。

**Q: `BaselineType.Baseline` 与其他基准类型有什么区别？**  
A: `BaselineType.Baseline` 指的是主要基准（基准 1）。Aspose.Tasks 还支持 Baseline 2‑10 作为额外快照。

**Q: 我可以将基准数据导出为 Excel 或 CSV 吗？**  
A: 可以，您可以遍历 `TaskBaseline` 对象，并使用标准 Java I/O 将值写入 CSV 文件。

**Q: 设置基准会影响现有任务日期吗？**  
A: 设置基准会捕获当前日期，但不会修改任务的活动进度。基准设置后仍可调整开始/结束日期。

**Q: 能否以编程方式比较多个基准？**  
A: 完全可以。通过 `task.getBaselines().get(index)` 获取每个基准，并比较其 `Start`、`Finish` 和 `Duration` 属性。

---

**最后更新:** 2026-08-29  
**已测试:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 相关教程

- [使用 Aspose.Tasks 创建任务列表 Java – MS Project 基准](/tasks/java/task-baselines/create-task-baseline/)
- [如何在 Aspose.Tasks for Java 中设置基准持续时间](/tasks/java/task-baselines/task-baseline-duration/)
- [创建 MPP 项目 Java – 使用 Aspose.Tasks 更改任务进度](/tasks/java/task-properties/change-progress/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}