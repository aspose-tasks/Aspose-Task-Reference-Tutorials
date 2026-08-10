---
date: 2026-06-25
description: 了解如何使用 Aspose.Tasks for Java 添加任务并更新 MPP 文件，这是一款 Java 项目管理库，可让您创建任务 Microsoft
  Project 文件并将项目保存为 MPP。
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: 如何在 Aspose.Tasks 中添加任务并更新 MPP 文件
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中添加任务并更新 MPP 文件
url: /zh/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中添加任务并更新 MPP 文件

## 介绍
在本教程中，您将学习 **如何向现有 Microsoft Project (MPP) 文件添加任务**，并使用 Aspose.Tasks for Java（领先的 **java 项目管理库**）保存更新后的计划。无论您是构建自定义调度器、自动化批量更新，还是将项目数据集成到更大的系统中，下面的分步指南都将展示如何加载项目、插入新任务、设置其日期，并将结果持久化为全新的 MPP 文档。

## 快速答案
- **“如何添加任务”在此上下文中是什么意思？** 它指的是以编程方式在现有 MPP 文件中创建一个新的工作项。  
- **哪个库负责此操作？** Aspose.Tasks for Java，一个强大的 java 项目管理库。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **我可以将结果保存为 MPP 吗？** 是的——使用 `project.save(..., SaveFileFormat.Mpp)` **将项目保存为 mpp**。  
- **需要哪个 Java 版本？** Java 8 或更高。

## “如何添加任务”在 MPP 文件中意味着什么？
添加任务指的是在项目层次结构中插入一个新的工作项，定义其开始/结束日期，并将更改持久化回 MPP 文件。Aspose.Tasks 抽象了底层文件格式细节，让您专注于业务逻辑，同时自动处理资源分配、日历和依赖关系计算。它还会更新任何相关的分配并重新计算项目进度，以保持依赖任务之间的一致性。

## 为什么使用 Aspose.Tasks for Java？
- **完整兼容性**：支持 Microsoft Project 2007‑2021 的 100% 功能（超过 150 种任务类型和 200 个资源字段）。  
- **零依赖**：无需 COM、Office 或本机库——纯 Java API 可在任何运行 JRE 的环境中运行。  
- **功能丰富**：包括任务链接、资源分配、自定义字段和内置报表。  
- **高性能**：处理多达 10,000 个任务的项目时内存占用低于 200 MB，适合服务器端自动化。

## 前置条件
1. **Java 开发环境** – 已安装并配置 JDK 8+。  
2. **Aspose.Tasks for Java** – 从[下载页面](https://releases.aspose.com/tasks/java/)获取。  
3. **基础 Java 知识** – 熟悉类、对象和日期处理。

## 导入包
首先，导入您需要的类。这将为您提供项目操作、任务属性和日期处理的访问权限。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` 表示加载到内存中的 Microsoft Project 文件。`SaveFileFormat` 枚举了可保存的格式，如 MPP 或 PDF。`Task` 对应项目层次结构中的单个工作项。`Tsk` 提供任务字段常量，用于设置或获取值。`Calendar` 提供日期时间工具，用于定义计划。

## 步骤 1：定义数据目录
```java
String dataDir = "Your Data Directory";
```  
将 `"Your Data Directory"` 替换为源 MPP 文件所在的绝对路径。

## 步骤 2：读取现有项目
`Project` 类是 Aspose.Tasks 的核心对象，代表内存中的 Microsoft Project 文件。  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
构造函数加载 **SampleMSP2010.mpp**，为您提供一个可完全操作的对象模型。

## 步骤 3：创建新任务（如何添加任务）
`Task` 类表示项目层次结构中的单个工作项。  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
此行 **在 mpp 中创建任务**，通过向根任务添加名为 *Task1* 的子任务实现。

## 步骤 4：设置开始和结束日期
`Calendar` 类提供日期时间工具；月份采用零基计数（例如 `Calendar.JULY`）。  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
在这里为新添加的任务定义计划。根据您的项目时间线调整日期。

## 步骤 5：保存项目（将项目保存为 mpp）
`SaveFileFormat.Mpp` 告诉 Aspose.Tasks 将文件以原生 Microsoft Project 格式写回。  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
更新后的项目现在包含新任务，并以 **AfterLinking.mpp** 形式持久化。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **文件未找到** | 确认 `dataDir` 以路径分隔符（`/` 或 `\\`）结尾，且文件名正确。 |
| **日期不正确** | 记住 `Calendar` 的月份是零基的；`Calendar.JULY` 对应七月。 |
| **许可证异常** | 在调用任何 API 之前安装有效的 Aspose.Tasks 许可证，以避免评估水印。 |

## 常见问答
**问：如何一次性添加多个任务？**  
答：遍历任务名称集合，在循环内部重复 “创建任务” 代码块。

**问：我可以为新任务设置自定义字段吗？**  
答：可以——使用 `task.set(Tsk.CUSTOM_FIELD_x, value)`，其中 *x* 为字段索引。

**问：是否可以将现有任务复制为模板？**  
答：克隆源任务（`Task cloned = sourceTask.clone();`），然后将其添加到所需的父任务中。

**问：如果需要更新已有任务而不是添加新任务怎么办？**  
答：通过 ID 获取任务（`Task existing = project.getRootTask().getChildren().getById(id);`），并修改其属性。

**问：Aspose.Tasks 是否支持保存为 PDF、PNG 等其他格式？**  
答：支持——使用 `project.save("output.pdf", SaveFileFormat.Pdf);` 或 `SaveFileFormat.Png` 生成可视化表示。

---

**最后更新：** 2026-06-25  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相关教程

- [如何创建 MPP 文件 – 使用 Aspose.Tasks 创建并保存空项目为 MPP 格式](/tasks/java/project-configuration/create-save-mpp/)
- [如何创建项目 – 使用 Aspose.Tasks 设置新任务属性](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Java 创建任务列表 – 使用 Aspose.Tasks 设置 MS Project 基线](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}