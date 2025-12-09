---
date: 2025-12-03
description: 学习如何使用 Aspose.Tasks for Java 创建日历 MS Project、将项目转换为 MPP，并轻松保存项目为 MPP。
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 创建日历 MS Project 并保存为 MPP
url: /zh/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建日历 MS Project 并保存为 MPP（使用 Aspose.Tasks）

## Introduction

在现代项目管理中，您经常需要**创建日历 MS Project**文件，然后以原生 MPP 格式共享它们。无论是从多个来源整合进度表，还是迁移遗留数据，能够以编程方式生成日历都能节省时间并消除手动错误。本教程将带您完整了解在 MS Project 中创建日历、定制它，并最终使用 Aspose.Tasks Java API **将项目转换为 MPP**。

## Quick Answers
- **本教程涵盖什么？** 在 MS Project 中创建日历并使用 Aspose.Tasks for Java 将其保存为 MPP 文件。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **需要哪个 Java 版本？** Java 8 或更高（JDK 8+）。  
- **我可以自定义日历吗？** 可以——您可以添加工作时间、例外和假期。  
- **实现需要多长时间？** 基本日历大约需要 10‑15 分钟。

## What is “create calendar MS Project”?

创建日历 MS Project 是指以编程方式定义工作日、工作时间和例外，这些信息驱动 Microsoft Project 文件中的任务调度。通过使用 Aspose.Tasks，您可以构建、修改并持久化这些日历，而无需打开 Microsoft Project UI。

## Why use Aspose.Tasks for this task?

- **完整的 .NET/Java 兼容性** – 在任何支持 Java 的平台上均可运行。  
- **无需 COM 或 Office 安装** – 适用于服务器端自动化。  
- **丰富的 API** – 支持所有日历属性，包括自定义工作周和假期。  
- **直接输出 MPP** – 您可以 **保存项目为 MPP**，无需中间转换。

## Prerequisites

1. **Java Development Kit (JDK) 8+** – 确保 `java -version` 显示 1.8 或更高。  
2. **Aspose.Tasks for Java** – 从 [Aspose 网站](https://releases.aspose.com/tasks/java/) 下载最新的 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse 或您喜欢的任何编辑器。  
4. **基本的 Java 知识** – 熟悉类、方法和文件 I/O。

## Step‑by‑Step Guide

### Step 1: Import Required Packages

首先，将 Aspose.Tasks 类和 Java 实用工具导入作用域。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Step 2: Set Up the Data Directory

定义输入模板和输出文件所在的位置。将占位符替换为您机器上的实际路径。

```java
String dataDir = "Your Data Directory";
```

### Step 3: Define Input and Output File Names

我们将加载现有的 MPP 文件（或空白项目），并将结果写入新文件。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Step 4: Load the Project and Add a New Calendar

从源文件创建 `Project` 实例，并添加名为 **“Calendar 1”** 的日历。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Step 5: Customize the Calendar (Optional)

如果需要特定的工作时间、假期或例外，请调用您自己的辅助方法。示例使用 `GetTestCalendar` 作为占位符。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **专业提示：** 您可以直接操作 `cal1.getWeekDays()` 为一周中的每一天设置工作时间。

### Step 6: Assign the Calendar to the Project

告诉项目使用新创建的日历进行所有调度计算。

```java
project.set(Prj.CALENDAR, cal1);
```

### Step 7: Save the Project as MPP

现在通过使用 `SaveFileFormat.Mpp` 选项保存，即可 **将项目转换为 MPP**。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Step 8: Confirm Successful Completion

一个简单的控制台消息会告诉您过程已成功完成且没有错误。

```java
System.out.println("Process completed Successfully");
```

## Common Use Cases

- **自动化进度生成**，用于重复项目（例如每周冲刺）。  
- **将遗留的 CSV 或 Excel 日历迁移** 到功能完整的 MS Project 文件。  
- **服务器端报表**，Web 服务按需返回 MPP 文件。

## Troubleshooting & Common Pitfalls

| Issue | Cause | Fix |
|-------|-------|-----|
| `project.save` 时的 NullPointerException | `dataDir` 指向不存在的文件夹 | 确保目录存在，或通过代码创建它。 |
| 日历未应用到任务 | 任务仍引用默认日历 | 在设置 `Prj.CALENDAR` 后，还需更新每个任务的 `Task.CALENDAR`（如果之前被覆盖）。 |
| 输出文件为 0 KB | 缺少写入权限 | 以适当的文件系统权限运行 JVM，或选择可写路径。 |

## Frequently Asked Questions

**问：Aspose.Tasks for Java 是否兼容不同版本的 MS Project？**  
答：是的，Aspose.Tasks for Java 支持广泛的 MS Project 版本，从 Project 2007 到最新版本，确保无缝兼容。

**问：我可以根据特定项目需求自定义日历吗？**  
答：当然可以。您可以定义工作日、设置自定义工作周、添加假期，甚至在单个项目文件中创建多个日历。

**问：Aspose.Tasks for Java 是否提供故障排除和帮助支持？**  
答：是的，您可以在 Aspose.Tasks 社区论坛获取帮助，[点击此处](https://forum.aspose.com/c/tasks/15)。

**问：Aspose.Tasks for Java 是否提供免费试用？**  
答：是的，完整功能的免费试用可在[此处](https://releases.aspose.com/)获取。

**问：如何获取 Aspose.Tasks for Java 的临时许可证？**  
答：可通过 Aspose 网站[此处](https://purchase.aspose.com/temporary-license/)申请临时许可证。

---

**最后更新：** 2025-12-03  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}