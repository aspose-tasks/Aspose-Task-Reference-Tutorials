---
title: Aspose.Tasks 中资源分配的集合
linktitle: Aspose.Tasks 中资源分配的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 中的资源分配。带有代码示例的分步教程。
type: docs
weight: 12
url: /zh/net/resource-risk-analysis/resource-assignment-collection/
---
## 介绍
欢迎阅读这个关于使用 Aspose.Tasks for .NET 在 Microsoft Project 中管理资源分配的综合教程。在本教程中，我们将逐步深入研究该过程，确保您充分了解如何有效地操纵资源分配。无论您是经验丰富的开发人员还是刚刚入门，本指南都将引导您完成您需要了解的所有内容。
## 先决条件
在我们深入研究代码之前，请确保您已进行以下设置：
1. 已安装 Aspose.Tasks for .NET：确保您的开发环境中安装了 Aspose.Tasks for .NET。如果没有，您可以从以下位置下载[这里](https://releases.aspose.com/tasks/net/).
2. C# 基础知识：本教程假设您对 C# 编程语言有基本了解。
3. Microsoft Project 文件：准备好 Microsoft Project 文件以用于测试目的。如果没有，您可以创建一个示例文件。

## 导入命名空间
首先，让我们导入必要的名称空间：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 第 1 步：加载项目文件
首先加载 Microsoft Project 文件：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## 步骤 2：添加任务和资源
现在，让我们向项目添加任务和资源：
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## 步骤 3：将资源分配给任务
接下来，我们将资源分配给任务：
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## 步骤 4：处理不同的作业类型
您还可以处理涉及单位或成本的作业：
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
//设置单位和成本分配的属性，与步骤 3 中所示类似
```
## 第 5 步：打印作业
打印项目的作业：
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    //打印作业详细信息
}
```
## 第 6 步：通过 UID 检索分配
您可以通过 UID 检索分配：
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## 第7步：检查只读状态
验证资源分配集合是否是只读的：
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## 第 8 步：将集合转换为列表并迭代
将集合转换为列表并对其进行迭代：
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## 结论
恭喜！您已经了解了如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 中的资源分配。通过执行这些步骤，您可以有效地操纵任务和资源，使项目管理变得轻而易举。
## 常见问题解答
### 问：我可以将 Aspose.Tasks for .NET 与不同版本的 Microsoft Project 文件一起使用吗？
答：是的，Aspose.Tasks for .NET 支持各种版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### 问：购买 Aspose.Tasks for .NET 之前是否有试用版？
答：是的，您可以从以下位置获得 Aspose.Tasks for .NET 的免费试用版：[这里](https://releases.aspose.com/).
### 问：如果在使用 Aspose.Tasks for .NET 时遇到任何问题，如何获得支持？
答：您可以从Aspose.Tasks论坛寻求支持[这里](https://forum.aspose.com/c/tasks/15).
### 问：我可以使用 Aspose.Tasks for .NET 的临时许可证吗？
答：是的，临时许可证可用于评估目的。您可以从以下位置获取一个[这里](https://purchase.aspose.com/temporary-license/).
### 问：在哪里可以购买 Aspose.Tasks for .NET 的完整许可证？
答：您可以从 Aspose 在线商店购买完整许可证[这里](https://purchase.aspose.com/buy).