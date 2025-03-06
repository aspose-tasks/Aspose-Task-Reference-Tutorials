---
title: 使用 Aspose.Tasks for .NET 掌握 WBS 代码掩码
linktitle: Aspose.Tasks 中 WBS 代码掩码的集合
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 增强项目管理。在这个综合教程中学习如何轻松创建、管理和传输 WBS 代码掩码。
weight: 15
url: /zh/net/view-wbs-code-configuration/wbs-code-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for .NET 掌握 WBS 代码掩码

## 介绍
在项目管理的动态世界中，有效地组织任务至关重要。 Aspose.Tasks for .NET 提供了一个强大的解决方案来轻松管理项目工作分解结构 (WBS) 代码。在本教程中，我们将深入研究 WBS 代码掩码集合，探索如何使用 Aspose.Tasks for .NET 实现和操作它们。
## 先决条件
在我们开始此编码之旅之前，请确保您具备以下先决条件：
- C# 编程语言的应用知识。
-  Aspose.Tasks for .NET 安装在您的开发环境中。如果没有，请下载[这里](https://releases.aspose.com/tasks/net/).
- 像 Visual Studio 这样的代码编辑器可提供无缝的编码体验。
## 导入命名空间
首先，让我们导入必要的命名空间：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 初始化项目和WBS代码定义
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. 定义 WBS 代码掩码
清除所有现有的代码掩码并添加新的代码掩码：
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. 显示代码掩码信息
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. 将任务添加到项目中
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. 检索任务信息
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. 操纵代码掩码
删除代码掩码并确保将其删除：
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. 将代码掩码复制到另一个项目
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. 在另一个项目中显示代码掩码
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. 将任务添加到其他项目
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. 在其他项目中显示 WBS 代码
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 结论
借助 Aspose.Tasks for .NET，管理 WBS 代码变得毫不费力。本教程涵盖了 WBS 代码掩码的创建、操作和传输，为您提供了增强项目管理体验的全面指南。
## 常见问题解答
### 问：我可以将 Aspose.Tasks for .NET 与其他编程语言一起使用吗？
答：Aspose.Tasks 主要支持 .NET 语言，但您可以探索与其他语言的互操作性选项。
### 问：Aspose.Tasks for .NET 有试用版吗？
答：是的，您可以下载试用版[这里](https://releases.aspose.com/).
### 问：如何寻求帮助或报告 Aspose.Tasks for .NET 问题？
答：访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以寻求支持和讨论。
### 问：WBS 代码在项目管理中的用途是什么？
答：WBS 代码有助于分层组织和构建项目任务，为项目规划提供系统方法。
### 问：我可以在 Aspose.Tasks for .NET 中自定义 WBS 代码的格式吗？
答：当然，您可以使用 Aspose.Tasks for .NET 完全控制 WBS 代码的格式和结构。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
