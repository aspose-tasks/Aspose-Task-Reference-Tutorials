---
date: 2026-06-15
description: 了解如何使用 Aspose.Tasks for Java 从 MS Project 资源中提取时间相位数据。逐步指南，按 ID 获取资源。
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: 读取 Aspose.Tasks 中资源的时间相位数据
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 读取 Aspose.Tasks 中资源的时间相位数据 – 按 ID 获取资源
url: /zh/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 读取 Aspose.Tasks 中资源的时间相位数据

## 简介
在本教程中，您将学习 **how to get resource by id** 并使用 Aspose.Tasks for Java 读取其时间相位数据。我们将逐步演示每个步骤——从设置项目文件夹到打印工作和成本的时间相位值——帮助您以编程方式从任何 Microsoft Project 文件中提取有价值的调度信息。Aspose.Tasks for Java 是一个全面的 API，使开发人员能够创建、读取、修改和转换 Microsoft Project 文件，而无需安装 Microsoft Project，支持广泛的项目管理功能和格式。

## 快速答案
- **“get resource by id” 是做什么的？** 它使用唯一标识符从 `Project` 中检索特定的 `Resource` 对象。  
- **哪个库处理时间相位数据？** Aspose.Tasks for Java 提供 `Resource.getTimephasedData` API。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **我可以读取大型项目吗？** 是的——Aspose.Tasks 能够处理包含多达 10,000 个任务的文件，而无需将整个文件加载到内存中。  
- **需要哪个 Java 版本？** Java 8 或更高版本；该库兼容所有主流 JDK。

## 什么是 “get resource by id”？
`get resource by id` 是一种方法调用，它使用资源的数字 ID 从已加载的 `Project` 中获取 `Resource` 实例。此操作可精确访问资源的详细属性，如其分配、日历和自定义字段，对于提取与该特定资源关联的时间相位工作或成本数据至关重要。

## 为什么使用 Aspose.Tasks 处理时间相位数据？
Aspose.Tasks 支持 **50+ 输入和输出格式**（MPP、XML、CSV 等），并且能够提取跨多年计划的资源的时间相位工作和成本值，同时保持低内存使用。该 API 默认以 15 分钟间隔返回数据，为报告或自定义分析提供细粒度洞察。

## 先决条件
在开始之前，请确保您具备以下先决条件：
1. Java Development Kit (JDK)：确保系统已安装 JDK。您可以从 [网站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下载并按照安装说明进行操作。  
2. Aspose.Tasks for Java 库：从 [下载页面](https://releases.aspose.com/tasks/java/) 下载 Aspose.Tasks for Java 库，并按照文档中提供的安装说明进行操作。

## 导入包
第一步是将所需的 Aspose.Tasks 类导入到您的 Java 源文件中。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## 步骤 1：设置数据目录
首先，定义存放 MS Project 文件的目录。将数据文件夹与源代码分离可使项目更易于维护。

```java
String dataDir = "Your Data Directory";
```

## 步骤 2：读取 MS Project 模板文件
指定您的 MS Project 模板文件的名称。使用模板可确保不同项目之间列设置的一致性。

```java
String fileName = "ResourceTimephasedData.mpp";
```

## 步骤 3：将输入文件读取为 Project
`Project` 类是 Aspose.Tasks 的核心对象，表示内存中的 Microsoft Project 文件。加载文件后，您即可以编程方式访问任务、资源和进度表。

```java
Project project = new Project(dataDir + fileName);
```

## 步骤 4：按 ID 获取资源
要检索特定资源，请调用 `getResources().getById(id)` 方法。这正是主关键字所引用的操作。

```java
Resource resource = project.getResources().getByUid(1);
```

## 步骤 5：打印资源工作时间相位数据
获取 `Resource` 对象后，您可以调用 `resource.getTimephasedData(ResourceTimephasedDataType.Work)` 来获取随时间变化的工作分配。返回的集合包含 `TimephasedData` 对象，其中包括每个间隔的开始日期、结束日期以及工作量。

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## 步骤 6：打印资源成本时间相位数据
同样，`resource.getTimephasedData(ResourceTimephasedDataType.Cost)` 返回按相同时间间隔划分的成本信息。这对于预算和成本跟踪报告非常有用。

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 如何在一行代码中获取资源 ID？
加载项目后，调用 `project.getResources().getById(5)`——将 **5** 替换为实际需要的资源 ID。此单次调用返回 `Resource` 对象，随后您可以查询其时间相位数据、分配或自定义字段。该方法的时间复杂度为 O(1)，因为资源在内部已建立索引。

## 常见问题及解决方案
- **未找到资源** – 确保该 ID 在项目文件中存在；ID 从 1 开始，并且每个资源唯一。  
- **时间相位数据为空** – 确认该资源具有工作或成本分配；否则集合将为空。  
- **大文件性能** – 使用 `Project.setLoadOptions(LoadOptions.fromFile(...))` 为大于 500 MB 的项目启用惰性加载，以提升性能。

## 常见问题
**Q: Aspose.Tasks 能处理除 Microsoft Project 之外的其他类型项目文件吗？**  
A: 可以，Aspose.Tasks 支持 MPP、XML、CSV 等多种格式，能够在不同标准之间进行读取和写入。

**Q: Aspose.Tasks 与不同的 Java 开发环境兼容吗？**  
A: 当然。该库兼容所有主流 IDE（IntelliJ IDEA、Eclipse、NetBeans）和构建工具（Maven、Gradle）。

**Q: 我可以使用 Aspose.Tasks 操作项目数据吗？**  
A: 可以，您可以通过 API 创建、修改、删除任务、资源、分配，甚至自定义字段。

**Q: Aspose.Tasks 适用于企业级项目吗？**  
A: 是的。企业依赖 Aspose.Tasks 进行大批量处理、批量转换和服务器端报告，因为它无需安装 Microsoft Project。

**Q: 使用 Aspose.Tasks 时遇到问题，我可以在哪里获得支持？**  
A: 您可以访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取社区和支持团队的帮助。

## 结论
在本教程中，我们学习了如何 **get resource by id** 并使用 Aspose.Tasks for Java 读取其时间相位工作和成本数据。按照这些步骤，您可以高效地从项目文件中提取有价值的调度信息，并将其集成到自定义报告或分析流程中。

---

**最后更新：** 2026-06-15  
**测试版本：** Aspose.Tasks 24.11 for Java  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Tasks for Java 向项目添加资源](/tasks/java/resource-management/create-resources/)
- [使用 Aspose.Tasks for Java 管理 MS Project 资源成本](/tasks/java/resource-management/resource-cost/)
- [使用 Aspose.Tasks 从 MS Project 日历读取工作周（Java）](/tasks/java/calendars/read-work-weeks/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}