---
title: 使用 Aspose.Tasks 掌握 MS 项目大纲值
linktitle: 在Aspose.Tasks中管理大纲值
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效管理 MS Project 大纲值。轻松定制项目大纲。
type: docs
weight: 16
url: /zh/net/outline-code-page-settings/outline-values/
---
## 介绍
在本教程中，我们将探索如何使用 .NET 的 Aspose.Tasks 库管理 Microsoft Project 大纲值。使用Aspose.Tasks，您可以轻松操作大纲代码，创建新的大纲值，并根据您的要求自定义项目大纲。
## 先决条件
在开始之前，请确保您具备以下条件：
1. 安装 Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET 库[这里](https://releases.aspose.com/tasks/net/).
2. 开发环境：确保您设置了具有 .NET 框架兼容性的开发环境，例如 Visual Studio。
3. 对 C# 编程的基本了解：熟悉 C# 编程语言基础知识，因为我们将使用 C# 来处理 Aspose.Tasks 库。

## 导入命名空间
首先将必要的命名空间导入到您的 C# 代码中：
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 第 1 步：加载项目文件
```csharp
//文档目录的路径。
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
此步骤初始化一个新的 Project 对象并从指定目录加载 Microsoft Project 文件。
## 第 2 步：定义大纲代码定义
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
在这里，我们定义了两个 OutlineCodeDefinition 对象并将它们添加到项目的 OutlineCodes 集合中。
## 第 3 步：定义轮廓蒙版
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
此步骤为大纲代码定义设置 OutlineMask。
## 第 4 步：创建轮廓值
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
在此步骤中，我们创建两个 OutlineValue 对象并设置它们的属性，例如值、值 ID、类型、描述和折叠状态。

## 结论
通过提供的功能，使用 Aspose.Tasks for .NET 管理 MS Project 大纲值非常简单。通过遵循本教程中概述的步骤，您可以高效地操作大纲代码和值，以根据您的需求自定义项目大纲。
## 常见问题解答
### 问：我可以将 Aspose.Tasks 与其他 .NET 框架一起使用吗？
答：是的，Aspose.Tasks 与各种.NET 框架兼容，确保您的开发环境的灵活性。
### 问：Aspose.Tasks 有试用版吗？
答：是的，您可以从以下位置访问 Aspose.Tasks 的免费试用版：[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.Tasks 的支持？
答：如需支持和帮助，您可以访问 Aspose.Tasks 论坛。[这里](https://forum.aspose.com/c/tasks/15).
### 问：我可以购买 Aspose.Tasks 的临时许可证吗？
答：是的，您可以从以下位置购买 Aspose.Tasks 的临时许可证：[这里](https://purchase.aspose.com/temporary-license/).
### 问：在哪里可以找到 Aspose.Tasks 的详细文档？
答：您可以参考可用的综合文档[这里](https://reference.aspose.com/tasks/net/).