---
date: 2026-10-05
description: 了解如何使用 Aspose.Tasks for Java 创建测试项目并计算日期之间的天数，添加自定义字段，并高效操作 MPP 文件。
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: 在 Aspose.Tasks 中使用公式
og_description: 使用 Aspose.Tasks for Java 创建测试项目并计算日期之间的天数。本指南展示了如何添加自定义字段、设置任务截止日期以及将项目保存为
  MPP 文件。
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: 创建测试项目并计算日期之间的天数
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: 创建测试项目并计算日期之间的天数
url: /zh/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建测试项目并计算日期之间的天数

在本教程中，您将**创建测试项目**并**计算日期之间的天数**，通过添加自定义字段、定义扩展属性，并通过 Aspose.Tasks for Java 库应用 Microsoft Project 公式。无论您是需要生成计划、计算截止日期，还是自动化报告，Aspose.Tasks 都可以在无需桌面安装的情况下以编程方式操作 Project 数据，支持 50 多种输入和输出格式，并以内存高效模式处理数百页的文件。

## 快速答案
- **本教程涵盖什么内容？** 它展示了如何创建测试项目、定义扩展属性、设置任务截止日期，以及使用公式计算日期之间的天数。  
- **需要哪个库？** Aspose.Tasks for Java（最新版本）。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **我可以使用哪种 IDE？** 任何支持 JDK 8+ 的 Java IDE（IntelliJ IDEA、Eclipse、VS Code）。  
- **实现大约需要多长时间？** 大约 10‑15 分钟，复制代码并运行即可。

## 在 Aspose.Tasks 中，“计算日期之间的天数” 是什么？
在 Aspose.Tasks 中，公式是一个可以引用任务字段并执行计算的字符串。`[Deadline] - [Finish]` 是 Aspose.Tasks 用于返回两个日期字段之间天数差的公式语法。结果以表示完整天数的数值形式存储，您可以在自定义字段中显示或用于进一步计算。

## 为什么使用 Aspose.Tasks 来计算日期之间的天数？
Aspose.Tasks 为每个 Project、Task 和 Resource 属性提供**完整的 API 覆盖**，可在 Windows、Linux 和 macOS 上运行，且**不需要安装 Microsoft Project 或 Office**。该引擎能够在典型服务器硬件上在一秒钟内处理**500+ 任务**的项目，非常适合 CI 流水线、Docker 容器和高并发批处理。

## 如何为任务设置截止日期
`java.util.Calendar` 是一个表示特定时间点的 Java 类。您可以通过将 `java.util.Calendar` 值分配给任务的 `Tsk.DEADLINE` 字段来设置截止日期。创建 Calendar 实例后，设置其年份、月份和日期为所需的截止时间，然后调用 `task.set(Tsk.DEADLINE, calendar);`。截止日期存储在项目文件中，可在公式如 `[Deadline] - [Finish]` 中使用。

## 如何定义扩展属性
扩展属性是存储公式结果的自定义字段。您只需创建一次，给它一个友好的别名，并附加 `[Deadline] - [Finish]` 表达式，这样每个任务就能自动计算间隔。通过实例化 `ExtendedAttribute`、设置其 Alias、分配公式并将其添加到项目的集合中即可完成创建。

## 前置条件
在开始之前，请确保您具备以下条件：

- **Java Development Kit (JDK) 8+** – 从 Oracle 网站下载或使用 OpenJDK。  
- **Aspose.Tasks for Java** – 从 [Aspose.Tasks for Java 下载页面](https://releases.aspose.com/tasks/java/) 获取最新的 JAR，并将其添加到项目的 classpath 或 Maven/Gradle 依赖中。

## 导入包
首先，导入我们需要的类：

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 步骤指南

### 步骤 1：使用自定义字段创建测试项目
我们首先**创建测试项目**并添加一个自定义字段，以便后续存放公式结果。

```java
Project project = CreateTestProjectWithCustomField();
```

> *小贴士:* `CreateTestProjectWithCustomField()` 是一个帮助方法，用于构建最小日程并注册一个准备好分配公式的扩展属性。

### 步骤 2：定义扩展属性（添加自定义字段）
接下来，我们**定义扩展属性**——本质上是自定义字段——并为其提供一个友好的别名。这就是我们**添加自定义字段**逻辑的所在。

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** 使字段在 Project 中可读。  
- **Formula** 计算任务的 *Finish* 日期与其 *Deadline* 之间的天数——即 *计算日期之间的天数* 的核心。

### 步骤 3：为任务设置截止日期（添加截止任务并设置任务截止日期）
现在我们**添加截止任务**数据，通过在特定任务上设置 *Deadline* 属性来实现。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 实例定义了确切的截止时间点。  
- `set(Tsk.DEADLINE, …)` **设置任务截止日期** 为所选任务。

### 步骤 4：保存项目（操作 Microsoft Project 文件）
最后，我们**操作 Microsoft Project**，将更改持久化到 MPP 文件中。

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

您可以在 Microsoft Project 中打开 `SaveFile.mpp`，查看自定义字段、公式结果以及截止日期在计划中的体现。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **公式未计算** | 确保属性的 `Formula` 字符串使用了正确的字段名称（例如 `[Deadline]`、`[Finish]`）。 |
| **未找到任务** | 验证示例中的任务 ID（`1`）是否存在；使用 `project.getRootTask().getChildren().size()` 进行调试。 |
| **许可证异常** | 在调用任何 API 方法之前，应用有效的 Aspose.Tasks 许可证（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## 常见问题

**Q: 我可以在其他编程语言中使用 Aspose.Tasks 吗？**  
A: 是的，Aspose.Tasks 为 .NET、Java 等平台提供 API，允许您使用所选语言操作 Microsoft Project 文件。

**Q: Aspose.Tasks 是否提供免费试用？**  
A: 当然。可从 [Aspose.Tasks 下载页面](https://releases.aspose.com/) 下载功能完整的试用版。

**Q: 我在哪里可以找到 Aspose.Tasks 的详细文档？**  
A: 官方文档位于 [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/)。

**Q: 我如何获得 Aspose.Tasks 的支持？**  
A: 请访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 提问并与社区分享经验。

**Q: 评估时是否需要临时许可证？**  
A: 可提供用于短期测试的临时许可证；您可以在 [临时许可证请求页面](https://purchase.aspose.com/temporary-license/) 申请。

---

**最后更新：** 2026-10-05  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose

## 相关教程

- [如何创建 MPP 文件 – 使用 Aspose.Tasks 创建并保存空项目（MPP 格式）](/tasks/java/project-configuration/create-save-mpp/)
- [使用 Aspose.Tasks for Java 设置 MS Project 项目开始日期](/tasks/java/project-properties/write-project-info/)
- [如何在 Java 中使用 Aspose.Tasks 创建扩展属性](/tasks/java/resource-management/extended-resource-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}