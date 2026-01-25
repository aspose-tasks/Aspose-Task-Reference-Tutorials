---
date: 2026-01-25
description: 学习如何在 Aspose.Tasks for Java 中创建任务。管理项目、创建汇总任务、设置文档目录等，使用本分步指南。
linktitle: Create Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中创建任务
url: /zh/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中创建任务

## 介绍
欢迎！在本教程中，您将了解如何在 Aspose.Tasks for Java 中**创建任务**，从设置文档目录到添加汇总任务和子任务。无论您是在构建一个简单的待办清单还是完整的项目计划，下面的步骤都为您提供了清晰、实用的路径，帮助您快速建立并运行项目层次结构。

## 快速答案
- **主要目的是什么？** 使用 Aspose.Tasks for Java 以编程方式在 Microsoft Project 文件中创建和组织任务。  
- **需要哪个库版本？** 任意近期的 Aspose.Tasks for Java 发行版（API 在各版本之间保持稳定）。  
- **我需要许可证吗？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **我可以创建汇总任务吗？** 可以——使用根任务的子集合的 `add` 方法。  
- **文件保存在哪里？** 保存于您在 *set document directory* 步骤中设置的目录。

## 什么是 Aspose.Tasks 中的“创建任务”？
创建任务是指以编程方式并将结构持久化为 MPP 文件。这使得项目自动生成、批量更新以及与其他系统的集成成为可能。

## 为什么使用 Aspose.Tasks for Java？
- **完全控制** 项目数据，无需安装 Microsoft Project。  
- **跨平台** 兼容性——可在 Windows、Linux 和 macOS 上运行。  
- **丰富的 API**，用于任务属性、资源、日历等。  
- **可扩展**——适用于小型工具或企业级调度引擎。

## 先决条件
在开始之前，请确保您已具备：

- **Java Development Kit (JDK)** 已在您的机器上安装。  
- **Aspose.Tasks for Java** 库已从 [here](https://releases.aspose.com/tasks/java/) 下载。  
- 一个 IDE，例如 **Eclipse** 或 **IntelliJ IDEA**，用于编写和运行 Java 代码。

## 导入包
将所需的 Aspose.Tasks 类添加到 Java 源文件的顶部：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## 步骤 1：设置文档目录
定义项目文件的读取或写入所在文件夹。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

*此步骤满足 **set document directory** 要求，为 API 提供了 MPP 文件的明确位置。*

## 步骤 2：创建新项目
实例化一个 `Project` 对象，可选择加载已有的 MPP 文件或从空白模板开始。

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

## 步骤 3：添加汇总任务
汇总任务用于分组相关的子任务。这里我们**创建汇总任务** “Summary1”。

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

## 步骤 4：添加子任务
现在在汇总任务下添加子任务，以构建层次结构。

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

根据需要继续添加更多任务和子任务，以反映项目结构。每次调用 `add` 都会扩展层次结构，使您能够以编程方式建模复杂的计划。

## 常见问题与技巧
- **路径错误：** 确保 `dataDir` 以适当的文件分隔符（`/` 或 `\\`）结尾。  
- **许可证异常：** 如果出现许可证错误，请确认在创建 `Project` 之前已加载有效的许可证文件。  
- **保存更改：** 修改项目后，调用 `project.save(dataDir + "updated_project.mpp");` 以持久化更改。

## 常见问题

### Aspose.Tasks 适用于小规模项目吗？
当然！该 API 可从简单的任务列表扩展到大型企业计划。

### 在哪里可以找到 Aspose.Tasks for Java 的详细文档？
请参阅文档 [here](https://reference.aspose.com/tasks/java/)。

### 如何获取 Aspose.Tasks 的临时许可证？
访问 [this link](https://purchase.aspose.com/temporary-license/) 获取可用于评估的试用许可证。

### 我可以使用 Aspose.Tasks 自定义任务属性吗？
是的，您可以在每个 `Task` 对象上设置开始日期、持续时间、资源、自定义字段以及许多其他属性。

### 是否有 Aspose.Tasks 用户的支持社区？
当然！加入 Aspose.Tasks 社区的 [the support forum](https://forum.aspose.com/c/tasks/15)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

**最后更新：** 2026-01-25  
**测试环境：** Aspose.Tasks for Java (latest release)  
**作者：** Aspose