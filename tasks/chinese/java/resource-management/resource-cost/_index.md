---
date: 2026-06-15
description: 了解如何使用 Aspose.Tasks for Java 管理 MS Project 文件中的成本，包括如何加载 MPP 文件以及读取 actual
  cost work 和 budgeted cost schedule。
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: 在 Aspose.Tasks 中处理资源成本
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 在 MS Project 中管理成本
url: /zh/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 在 MS Project 中管理成本

## 介绍

管理项目预算是每个项目经理的核心职责，**如何管理成本**的有效性可以决定项目的成败。Aspose.Tasks for Java 为您提供对 Microsoft Project 文件的编程控制，让您无需手动打开 .mpp 文件即可读取和更新资源成本数据。在本教程中，您将逐步了解如何加载 MPP 文件、检查实际成本工作，并提取每个资源的预算成本计划。

## 快速答案
- **Aspose.Tasks for Java 的作用是什么？** 它读取和写入 Microsoft Project 文件 (.mpp)，无需安装 Microsoft Project。  
- **如何加载 MPP 文件？** 使用 `new Project("path/to/file.mpp")` – API 在内存中解析该文件。  
- **有哪些成本字段可用？** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS), and Budgeted Cost of Work Performed (BCWP).  
- **开发是否需要许可证？** A free temporary license works for testing; a full license is required for production.  
- **支持哪些 Java 版本？** Java 8 及更高版本，包括 Java 17 LTS.

## 如何在 MS Project 中管理成本？

使用 `new Project("yourFile.mpp")` 加载项目，然后遍历每个 `Resource` 对象以读取诸如 ACWP、BCWS 和 BCWP 等成本相关属性。Aspose.Tasks 会自动将内部成本值转换为项目的货币，因此您可以直接显示或存储它们。这种方法消除了手动电子表格计算，并确保所有项目报告中的数据一致性。

## 前提条件

1. 对 Java 编程有基本了解。  
2. 将 Aspose.Tasks for Java 库添加到您的项目中（Maven/Gradle 或手动 JAR）。  
3. 访问您想要分析的 Microsoft Project 文件（`.mpp`）。

## 导入包

`Project` 和 `Resource` 类是处理项目数据的入口点。

`Project` 类是 Aspose.Tasks 的顶层对象，表示内存中的单个 Microsoft Project 文件。  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## 步骤 1：定义数据目录

首先，指定包含 `.mpp` 文件的文件夹。此路径可以是绝对路径，也可以是相对于应用程序工作目录的相对路径。

```text
```java
String dataDir = "Your Data Directory";
```
```

## 步骤 2：加载 MS Project 文件

`Project` 加载文件并构建可查询的对象模型。API 在无需安装 Microsoft Project 的情况下解析文件，支持超过 30 种输入格式。

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## 步骤 3：遍历资源

`Resource` 对象代表消耗预算的人员、设备或材料。您可以遍历 `project.getResources()` 集合来访问每个资源。

```text
```java
for (Resource res : prj.getResources()) {
```
```

## 步骤 4：检查资源名称和成本

对于每个资源，先确认名称已定义，然后读取成本字段。`getActualCost()` 方法返回 **实际成本工作** (ACWP)，而 `getBudgetedCost()` 则提供 **预算成本计划** (BCWS/BCWP)。

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## 为什么使用 Aspose.Tasks for Java 加载 MPP 文件？

Aspose.Tasks 支持 **30 多种文件格式**（包括 `.mpp`、`.xml` 和 `.xlsx`），并且能够在使用不到 200 MB RAM 的情况下处理 **多达 10,000 个任务** 的项目。该库在服务器端完成所有计算，消除了对 Microsoft Project 授权副本的需求。

## 常见问题及解决方案

- **资源名称为空**：某些旧文件包含占位资源。访问成本属性前请始终检查 `resource.getName() != null`。  
- **大文件导致内存压力**：LoadOptions 是一个配置类，可让您指定加载哪些项目数据。使用 `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` 仅加载所需数据，必要时再启用。  
- **货币不匹配**：API 遵循项目的货币设置；如有需要，可使用 `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` 覆盖。CostRateTableType 列举了可应用于任务的不同成本费率表。

## 常见问答

**Q: Aspose.Tasks for Java 能处理复杂的项目结构吗？**  
A: 是的，它完全支持嵌套的汇总任务、多资源日历以及所有受支持的 Project 版本中的自定义字段。

**Q: 该库是否兼容不同版本的 Microsoft Project 文件？**  
A: 完全兼容。Aspose.Tasks 能读取和写入从 Microsoft Project 2000 到最新的 2023 格式的文件。

**Q: 我可以将 Aspose.Tasks for Java 与其他 Java 库集成吗？**  
A: 可以，API 返回标准的 Java 对象，能够无缝集成日志框架、ORM 工具或报表库。

**Q: Aspose.Tasks for Java 是否提供客户支持？**  
A: Aspose 为授权用户提供专门的论坛支持、详细文档以及及时的电子邮件帮助。

**Q: 是否有 Aspose.Tasks for Java 的免费试用？**  
A: 您可以从 Aspose 网站下载 30 天的评估许可证，免费体验所有功能。

---

**最后更新：** 2026-06-15  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Tasks 计算成本差异并管理分配成本](/tasks/java/resource-assignments/assignment-cost/)
- [Aspose.Tasks 中任务的预算、工作和成本管理](/tasks/java/task-properties/task-budget-work-cost/)
- [使用 Aspose.Tasks for Java 向项目添加资源](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}