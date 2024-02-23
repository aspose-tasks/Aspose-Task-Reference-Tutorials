---
title: 使用 Aspose.Tasks for .NET 掌握时间分段数据处理
linktitle: 在 Aspose.Tasks 中处理时间分段数据
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 轻松处理时间分段数据、增强项目规划并优化资源管理。 #Aspose #Tasks #MS 项目
type: docs
weight: 14
url: /zh/net/text-view-configuration/timephased-data/
---
## 介绍
在项目管理领域，有效处理时间分段数据对于资源分配、成本估算和总体项目规划至关重要。 Aspose.Tasks for .NET 提供了一个强大的解决方案来无缝处理自定义时间分段数据。本教程将指导您完成使用 Aspose.Tasks 处理时间分段数据的过程，使您能够优化项目中的资源管理。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- 对项目管理概念的基本了解。
- 安装了 .NET 的 Aspose.Tasks。你可以下载它[这里](https://releases.aspose.com/tasks/net/).
- 代码编辑器，例如 Visual Studio，用于实现提供的示例。
## 导入命名空间
在您的 .NET 项目中，请确保导入必要的命名空间以利用 Aspose.Tasks 功能。在代码文件的开头添加以下行：
```csharp
    using Aspose.Tasks;
    using System;
    
```
现在，让我们将提供的示例分解为多个步骤，以指导您使用 Aspose.Tasks 处理时间分段数据：
## 第 1 步：设置项目
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
在这里，我们初始化一个新项目并设置其计算模式。
## 第 2 步：定义资源和任务
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
创建工作和成本资源以及任务来模拟项目结构。
## 步骤 3：为任务分配资源
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
将工时和成本资源分配给任务。
## 步骤 4：添加自定义时间分段数据
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
//costAssignment 的类似步骤
costAssignment.TimephasedData.Clear();
```
为工作和成本分配添加自定义时间分段数据。
## 第 5 步：显示时间分段数据
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        //显示有关每个时间分段数据条目的相关信息
    }
}
```
最后，显示每个作业的时间分段数据。
#
## 结论
在 Aspose.Tasks 中有效处理时间分段数据为详细的项目规划和资源管理开辟了新的可能性。通过遵循本分步指南，您已了解如何操作时间分段数据以满足项目的特定需求。
## 经常问的问题
### 我可以将 Aspose.Tasks for .NET 与其他项目管理工具一起使用吗？
Aspose.Tasks 主要是为.NET 开发而设计的。然而，它的功能可以补充各种项目管理工具。
### Aspose.Tasks for .NET 是否有免费试用版？
是的，您可以探索免费试用[这里](https://releases.aspose.com/).
### 如何获得 Aspose.Tasks for .NET 支持？
访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持。
### 什么是临时许可证？如何获得临时许可证？
了解临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以找到 Aspose.Tasks for .NET 的文档？
参考综合[文档](https://reference.aspose.com/tasks/net/)获取详细信息。