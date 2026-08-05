---
date: 2026-02-13
description: 学习如何计算日期之间的天数、创建测试项目，并在使用 Aspose.Tasks for Java 操作 Microsoft Project
  文件时添加自定义字段。
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 计算日期之间的天数
url: /zh/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 计算日期之间的天数

## Introduction
在本教程中，您将通过创建测试项目、添加自定义字段，并使用 Aspose.Tasks for Java 库中的 Microsoft Project 公式来 **计算日期之间的天数**。无论是生成进度表、计算截止日期，还是自动化报表，Aspose.Tasks 都可以让您在无需桌面安装的情况下以编程方式操作 Project 数据。完成本指南后，您将拥有一个可运行的示例，演示如何定义扩展属性、为任务设置截止日期，并将项目保存为 MPP 文件。

## Quick Answers
- **本教程覆盖哪些内容？** 创建测试项目、添加自定义字段、定义扩展属性，以及使用公式为任务设置截止日期以计算日期之间的天数。  
- **需要哪个库？** Aspose.Tasks for Java（最新版本）。  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境需要正式许可证。  
- **可以使用哪种 IDE？** 任意支持 JDK 8+ 的 Java IDE（IntelliJ IDEA、Eclipse、VS Code 等）。  
- **实现大概需要多长时间？** 复制代码并运行约需 10‑15 分钟。

## What is “calculate days between dates” in Aspose.Tasks?
在 Aspose.Tasks 中，计算日期之间的天数是指使用 Project 公式将一个日期字段（例如 **Finish**）从另一个日期字段（例如 **Deadline**）中相减，并返回以天为单位的数值差。此功能可用于跟踪进度偏差、衡量缓冲时间或生成自定义报表。

## Why Use Aspose.Tasks to Calculate Days Between Dates?
- **Full API coverage** – 访问每个 Project、Task 和 Resource 属性。  
- **No Office installation required** – 可在服务器、CI 流水线和 Docker 容器中运行。  
- **Cross‑platform** – 在 Windows、Linux 和 macOS 上使用相同的 Java 代码。  
- **Robust formula engine** – 直接在项目文件中定义诸如 `[Deadline] - [Finish]` 的计算公式。

## How to set deadline for a task
在计算间隔之前，需要先设置截止日期。截止日期存储在任务的 `Tsk.DEADLINE` 字段中，可通过 `java.util.Calendar` 实例进行赋值。

## How to define extended attribute
扩展属性是用于保存公式结果的自定义字段。您只需定义一次，为其指定易读的别名，然后附加执行日期相减的公式。

## Prerequisites
在开始之前，请确保具备以下条件：

- **Java Development Kit (JDK) 8+** – 可从 Oracle 官网或 AdoptOpenJDK 下载。  
- **Aspose.Tasks for Java** – 从 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 获取最新 JAR，并将其添加到项目的 classpath 或 Maven/Gradle 依赖中。

## Import Packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Test Project with a Custom Field
We begin by **creating a test project** and adding a custom field that will later hold our formula result.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` is a helper method that builds a minimal schedule and registers an extended attribute ready for formula assignment.

### Step 2: Define an Extended Attribute (Add Custom Field)
Next, we **define an extended attribute** – essentially the custom field – and give it a friendly alias. This is where we **add custom field** logic.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** makes the field readable in Project.  
- **Formula** calculates the number of days between a task’s *Finish* date and its *Deadline* – the core of *calculate days between dates*.

### Step 3: Set Deadline for a Task (Add Deadline Task & Set Task Deadline)
Now we **add deadline task** data by setting the *Deadline* property on a specific task.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- The `Calendar` instance defines the exact deadline moment.  
- `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.

### Step 4: Save the Project (Manipulate Microsoft Project File)
Finally, we **manipulate Microsoft Project** by persisting the changes to an MPP file.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

You can open `SaveFile.mpp` in Microsoft Project to see the custom field, formula result, and deadline reflected in the schedule.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Formula not evaluating** | Ensure the attribute’s `Formula` string uses correct field names (e.g., `[Deadline]`, `[Finish]`). |
| **Task not found** | Verify the task ID (`1` in the example) exists; use `project.getRootTask().getChildren().size()` to debug. |
| **License exception** | Apply a valid Aspose.Tasks license before calling any API methods (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing you to **manipulate Microsoft Project** files in the language of your choice.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Absolutely. Download a fully functional trial from the [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: How can I get support for Aspose.Tasks?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to ask questions and share experiences with the community.

**Q: Do I need a temporary license for evaluation?**  
A: A temporary license is available for short‑term testing; you can request one [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}