---
title: 使用 Aspose.Tasks 将 MS 项目文件另存为模板
linktitle: 保存 Aspose.Tasks 的模板选项
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 将 Microsoft Project 文件另存为模板。自定义模板设置以简化项目管理。
weight: 18
url: /zh/net/saving-options/save-template-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 将 MS 项目文件另存为模板

## 介绍
在本教程中，我们将逐步介绍使用 Aspose.Tasks for .NET 保存模板的过程。模板对于标准化项目结构和设置以供将来使用非常有用。我们将演示如何将项目另存为模板，并在此过程中调整其属性。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1.  Aspose.Tasks for .NET 库：确保您已安装 Aspose.Tasks for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).
2. C# 编程知识：需要具备 C# 编程基础知识才能理解和实现所提供的代码片段。
3. Microsoft Project 文件：准备好要另存为模板的 Microsoft Project 文件（MPP 格式）。

## 导入命名空间
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 第 1 步：加载项目
首先，我们需要加载要另存为模板的 Microsoft Project 文件 (.mpp)。
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 第2步：获取项目文件信息
检索有关加载的项目文件的信息，例如其格式。
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## 步骤 3：配置保存模板选项
创建模板保存选项并根据您的要求配置其属性。这些选项允许您自定义应从模板中删除哪些数据。
```csharp
var options = new SaveTemplateOptions
{
	//从项目模板中删除所有固定成本
	RemoveFixedCosts = true,
	//从项目模板中删除所有实际值
	RemoveActualValues = true,
	//从项目模板中删除资源费率
	RemoveResourceRates = true,
	//从项目模板中删除所有基线值
	RemoveBaselineValues = true
};
```
## 第 4 步：将项目另存为模板
将项目保存为具有指定选项的模板。
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## 第5步：获取模板文件信息
检索有关已保存模板文件的信息，例如其格式。
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
恭喜！您已成功使用 Aspose.Tasks for .NET 保存模板，并根据需要自定义其属性。

## 结论
在本教程中，我们探讨了如何使用 Aspose.Tasks for .NET 将 Microsoft Project 文件另存为模板。模板对于标准化项目结构和设置、简化未来的项目创建非常有价值。
## 常见问题解答
### 问：我可以自定义从模板中删除哪些数据吗？
答：是的，您可以配置“保存模板选项”来删除特定数据，例如固定成本、实际值、资源费率和基准值。
### 问：Aspose.Tasks for .NET 是否与所有版本的 Microsoft Project 兼容？
答：Aspose.Tasks for .NET 提供与 Microsoft Project 各个版本的广泛兼容性，确保无缝集成和功能。
### 问：我可以将模板应用到现有项目吗？
答：是的，您可以通过加载模板文件并根据需要将其与当前项目合并来将模板应用到现有项目。
### 问：Aspose.Tasks for .NET 支持跨平台开发吗？
答：Aspose.Tasks for .NET 主要是为 Windows 平台上运行的 .NET 框架应用程序设计的。
### 问：Aspose.Tasks for .NET 是否提供技术支持？
答：是的，您可以向 Aspose.Tasks 社区寻求技术帮助和指导[论坛](https://forum.aspose.com/c/tasks/15)或直接联系他们的支持团队。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
