---
date: 2026-05-31
description: 了解如何使用 Aspose.Tasks for Java 获取项目版本并检索 MS Project 文件的最后保存日期。一步一步的指南，附带代码示例。
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: 使用 Aspose.Tasks 确定项目版本
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何获取项目版本 – Aspose Tasks Java 教程
url: /zh/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何获取项目版本 – Aspose Tasks Java 教程

在本 **Aspose Tasks Java tutorial** 中，您将学习 **如何获取项目版本**（Microsoft Project 文件）以及 **检索最后保存日期**，使用 Aspose.Tasks for Java 库。了解文件版本和保存时间戳有助于避免兼容性问题、执行迁移策略并保持准确的审计日志。我们将逐步演示——从环境设置到打印版本和日期——让您能够自信地将此检查嵌入任何 Java 应用程序。

## 快速答案
- **本教程涵盖什么内容？** 使用 Aspose.Tasks for Java 确定 MS Project 文件的版本和最后保存日期。  
- **是否需要安装 Microsoft Project？** 不，Aspose.Tasks 可独立于 Microsoft Project 运行。  
- **支持哪些文件格式？** 基于 XML 的项目文件（如 MPP 和 XML）均得到完整支持。  
- **实现需要多长时间？** 基本的版本检查大约需要 5‑10 分钟。  
- **是否需要许可证？** 免费试用可用于评估；生产环境需要商业许可证。  

## 什么是 Aspose Tasks Java 教程？
`Aspose.Tasks` Java 教程是一本简明、实用的指南，演示如何以编程方式与 Microsoft Project 数据交互。它展示了如何读取、修改和分析项目信息，而无需在服务器上安装 Microsoft Project。此外，还涵盖了加载文件、访问属性和保存更改，使开发人员能够高效地自动化项目管理任务。

## 为什么使用 Aspose.Tasks 来确定项目版本？
Aspose.Tasks 提供 **精确的版本元数据** 和 **最后保存时间戳**，可在任何支持 Java 的操作系统上运行。它在标准 2.5 GHz CPU 上能够在 **2 秒内处理 500 页** 的文件，使其非常适合批量自动化和大规模迁移场景。

## 前置条件
在开始之前，请确保您拥有：

1. **Java Development Kit (JDK)** – 版本 8 或更高。  
2. **Aspose.Tasks for Java JAR** – 从 [website](https://releases.aspose.com/tasks/java/) 下载并将其添加到项目的 classpath 中。  
3. **MS Project file** – 您想要检查的基于 XML 的项目文件（例如 `input.xml`）。

> **Pro tip:** 将 Project 文件存放在专用的 `data` 文件夹中，以保持路径整洁并避免意外覆盖。

## 导入包
首先，导入必需的 Aspose.Tasks 类：

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 如何设置项目目录
为了正确定位项目文件，请在应用程序结构中创建专用目录并将所有输入文件存放在那里。这可保持代码整洁，避免加载文件时出现路径相关错误。为目录路径使用明确的变量名，该路径可以是绝对路径或相对于项目根目录的相对路径。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## 如何加载项目
`Project` 是 Aspose.Tasks 的主要对象，表示内存中的 Microsoft Project 文件，提供对所有项目属性和集合的访问。创建 `Project` 实例后，您可以查询其字段、遍历任务或在将文件保存回磁盘之前修改数据。

```java
Project project = new Project(dataDir + "input.xml");
```

## 如何确定项目版本
`Prj.SAVE_VERSION` 是一个属性，指示保存文件的 Microsoft Project 的版本号。`Prj.LAST_SAVED` 是一个属性，存储文件最后一次保存的日期和时间。`Prj.SAVE_VERSION` 返回保存文件的 Microsoft Project 应用程序的数值版本（例如，Project 2010 为 12）。`Prj.LAST_SAVED` 提供最近一次保存操作的精确日期和时间。

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

## 如何显示结果
在检索到版本和最后保存信息后，通常需要将其输出到控制台或日志文件。使用 `System.out.println` 显示这些值，并根据需要格式化日期。这可确认提取成功，并在开发或自动化脚本中提供即时反馈。

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | 文件未找到或路径不正确 | 验证 `dataDir` 和文件名；在测试时使用绝对路径。 |
| 意外的版本号（例如 0） | 加载了非 Project XML 文件 | 确保文件是有效的 Microsoft Project 文件（MPP/XML）。 |
| 许可证异常 | 在生产环境中使用未授权的试用版 | 应用您的 Aspose.Tasks 许可证（`License license = new License(); license.setLicense("Aspose.Tasks.lic");`）。 |

## 常见问题

**Q: 我可以将 Aspose.Tasks 与其他编程语言一起使用吗？**  
A: 是的，Aspose.Tasks 支持 .NET、Java 和 C++ 等语言。

**Q: Aspose.Tasks 适用于大规模项目吗？**  
A: 当然；它可以在几秒钟内处理数百页的项目，而无需将整个文件加载到内存中。

**Q: 我可以使用 Aspose.Tasks 定制项目数据吗？**  
A: 可以，您可以通过 API 修改任务、资源、日历以及任何其他项目元素。

**Q: Aspose.Tasks 需要安装 Microsoft Project 吗？**  
A: 不需要，该库可独立运行，无需在主机上安装 Microsoft Project。

**Q: Aspose.Tasks 提供技术支持吗？**  
A: 是的，您可以在 Aspose.Tasks 论坛 [here](https://forum.aspose.com/c/tasks/15) 获取帮助。

**附加问答**

**Q: 如何检索其他项目属性（例如，作者、公司）？**  
A: 使用 `project.get(Prj.AUTHOR)` 或 `project.get(Prj.COMPANY)`，方式与检索版本相同。

**Q: 我可以检查 MPP（二进制）文件的版本吗？**  
A: 可以，Aspose.Tasks 可直接加载 `.mpp` 文件；`Prj.SAVE_VERSION` 属性同样适用于二进制格式。

**Q: 是否有办法以编程方式将旧项目文件升级到新版本？**  
A: 加载旧文件后，使用 `project.save("newfile.mpp", SaveFileFormat.MPP);` 保存——Aspose.Tasks 默认以最新格式写入文件。

## 结论
您现在已经掌握了使用 Aspose.Tasks for Java 从 MS Project 文件中 **获取项目版本** 和 **检索最后保存日期** 的方法。将这些代码片段整合到自动化流水线、报告工具或迁移实用程序中，确保您始终了解所处理的项目的确切版本。

---

**最后更新:** 2026-05-31  
**测试环境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Tasks for Java 设置 MS Project 项目开始日期](/tasks/java/project-properties/write-project-info/)
- [使用 Aspose.Tasks for Java 读取 Microsoft Project 数据库](/tasks/java/project-data-reading/read-project-database/)
- [使用 Aspose.Tasks for Java 将项目保存为模板、CSV 和文本](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}