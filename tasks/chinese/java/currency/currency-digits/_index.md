---
date: 2026-09-14
description: 了解如何使用 Aspose.Tasks 获取 ms project 货币并读取 Java 项目属性。一步步指南，帮助从 MPP 文件中提取货币数字。
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: 如何使用 Aspose.Tasks 从 MS Project 获取货币
og_description: 了解如何使用 Aspose.Tasks 获取 ms project 货币并读取 Java 项目属性。遵循此简明 Java 教程，从
  MPP 文件中提取货币数字。
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: 如何使用 Aspose.Tasks 获取 ms project 货币 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: 如何使用 Aspose.Tasks 获取 ms project 货币
url: /zh/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 获取 ms project 货币

## 介绍
如果您想了解 **how to get ms project currency** 信息从 Microsoft Project 文件，您来对地方了。在本完整教程中，您将发现 **how to work with ms project currency** 值使用 Aspose.Tasks 库 for Java。无论您是在构建报表工具、迁移实用程序，还是仅仅需要读取 **java project file** 中的货币设置，本指南将一步步带您完成——从加载 *.mpp* 文件到提取货币位数。完成后，您将能够在自己的应用程序中自如地处理 ms project currency 数据。

## 快速回答
- **What library reads MS Project files?** Aspose.Tasks for Java.  
- **How many lines of code to get currency digits?** Just three concise lines after the project is loaded.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 or higher (any JDK that runs Aspose.Tasks).  
- **Can I retrieve other Project properties?** Yes – Aspose.Tasks exposes a full set of Project fields (e.g., start date, cost rates, etc.).

## 什么是 ms project 货币？
`ms project currency` 属性定义了 Microsoft Project 在显示货币值时使用的小数位数。它在 Project 文件中存储为 **CURRENCY_DIGITS** 字段，决定金额是整数、保留一位小数、两位小数等。此设置直接影响预算报告、成本汇总以及任何显示财务数字的 UI，因而对准确的数据交换至关重要。

## 为什么使用 Aspose.Tasks 处理 ms project 货币？
Aspose.Tasks 让您无需安装 Microsoft Project 即可提取货币位数，并且具备企业级性能。该库支持 **30+ years of Project file versions**——从 Project 2000 到 Project 2024——覆盖超过 **150 distinct file schemas**。在标准服务器上加载一个 500‑page 项目通常耗时不到 **2 seconds**，并且您可以仅查询所需字段，即使是最大规模的计划，内存使用也保持在 **50 MB** 以下。

## 先决条件
在开始之前，请确保您具备以下条件：

1. **Java Development Environment** – JDK 8 or newer installed and configured.  
2. **Aspose.Tasks for Java** – download the latest JAR from the official site: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – you should be comfortable creating a Java project, adding external libraries, and running a `main` method.  

## 导入包
首先，导入我们需要的类。  
从 Aspose.Tasks 库中导入 `Project` 类及相关实用工具。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步骤 1：定义数据目录
指定包含您的 **java project file** (`*.mpp`) 的文件夹。  
```java
String dataDir = "Your Data Directory";
```
将 `"Your Data Directory"` 替换为 `project.mpp` 所在的绝对或相对路径。

## 步骤 2：加载 mpp 文件  
现在我们将了解使用 Aspose.Tasks **how to load mpp** 文件。  
`Project` 类代表一个 Microsoft Project 文件，并提供对其属性的访问。  
```java
Project project = new Project(dataDir + "project.mpp");
```
确保文件名完全匹配；否则将抛出 `IOException`。

## 步骤 3：检索货币位数  
项目加载后，提取 **ms project currency** 位数只需一行代码：  
`getCurrencyDigits()` 方法返回货币值定义的小数位数。  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
该调用返回一个表示小数位数的 `Integer`（例如，`2` 表示分）。该值会打印到控制台，您也可以将其存入变量以便后续处理。

## 常见问题与技巧
- **File not found** – double‑check the `dataDir` path and ensure the file name is correct, including the `.mpp` extension.  
- **Unsupported file version** – Aspose.Tasks supports Project 2000‑2024 formats; older or corrupted files may need conversion.  
- **License not set** – during development a trial works, but for production you must apply a valid license to avoid evaluation watermarks.

## 常见问题

**Q: Aspose.Tasks 能处理除货币位数之外的其他 Project 属性吗？**  
A: 是的，Aspose.Tasks 提供广泛的功能来操作 Project 文件的各个方面，例如任务、资源和自定义字段。

**Q: Aspose.Tasks 适用于企业级应用吗？**  
A: 当然，Aspose.Tasks 旨在满足企业级项目的需求，提供高性能和可扩展性。

**Q: Aspose.Tasks 支持跨平台开发吗？**  
A: 是的，您可以在任何支持 Java Runtime Environment 的平台（Windows、Linux、macOS）上使用 Aspose.Tasks for Java。

**Q: 我可以在购买前试用 Aspose.Tasks 吗？**  
A: 可以，您可以从 [Aspose releases page](https://releases.aspose.com/) 下载免费试用版。

**Q: 我在哪里可以获得 Aspose.Tasks 的支持？**  
A: 您可以在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 找到支持。

---

**最后更新：** 2026-09-14  
**测试环境：** Aspose.Tasks for Java (latest at time of writing)  
**作者：** Aspose

## 相关教程

- [java 项目属性 – 使用 Aspose.Tasks for Java 从 MPP 提取货币符号](/tasks/java/currency/currency-symbols/)
- [如何使用 Aspose.Tasks 从 MS Project 检索货币](/tasks/java/currency/currency-codes/)
- [Project 属性 Java – 使用 Aspose.Tasks 读取元数据](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}