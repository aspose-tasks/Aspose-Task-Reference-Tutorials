---
title: 使用 Aspose.Tasks 操作 MS Project 扩展属性
linktitle: 在 Aspose.Tasks 中使用扩展属性
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 来处理 MS Project 扩展属性。以编程方式轻松操作任务数据。
type: docs
weight: 11
url: /zh/net/tasks-project-management/working-with-extended-attributes/
---
## 介绍
Aspose.Tasks for .NET 是一个功能强大的库，允许开发人员以编程方式操作 Microsoft Project 文件。该库的主要功能之一是它能够使用 MS Project 扩展属性。扩展属性为项目中的任务提供额外的自定义和元数据，使用户能够存储和管理标准任务属性之外的特定信息。
在本教程中，我们将探索如何使用 Aspose.Tasks for .NET 来处理 MS Project 扩展属性。我们将介绍先决条件、导入命名空间，并以分步指南的形式将每个示例分解为多个步骤。学完本教程后，您将深入了解如何在 .NET 应用程序中利用扩展属性。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
### 1.安装Visual Studio
确保您的系统上安装了 Visual Studio。如果您还没有下载，可以从网站下载。
### 2..NET 库的 Aspose.Tasks
从以下位置下载并安装 Aspose.Tasks for .NET 库[网站](https://releases.aspose.com/tasks/net/).

## 导入命名空间
要开始使用 Aspose.Tasks for .NET，您需要将必要的命名空间导入到您的项目中。按着这些次序：
### 第 1 步：打开 Visual Studio
在您的系统上启动 Visual Studio。
### 第2步：创建一个新项目
创建一个新项目或打开一个要使用 Aspose.Tasks 的现有项目。
### 第 3 步：导入命名空间
在 C# 文件的开头添加以下命名空间：
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

现在我们已经设置了环境，让我们深入使用 Aspose.Tasks for .NET 来处理 MS Project 扩展属性。
## 第 1 步：定义数据目录
定义 MS Project 文件所在目录的路径：
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`与文档目录的实际路径。
## 第 2 步：加载项目文件
使用以下命令加载 MS Project 文件`Project`班级：
```csharp
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
这段代码初始化了一个新的实例`Project`类，加载指定的 MS Project 文件。
## 步骤 3：读取任务的扩展属性
迭代任务及其扩展属性来读取信息：
```csharp
foreach (var task in project.RootTask.Children)
{
    foreach (var attribute in task.ExtendedAttributes)
    {
        //阅读有关扩展属性的常见信息
        Console.WriteLine("Extended Attribute: " + attribute.ToString());
    }
}
```
此代码片段循环遍历每个任务及其扩展属性，将其信息打印到控制台。

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 来处理 MS Project 扩展属性。通过执行上述步骤，您可以有效地管理和操作 .NET 应用程序中的扩展属性数据。
## 常见问题解答
### Aspose.Tasks for .NET 是否与所有版本的 Microsoft Project 兼容？
是的，Aspose.Tasks for .NET 支持各种版本的 Microsoft Project，包括 2003、2007、2010、2013、2016 和 2019。
### 我可以使用 Aspose.Tasks for .NET 创建新的 MS Project 文件吗？
绝对地！ Aspose.Tasks for .NET 允许您以编程方式创建、修改和操作 MS Project 文件。
### Aspose.Tasks for .NET 是否需要商业用途许可证？
是的，您需要购买 Aspose.Tasks for .NET 的商业使用许可证。但是，您也可以利用免费试用来评估其功能。
### 我可以根据项目需求自定义扩展属性吗？
是的，Aspose.Tasks for .NET 提供了广泛的功能来自定义扩展属性以满足您项目的特定需求。
### 如果在使用 Aspose.Tasks for .NET 时遇到任何问题，我可以在哪里获得支持？
您可以从 Aspose.Tasks 社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).