---
title: Aspose.Tasks .NET 中的分步 WBS 代码配置
linktitle: 在 Aspose.Tasks 中配置 WBS 代码掩码
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks 探索 .NET 项目中的分步 WBS 代码掩码配置。轻松提升项目管理能力。
type: docs
weight: 14
url: /zh/net/view-wbs-code-configuration/wbs-code-masks/
---
## 介绍
Aspose.Tasks for .NET 是一个功能强大的库，使开发人员能够有效地操作 .NET 应用程序中的项目管理数据。在本教程中，我们将探索使用 Aspose.Tasks 配置工作分解结构 (WBS) 代码掩码的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
-  Aspose.Tasks for .NET Library：从以下地址下载并安装该库[Aspose.Tasks for .NET 文档](https://reference.aspose.com/tasks/net/).
- 开发环境：确保您设置了有效的 .NET 开发环境。
- 文档目录：选择系统上的一个目录来存储项目文件。
## 导入命名空间
在您的 .NET 项目中，包含使用 Aspose.Tasks 所需的命名空间：
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## 第1步：创建项目实例
首先创建一个新的项目实例：
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 步骤 2：定义 WBS 代码定义
为您的项目设置 WBS 代码定义：
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 步骤 3：添加 WBS 代码掩码
定义 WBS 代码掩码并将其添加到项目中：
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## 第 4 步：创建任务
将任务添加到项目中：
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## 第 5 步：重新计算
重新计算项目以确保正确应用 WBS 代码：
```csharp
project.Recalculate();
```
## 步骤 6：显示 WBS 掩码信息
将有关 WBS 掩码的信息输出到控制台：
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## 第 7 步：保存项目
使用添加的 WBS 代码保存项目：
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
恭喜！您已在 Aspose.Tasks 项目中成功配置了 WBS 代码掩码。
## 结论
在本教程中，我们探索了使用 Aspose.Tasks for .NET 配置 WBS 代码掩码的分步过程。这个功能强大的库为开发人员提供了一种无缝的方式来增强其 .NET 应用程序中的项目管理功能。

## 常见问题解答
### 我可以免费使用 Aspose.Tasks 吗？
 Aspose.Tasks 提供免费试用版，您可以下载[这里](https://releases.aspose.com/).
### 我在哪里可以找到额外的支持？
参观[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持。
### 我怎样才能获得临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 有详细的文档吗？
是的，有完整的文档可供使用[这里](https://reference.aspose.com/tasks/net/).
### 在哪里可以购买 Aspose.Tasks？
购买 Aspose.Tasks[这里](https://purchase.aspose.com/buy).