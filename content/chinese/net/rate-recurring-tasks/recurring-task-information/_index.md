---
title: 在 Aspose.Tasks 中提取重复任务信息
linktitle: 在 Aspose.Tasks 中提取重复任务信息
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 从 MS Project 文件中提取重复任务信息。 .NET 开发人员可以轻松集成。
type: docs
weight: 13
url: /zh/net/rate-recurring-tasks/recurring-task-information/
---
## 介绍
Aspose.Tasks for .NET 是一个功能强大的库，允许开发人员在其 .NET 应用程序中使用 Microsoft Project 文件。在本教程中，我们将探索如何使用 Aspose.Tasks 从 MS Project 文件中提取重复任务信息。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
1. 对 C# 编程语言有基本了解。
2. Visual Studio 安装在您的系统上。
3. 安装了 .NET 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).
## 导入命名空间
首先，在 C# 代码中导入必要的命名空间：
```csharp
    using Aspose.Tasks;
    using System;
    
```
现在，让我们将示例分解为多个步骤：
## 第一步：设置项目文件路径
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`以及 MS Project 文件的路径。
## 第 2 步：加载 MS 项目文件
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
该行初始化一个新的`Project`通过加载路径指定的 MS Project 文件来实现对象。
## 步骤 3：读取任务的重复信息
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    //访问并显示重复任务信息
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    //根据需要继续显示其他重复任务信息
}
```
此循环迭代项目中的所有任务，并检查每个任务是否具有与其关联的重复信息。如果是，它会检索并显示重复任务的各种属性，例如开始日期、持续时间、结束日期等。
## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 从 MS Project 文件中提取重复任务信息。有了这些知识，您现在可以将此功能集成到您的 .NET 应用程序中，以更有效地处理重复任务。
## 常见问题解答
### 问：我可以使用 Aspose.Tasks for .NET 修改重复任务信息吗？
答：是的，您可以使用提供的 API 以编程方式修改重复任务信息。
### 问：Aspose.Tasks 是否支持除 MS Project 之外的其他项目文件格式？
答：是的，Aspose.Tasks 支持各种项目文件格式，例如 MPP、XML 和 CSV。
### 问：Aspose.Tasks for .NET 是否有免费试用版？
答：是的，您可以从以下位置下载免费试用版：[这里](https://releases.aspose.com/).
### 问：在哪里可以找到 Aspose.Tasks for .NET 的文档？
答：你可以找到文档[这里](https://reference.aspose.com/tasks/net/).
### 问：如何获得 Aspose.Tasks for .NET 的技术支持？
答：您可以从 Aspose.Tasks 论坛获得技术支持。[这里](https://forum.aspose.com/c/tasks/15).