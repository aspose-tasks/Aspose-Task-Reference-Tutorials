---
date: 2026-01-18
description: 学习如何使用 Java 创建任务列表并将任务添加到 Microsoft Project，使用 Aspose.Tasks 在不使用 MS Project
  的情况下设置基准。
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 在 Java 中创建任务列表 – MS Project 基线
url: /zh/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建任务列表 Java – 使用 Aspose.Tasks 的 MS Project 基线

## 介绍
在本教程中，您将通过使用 Aspose.Tasks for Java 生成 Microsoft Project 任务基线来 **创建任务列表 Java**。Aspose.Tasks 让您无需安装 Microsoft Project 即可处理 Project 文件，因此您可以 **向 Microsoft Project 添加任务**、操作资源，甚至 **在没有 MS Project 的情况下设置基线**——全部使用纯 Java 代码完成。

## 快速答案
- **Aspose.Tasks 是做什么的？** 它提供了一个 Java API，用于在没有 MS Project 的情况下创建、读取和编辑 Microsoft Project 文件。  
- **需要安装 Microsoft Project 吗？** 不需要，Aspose.Tasks 可独立运行。  
- **需要哪个 Java 版本？** JDK 8 或更高。  
- **可以为单个任务设置基线吗？** 可以，使用 `setBaseline` 并传入任务列表。  
- **生产环境需要许可证吗？** 需要，商业许可证可去除评估限制。

## 什么是任务基线？
任务基线记录任务的原始计划开始、完成和工作量值。它作为参考点，用于将实际进度与原始计划进行比较。

## 为什么使用 Aspose.Tasks 来创建任务列表 Java？
- **无需 MS Project 依赖** – 适合服务器端自动化。  
- **通过 Java 代码完全控制** 任务、资源和日历。  
- **跨版本兼容**，支持 Project 2007‑2024 文件。

## 前置条件
1. **Java 开发工具包 (JDK)** – 安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从[下载链接](https://releases.aspose.com/tasks/java/)获取库。

## 导入包
要在 Java 项目中使用 Aspose.Tasks，导入所需的包：
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 步骤 1：创建 Project 对象
```java
Project project = new Project();
```
这里我们实例化一个新的 `Project` 对象——它代表将保存任务列表的 MS Project 文件。

## 步骤 2：向项目添加任务
```java
Task task = project.getRootTask().getChildren().add("Task");
```
通过 `getRootTask()` 访问项目层次结构的根节点并 **向 Microsoft Project 添加任务**。字符串 `"Task"` 为任务名称，您可以替换为任意描述。

## 步骤 3：为指定任务设置基线
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
要 **在没有 MS Project 的情况下设置基线**，创建包含需要基线的任务的列表（此处为 `myList`），并将其传递给 `setBaseline`。如果只需对部分任务设置基线，请将已添加的任务填入 `myList`。

## 步骤 4：为整个项目设置基线
```java
project.setBaseline(BaselineType.Baseline);
```
如果希望一次性为整个项目设置基线，只需使用所需的 `BaselineType` 调用 `setBaseline`。

## 如何使用 Aspose.Tasks 向 Microsoft Project 添加任务
除了上面的单任务示例，您还可以添加多个任务、子任务并分配资源。每次调用 `add()` 都会返回一个 `Task` 对象，您可以进一步配置（持续时间、开始日期等）。

## 如何在没有 MS Project 的情况下设置基线
Aspose.Tasks 完全通过代码实现基线创建。您可以通过更改 `BaselineType` 枚举设置不同的基线类型（Baseline、Baseline1‑Baseline10），从而在不打开 MS Project 的情况下跟踪多个修订基线。

## 常见问题及解决方案
- **基线未显示：** 确保在设置基线后调用 `project.save("output.mpp")`（此处为简洁省略保存步骤）。  
- **任务列表为空：** 检查是否向正确的父节点（`getRootTask()` 或子任务）添加了任务。  
- **版本不匹配错误：** 使用最新的 Aspose.Tasks JAR，以确保兼容更新的 .mpp 格式。

## 常见问答

**问：可以在没有安装 Microsoft Project 的情况下使用 Aspose.Tasks for Java 吗？**  
答：可以，Aspose.Tasks 可独立运行，无需在主机上安装 Microsoft Project。

**问：Aspose.Tasks for Java 是否兼容不同版本的 Microsoft Project？**  
答：完全兼容。该库支持 2007 至最新 2024 版本的 Project 文件。

**问：可以使用 Aspose.Tasks for Java 操作项目资源吗？**  
答：可以，您可以以编程方式添加、更新和删除资源，方式与操作任务相同。

**问：Aspose.Tasks for Java 是否支持设置任务依赖关系？**  
答：支持，您可以使用 `TaskLink` 类定义前置任务‑后置任务关系。

**问：Aspose.Tasks for Java 是否提供技术支持？**  
答：提供，您可以通过[支持论坛](https://forum.aspose.com/c/tasks/15)获取帮助，Aspose 员工和社区成员会回复查询。

## 结论
通过遵循上述步骤，您已经学习了如何 **创建任务列表 Java**、**向 Microsoft Project 添加任务**，以及 **在没有 MS Project 的情况下设置基线**，全部使用 Aspose.Tasks 实现。这种方法简化了项目自动化，消除了对桌面 Project 安装的需求，并为您的项目数据提供了完整的编程控制。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-01-18  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

---