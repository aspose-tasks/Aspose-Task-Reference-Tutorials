---
title: 在 Aspose.Tasks 中配置 MS Project 资源使用视图
linktitle: 在 Aspose.Tasks 中配置资源使用视图
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 配置 MS Project 资源使用视图。包含代码示例的分步指南。
weight: 15
url: /zh/net/resource-risk-analysis/resource-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中配置 MS Project 资源使用视图

## 介绍
Microsoft Project (MS Project) 是一个强大的项目管理工具，允许用户高效地计划、执行和跟踪他们的项目。 Aspose.Tasks for .NET 提供与 MS Project 文件的无缝集成，使开发人员能够以编程方式操作项目数据。在本教程中，我们将探讨如何使用 Aspose.Tasks for .NET 配置 MS Project 资源使用视图。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET 库：[下载链接](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 文件：有一个 Microsoft Project 文件 (`.mpp`）包含您要使用的项目数据。

## 导入命名空间
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## 第 1 步：加载项目文件
首先，使用 Aspose.Tasks 加载 MS Project 文件：
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## 第 2 步：定义保存选项
定义指定所需时间刻度设置和演示格式的保存选项：
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## 步骤 3：使用资源使用视图保存项目
将具有配置的资源使用视图的项目保存到 PDF 文件：
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 配置 MS Project 资源使用视图。通过遵循提供的步骤，开发人员可以将 Aspose.Tasks 无缝集成到他们的 .NET 应用程序中，以有效地操作项目数据。

## 常见问题解答
### 问：Aspose.Tasks 是否与不同版本的 Microsoft Project 文件兼容？
答：是的，Aspose.Tasks 支持各种版本的 Microsoft Project 文件，包括 .mpp、.mpt、.xml 和 .mpx。
### 问：我可以进一步自定义时间刻度设置和演示格式吗？
答：当然，Aspose.Tasks 提供了根据您的要求自定义时间刻度设置和演示格式的灵活性。
### 问：Aspose.Tasks 是否支持除 PDF 之外的其他输出格式？
答：是的，Aspose.Tasks 支持多种输出格式，包括 XLSX、MPP、XML、HTML 等。
### 问：是否有 Aspose.Tasks 支持的社区或论坛？
答： 是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)如有任何疑问、讨论或支持需求。
### 问：我可以在购买前试用 Aspose.Tasks 吗？
答：当然，您可以通过免费试用版探索 Aspose.Tasks[这里](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
