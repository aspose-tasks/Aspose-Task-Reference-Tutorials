---
date: 2025-12-07
description: 学习如何在使用 Aspose.Tasks for Java 操作 Microsoft Project 文件时**创建测试项目**和**添加自定义字段**。
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 创建测试项目并在 Aspose.Tasks for Java 中使用公式
url: /zh/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建测试项目并在 Aspose.Tasks for Java 中使用公式

## Introduction
在本教程中，您将**创建测试项目**文件，添加自定义字段，并使用 Aspose.Tasks for Java 库处理 MS Project 公式。Aspose.Tasks 使得以编程方式**操作 Microsoft Project**数据变得直观——无论是生成计划、计算日期还是自动化报告。完成本指南后，您将拥有一个可运行的示例，定义扩展属性，为任务设置截止日期，并将项目保存为 MPP 文件。

## Quick Answers
- **What does the tutorial cover?** 本教程涵盖内容？ 创建测试项目，添加自定义字段，定义扩展属性，并使用公式设置任务截止日期。  
- **Which library is required?** 需要的库？ Aspose.Tasks for Java（最新版本）。  
- **Do I need a license?** 是否需要许可证？ 免费试用可用于开发；生产环境需要许可证。  
- **What IDE can I use?** 可以使用哪些 IDE？ 任意支持 JDK 8+ 的 Java IDE（IntelliJ IDEA、Eclipse、VS Code）。  
- **How long does the implementation take?** 实现大约需要多长时间？ 复制代码并运行大约需要 10‑15 分钟。

## What is a “Test Project” in Aspose.Tasks?
在 Aspose.Tasks 中，“测试项目”是什么？

**测试项目** 是一个轻量级的 Microsoft Project 文件，程序化创建，用于演示或验证功能。它包含最少量的任务、资源和自定义字段，您可以在不影响真实项目数据的情况下进行操作。

## Why Use Aspose.Tasks to Manipulate Microsoft Project?
- **Full API coverage** – 完整的 API 覆盖 – 可访问每个 Project、Task 和 Resource 属性。  
- **No Office installation required** – 无需安装 Office – 可在服务器、CI 流水线和 Docker 容器上运行。  
- **Cross‑platform** – 跨平台 – 在 Windows、Linux 和 macOS 上使用相同的 Java 代码运行。  
- **Robust formula engine** – 强大的公式引擎 – 在项目文件内部直接计算日期、持续时间和自定义字段。

## Prerequisites
在开始之前，请确保您具备以下条件：

- **Java Development Kit (JDK) 8+** – 从 Oracle 网站或采用 OpenJDK 下载。  
- **Aspose.Tasks for Java** – 从 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 获取最新 JAR，并将其添加到项目的 classpath 或 Maven/Gradle 依赖中。

## Import Packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Test Project with a Custom Field
我们首先**创建测试项目**并添加一个自定义字段，稍后用于保存公式结果。

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` 是一个帮助方法，用于构建最小日程并注册一个准备好分配公式的扩展属性。

### Step 2: Define an Extended Attribute (Add Custom Field)
接下来，我们**定义扩展属性**——本质上是自定义字段——并为其提供友好的别名。这里是我们**添加自定义字段**逻辑的地方。

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** 使字段在 Project 中可读。  
- **Formula** 计算任务的 *Finish* 日期与其 *Deadline* 之间的天数。

### Step 3: Set Deadline for a Task (Add Deadline Task & Set Task Deadline)
现在，我们通过在特定任务上设置 *Deadline* 属性来**添加截止日期任务**数据。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` 实例定义了精确的截止时间点。  
- `set(Tsk.DEADLINE, …)` 为选定任务**设置任务截止日期**。

### Step 4: Save the Project (Manipulate Microsoft Project File)
最后，我们通过将更改持久化为 MPP 文件来**操作 Microsoft Project**。

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

您可以在 Microsoft Project 中打开 `SaveFile.mpp`，查看自定义字段、公式结果以及在计划中体现的截止日期。

## Common Issues and Solutions
| 问题 | 解决方案 |
|-------|----------|
| **公式未计算** | 确保属性的 `Formula` 字符串使用了正确的字段名称（例如 `[Deadline]`、`[Finish]`）。 |
| **未找到任务** | 验证任务 ID（示例中的 `1`）是否存在；使用 `project.getRootTask().getChildren().size()` 进行调试。 |
| **许可证异常** | 在调用任何 API 方法之前应用有效的 Aspose.Tasks 许可证（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
**A:** 可以，Aspose.Tasks 为 .NET、Java 等平台提供 API，允许您在所选语言中**操作 Microsoft Project**文件。

**Q: Is there a free trial available for Aspose.Tasks?**  
**A:** 当然。可从 [Aspose.Tasks download page](https://releases.aspose.com/) 下载功能完整的试用版。

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
**A:** 官方文档位于 [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/)。

**Q: How can I get support for Aspose.Tasks?**  
**A:** 请访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 提问并与社区分享经验。

**Q: Do I need a temporary license for evaluation?**  
**A:** 短期测试可使用临时许可证；您可以在此处 [here](https://purchase.aspose.com/temporary-license/) 申请。

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}