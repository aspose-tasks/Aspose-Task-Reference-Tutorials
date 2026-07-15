---
date: 2026-02-10
description: 学习如何获取货币值、读取 MS Project 文件并使用 Aspose.Tasks 将项目文件转换为 Java。一步一步的指南，帮助提取货币数字。
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 从 MS Project 获取货币
url: /zh/java/currency/currency-digits/
weight: 11
---

 blocks/products/products-backtop-button >}}

Make sure to keep all shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 从 MS Project 获取货币信息

## Introduction
如果您想了解 **如何获取货币** 信息从 Microsoft Project 文件，您来对地方了。在本综合教程中，您将发现 **如何使用 Aspose.Tasks for Java** 库处理 ms project currency 值。无论您是在构建报告工具、迁移实用程序，还是仅仅需要读取 **java project file** 中的货币设置，本指南将一步步带您完成——从加载 *.mpp* 文件到提取货币位数。完成后，您将能够在自己的应用程序中自如处理 ms project currency 数据。

## Quick Answers
- **读取 MS Project 文件的库是什么？** Aspose.Tasks for Java.  
- **获取货币位数需要多少行代码？** 项目加载后只需三行简洁代码。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持哪个 Java 版本？** Java 8 或更高（任何能运行 Aspose.Tasks 的 JDK）。  
- **我可以检索其他 Project 属性吗？** 可以 – Aspose.Tasks 提供完整的 Project 字段集合（例如开始日期、成本率等）。

## What is ms project currency?
`ms project currency` 指的是 Microsoft Project 在显示货币值时使用的数字精度（小数位数）。它在项目文件中存储为 **CURRENCY_DIGITS** 属性，决定金额是显示为整数、保留一位小数、两位小数等。

## Why use Aspose.Tasks for handling ms project currency?
- **无需安装 Microsoft Project** – 直接在任何支持 Java 的平台上处理 *.mpp* 文件。  
- **强类型安全** – API 返回强类型值，减少解析错误。  
- **性能优化** – 快速加载大型项目，仅提取所需字段。  
- **跨平台** – 在 Windows、Linux 或 macOS 上运行，无需修改。

## Prerequisites
在开始之前，请确保具备以下条件：

1. **Java 开发环境** – 已安装并配置 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从官方站点下载最新 JAR: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)。  
3. **基本的 Java 知识** – 您应熟悉创建 Java 项目、添加外部库以及运行 `main` 方法。  

## Import Packages
首先，导入我们需要的类。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Define Data Directory
指定包含您的 **java project file** (`*.mpp`) 的文件夹。  
```java
String dataDir = "Your Data Directory";
```
将 `"Your Data Directory"` 替换为 `project.mpp` 所在的绝对或相对路径。

## Step 2: Load the MPP File  
现在我们将看到使用 Aspose.Tasks **加载 mpp** 文件的方法。  
```java
Project project = new Project(dataDir + "project.mpp");
```
确保文件名完全匹配；否则将抛出 `IOException`。

## Step 3: Retrieve Currency Digits  
项目加载后，提取 **ms project currency** 位数只需一行代码：  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
此调用返回一个 `Integer`，表示小数位数（例如 `2` 表示分）。该值会打印到控制台，也可以存入变量以供后续处理。

## Common Issues & Tips
- **文件未找到** – 再次检查 `dataDir` 路径，并确保文件名正确，包括 `.mpp` 扩展名。  
- **不支持的文件版本** – Aspose.Tasks 支持 Project 2000‑2024 格式；较旧或损坏的文件可能需要转换。  
- **未设置许可证** – 开发阶段可使用试用版，但生产环境必须应用有效许可证以避免评估水印。

## Frequently Asked Questions

**问：Aspose.Tasks 能处理除货币位数之外的其他 Project 属性吗？**  
**答：可以，Aspose.Tasks 提供广泛功能，可操作 Project 文件的各个方面，如任务、资源和自定义字段。**

**问：Aspose.Tasks 适合企业级应用吗？**  
**答：当然，Aspose.Tasks 旨在满足企业级项目的需求，提供高性能和可扩展性。**

**问：Aspose.Tasks 支持跨平台开发吗？**  
**答：是的，您可以在任何支持 Java Runtime Environment 的平台（Windows、Linux、macOS）上使用 Aspose.Tasks for Java。**

**问：我可以在购买前试用 Aspose.Tasks 吗？**  
**答：可以，您可以从 [此处](https://releases.aspose.com/) 下载免费试用版。**

**问：在哪里可以获得 Aspose.Tasks 的支持？**  
**答：您可以在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获得支持。**

## Conclusion
现在，您已经了解如何使用 Aspose.Tasks for Java 从 MS Project 文件中 **获取货币位数**。过程非常简单：加载项目，调用 `project.get(Prj.CURRENCY_DIGITS)`，并在您的应用中使用该结果。欢迎使用相同模式探索其他项目属性，并将此逻辑集成到更大的报告或迁移解决方案中。

---

**最后更新：** 2026-02-10  
**测试环境：** Aspose.Tasks for Java（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}