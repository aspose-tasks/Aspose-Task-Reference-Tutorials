---
date: 2026-09-25
description: 了解如何在 Java 中使用 Aspose.Tasks 创建项目进度表。本指南展示了如何添加汇总任务、管理项目层次结构以及高效设置文档目录。
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: 在 Aspose.Tasks 中创建任务
og_description: 了解如何在 Java 中使用 Aspose.Tasks 创建项目进度表。按照分步说明添加汇总任务、管理层次结构并设置文档目录。
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: 如何使用 Aspose.Tasks for Java 创建项目进度表
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: 如何使用 Aspose.Tasks for Java 创建项目进度表
url: /zh/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 创建项目计划

## 介绍
在本教程中，您将学习如何在 Java 应用程序中使用 Aspose.Tasks **创建项目计划**。无论您是构建一个简单的待办事项列表，还是一个复杂的企业级规划器，下面的步骤将指导您添加汇总任务、管理项目层次结构以及设置文档目录——所有示例均为清晰可运行的代码片段。完成后，您将拥有一个完整结构的计划，可进一步进行操作或导出。

## 快速答案
- **Aspose.Tasks 管理什么？** 它处理任务层次结构、资源、日历以及项目文件格式（MS‑Project、Primavera 等）。  
- **开发是否需要许可证？** 免费的临时许可证可用于评估；生产环境需要完整许可证。  
- **支持哪个 Java 版本？** 完全支持 Java 8 及更高版本。  
- **我可以向任务添加自定义字段吗？** 可以，您可以通过 API 使用用户定义的字段扩展任务。  
- **是否内置对甘特图的支持？** Aspose.Tasks 可以导出包含甘特可视化的 PDF/HTML。

## Aspose.Tasks 中的项目计划是什么？
项目计划是定义工作执行方式的完整任务、依赖关系和时间线集合。Aspose.Tasks 将这些信息存储在 `Project` 对象中，您可以读取、修改并以多种格式保存。它包括开始和结束日期、约束条件以及资源分配，从而实现全面的计划和报告。

## 为什么在 Java 项目管理中使用 Aspose.Tasks？
Aspose.Tasks 支持 **30 多种输入和输出格式**，并且能够在不将整个文件加载到内存的情况下处理 **多达 10,000 个任务** 的项目，为大规模 Java 项目管理场景提供高性能。

## 前置条件
在开始教程之前，请确保已具备以下前置条件：
- **Java Development Kit (JDK)** – 已在机器上安装 JDK 8 或更高版本。  
- **Aspose.Tasks for Java 库** – 从 [Aspose.Tasks for Java 下载](https://releases.aspose.com/tasks/java/) 下载并安装该库。  
- **集成开发环境 (IDE)** – 使用 Eclipse、IntelliJ IDEA 或您喜欢的任何 Java 开发环境。

## 导入包
`Project`、`Task` 以及相关类位于 `com.aspose.tasks` 命名空间。请在 Java 文件的顶部导入它们：

`Project` 类表示完整的项目计划，并提供操作任务和资源的方法。

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

`Project` 类是对项目文件进行所有操作的入口点。

## 如何使用 Aspose.Tasks 创建项目计划？

加载一个新的 `Project` 实例，设置文档目录，然后开始添加任务。此段落直接说明核心流程：您创建一个 `Project`，配置其 `RootFolder`（文档目录），随后添加一个汇总任务以及子任务。所有更改都保存在内存中，直到调用 `save` 将计划持久化到文件。

### 步骤 1：设置文档目录
定义生成的项目文件将写入的位置。提前设置目录可确保所有后续的保存操作使用一致的路径。

`RootFolder` 属性指定读取或写入项目文件的基础文件夹。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### 步骤 2：创建新项目
实例化一个新的 `Project` 对象来保存您的计划。您也可以选择传入已有的文件路径，以加载现有计划进行修改。

`Project` 构造函数创建一个空的计划，准备添加任务。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步骤 3：添加汇总任务
汇总任务将相关子任务分组，并在甘特图中显示为可折叠节点。使用 `Task` 类并将 `IsSummary` 设置为 `true`。

`addTask` 方法在指定的父任务下创建新任务并返回其 ID。

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### 步骤 4：添加子任务
子任务默认继承其父汇总任务的开始/结束日期，除非您进行覆盖。添加子任务只需再次调用 `addTask` 并指定父任务 ID。

使用父任务 ID 调用 `addTask` 会在该汇总任务下添加子任务。

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

继续根据项目需要添加任意数量的任务和子任务。每一步都有助于构建可导出为 MS‑Project、PDF 或其他支持格式的结构化项目层次结构。

## 常见问题及解决方案
- **问题：** “未找到文档目录”。  
  **解决方案：** 确认分配给 `RootFolder` 的路径在文件系统中存在，并且您的 Java 进程具有写入权限。  
- **问题：** 子任务未出现在汇总任务下。  
  **解决方案：** 确保在调用 `addTask` 时传入正确的父任务 ID。API 要求将父任务 ID 作为第二个参数。  
- **问题：** 大型项目导致 OutOfMemoryError。  
  **解决方案：** Aspose.Tasks 以流式模式处理任务；请增大 JVM 堆大小（`-Xmx2g`）或将计划拆分为多个文件。

## 常见问答
**Q: Aspose.Tasks 适用于小规模项目吗？**  
**A:** 当然。该库可以从单任务列表扩展到拥有数千任务的企业级计划。

**Q: 在哪里可以找到 Aspose.Tasks for Java 的详细文档？**  
**A:** 请参阅文档 [Aspose.Tasks Java API 参考](https://reference.aspose.com/tasks/java/)。

**Q: 如何获取 Aspose.Tasks 的临时许可证？**  
**A:** 访问 [临时许可证请求页面](https://purchase.aspose.com/temporary-license/)，获取用于开发和测试的限时许可证。

**Q: 我可以使用 Aspose.Tasks 自定义任务属性吗？**  
**A:** 可以，您可以通过自定义字段扩展任务，分配资源，并以编程方式修改日历。

**Q: 是否有 Aspose.Tasks 用户的支持社区？**  
**A:** 当然！加入 Aspose.Tasks 社区的 [支持论坛](https://forum.aspose.com/c/tasks/15)。

---

**最后更新：** 2026-09-25  
**测试环境：** Aspose.Tasks 24.12 for Java  
**作者：** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## 相关教程

- [使用 Aspose.Tasks for Java 设置 MS Project 项目开始日期](/tasks/java/project-properties/write-project-info/)
- [在 Aspose.Tasks 中创建项目管理任务依赖关系](/tasks/java/task-links/create-task-link/)
- [如何向项目添加资源并在 Aspose.Tasks 中创建资源分配](/tasks/java/resource-assignments/create-resource-assignments/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}