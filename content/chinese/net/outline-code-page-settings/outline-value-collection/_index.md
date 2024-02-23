---
title: 使用 Aspose.Tasks 管理 MS 项目大纲值
linktitle: Aspose.Tasks中大纲值的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 文件中的大纲值。带有代码示例的分步教程。
type: docs
weight: 17
url: /zh/net/outline-code-page-settings/outline-value-collection/
---
## 介绍
Aspose.Tasks for .NET 提供了一套全面的功能来与 Microsoft Project 文件进行交互。其中一项功能是能够管理项目内的大纲值。在本教程中，我们将探索如何使用 Aspose.Tasks for .NET 收集和操作大纲值。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1.  Aspose.Tasks for .NET：您可以从以下位置下载该库：[这里](https://releases.aspose.com/tasks/net/).
2. 开发环境：确保安装了合适的IDE，例如Visual Studio。
3. C# 基础知识：熟悉 C# 编程语言将会很有帮助。
## 导入命名空间
在您的 C# 代码文件中，导入必要的命名空间以访问 Aspose.Tasks 类和方法：
```csharp
using Aspose.Tasks;
using System;

```
让我们将提供的示例分解为多个步骤：
## 第 1 步：加载项目文件
首先，初始化一个`Project`通过加载现有的 Microsoft Project 文件来对象：
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 第 2 步：清除现有大纲值
接下来，清除项目中任何现有的大纲值：
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## 第 3 步：定义新的大纲代码
现在，定义一个带有描述和值的新大纲代码：
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## 第 4 步：更新轮廓值
更新大纲代码的值：
```csharp
codeDefinition.Values[0].Value = "654321";
```
## 第 5 步：迭代轮廓值
迭代大纲值并打印其详细信息：
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## 第 6 步：操纵轮廓值
根据需要执行删除、插入和复制轮廓值等操作：
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 处理 Microsoft Project 文件中的大纲值。通过遵循提供的步骤，您可以有效地管理项目中的大纲值，从而实现更好的控制和灵活性。
## 常见问题解答
### 问：我可以同时操作多个大纲代码吗？
答：是的，您可以使用 Aspose.Tasks 在项目中定义和操作多个大纲代码。
### 问：Aspose.Tasks 是否与不同版本的 Microsoft Project 文件兼容？
答：是的，Aspose.Tasks 支持各种版本的 Microsoft Project 文件，包括 MPP 和 XML 格式。
### 问：使用轮廓值时如何处理错误？
答：您可以实现错误处理机制（例如 try-catch 块）来优雅地管理异常。
### 问：我可以在项目中自定义轮廓值的外观吗？
答：是的，Aspose.Tasks 提供了广泛的 API 来根据您的要求自定义大纲值的外观和行为。
### 问：在哪里可以找到 Aspose.Tasks 的其他资源和支持？
答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求社区支持并探索[文档](https://reference.aspose.com/tasks/net/)有关 API 和功能的详细信息。