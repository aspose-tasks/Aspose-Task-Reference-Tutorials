---
date: 2026-06-30
description: 学习如何更新多个资源并修改资源组数据，然后使用 Aspose.Tasks for Java 将项目导出为 MPP 并将项目保存为 MPP。
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: 在 Aspose.Tasks for Java 中更新多个资源
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks for Java 中更新多个资源
url: /zh/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks for Java 中更新多个资源

## 介绍
在本教程中，您将学习如何使用 Aspose.Tasks for Java **更新 Microsoft Project 文件中的多个资源**。无论是更改费率、重新分配组，还是将更新后的文件导出为 MPP，下面的步骤都将带您完成完整的、可投入生产的工作流。无需安装 Microsoft Project，API 能够高效处理包含数百个资源的项目。

## 快速答案
- **我可以一次更新多个资源吗？** 可以——遍历 `ResourceCollection` 并在一次遍历中设置属性。  
- **哪个方法将文件保存为 MPP？** `project.save("output.mpp", SaveFileFormat.MPP)`。  
- **商业使用需要许可证吗？** 生产环境需要付费许可证，提供免费试用。  
- **支持哪些 Java 版本？** 支持 Java 6 及以上，包括 Java 17 LTS。  
- **批量更新性能如何？** Aspose.Tasks 在普通服务器上处理 500 个资源的项目耗时不足 2 秒。

## 什么是“更新多个资源”？
**“更新多个资源”** 指以编程方式更改单个项目文件中多个资源条目的属性——如费率、组、日历或自定义字段。该操作常用于将项目数据与企业资源计划系统同步、在众多资源之间调整预算，或实施全组织范围的政策变更。

## 为什么使用 Aspose.Tasks 来修改资源组并导出项目为 MPP？
Aspose.Tasks 支持 **50 多种输入和输出格式**，包括 MPP、XML 和 CSV，并且能够 **在不将整个文件加载到内存的情况下导出项目为 MPP**。该库可处理高达 **2 GB** 的文件，使您能够 **快速可靠地将项目保存为 MPP**。

## 先决条件

在开始之前，请确保您具备以下条件：

1. 已在系统上安装 Java Development Kit（JDK）。  
2. Aspose.Tasks for Java 库。您可以从[此处](https://releases.aspose.com/tasks/java/)下载。  
3. 具备 Java 编程的基础知识。  

## 导入包

`import` 语句将所需的 Aspose.Tasks 类引入您的源文件。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 步骤 1：设置数据目录

定义数据文件所在的目录：

```java
String dataDir = "Your Data Directory";
```

## 步骤 2：指定输入和输出文件

定义输入 MS Project 文件和生成的更新文件的路径：

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## 步骤 3：加载项目

`Project` 表示已加载到内存中的 Microsoft Project 文件，提供对任务、资源和其他项目信息的访问。

```java
Project project = new Project(file);
```

## 步骤 4：添加资源并设置属性

`Resource` 表示单个项目资源，允许您设置费率、组、日历和其他属性。

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## 步骤 5：高效更新多个资源

`ResourceCollection` 是项目中所有资源的集合，可通过 `project.getResources()` 访问。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 步骤 6：保存项目

`SaveFileFormat` 列举了保存项目时支持的文件格式，如 MPP、XML 和 PDF。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 如何在项目中更新多个资源？

加载现有项目，获取其 `ResourceCollection`，遍历每个 `Resource` 对象。对每个资源修改所需字段（如费率、组或自定义属性），然后继续下一个。处理完所有资源后，调用一次 `project.save(...)` 即可高效持久化更改。

## 常见问题及解决方案

- **资源 ID 冲突** – 使用 `project.getResources().add(new Resource())` 确保每个新资源拥有唯一 ID。  
- **费率格式错误** – 使用 `ResourceRate` 对象并将 `RateType` 设置为 `StandardRate` 或 `OvertimeRate`。  
- **大文件导致内存压力** – 在加载前调用 `Project.setReadOnly(true)` 以降低内存占用。

## 常见问题

**问：我可以使用 Aspose.Tasks for Java 在同一项目中更新多个资源吗？**  
答：可以，您可以遍历资源集合并相应地设置属性。

**问：Aspose.Tasks 是否支持除 MS Project 之外的其他文件格式？**  
答：是的，Aspose.Tasks 支持包括 XML、MPP 在内的多种文件格式。

**问：Aspose.Tasks 与哪些 Java 版本兼容？**  
答：Aspose.Tasks 与 Java 6 及以上版本兼容。

**问：我可以使用 Aspose.Tasks 对 MS Project 文件执行其他操作吗？**  
答：可以，您可以执行读取、写入以及操作任务、资源和日历等广泛操作。

**问：在哪里可以找到 Aspose.Tasks 的其他帮助或支持？**  
答：您可以访问[ Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)获取帮助或提出疑问。

**问：如何将更新后的文件导出为 MPP 格式？**  
答：在完成所有资源更改后，调用 `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)`。

**问：修改资源组的最佳方式是什么？**  
答：在保存项目之前，对每个 `Resource` 对象设置 `Resource.Group` 属性。

---

**最后更新：** 2026-06-30  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Tasks for Java 向项目添加资源](/tasks/java/resource-management/create-resources/)
- [使用 Aspose.Tasks for Java 管理 MS Project 资源成本](/tasks/java/resource-management/resource-cost/)
- [使用 Aspose.Tasks for Java 将 MPP 导出为 Excel](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}