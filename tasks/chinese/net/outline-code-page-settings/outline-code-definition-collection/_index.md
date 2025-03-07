---
title: Aspose.Tasks .NET 中大纲代码定义的集合
linktitle: Aspose.Tasks 中大纲代码定义的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 操作 Microsoft Project 文档中的大纲代码定义。轻松对项目数据进行分类。
weight: 13
url: /zh/net/outline-code-page-settings/outline-code-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks .NET 中大纲代码定义的集合

## 介绍
Aspose.Tasks 是一个功能强大的.NET 库，旨在轻松高效地操作 Microsoft Project 文档。其主要功能之一是能够使用大纲代码定义，允许用户有效地组织和分类项目数据。在本教程中，我们将探索如何使用 Aspose.Tasks for .NET 处理大纲代码定义。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下条件：
1. 对 C# 的基本了解：熟悉 C# 编程语言将会很有帮助。
2. Visual Studio：安装 Visual Studio 或任何其他首选的 C# 开发环境。
3.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks for .NET 库[这里](https://releases.aspose.com/tasks/net/).

## 导入命名空间
首先，请确保导入必要的命名空间：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 第 1 步：加载 Microsoft Project 文档
首先，加载 Microsoft Project 文档以开始使用大纲代码定义：
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## 第 2 步：访问大纲代码定义
现在，让我们访问项目中的大纲代码定义：
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## 步骤 3：添加自定义大纲代码定义
您可以添加自定义大纲代码定义，如下所示：
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## 步骤 4：修改大纲代码定义
轻松修改现有大纲代码定义：
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## 步骤 5：删除大纲代码定义
当不再需要时删除大纲代码定义：
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## 第 6 步：保存更改
最后，保存对项目文档的更改：
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## 结论
总之，Aspose.Tasks for .NET 提供了管理 Microsoft Project 文档中大纲代码定义的全面功能。通过遵循本教程中概述的步骤，您可以有效地操作大纲代码定义，以有效地组织和分类项目数据。
## 常见问题解答
### 问：我可以在一个项目中添加多个大纲代码定义吗？
答：是的，您可以根据需要在项目中添加多个大纲代码定义。只需使用`Add`您想要包含的每个定义的方法。
### 问：是否可以一次性从项目中删除所有大纲代码定义？
答：是的，您可以使用以下命令清除项目中的所有大纲代码定义：`Clear`方法。
### 问：如果我尝试修改只读大纲代码定义，会发生什么情况？
答：如果大纲代码定义是只读的，您将无法直接修改它。在尝试任何修改之前，您需要检查其只读状态。
### 问：我可以添加到项目中的大纲代码定义数量有限制吗？
答：Aspose.Tasks for .NET 不会对您可以添加到项目中的大纲代码定义的数量施加任何特定限制。但是，在使用大量定义时，请考虑性能影响。
### 问：我可以使用大纲代码定义根据自定义标准对任务进行分组吗？
答：是的，大纲代码定义允许您根据自定义标准对任务进行分类，从而提供组织项目数据的灵活性。## 完整源代码
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
