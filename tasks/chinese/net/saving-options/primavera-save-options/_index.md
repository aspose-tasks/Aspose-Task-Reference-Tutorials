---
title: 使用 Aspose.Tasks 保存 MS 项目选项 Primavera
linktitle: Aspose.Tasks 的 Primavera 保存选项
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 无缝保存 Primavera 的 MS Project 选项。请按照我们的分步教程进行操作。
type: docs
weight: 14
url: /zh/net/saving-options/primavera-save-options/
---
## 介绍
Aspose.Tasks for .NET 是一个功能强大的库，使开发人员能够在其 .NET 应用程序中无缝地使用 Microsoft Project 文件。它提供的关键功能之一是能够为流行的项目管理软件 Primavera 保存 MS Project 选项。在本教程中，我们将深入研究如何使用 Aspose.Tasks 来实现这一目标。
## 先决条件
在我们开始之前，请确保您具备以下条件：
- 对 C# 和 .NET 框架有基本了解。
-  Aspose.Tasks for .NET 安装在您的开发环境中。如果没有的话可以下载[这里](https://releases.aspose.com/tasks/net/).
- 用于实验的示例 MS Project 文件。

## 导入命名空间
首先，让我们将必要的命名空间导入到我们的 C# 代码中：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 第 1 步：加载 MS 项目文件
首先将要使用的 MS Project 文件加载到 C# 应用程序中。您可以使用`Project`由Aspose.Tasks提供的类。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 第 2 步：定义 Primavera 保存选项
接下来，创建 Primavera 保存选项并根据您的要求进行自定义。此步骤涉及指定活动 ID 前缀、后缀、增量以及是否对活动 ID 重新编号等参数。
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## 步骤 3：保存 Primavera 的 MS 项目选项
现在您已经加载了项目文件并定义了 Primavera 保存选项，是时候保存 Primavera 的选项了。使用`Save`提供的方法`Project`类，传递所需的输出文件路径和 Primavera 保存选项。
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## 结论
总之，利用 Aspose.Tasks for .NET 允许开发人员无缝操作 MS Project 文件，包括 Primavera 的保存选项。通过遵循本教程中概述的步骤，您可以将此功能有效地集成到您的 .NET 应用程序中。
## 常见问题解答
### 问：保存 Primavera 的 MS Project 选项时，除了活动 ID 之外，我还可以自定义其他参数吗？
答：是的，Aspose.Tasks 提供了广泛的定制选项，包括资源分配和任务调度。
### 问：Aspose.Tasks 是否支持除 Primavera 之外的其他项目管理软件？
答：是的，Aspose.Tasks 支持与流行的项目管理工具（例如 Oracle Primavera、Microsoft Project Server 等）兼容的各种格式。
### 问：Aspose.Tasks 适合小型和企业级项目吗？
答：当然，Aspose.Tasks 旨在满足开发各种规模项目的开发人员的需求，提供可扩展性和强大的性能。
### 问：我可以在购买前免费试用 Aspose.Tasks 吗？
答：是的，您可以从以下位置下载 Aspose.Tasks 的免费试用版：[这里](https://releases.aspose.com/)探索其特性和功能。
### 问：如果在使用 Aspose.Tasks 时遇到问题或有疑问，我可以在哪里获得支持？
答：您可以向 Aspose.Tasks 社区和支持团队寻求帮助[论坛](https://forum.aspose.com/c/tasks/15).