---
date: 2026-10-15
description: 了解如何在 Aspose.Tasks for .NET 中添加自定义属性并管理自定义项目属性，提升项目 metadata 控制能力。
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: 在 Aspose.Tasks 中管理自定义项目属性集合
og_description: 使用 Aspose.Tasks for .NET 将自定义属性添加到项目文件中。本指南展示了如何管理自定义属性、读取属性以及高效地添加布尔或
  string 值。
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: 使用 Aspose.Tasks .NET API 为项目添加自定义属性
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: 如何在 Aspose.Tasks for .NET 中添加自定义属性
url: /zh/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for .NET 中添加自定义属性

## 介绍

添加自定义属性支持让您能够存储项目特定的元数据，这些是内置字段无法覆盖的。在本教程中，您将学习如何**添加自定义属性**、读取它以及使用 Aspose.Tasks for .NET 管理整个自定义属性集合。完成后，您将能够使用布尔、日期时间、双精度和字符串值定制项目文件，以符合业务规则。

## 快速答案
- **我可以添加布尔自定义属性吗？** 是的 – 使用 `CustomPropertyType.Boolean`。
- **支持多少种自定义属性类型？** 四种：Boolean、DateTime、Double、String。
- **自定义属性集合是只读的吗？** 如果项目是从只读源加载的，则可能是只读的。
- **使用此功能需要许可证吗？** 临时许可证可用于评估；生产环境需要完整许可证。
- **兼容哪些 .NET 版本？** .NET Framework 4.5 及以上、.NET Core 3.1 及以上、.NET 5/6/7。

## 什么是自定义属性？

自定义属性是您附加到 Project 对象的用户定义元数据字段。它允许您存储额外信息，例如“风险等级”、 “客户 ID” 或任何标准 MS‑Project 字段未涵盖的布尔标记。

## 为什么在 Aspose.Tasks 中添加自定义属性？

Aspose.Tasks 支持 **50 多种输入和输出格式**，并且能够在不将整个文件加载到内存的情况下处理 **多达 10,000 个任务** 的项目。添加自定义属性可以将业务关键数据直接嵌入项目文件，消除对外部数据库的需求，并确保数据随项目一起传递。

## 前提条件

- 在工作站上安装 Visual Studio（任意近期版本）。  
- Aspose.Tasks for .NET – 从[下载链接](https://releases.aspose.com/tasks/net/)下载。  
- 对 C# 语法和 .NET 项目结构有基本了解。

## 导入命名空间

以下命名空间为您提供对核心项目模型和自定义属性 API 的访问。

```csharp
using Aspose.Tasks;
using System;


```

## 如何在 Aspose.Tasks 中添加自定义属性？

要添加自定义属性，首先加载项目，然后创建 `CustomProperty` 对象，设置其名称、类型和值，最后将其添加到项目的 `CustomProperties` 集合中。此操作将元数据直接嵌入项目文件，并在调用 `project.Save(...)` 时保存更改。  

`CustomProperty` 表示附加到项目的单个用户定义字段。

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### 步骤 1：初始化项目

`Project` 是在 Aspose.Tasks 中表示项目文件的主要类。

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### 步骤 2：检查自定义属性集合的就绪状态

`CustomProperties` 是保存项目所有自定义属性对象的集合。

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### 步骤 3：添加自定义属性

`Add` 方法向项目集合中插入一个新的自定义属性。

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### 步骤 4：访问自定义属性

`CustomProperties` 集合实现了 IEnumerable，允许遍历每个 `CustomProperty`。

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### 步骤 5：检索自定义属性值

`Get` 方法根据名称返回自定义属性的值。

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### 步骤 6：遍历自定义属性名称

`Names` 属性提供集合中所有自定义属性名称的列表。

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### 步骤 7：移除或清除自定义属性

`Remove` 方法删除特定属性，而 `Clear` 则清空整个集合。

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## 常见问题和故障排除

- **只读集合** – 如果 `project.CustomProperties.IsReadOnly` 返回 `true`，请确保源文件未以独占读取方式打开，或在编辑前将其复制到可写位置。  
- **类型不匹配** – 为与声明的 `CustomPropertyType` 不匹配的值赋值会抛出 `ArgumentException`。请在定义正确的 `Type` 后再设置 `Value`。  
- **保存更改** – 添加或删除属性后，调用 `project.Save("output.mpp")` 以持久化修改；否则更改仅保留在内存中。

## 常见问题

**问：我可以使用 Aspose.Tasks for .NET 向我的项目添加任何数据类型的自定义属性吗？**  
答：可以，您可以添加支持 Boolean、DateTime、Double 和 String 类型的自定义属性。

**问：在 Aspose.Tasks for .NET 中可以遍历自定义属性名称吗？**  
答：当然可以，您可以使用 `Names` 属性遍历自定义属性名称。

**问：如何从项目中移除特定的自定义属性？**  
答：您可以使用 `Remove` 方法通过属性名称移除自定义属性。

**问：Aspose.Tasks for .NET 是否支持临时许可证？**  
答：是的，您可以从 Aspose 网站获取用于评估的临时许可证。

**问：在哪里可以找到关于 Aspose.Tasks for .NET 的支持或进一步帮助？**  
答：您可以访问 Aspose.Tasks 论坛 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 获取任何查询或帮助。

---

**最后更新：** 2026-10-15  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Tasks for .NET 读取内置项目属性](/tasks/net/advanced-features/built-in-project-property-collection/)
- [在 Aspose.Tasks 中管理 MS Project 属性集合](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks 自定义字段类型 – 日历和计划](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}