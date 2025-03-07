---
title: 在 Aspose.Tasks 中自定义 MS Project 页面视图设置
linktitle: 在 Aspose.Tasks 中配置页面视图设置
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中配置页面视图设置以定制 Microsoft Project 文档的打印格式。
weight: 21
url: /zh/net/outline-code-page-settings/page-view-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中自定义 MS Project 页面视图设置

## 介绍
Microsoft Project 是一个功能强大的项目管理工具，但有时您需要自定义项目的查看和打印方式。使用 Aspose.Tasks for .NET，您可以轻松配置页面视图设置以满足您的特定要求。在本教程中，我们将逐步指导您完成该过程。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1.  Aspose.Tasks for .NET：确保您已下载并安装 Aspose.Tasks for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 文件：准备好要配置页面视图设置的 Microsoft Project 文件。

## 导入命名空间
首先，您需要导入必要的命名空间以在 .NET 项目中使用 Aspose.Tasks。
```csharp
    
    using Aspose.Tasks.Saving;
```
## 第 1 步：加载项目文件
首先将 Microsoft Project 文件加载到`Project`班级。
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## 第 2 步：设置第一列数
指定要在所有页面上打印的第一列的数量。
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## 第三步：打印笔记
选择是否随项目一起打印注释。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## 第 4 步：将时间刻度调整到页尾
决定打印时是否使时间刻度适合页面末尾。
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## 第 5 步：打印所有工作表列
指定是否打印视图的所有工作表列。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## 步骤 6：打印空白页
选择是否打印视图的空白页。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## 步骤 7：在所有页面上打印第一列
设置是否在所有页面上打印指定数量的第一列。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## 步骤 8：使用配置的设置保存项目
最后，使用配置的页面视图设置保存项目，并指定输出格式，例如 PDF。
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## 结论
在 Aspose.Tasks for .NET 中配置 Microsoft Project 页面视图设置非常简单，并且允许您根据您的具体需求定制打印格式。通过遵循本教程中概述的步骤，您可以确保您的项目文档完全按照要求呈现。
## 常见问题解答
### 问：我可以为除 PDF 之外的其他文件格式配置页面视图设置吗？
答：是的，Aspose.Tasks 支持保存项目的各种文件格式，包括 XLSX、MPP 和 HTML。
### 问：我可以打印的列数有限制吗？
答：Aspose.Tasks 允许您根据您的要求自定义要打印的列数。
### 问：我可以为不同的项目应用不同的页面视图设置吗？
答：是的，您可以为您使用的每个项目文件单独调整页面视图设置。
### 问：Aspose.Tasks 是否与所有版本的 Microsoft Project 兼容？
答：Aspose.Tasks 提供与 Microsoft Project 2003 及更高版本的兼容性。
### 问：我在哪里可以找到有关 Aspose.Tasks 的进一步帮助或支持？
答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)对于您在使用过程中遇到的任何疑问或问题。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
