---
date: 2026-09-25
description: 了解如何使用 Aspose.Tasks for Java 从 MS Project 文件中检索货币代码——为 Java 开发者提供快速获取货币代码的方法。
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: 在 Aspose.Tasks 中管理货币代码
og_description: 使用 Aspose.Tasks 从 MS Project 文件中检索 Java 货币代码。本指南展示了如何读取项目、提取 ISO 货币标识符，并在
  Java 应用程序中使用它。
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: 从 MS Project 检索 Java 货币代码
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: 使用 Aspose.Tasks 从 MS Project 检索 Java 货币代码
url: /zh/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 从 MS Project 检索货币代码（Java）

## 介绍
在本教程中，您将学习 **如何检索货币代码（Java）**，通过使用 Aspose.Tasks Java API 从 MS Project 文件中获取。无论您是需要生成多币种财务报告、在不同地区合并项目，还是仅在下游系统中显示正确的货币符号，下面的步骤都将帮助您从环境设置一直到返回 ISO 货币标识符的单行调用。完成本指南后，您将能够轻松加载任何受支持的 Project 文件格式，并提取诸如 `USD`、`EUR` 或 `GBP` 等三字母货币代码。

## 快速答案
- **API 的作用是什么？** 它读取 MS Project 文件并公开诸如货币代码等属性。  
- **使用的语言是什么？** Java，通过 Aspose.Tasks for Java 库。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **我可以一行代码检索代码吗？** 可以——`prj.get(Prj.CURRENCY_CODE)` 会立即返回货币代码字符串。  
- **它兼容所有 Project 版本吗？** Aspose.Tasks 支持超过 20 种输入格式，包括旧版 MPP、XML 和 XER 文件。

## 什么是读取 MS Project 文件？
读取 MS Project 文件意味着以编程方式打开 *.mpp*（或任何其他受支持的格式，如 XML 或 XER）并访问其内部数据结构。这些结构包括任务、资源、日历、费用表和财务设置。通过解析文件，您可以在不启动 Microsoft Project 的情况下提取信息，从而实现自动化报告、迁移和集成工作流。

## 为什么使用 Aspose.Tasks 读取 msproject 文件？
Aspose.Tasks 提供纯 Java 解决方案，消除对 COM 互操作或本地 Microsoft Project 安装的需求。它支持超过 20 种文件格式，能够在使用不到 100 MB 内存的情况下处理包含数千个任务的项目，并提供丰富的对象模型。直接访问诸如 `Prj.CURRENCY_CODE` 的常量，可让您即时且可靠地检索货币信息。

## 前提条件
在深入代码之前，请确保具备以下条件：

### 已安装 Java 开发工具包 (JDK)
需要最近的 JDK（11 或更高版本）。请从官方 Oracle 网站下载：[这里](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)。

### Aspose.Tasks for Java 库
获取最新的 Aspose.Tasks for Java 二进制文件并将其添加到项目的类路径中。完整文档和下载链接可在[这里](https://reference.aspose.com/tasks/java/)获取。

## 导入包
`Project` 类和 `Prj` 常量位于 `com.aspose.tasks` 命名空间。请在 Java 源文件顶部导入它们：

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 步骤指南

### 步骤 1：设置数据目录
定义包含 *.mpp* 文件的文件夹。调整路径以匹配您的环境，使运行时能够定位项目文件。

```java
String dataDir = "Your Data Directory";
```

### 步骤 2：加载项目文件
`Project` 类是 Aspose.Tasks 的顶层对象，表示内存中的单个 MS Project 文件。创建实例会读取文件并构建可查询的内存模型。

```java
Project prj = new Project(dataDir + "project.mpp");
```

### 步骤 3：检索货币代码
`Prj.CURRENCY_CODE` 常量标识存储 ISO 货币标识符的属性。调用 `prj.get(Prj.CURRENCY_CODE)` 会在一次操作中返回三字母代码。

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
输出将是项目配置使用的三字母 ISO 货币代码（例如 `USD`、`EUR`、`GBP`）。

### 步骤 4：在 Java 中检索货币代码（附加说明）
加载项目，调用 `prj.get(Prj.CURRENCY_CODE)`，并将结果存入 `String`。随后您可以将该值传递给任何需要货币标识符的金融服务、报告引擎或 UI 组件。

### 步骤 5：（可选）使用货币代码
典型的下游场景包括：

- **报告生成** – 在成本列前加上代码（`USD 1,200`）。  
- **API 集成** – 将 ISO 代码发送给需要货币参数的支付网关。  
- **数据合并** – 按货币对多个项目进行分组，以进行组合层面的分析。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **空输出** | 项目文件未定义货币（默认为空）。 | 在 Microsoft Project 中设置货币，或在读取前通过 `prj.set(Prj.CURRENCY_CODE, "USD");` 进行赋值。 |
| **文件未找到** | `dataDir` 路径不正确。 | 检查路径并确保文件名完全匹配，包括大小写。 |
| **不支持的文件版本** | 非常旧或损坏的 *.mpp* 文件。 | 升级到最新的 Aspose.Tasks 版本，或先在 Microsoft Project 中将文件转换为更新的格式。 |

## 常见问题

**Q: Aspose.Tasks 能处理复杂的项目结构吗？**  
A: 是的，API 可以读取多层任务层次结构、资源池、自定义字段和日历，且没有限制。

**Q: Aspose.Tasks 与不同版本的 MS Project 文件兼容吗？**  
A: 绝对兼容。它支持从 Project 98 到最新 Office 版本的 MPP、XML、XER 等格式。

**Q: Aspose.Tasks 提供文档和支持吗？**  
A: 完整的 API 参考、代码示例以及专门的技术支持均可在 Aspose 网站上获取。

**Q: 我可以在购买前试用 Aspose.Tasks 吗？**  
A: 提供免费试用，您可以评估所有功能，包括货币代码提取。

**Q: 临时许可证可在[网站](https://purchase.aspose.com/temporary-license/)获取。**  

---

**最后更新：** 2026-09-25  
**测试环境：** Aspose.Tasks for Java（最新版本）  
**作者：** Aspose

## 相关教程

- [Project Properties Java – 使用 Aspose.Tasks 读取元数据](/tasks/java/project-properties/)
- [如何使用 Aspose.Tasks for Java 从 Microsoft Project 读取项目信息](/tasks/java/project-properties/read-project-info/)
- [在 Aspose.Tasks 中检索 MS Project 大纲代码](/tasks/java/project-file-operations/retrieve-outline-codes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}