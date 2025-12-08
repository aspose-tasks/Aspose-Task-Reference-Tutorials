---
date: 2025-12-04
description: 了解如何在 Aspose.Tasks Java 项目中设置货币，包括如何更改货币以及更改货币符号。轻松操作 Microsoft Project
  文件。
language: zh
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 项目中设置货币 – Java 指南
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 项目中设置货币 – Java 指南

## Introduction
在本教程中，您将学习 **如何设置货币** 为 Microsoft Project 文件使用 Aspose.Tasks Java API。无论您需要 *更改货币* 为国际团队，还是在 Java 中调整 *货币符号*，下面的步骤将通过清晰的解释和可直接运行的代码，引导您完成整个过程。

## Quick Answers
- **需要的库是什么？** Aspose.Tasks for Java.  
- **我可以更改货币符号吗？** 是 – 使用 `CurrencySymbolPositionType` 和 `Prj.CURRENCY_SYMBOL`.  
- **支持哪些文件格式？** XML、MPP，以及通过 `SaveFileFormat` 支持的许多其他格式.  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要许可证.  
- **实现大约需要多长时间？** 基本设置约需 5‑10 分钟.

## 项目文件中的“货币”是什么？
项目的货币定义了成本值的显示方式——代码（例如 `AUD`）、小数位数、符号（`$`），以及符号的位置。设置这些属性可确保每个与成本相关的字段（资源费率、任务预算等）都以正确的货币格式呈现给受众。

## 为什么使用 Aspose.Tasks 更改货币？
- **无需安装 Microsoft Project** – 在任何服务器上操作文件.  
- **完整的 API 覆盖** – 所有与货币相关的字段均通过 `Prj` 常量公开.  
- **跨平台** – 在 Windows、Linux 和 macOS 上均可使用任何兼容 Java 的 IDE.  
- **高性能** – 快速且可靠地处理大型项目文件.

## Prerequisites
在开始之前，请确保您已具备：

1. **Java Development Kit (JDK)** – 8 版或更高.  
2. **Aspose.Tasks for Java** – 从 [Aspose.Tasks 下载页面](https://releases.aspose.com/tasks/java/) 下载最新的 JAR.  
3. **IDE** – Eclipse、IntelliJ IDEA 或您喜欢的任何编辑器.  
4. **可写文件夹** – 用于保存生成的项目文件.

## Import Packages
First, import the classes that provide access to project properties and file handling.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Specify the folder that contains your source files and where the output will be written.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object. This object represents an in‑memory Microsoft Project file.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Here’s where we **how to set currency** details such as code, digits, symbol, and symbol position.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **专业提示：** 如果您需要 **更改货币** 为现有项目，只需使用 `new Project("file.mpp")` 加载文件，然后再应用上述设置.

### Step 4: Save the Updated Project
Write the project back to disk in the desired format. In this example we use the XML format, but you can also choose `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Print a friendly message so you know the operation completed without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **`NullPointerException` 在 `project.save`** | `dataDir` 不是有效路径或缺少写入权限. | 确保目录存在且您的 Java 进程具有写入权限. |
| **货币符号未显示** | 符号位置对您的地区设置不正确. | 如果符号应位于金额前，请使用 `CurrencySymbolPositionType.Before`. |
| **项目文件在 MS Project 中无法打开** | 以不兼容的设置保存为旧格式. | 使用 `SaveFileFormat.MPP` 保存，以完全兼容最近的 MS Project 版本. |

## Frequently Asked Questions

**问：我可以在单个项目中使用 Aspose.Tasks 设置多种货币吗？**  
答：是的，Aspose.Tasks 允许您通过对每个资源或每个任务设置货币属性，在单个项目文件中处理多种货币。

**问：Aspose.Tasks 是否兼容不同版本的 Microsoft Project 文件？**  
答：完全兼容。该库支持从 Project 2000 到最新版本的 MPP 文件，以及 XML 等其他格式。

**问：Aspose.Tasks 是否支持自定义货币格式？**  
答：是的，您可以定义自定义符号、小数位数和位置，以满足任何地区需求。

**问：我可以将 Aspose.Tasks 与其他 Java 库或框架集成吗？**  
答：当然可以。该 API 纯 Java，实现了与 Spring、Hibernate、Maven、Gradle 等生态系统的无缝集成。

**问：我在哪里可以找到 Aspose.Tasks 的额外支持或帮助？**  
答：访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取社区帮助，或查阅官方文档获取详细的 API 参考。

## Conclusion
现在您已经了解 **如何设置货币**、**如何更改货币** 值，以及 **如何以 Java 方式更改货币符号**，使用 Aspose.Tasks for Java。这些功能使您能够为全球团队定制成本数据，生成特定地区的报告，并保持项目文件在跨地区时的一致性。

---

**最后更新：** 2025-12-04  
**已测试版本：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}