---
date: 2026-09-09
description: 了解如何在 Aspose.Tasks Java 项目中更改货币符号，设置货币代码，调整符号，并为 Microsoft Project 文件应用自定义格式。
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: 在 Aspose.Tasks 项目中设置货币属性
og_description: 如何使用 Java 更改 Aspose.Tasks 中的货币符号。了解分步说明、先决条件以及自定义项目成本格式的技巧。
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: 如何在 Aspose.Tasks 中更改货币符号 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: 如何在 Aspose.Tasks 项目中更改货币符号 – Java 指南
url: /zh/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中更改货币符号 – Java 指南

## 介绍
在本教程中，您将学习**如何更改货币符号**，以使用 Aspose.Tasks Java API 处理 Microsoft Project 文件。无论您是为海外客户准备报告、整合多个地区的预算，还是仅需符合公司会计标准，调整货币符号可确保每个与成本相关的字段显示正确的货币符号。指南将逐步演示从设置开发环境到在新项目或现有项目文件中持久化更改的每一步。

## 快速答案
- **需要的库是什么？** Aspose.Tasks for Java.  
- **我可以更改货币符号吗？** 是的 – set `Prj.CURRENCY_SYMBOL` and choose `CurrencySymbolPositionType`.  
- **支持哪些文件格式？** XML, MPP, and many others via `SaveFileFormat`.  
- **开发是否需要许可证？** A free trial works for testing; a license is required for production.  
- **实现需要多长时间？** About 5‑10 minutes for a basic setup.

## 如何使用 Java 在 Aspose.Tasks 中更改货币符号？
加载目标项目（或创建新项目），设置所需的货币属性，然后保存文件。整个操作由三个 API 调用组成：创建或加载 `Project` 对象，分配货币代码、符号和位置，最后调用 `project.save`。此方法适用于全新项目和已有文件，无需安装 Microsoft Project。

## 为什么使用 Aspose.Tasks 更改货币？
Aspose.Tasks 提供**对 30 多个货币相关属性的完整 API 覆盖**，使您能够在一个地方定义代码、符号、小数位数和位置。该库在典型服务器硬件上能够在不到一秒的时间内处理数百页的 Project 文件，并且在 Windows、Linux 和 macOS 上均可运行，无需任何额外依赖。

## 前提条件
在开始之前，请确保您具备：

1. **Java Development Kit (JDK) 8 或更高** – API 至少需要 JDK 8。  
2. **Aspose.Tasks for Java** – 从 [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) 下载最新的 JAR。  
3. **IDE** – Eclipse、IntelliJ IDEA 或任何支持 Java 的编辑器。  
4. **可写文件夹** – 用于保存生成的项目文件。

## 导入包
以下类让您能够访问项目属性、文件处理和货币设置。  

`Project` – 表示内存中的 Microsoft Project 文件。  
`Prj` – 包含所有项目级属性的常量，包括货币字段。  
`CurrencySymbolPositionType` – 枚举货币符号的可能位置（在金额之前或之后）。  

在任何代码操作项目之前，都需要这些导入。

## 步骤指南

### 第一步：定义数据目录
选择一个保存源文件并写入输出的文件夹。确保目录存在且您的 Java 进程拥有写权限。

### 第二步：创建新项目实例
`Project` 类是 Aspose.Tasks 的顶层对象，表示内存中的单个 Project 文件。实例化它会创建一个空白项目，准备进行配置。

### 第三步：设置货币属性
在此您可以配置货币代码、小数位数、符号本身以及符号的位置。  

- **Currency code** – a three‑letter ISO 4217 code such as `AUD` or `USD`.  
- **Decimal digits** – typically 2 for most currencies.  
- **Currency symbol** – the character or string displayed with amounts, e.g., `$` or `€`.  
- **Symbol position** – `CurrencySymbolPositionType.Before` places the symbol before the number; `After` places it after.

这些设置会影响项目中所有与成本相关的字段（资源费率、任务预算等）。

> **Pro tip:** 如果需要为已有文件更改货币，请在应用上述设置之前使用 `new Project("file.mpp")` 加载它。

### 第四步：保存更新的项目
使用所需的格式将项目写回磁盘。XML 格式可人类可读，而 `SaveFileFormat.MPP` 则保持与 Microsoft Project 的完整兼容性。

### 第五步：确认成功
打印简短的消息或日志条目，以便您知道操作已成功完成且没有错误。这在自动化流水线中尤为有用。

## 常见问题与解决方案
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` is not a valid path or lacks write permission. | Ensure the directory exists and your Java process has write access. |
| **Currency symbol not showing** | The symbol position is set incorrectly for your locale. | Use `CurrencySymbolPositionType.Before` if the symbol should precede the amount. |
| **Project file does not open in MS Project** | Saving in an older format with incompatible settings. | Save using `SaveFileFormat.MPP` for full compatibility with recent MS Project versions. |

## 常见问答

**Q: 我可以在单个项目中使用 Aspose.Tasks 设置多种货币吗？**  
A: 是的，您可以在定义项目级货币后，通过修改各自的成本字段，为单独的资源或任务分配不同的货币设置。

**Q: Aspose.Tasks 是否兼容不同版本的 Microsoft Project 文件？**  
A: 绝对兼容。该库支持从 Project 2000 到最新版本的 MPP 文件，以及 XML 和其他交换格式。

**Q: Aspose.Tasks 是否提供自定义货币格式的支持？**  
A: 是的，您可以定义自定义符号、小数位数和位置，以满足任何地区需求，这些设置会保存在保存的文件中。

**Q: 我可以将 Aspose.Tasks 与其他 Java 框架集成吗？**  
A: 当然。该 API 纯 Java 实现，可与 Spring、Hibernate、Maven、Gradle 等生态系统无缝配合。

**Q: 我在哪里可以找到更多帮助或示例？**  
A: 访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 获取社区支持，或查阅官方文档获取详细的 API 参考。

## 结论
您现在已经了解**如何在 Aspose.Tasks 项目中使用 Java 更改货币符号**，以及如何设置货币代码、调整小数位数并应用自定义符号。这些功能使您能够生成符合地区特性的成本报告，使项目预算与区域会计标准保持一致，并在全球团队之间保持 Microsoft Project 文件的一致性。

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## 相关教程

- [java project properties – Extract currency symbol from MPP using Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Read Currency Properties Java with Aspose.Tasks Projects](/tasks/java/currency-properties/read-properties/)
- [Manage Currency Codes Java with Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}