---
title: 在 Aspose.Tasks 中以各种格式保存 MS 项目文件
linktitle: 在Aspose.Tasks中以各种格式保存文件
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 以各种格式保存 MS Project 文件。简单的步骤即可实现高效的项目管理。
weight: 17
url: /zh/net/rate-recurring-tasks/save-file-formats/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中以各种格式保存 MS 项目文件

## 介绍
在本教程中，我们将探讨如何使用 Aspose.Tasks for .NET 以各种格式保存 Microsoft Project 文件。 Aspose.Tasks 是一个功能强大的 API，允许开发人员以编程方式操作和管理项目文件。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[这里](https://releases.aspose.com/tasks/net/).
2. 开发环境：搭建.NET开发环境，例如Visual Studio。
3. 对 C# 的基本了解：熟悉 C# 编程语言将会很有帮助。

## 导入命名空间
确保在 C# 文件的开头导入必要的命名空间：
```csharp

using Aspose.Tasks.Saving;
```
## 第 1 步：创建项目对象
首先，创建一个 Project 对象并加载 Microsoft Project 文件。
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## 第 2 步：将项目保存为 CSV 格式
现在，让我们将项目保存为 CSV 格式。 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## 第 3 步：探索其他格式
Aspose.Tasks 支持保存项目文件的各种格式，例如 XML、PDF、XLSX 等。您只需更改以下内容即可探索这些格式`SaveFileFormat`中的参数`Save`方法。
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
通过执行以下步骤，您可以使用 Aspose.Tasks for .NET 轻松地将 Microsoft Project 文件保存为各种格式。

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 以不同格式保存 MS Project 文件。 Aspose.Tasks 简化了以编程方式操作项目文件的过程，为开发人员提供了灵活性和效率。
## 常见问题解答
### 问：Aspose.Tasks 是否与所有版本的 Microsoft Project 兼容？
答：Aspose.Tasks 支持 Microsoft Project 2003 XML、Microsoft Project 2007 MPP 和 Microsoft Project 2010 MPP 格式。
### 问：我可以在购买前试用 Aspose.Tasks 吗？
答：是的，您可以从以下位置下载免费试用版：[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.Tasks 的支持？
答：您可以从 Aspose.Tasks 社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).
### 问：Aspose.Tasks 是否可以获得临时许可证？
答：是的，临时许可证可用于评估目的。您可以获得一个[这里](https://purchase.aspose.com/temporary-license/).
### 问：Aspose.Tasks 的定价是多少？
答：定价信息可以在 Aspose.Tasks 购买页面找到[这里](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
