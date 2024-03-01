---
title: 使用 Aspose.Tasks for .NET 掌握 WBS 序列
linktitle: 在 Aspose.Tasks 中定义 WBS 序列
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 增强您的项目管理能力 – 无缝定义 WBS 序列并轻松提高效率。 #Aspose #Tasks #MS 项目
type: docs
weight: 16
url: /zh/net/view-wbs-code-configuration/wbs-sequences/
---
## 介绍
您是否正在开发项目管理应用程序并需要一个强大的工具来处理工作分解结构 (WBS) 序列？ Aspose.Tasks for .NET 就是您的最佳选择，它是一个功能强大的库，可以简化项目管理任务。在本教程中，我们将指导您逐步完成定义 WBS 序列的过程。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- [下载并安装 Aspose.Tasks for .NET](https://releases.aspose.com/tasks/net/)
- C# 编程基础知识
- 为.NET项目设置的开发环境
## 导入命名空间
在您的 C# 代码中，请确保包含必要的命名空间以利用 Aspose.Tasks 的功能。在脚本的开头添加以下内容：
```csharp
    
    using Aspose.Tasks.Saving;
```
## 定义 WBS 序列 - 分步指南
## 第 1 步：设置项目
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project();
```
## 步骤 2：配置 WBS 代码定义
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 步骤 3：定义 WBS 代码掩码
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
## 步骤 4：将任务添加到项目中
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
```
## 第 5 步：重新计算项目数据
```csharp
project.Recalculate();
```
## 第 6 步：保存项目
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
恭喜！您已使用 Aspose.Tasks for .NET 在项目中成功定义了 WBS 序列。
## 结论
管理 WBS 序列对于有效的项目管理至关重要，而 Aspose.Tasks for .NET 可以无缝地完成此任务。通过执行这些简单的步骤，您可以增强项目管理应用程序中的 WBS 功能。
## 经常问的问题
### Aspose.Tasks 与 .NET Core 兼容吗？
是的，Aspose.Tasks 支持 .NET Core，允许您构建跨平台应用程序。
### 我可以进一步自定义 WBS 代码格式吗？
绝对地！ Aspose.Tasks 提供了根据您的项目需求定义 WBS 代码的灵活性。
### 有试用版吗？
是的你可以[下载免费试用版](https://releases.aspose.com/)在购买前探索功能。
### 我如何获得 Aspose.Tasks 的社区支持？
参观[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)与社区联系并寻求帮助。
### 可以使用临时许可证吗？
是的，您可以获得[临时执照](https://purchase.aspose.com/temporary-license/)用于测试目的。