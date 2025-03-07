---
title: MS Project 中 Aspose.Tasks 的字体操作
linktitle: Aspose.Tasks 中的字体保存参数
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 操作 MS Project 文件中的字体。开发人员的分步指南。
weight: 19
url: /zh/net/tasks-project-management/font-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project 中 Aspose.Tasks 的字体操作

## 介绍
欢迎来到我们关于使用 Aspose.Tasks for .NET 操作 MS Project 文档中的字体的综合教程。 Aspose.Tasks 是一个功能强大的库，允许开发人员以编程方式处理 Microsoft Project 文件，从而为任务提供广泛的功能，例如读取、写入和修改项目数据。
在本教程中，我们将特别关注使用 Aspose.Tasks for .NET 在 MS Project 文件中保存字体。我们将把这个过程分解为易于遵循的步骤，确保您可以将字体保存功能无缝集成到您的 .NET 应用程序中。
## 先决条件
在开始之前，请确保您已设置以下先决条件：
1. 开发环境：确保您已设置安装了 Visual Studio 和 .NET 的开发环境。
2.  Aspose.Tasks for .NET 库：从以下位置下载并安装 Aspose.Tasks for .NET 库：[下载页面](https://releases.aspose.com/tasks/net/).
3. 许可证：获取 Aspose.Tasks for .NET 的许可证。如果您还没有临时许可证，您可以从[这里](https://purchase.aspose.com/temporary-license/).
4. C# 的基本了解：熟悉 C# 编程语言基础知识。

## 导入命名空间
首先，将必要的命名空间导入到您的 C# 项目中。这些命名空间提供对使用 Aspose.Tasks 功能所需的类和方法的访问。
## 第 1 步：打开您的 C# 项目
在 Visual Studio 或任何其他首选 IDE 中打开 C# 项目。
## 第2步：导入Aspose.Tasks命名空间
添加以下内容`using`在 C# 文件开头添加指令来导入 Aspose.Tasks 命名空间：
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

现在我们已经设置了项目并导入了所需的命名空间，接下来让我们深入了解使用 Aspose.Tasks for .NET 在 MS Project 文件中保存字体的过程。
## 第 1 步：定义文档目录
设置 MS Project 文件所在文档目录的路径：
```csharp
String DataDir = "Your Document Directory";
```
## 第2步：创建文件流
创建一个 FileStream 来写入字体数据：
```csharp
var stream = new FileStream(DataDir + "fonts/" + args.FileName, FileMode.Create);
```
## 步骤 3：将 FileStream 分配给 Args
将创建的FileStream分配给`Stream`字体保存参数的属性：
```csharp
args.Stream = stream;
```
## 步骤 4：指定文件 URI
设置项目目录中字体文件的 URI：
```csharp
args.Uri = DataDir + "fonts/" + args.FileName;
```
## 第5步：使用后关闭FileStream
确保FileStream在使用后关闭以释放系统资源：
```csharp
args.KeepStreamOpen = false;
```

## 结论
在本教程中，我们介绍了使用 Aspose.Tasks for .NET 在 MS Project 文件中保存字体的过程。通过执行上述步骤，您可以将字体保存功能无缝集成到您的 .NET 应用程序中，从而增强您的项目管理工作流程。
## 常见问题解答
### 我可以在没有许可证的情况下使用 Aspose.Tasks for .NET 吗？
不可以，您需要有效的许可证才能在应用程序中使用 Aspose.Tasks for .NET。但是，您可以获得用于评估目的的临时许可证。
### Aspose.Tasks for .NET 是否与所有版本的 Microsoft Project 文件兼容？
Aspose.Tasks for .NET 从 2003 年起支持 Microsoft Project 文件格式，包括 MPP、XML 和 MPX 格式。
### 我可以使用 Aspose.Tasks for .NET 操作 MS Project 文件的其他方面吗？
是的，Aspose.Tasks for .NET 提供了广泛的功能，用于读取、写入和修改 MS Project 文件的各个方面，例如任务、资源和日历。
### Aspose.Tasks for .NET 是否同时适用于桌面和 Web 应用程序？
是的，Aspose.Tasks for .NET 可以在使用 .NET 框架开发的桌面和 Web 应用程序中使用。
### 在哪里可以找到 Aspose.Tasks for .NET 的其他支持和资源？
您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)如需支持，请访问以下文档：[文档页](https://reference.aspose.com/tasks/net/)，并探索 Aspose.Tasks 网站上的教程和示例。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
