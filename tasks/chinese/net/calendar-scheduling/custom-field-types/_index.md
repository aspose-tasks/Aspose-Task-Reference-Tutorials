---
date: 2026-07-19
description: 了解如何在 Aspose.Tasks for .NET 中添加自定义字段类型，包括逐步代码、前置条件和常见问题解答。
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Aspose.Tasks 中的自定义字段类型
og_description: 了解如何在 Aspose.Tasks for .NET 中添加自定义字段类型。遵循此逐步指南，高效创建、定义和使用扩展属性。
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: 如何在 Aspose.Tasks for .NET 中添加自定义字段类型
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: 如何在 Aspose.Tasks for .NET 中添加自定义字段类型
url: /zh/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中添加自定义字段类型

## 介绍

在本教程中，您将了解**如何添加自定义字段**类型，使用 Aspose.Tasks for .NET 将其添加到 Microsoft Project 文件中。自定义字段允许您在任务、资源或项目本身上直接存储额外信息——例如风险评分、部门代码或自定义备注。我们将从环境设置到定义、添加以及验证自定义文本字段，完整演示整个过程。

## 快速答案
- **什么是自定义字段？** 一个用户定义的列，可在任务/资源上保存文本、数字、日期或标记。  
- **哪个类定义自定义字段？** `ExtendedAttributeDefinition`。  
- **我可以向现有项目添加自定义字段吗？** 可以——加载项目，创建定义，然后将其添加到集合中。  
- **我需要 Aspose.Tasks 的许可证吗？** 生产环境需要许可证；免费试用可用于评估。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 在 Aspose.Tasks 中“如何添加自定义字段”是什么？
**如何添加自定义字段**是指创建 `ExtendedAttributeDefinition` 并将其附加到项目的 `ExtendedAttributes` 集合的过程。这使您能够存储不属于标准 Project 架构的额外元数据。它可用于任务、资源或项目本身，帮助捕获如风险等级、部门代码或默认字段中不存在的自定义备注等信息。

## 为什么在项目管理中使用自定义字段？
Aspose.Tasks 支持 **50+ 内置的扩展属性类型**，并允许您定义 **任意数量的自定义字段**，且对文件大小影响不大。使用自定义字段您可以：  
这些字段在 Microsoft Project 中显示为额外列，可在公式、报告和筛选器中引用。它们存储在项目文件内部并随文件一起传递，确保下游工具保留这些自定义数据。

## 前提条件

### 1. 已安装 Visual Studio
确保您的机器上已安装 Visual Studio（2019 或更高版本）。您可以从 Microsoft 官网下载。

### 2. Aspose.Tasks for .NET
将 Aspose.Tasks NuGet 包添加到您的项目中。请从[此处](https://releases.aspose.com/tasks/net/)下载最新版本。

### 3. 基础 C# 知识
您应熟悉 C# 语法、类以及 .NET 项目结构。

## 导入命名空间

`Project`、`ExtendedAttributeDefinition` 以及相关枚举位于 `Aspose.Tasks` 命名空间。请在文件顶部导入它：

`Aspose.Tasks` 命名空间提供处理 Microsoft Project 文件所需的所有核心类型。

```csharp

```

## 如何向项目添加自定义字段？

加载现有项目，创建自定义字段定义，并将其添加到项目的扩展属性集合——全部通过三步简洁完成。此模式适用于任务、资源和项目本身，并确保在保存文件时自定义字段得以持久化。

### 步骤 1：创建 Project 对象
`Project` 是 Aspose.Tasks 的顶层对象，表示内存中的单个 Project 文件。实例化它会加载文件，并让您访问任务、资源和扩展属性。

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### 步骤 2：定义自定义字段
`ExtendedAttributeDefinition` 描述一个新列。在本示例中，我们为任务创建一个 **Text** 类型的自定义字段，并将其别名设为 “MyText”。`ExtendedAttributeTask.Text1` 枚举值指示 Aspose.Tasks 将值存储在何处。

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### 步骤 3：将自定义字段定义添加到项目
项目的 `ExtendedAttributes` 集合保存所有自定义字段定义。将定义添加进去后，项目中的每个任务都可以使用该字段。

```csharp
project.ExtendedAttributes.Add(definition);
```

## 常见问题及解决方案
- **字段未在 MS Project UI 中显示** – 确保已设置 `Alias` 属性；MS Project 会将别名显示为列标题。  
- **保存时抛出异常** – 检查项目文件是否为只读，并确认您拥有有效的许可证。  
- **重新加载后自定义字段值丢失** – 确保在为任务分配值后调用 `project.Save("output.mpp")`。

## 常见问答

**问：我可以在其他 .NET 框架中使用 Aspose.Tasks 吗？**  
答：可以，Aspose.Tasks 支持 .NET Framework、.NET Core 和 .NET 5/6/7。

**问：Aspose.Tasks 适合企业级应用吗？**  
答：当然。它支持处理包含 **多达 10,000 个任务** 的项目，并可在多线程服务器环境中运行。

**问：Aspose.Tasks 支持多种项目文件格式吗？**  
答：是的——Aspose.Tasks 能读取和写入 MPP、XML、HTML 和 CSV 格式，覆盖 **所有主要的 Microsoft Project 版本**。

**问：我可以使用 Aspose.Tasks 操作资源数据吗？**  
答：可以，您可以添加、更新、删除资源，并为其分配自定义字段。

**问：是否有 Aspose.Tasks 用户社区论坛？**  
答：有，您可以访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 与其他用户交流并获取 Aspose 团队的支持。

---

**最后更新：** 2026-07-19  
**测试环境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [掌握 Aspose.Tasks 中的 MS Project 扩展属性定义](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [使用 Aspose.Tasks 操作 MS Project 扩展属性](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Aspose.Tasks 中的字段助手与 MS Project 集成](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}