---
title: Aspose.Tasks 中大纲代码的集合 MS 项目
linktitle: Aspose.Tasks中大纲代码的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 收集 Microsoft Project 大纲代码。这个综合教程提供了分步说明。
type: docs
weight: 11
url: /zh/net/outline-code-page-settings/outline-code-collection/
---
## 介绍
在本教程中，我们将探讨如何使用 Aspose.Tasks for .NET 收集 Microsoft Project 大纲代码。我们将把该过程分解为分步说明，以确保清晰度和理解性。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. Visual Studio：在您的系统上安装 Visual Studio。
2.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[这里](https://releases.aspose.com/tasks/net/).
3. 对 C# 编程的基本了解：熟悉 C# 将会很有帮助。

## 导入命名空间
首先，导入必要的命名空间以访问 C# 项目中的 Aspose.Tasks 功能。
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## 第 1 步：加载项目文件
首先使用以下命令加载 Microsoft Project 文件`Project`班级。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## 第2步：收集大纲代码
创建一个收集器来收集项目任务中的大纲代码。
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## 第 3 步：迭代任务和大纲代码
迭代收集的任务和大纲代码，打印它们的详细信息。
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## 步骤 4：添加自定义大纲代码定义
将自定义大纲代码定义添加到项目中。
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## 第 5 步：创建并插入大纲代码
创建大纲代码并将其插入到任务中。
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## 第 6 步：操作大纲代码
根据需要操作大纲代码，例如插入、删除或清除。
```csharp
//操纵示例
//,
//在正确位置插入带有 2 的代码
task.OutlineCodes.Insert(2, code2);
//检查代码是否插入
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 收集 Microsoft Project 大纲代码。通过执行这些步骤，您可以有效地管理项目中的大纲代码，从而增强组织性和清晰度。
## 常见问题解答
### 问：我可以将 Aspose.Tasks for .NET 与其他编程语言一起使用吗？
答：是的，Aspose.Tasks for .NET 主要针对 .NET 平台，但它也通过 Aspose.Tasks for Cloud 提供对其他编程语言的支持。
### 问：Aspose.Tasks for .NET 可以处理的项目文件的大小是否有任何限制？
答：Aspose.Tasks for .NET 可以有效地处理大型项目文件，但性能可能会根据文件的复杂性和大小而有所不同。
### 问：Aspose.Tasks for .NET 与最新版本的 Microsoft Project 兼容吗？
答：是的，Aspose.Tasks for .NET 支持各种版本的 Microsoft Project，包括最新版本。
### 问：使用 Aspose.Tasks for .NET 时可以自定义输出格式吗？
答：当然，Aspose.Tasks for .NET 提供了广泛的选项，可根据您的要求自定义输出格式。
### 问：在哪里可以找到 Aspose.Tasks for .NET 的其他支持或资源？
答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)有关 Aspose.Tasks for .NET 的任何帮助或疑问。