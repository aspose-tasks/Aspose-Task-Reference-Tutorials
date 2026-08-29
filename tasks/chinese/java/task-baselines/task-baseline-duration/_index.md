---
date: 2026-08-29
description: 了解如何使用 Aspose.Tasks for Java 设置 baseline duration 并跟踪 project progress。本分步指南帮助您高效管理
  task baselines。
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: 如何在 Aspose.Tasks for Java 中设置 Baseline Duration
og_description: 了解如何使用 Aspose.Tasks for Java 设置 baseline duration 并跟踪 project progress。请参阅本详细指南，以高效管理
  task baselines。
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: 如何设置 baseline duration 以跟踪 project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: 如何设置 baseline duration 以跟踪 project progress
url: /zh/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何设置基准持续时间以跟踪项目进度

## 介绍
跟踪项目进度始于稳固的基准。在本教程中，您将了解如何使用 Aspose.Tasks for Java 库为 Microsoft Project 文件中的任务 **设置基准持续时间**，并理解为何及早建立基准有助于在项目整个生命周期中监控进度漂移、成本偏差和资源超额分配。

## 快速回答
- **“set baseline” 是什么意思？** 它记录任务的原始开始、完成和持续时间，以便您可以比较后续的更改。  
- **哪个 Aspose.Tasks 类用于创建项目？** `Project` 类 —— 您还将学习如何正确 **创建项目实例**。  
- **运行代码是否需要许可证？** 免费评估许可证可用于测试；生产环境需要商业许可证。  
- **我可以检索临时基准吗？** 可以，Aspose.Tasks 允许您查询临时基准及其固定成本。  
- **需要哪个 Java 版本？** 推荐使用 Java 8 或更高版本。  
- **这如何帮助我跟踪项目进度？** 设置基准后，您可以使用内置报告功能即时将实际日期与原计划进行比较。

## 什么是任务基准以及为何要设置它？
任务基准记录在特定时间点的计划进度（开始日期、完成日期和持续时间）。通过设置基准，您创建了一个参考点，便于在项目演进过程中轻松发现进度漂移、成本超支和资源超额分配。

## 为什么使用 Aspose.Tasks 进行基准管理？
Aspose.Tasks 提供 **完整的 .mpp 兼容性**——您可以在不安装 Microsoft Office 的情况下读取和写入原生 Microsoft Project 文件。该 API 为您提供对 **50 多种输入和输出格式** 的编程访问，支持 **临时基准 1‑10**，并且能够在不将整个文件加载到内存的情况下处理 **数百页的项目**，这对于高性能批处理至关重要。

## 前提条件
1. **Java 开发环境** – 已安装并配置 JDK 8+。  
2. **Aspose.Tasks for Java** – 从 [Aspose.Tasks for Java 下载页面](https://releases.aspose.com/tasks/java/) 下载库。  
3. **IDE 或构建工具** – Maven、Gradle 或您偏好的任何 IDE。

## 导入包
以下导入语句引入了处理项目、任务、基准和时间相位数据所需的核心 Aspose.Tasks 类。

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## 步骤 1：创建项目实例
`Project` 类在内存中表示一个 Microsoft Project 文件，是所有操作的入口点。

```java
Project project = new Project();
```

## 步骤 2：创建任务基准
`TaskBaseline` 用于存储特定任务的计划开始、完成和持续时间。

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 步骤 3：显示任务基准信息
`getBaselines()` 方法返回与任务关联的基准集合。

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 步骤 4：检查临时基准和固定成本
`BaselineType` 枚举了主要基准和临时基准（Baseline、Baseline1‑Baseline10）。

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## 步骤 5：打印时间相位数据
`TimephasedData` 表示特定时间间隔的调度信息片段。

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

按照这些步骤，您可以使用 Aspose.Tasks for Java 为任何任务 **设置基准持续时间** 并检索详细的基准信息，为您在整个项目生命周期中提供可靠的 **跟踪项目进度** 方法。

## 常见问题及解决方案
- **Baseline 未出现在 MS Project 中：** 确保在添加任务后调用 `project.setBaseline(BaselineType.Baseline)` **之后**。  
- **在 `getBaselines()` 上出现 NullPointerException：** 确认在设置基准之前已将任务添加到项目中。  
- **时间单位不匹配：** 使用 `TimeUnitType` 正确格式化持续时间，尤其是在使用自定义日历时。

## 常见问答

### 什么是 MS Project 中的任务基准？
MS Project 中的任务基准是对任务初始计划进度的快照，包括其开始日期、完成日期和持续时间。

### 为什么管理任务基准很重要？
管理任务基准有助于将计划进度与项目实际进展进行比较，从而促进更好的跟踪和决策。

### 设置后可以修改任务基准吗？
是的，您可以在 MS Project 中修改任务基准以反映项目计划的更改。但必须记录任何与原始基准的偏差。

### Aspose.Tasks 支持其他项目管理功能吗？
是的，Aspose.Tasks 提供广泛的项目管理功能，包括任务调度、资源分配和甘特图生成。

### 在哪里可以找到 Aspose.Tasks 的支持？
您可以在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 上获取支持，您可以在那里提问并与其他用户互动。

## 其他常见问题

**Q: 是否需要为每个任务单独调用 `setBaseline`？**  
A: 不需要。调用 `project.setBaseline(BaselineType.Baseline)` 会一次性为项目中的所有任务记录基准。

**Q: 如何为特定任务设置临时基准？**  
A: 在更新任务进度后使用 `project.setBaseline(BaselineType.Baseline1)`（或 Baseline2‑Baseline10）。

**Q: 能否将基准数据导出为 CSV？**  
A: 可以。遍历 `task.getBaselines()` 并使用标准 Java I/O 将所需字段写入 CSV 文件。

**Q: 能读取已经包含基准的现有 .mpp 文件吗？**  
A: 完全可以。使用 `new Project("myproject.mpp")` 加载文件，然后按上述方式访问每个任务的基准。

**Q: Aspose.Tasks 能处理多项目文件吗？**  
A: Aspose.Tasks 适用于单项目 .mpp 文件。对于多项目场景，需要通过编程方式合并项目。

---

**最后更新：** 2026-08-29  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相关教程

- [创建任务列表 Java – 使用 Aspose.Tasks 的 MS Project 基准](/tasks/java/task-baselines/create-task-baseline/)
- [创建 MPP 项目 Java – 使用 Aspose.Tasks 更改任务进度](/tasks/java/task-properties/change-progress/)
- [项目管理基准 – 使用 Aspose.Tasks 的任务调度](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}