---
title: Aspose.Tasks 中的资源类型
linktitle: Aspose.Tasks 中的资源类型
second_title: Aspose.Tasks .NET API
description: 通过分步教程，了解如何在 Aspose.Tasks for .NET 中使用不同类型的资源，包括工时、材料和成本资源。
weight: 14
url: /zh/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的资源类型

## 介绍
Aspose.Tasks for .NET 是一个功能强大的库，允许开发人员以编程方式处理 Microsoft Project 文件。无论您是管理任务、资源还是计划，Aspose.Tasks 都可以通过提供一套全面的 API 来简化流程。在本教程中，我们将深入研究您可以使用 Aspose.Tasks for .NET 在项目中使用的不同类型的资源。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. Visual Studio：安装 Visual Studio，这是一个用于 .NET 开发的强大集成开发环境 (IDE)。
2.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks for .NET 库[这里](https://releases.aspose.com/tasks/net/).
3. C# 基础知识：熟悉 C#，用于 .NET 开发的编程语言。

## 导入命名空间
首先，让我们导入必要的命名空间来访问 Aspose.Tasks for .NET 的功能：
```csharp
    
```

## 第 1 步：创建一个新的项目实例
```csharp
var project = new Project();
```
此行初始化一个新的 Project 对象，该对象充当所有与项目相关的数据和操作的容器。
## 第 2 步：添加工作资源
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
在这里，我们创建一个名为“Work resources”的新工作资源，并将其类型指定为 ResourceType.Work。
## 步骤 3：添加材质资源
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
此步骤添加名为“Material resources”的材质资源，其类型设置为 ResourceType.Material。此外，我们将材料标签指定为“kg”以指示计量单位。
## 步骤 4：添加成本资源
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
最后，我们添加一个名为“Cost resource”的成本资源，并将其类型设置为ResourceType.Cost。此外，我们将成本值设置为 59.99，表示与该资源相关的货币价值。

## 结论
在本教程中，我们探索了如何在 Aspose.Tasks for .NET 中使用不同类型的资源，包括工时、材料和成本资源。通过遵循分步指南，您可以以编程方式有效地管理项目中的资源。
## 常见问题解答
### 问：我可以将 Aspose.Tasks for .NET 与其他项目管理软件格式一起使用吗？
答：是的，Aspose.Tasks 支持多种格式，包括 Microsoft Project (MPP)、Primavera P6 等。
### 问：Aspose.Tasks for .NET 是否有免费试用版？
答：是的，您可以免费试用[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.Tasks for .NET 的技术支持？
答：您可以访问Aspose.Tasks论坛[这里](https://forum.aspose.com/c/tasks/15)寻求技术援助。
### 问：我可以购买 Aspose.Tasks for .NET 的临时许可证吗？
答：是的，您可以购买临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 问：Aspose.Tasks for .NET 是否提供参考文档？
答： 是的，你可以找到文档[这里](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
