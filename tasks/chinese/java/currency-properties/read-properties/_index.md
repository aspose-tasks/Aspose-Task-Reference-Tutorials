---
date: 2026-02-07
description: 学习如何使用 Aspose.Tasks for Java 从 MS Project 文件中读取货币属性（Java）并提取货币符号（Java）。请按照本分步指南，以编程方式提取货币代码、符号、位数和位置。
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 项目在 Java 中读取货币属性
url: /zh/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 读取货币属性 Java 与 Aspose.Tasks 项目

## Introduction
在本教程中，您将使用 Aspose.Tasks for Java API 从 Microsoft Project 文件中 **read currency properties java**。Aspose.Tasks 让您无需安装 Microsoft Project 即可处理 .mpp 文件，非常适合自动化报告、数据迁移或集成到基于 Java 的企业应用程序中。阅读完本指南后，您将能够直接从项目文件中提取货币代码、符号、小数位数以及符号位置。

## Quick Answers
- **“read currency properties java” 是什么意思？** 它指的是使用 Java 代码从 MS Project 文件中检索与货币相关的元数据（代码、符号、位数、位置）。  
- **我需要许可证才能尝试吗？** Aspose.Tasks 提供免费试用版；在生产环境中需要商业许可证。  
- **需要哪个 JDK 版本？** Java 8 或更高。  
- **读取后我可以修改货币设置吗？** 可以，Aspose.Tasks 允许对货币属性进行读取和写入操作。  
- **这兼容所有 .mpp 版本吗？** 该 API 支持 Microsoft Project 2003‑2021 创建的文件。

## What is read currency properties java?
在 Java 中读取货币属性是指访问项目级别的设置，这些设置决定了 Microsoft Project 文件中货币值的显示方式。这些设置包括 ISO 货币代码（例如 **USD**）、符号（**$**）、小数位数以及符号是出现在金额之前还是之后。

## Why read currency properties java with Aspose.Tasks?
- **无需安装 Microsoft Project** – 该 API 可在任何支持 Java 的平台上运行。  
- **快速、进程内提取** – 适用于批量处理大量项目文件。  
- **完全控制** – 您可以将检索到的值与自定义报告结合，或集成到 ERP 系统中。  
- **跨版本支持** – 可处理从 Project 2003 到最新 2021 版的 .mpp 文件。

## Prerequisites
Before you start, make sure you have:

1. **Java Development Kit (JDK)** – Java 8 or newer installed and configured in your `PATH`.  
2. **Aspose.Tasks for Java JAR** – download the latest library from [here](https://releases.aspose.com/tasks/java/) and add it to your project’s classpath.  

## Import Packages
Begin by importing the Aspose.Tasks namespace required for project manipulation:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
Define the folder that contains the `.mpp` file you want to analyze. Keeping the path in a variable makes the code reusable:

```java
String dataDir = "Your Data Directory";
```

*将 `"Your Data Directory"` 替换为 `project.mpp` 所在文件夹的绝对或相对路径。*

## Step 2: Create a Project Reader Instance
Load the Microsoft Project file into a `Project` object. This object gives you access to all project properties, including currency settings:

```java
Project project = new Project(dataDir + "project.mpp");
```

*如果文件名不同，请相应更改 `"project.mpp"`。*

## Step 3: Display Currency Properties
Now retrieve each currency attribute using the `Prj` enumeration and print the results to the console. The API returns objects that you can convert to strings for display:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**您将看到：**  
- **Currency Code** – ISO‑4217 代码，如 `USD`、`EUR`、`JPY`。  
- **Currency Digits** – 大多数货币通常为 `2`，日元为 `0`。  
- **Currency Symbol** – 报表中显示的字符（`$`、`€`、`¥`）。  
- **Currency Symbol Position** – `0` 表示 **在金额前**，`1` 表示 **在金额后**。

## How to extract currency symbol java?
If your only interest is the symbol itself, you can focus on the `Prj.CURRENCY_SYMBOL` property. The same `project.get(...)` call returns the symbol, which you can store, log, or pass to another service for further processing. This is especially useful when you need to **extract currency symbol java** for financial dashboards or localized UI components.

## Step 4: Process Completion
Signal that the extraction finished successfully. This simple message is helpful when the code runs as part of a larger batch job:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` 路径不正确或文件名拼写错误。 | 验证目录字符串并确保 `.mpp` 文件存在于指定位置。 |
| **NullPointerException on `project.get(...)`** | 项目文件不包含货币信息（不太可能）或属性键错误。 | 在读取前使用 `project.contains(Prj.CURRENCY_CODE)` 检查是否存在。 |
| **LicenseException** | 在生产环境中未使用有效的 Aspose.Tasks 许可证运行。 | 在创建 `Project` 对象之前使用 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 应用许可证文件。 |

## Frequently Asked Questions

**问：Aspose.Tasks 是否兼容所有版本的 Microsoft Project？**  
**答：** Aspose.Tasks 支持 Microsoft Project 2003‑2021 生成的 .mpp 文件，涵盖旧版和最新格式。

**问：我可以使用 Aspose.Tasks 修改货币属性吗？**  
**答：** 可以，您既可以读取也可以写入货币设置。使用 `project.set(Prj.CURRENCY_CODE, "EUR");` 然后保存项目。

**问：Aspose.Tasks 适合商业使用吗？**  
**答：** 当然。它是商业库，您可以在 [here](https://purchase.aspose.com/buy) 购买许可证。

**问：Aspose.Tasks 提供免费试用吗？**  
**答：** 是的，可从 [here](https://releases.aspose.com/) 获取功能完整的试用版。

**问：我可以在哪里寻求 Aspose.Tasks 的帮助或支持？**  
**答：** 官方 Aspose.Tasks 论坛是获取帮助的最佳地点——请访问 [here](https://forum.aspose.com/c/tasks/15)。

## Additional FAQ (AI‑Optimized)

**问：如何在 Java 中以编程方式仅提取货币符号？**  
**答：** 调用 `project.get(Prj.CURRENCY_SYMBOL)` 并将结果强制转换为 `String`。这将返回项目文件中使用的确切符号。

**问：我可以从受密码保护的 .mpp 文件读取货币属性吗？**  
**答：** 可以。使用接受密码的 `Project` 构造函数的相应重载加载文件，然后按示例读取属性。

**问：处理大量项目文件时性能如何？**  
**答：** Aspose.Tasks 在进程内运行，通常在几毫秒内读取标准 .mpp 文件。对于批量操作，尽可能复用相同的 `Project` 实例。

## Conclusion
您已经学习了如何使用 Aspose.Tasks for Java **read currency properties java** 和 **extract currency symbol java** 从 MS Project 文件中读取货币属性和提取货币符号。此功能使您能够在不依赖 Microsoft Project 本身的情况下，将货币元数据整合到自定义报告、财务分析或集成流水线中。欢迎尝试修改这些属性或将此数据与其他项目属性结合，以构建更丰富的解决方案。

---

**最后更新：** 2026-02-07  
**测试环境：** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}