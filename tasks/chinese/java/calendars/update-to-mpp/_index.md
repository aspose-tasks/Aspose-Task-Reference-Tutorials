---
date: 2026-02-05
description: 了解如何向日历添加假期、将日历分配给项目，并使用 Aspose.Tasks for Java 将 MS Project 文件保存为 MPP。
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 将假期添加到日历并保存为 MPP
url: /zh/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 将假期添加到日历并保存为 MPP

## 介绍

在现代项目管理中，您经常需要 **向日历文件添加假期**，创建 **MS Project 日历**，然后以原生 MPP 格式共享进度表。无论是整合来自多个来源的时间线，还是迁移遗留数据，使用编程方式生成日历都能消除手工错误并加快交付速度。本教程将手把手演示如何在 MS Project 中创建日历、为其添加假期、**将日历分配给项目**，以及最终使用 Aspose.Tasks Java API **将项目转换为 MPP**。

## 快速答疑
- **本教程覆盖哪些内容？** 向日历添加假期、将其分配给项目，并使用 Aspose.Tasks for Java 将结果保存为 MPP 文件。  
- **是否需要许可证？** 开发阶段可使用免费试用版；生产环境需购买商业许可证。  
- **需要哪个 Java 版本？** Java 8 或更高（JDK 8+）。  
- **可以自定义日历吗？** 可以——您可以添加工作时间、例外和假期。  
- **实现大概需要多长时间？** 基本日历约 10‑15 分钟即可完成。  

## 什么是 “create calendar MS Project”？

创建 calendar MS Project 是指通过代码定义工作日、工作小时以及例外情况，从而驱动 Microsoft Project 文件中的任务调度。使用 Aspose.Tasks，您可以 **java create project calendar**，对其进行修改，并在不打开 Microsoft Project UI 的情况下持久化更改。

## 为什么选择 Aspose.Tasks 来完成此任务？

- **完整的 .NET/Java 兼容性** —— 在任何支持 Java 的平台上均可运行。  
- **无需 COM 或 Office 安装** —— 适合服务器端自动化和 **automate schedule generation**。  
- **功能丰富的 API** —— 支持所有日历属性，包括自定义工作周和假期。  
- **直接输出 MPP** —— 您可以 **save project as MPP**，无需中间转换。

## 前置条件

1. **Java Development Kit (JDK) 8+** —— 确认 `java -version` 输出 1.8 或更高。  
2. **Aspose.Tasks for Java** —— 从 [Aspose website](https://releases.aspose.com/tasks/java/) 下载最新 JAR 包。  
3. **IDE** —— IntelliJ IDEA、Eclipse 或您喜欢的任何编辑器。  
4. **基础 Java 知识** —— 熟悉类、方法和文件 I/O。

## 如何向日历添加假期

下面我们将逐步演示从环境搭建到最终生成 MPP 文件的完整过程。代码块保持原样，说明文字已作中文扩展。

### 步骤 1：导入所需的包

首先，将 Aspose.Tasks 类和 Java 工具类导入到作用域中。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 步骤 2：设置数据目录

定义输入模板和输出文件所在的目录。将占位符替换为您机器上的实际路径。

```java
String dataDir = "Your Data Directory";
```

### 步骤 3：定义输入和输出文件名

我们将加载已有的 MPP 文件（或空白项目），并将结果写入新文件。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 步骤 4：加载项目并添加新日历

从源文件创建 `Project` 实例，并添加一个名为 **“Calendar 1”** 的日历。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 步骤 5：自定义日历（可选）

如果需要特定的工作时间、假期或例外，请调用您自己的辅助方法。示例中使用 `GetTestCalendar` 作为占位符。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **技巧提示：** 您可以直接操作 `cal1.getWeekDays()` 为每周的各天设置工作时间，或使用 `cal1.getExceptions()` 来 **add holidays to calendar**。

### 步骤 6：将日历分配给项目

告诉项目使用新创建的日历进行所有调度计算。

```java
project.set(Prj.CALENDAR, cal1);
```

### 步骤 7：将项目保存为 MPP

现在通过 `SaveFileFormat.Mpp` 选项 **convert project to MPP** 并保存。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 步骤 8：确认成功完成

简单的控制台信息会提示过程已顺利结束且无错误。

```java
System.out.println("Process completed Successfully");
```

## 常见使用场景

- **自动化生成进度表**，用于周期性项目（例如每周冲刺）。  
- **将遗留的 CSV 或 Excel 日历迁移** 到功能完整的 MS Project 文件。  
- **服务器端报表**，通过 Web 服务按需返回 MPP 文件。  

## 故障排查与常见陷阱

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| `NullPointerException` 在 `project.save` 时出现 | `dataDir` 指向不存在的文件夹 | 确认目录已存在，或在代码中动态创建该目录。 |
| 日历未应用到任务 | 任务仍引用默认日历 | 在设置 `Prj.CALENDAR` 后，还需更新已存在任务的 `Task.CALENDAR`（如果之前被覆盖）。 |
| 输出文件为 0 KB | 缺少写入权限 | 以拥有相应文件系统权限的方式运行 JVM，或选择可写路径。 |

## 常见问答

**问：Aspose.Tasks for Java 是否兼容不同版本的 MS Project？**  
答：是的，Aspose.Tasks for Java 支持广泛的 MS Project 版本，从 Project 2007 到最新发布，确保无缝兼容。

**问：我可以根据项目需求自定义日历吗？**  
答：完全可以。您可以定义工作日、设置自定义工作周、添加假期，甚至在同一项目文件中创建多个日历。

**问：Aspose.Tasks for Java 是否提供故障排查和技术支持？**  
答：提供，您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获取帮助。

**问：是否有 Aspose.Tasks for Java 的免费试用版？**  
答：有，完整功能的免费试用版可在 [here](https://releases.aspose.com/) 下载。

**问：如何获取 Aspose.Tasks for Java 的临时许可证？**  
答：可通过 Aspose 官网 [here](https://purchase.aspose.com/temporary-license/) 申请临时许可证。

---

**最后更新：** 2026-02-05  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}