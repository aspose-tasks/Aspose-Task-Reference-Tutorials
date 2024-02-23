---
title: 在 Aspose.Tasks 中管理任务集合
linktitle: 在 Aspose.Tasks 中管理任务集合
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 中高效的任务集合管理。从创作到编辑，轻松掌握项目管理。
type: docs
weight: 18
url: /zh/net/task-table-management/task-collection/
---
## 介绍
如果您正在使用 .NET 深入研究项目管理领域，Aspose.Tasks 是您无缝处理任务集合的首选解决方案。本教程将指导您完成有效管理任务集合的过程，确保您充分利用这个强大的库。
## 先决条件
在我们深入学习本教程之前，请确保您满足以下先决条件：
- C# 编程语言的基础知识。
- Visual Studio 安装在您的计算机上。
- 下载 Aspose.Tasks for .NET 库并在您的项目中引用。
## 导入命名空间
首先，让我们在 C# 项目中导入必要的命名空间：
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
这些命名空间提供对有效任务管理所需的基本类和方法的访问。
现在，让我们将教程分解为一系列步骤，以确保清晰和简单。
## 第1步：创建项目实例
```csharp
var project = new Project();
```
使用实例化一个新项目`Project`班级。
## 第 2 步：检查任务收集准备情况
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
验证任务集合是否是只读的。
## 第 3 步：创建任务
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
//设置其他任务属性，例如开始、持续时间和完成
//任务 2 和任务 3 的步骤类似
```
在项目中创建任务并设置其属性。
## 第 4 步：打印项目任务
```csharp
foreach (var child in project.RootTask.Children)
{
    //打印任务详细信息
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
打印项目中每个任务的详细信息。
## 第5步：编辑任务
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
使用任务 ID 或 UID 编辑任务。
## 第 6 步：添加重复任务
```csharp
var parameters = new RecurringTaskParameters
{
    //设置重复任务参数
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
将重复任务添加到项目中。
## 第 7 步：将集合转换为列表
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
将任务集合转换为列表并对每个任务执行操作。
## 结论
通过本分步指南，在 Aspose.Tasks for .NET 中管理任务集合变得轻而易举。无论您是创建、编辑还是删除任务，Aspose.Tasks 都可以让您无缝地进行项目管理。
## 经常问的问题
### Aspose.Tasks 与 .NET Core 兼容吗？
是的，Aspose.Tasks 支持 .NET Core，允许您在跨平台应用程序中使用它。
### 我可以将项目任务导出为不同的文件格式吗？
绝对地！ Aspose.Tasks 提供多种导出选项，包括 PDF、XLSX 和 MPP。
### 如何处理任务之间的依赖关系？
您可以使用以下命令设置任务依赖关系`TaskLink`由Aspose.Tasks提供的类。
### 是否有 Aspose.Tasks 支持的社区论坛？
是的，您可以在以下位置找到支持并与社区互动：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
### 我可以获得 Aspose.Tasks 的临时许可证吗？
是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).