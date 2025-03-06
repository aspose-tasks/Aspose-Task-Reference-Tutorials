---
title: 在 Aspose.Tasks 中管理任务
linktitle: 在 Aspose.Tasks 中管理任务
second_title: Aspose.Tasks .NET API
description: 探索有关使用 Aspose.Tasks for .NET 管理任务的综合指南。学习添加、显示拆分零件、移动、获取/设置属性等。
weight: 15
url: /zh/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理任务

## 介绍
如果您是一名 .NET 开发人员，希望有效管理项目中的任务，Aspose.Tasks for .NET 提供了一个强大的解决方案。本教程将指导您完成使用 Aspose.Tasks 管理任务的各个方面，并提供分步说明和代码示例。无论您是添加任务、显示拆分部分、在同一父级下移动任务、获取/设置任务属性、迭代任务分配、读取任务基线还是删除任务，本指南都能满足您的要求。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. Aspose.Tasks for .NET 库：确保您已安装 Aspose.Tasks for .NET 库。你可以下载它[这里](https://releases.aspose.com/tasks/net/).
2. 文档目录：设置存储项目文档的目录。
## 导入命名空间
在您的 .NET 项目中，包含使用 Aspose.Tasks 所需的命名空间：
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. 将任务添加到项目中
```csharp
//创建一个新项目
var project = new Project();
//添加任务
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
//保存项目
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. 显示任务的分割部分
```csharp
//加载具有拆分任务的项目
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//访问任务
var task = project.RootTask.Children.GetById(4);
//显示分割部分
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. 在同一父级下移动任务
```csharp
try
{
    //加载项目
    var project = new Project(DataDir + "MoveTask.mpp");
    //将 id 5 的任务移到 id 3 的任务之前
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    //保存修改后的项目
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. 获取/设置任务属性
```csharp
//创建一个新项目
var project = new Project();
//添加任务并设置属性
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
//收集并显示任务属性
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. 迭代任务的分配
```csharp
//加载带有作业的项目
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
//收集并显示任务分配
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. 读取任务的基线
```csharp
//创建一个新项目
var project = new Project();
//添加任务并设置基线
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
//显示任务基线持续时间
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. 删除任务
```csharp
//创建一个新项目
var project = new Project();
//添加任务
var task = project.RootTask.Children.Add("Task");
//显示删除前后的任务数
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
//删除任务
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## 结论
使用所提供的示例，在 Aspose.Tasks for .NET 中管理任务是一个无缝过程。无论您是经验丰富的开发人员还是刚刚入门，结合这些技术都将增强您的项目管理能力。
## 经常问的问题
### 问：Aspose.Tasks 是否与所有 .NET 框架兼容？
答：是的，Aspose.Tasks 支持各种.NET 框架，确保与您的开发环境兼容。
### 问：如何获得 Aspose.Tasks 的临时许可证？
答：您可以从以下地址获得 30 天的临时许可证：[这里](https://purchase.aspose.com/temporary-license/).
### 问：在 Aspose.Tasks 中处理拆分任务时有任何限制吗？
 A：拆分任务是一个很强大的功能，详细的文档可以找到[这里](https://reference.aspose.com/tasks/net/).
### 问：除了示例中显示的内容之外，我还可以自定义任务属性吗？
答：当然！ Aspose.Tasks 为任务属性提供了广泛的自定义选项。查看文档以获取更多详细信息。
### 问：如何获得 Aspose.Tasks 的支持？
答：访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持和讨论。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
