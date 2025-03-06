---
title: 掌握 Aspose.Tasks 中的时间分段数据收集
linktitle: Aspose.Tasks 中时间分段数据的收集
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 中的时间分段数据收集。分步指南、常见问题解答等。立即增强您的项目管理能力！
weight: 15
url: /zh/net/text-view-configuration/timephased-data-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 Aspose.Tasks 中的时间分段数据收集

## 介绍
您是否希望使用 Aspose.Tasks 在 .NET 应用程序中利用时间分段数据的强大功能？别再犹豫了！这个综合指南将引导您完成使用 Aspose.Tasks for .NET 收集时间分段数据的过程，确保您充分利用这个强大的库。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1.  Aspose.Tasks for .NET Library：从以下地址下载并安装该库[Aspose.Tasks .NET 文档](https://reference.aspose.com/tasks/net/).
2. .NET 开发环境：确保您已设置有效的 .NET 开发环境。
3. 您的文档目录：将代码片段中的占位符“您的文档目录”替换为您的文档目录的路径。
## 导入命名空间
在您的 .NET 项目中，首先导入必要的命名空间以利用 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 创建项目和资源
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. 将任务添加到项目中
```csharp
var task = project.RootTask.Children.Add("Task 1");
//设置任务属性...
var task2 = project.RootTask.Children.Add("Task 2");
//设置任务2属性...
```
## 3. 为任务分配资源
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
//设置分配属性...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//设置分配 2 属性...
```
## 4. 使用时间分段数据
```csharp
//设置轮廓工作轮廓
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
//检查时间分段数据收集是否为只读
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
//清除生成的时间分段数据
assignment.TimephasedData.Clear();
//创建并添加时间分段数据
var td = new TimephasedData
{
    //设置时间分段数据属性...
};
assignment.TimephasedData.Add(td);
//添加时间分段数据列表
var list = new List<TimephasedData>();
//将更多时间分段数据项添加到列表中...
assignment.TimephasedData.AddRange(list);
//按类型和日期范围过滤时间分段数据
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
//打印过滤后的时间分段数据...
```
## 5. 操作时间分段数据
```csharp
//添加错误的时间分段数据项，然后将其删除
var td4 = new TimephasedData
{
    //设置错误的时间分段数据属性...
};
assignment.TimephasedData.Add(td4);
//删除错误的时间分段数据项
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
//迭代所有时间分段项目
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    //打印按时间分段的项目详细信息...
}
```
## 6. 将时间分段数据复制到另一个作业
```csharp
//将时间分段数据复制到另一个作业
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
//将集合转换为普通列表
List<TimephasedData> tds = assignment.TimephasedData.ToList();
//一项一项删除时间分段数据项
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## 结论
总之，本教程提供了使用 Aspose.Tasks for .NET 收集时间分段数据的详细演练。通过执行这些步骤，您可以将此功能无缝集成到您的项目中，从而实现有效的时间跟踪和资源管理。
## 经常问的问题
### 我可以将 Aspose.Tasks for .NET 与其他项目管理工具一起使用吗？
是的，Aspose.Tasks for .NET 旨在与流行的项目管理工具配合使用，并支持各种文件格式。
### 我可以使用 Aspose.Tasks 管理的资源和任务数量是否有限制？
Aspose.Tasks可以处理不同规模的项目，并且对资源和任务的数量没有严格的限制。
### 对于与 Aspose.Tasks for .NET 相关的任何问题或查询，如何获得支持？
如需支持，请访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)与社区联系并获得帮助。
### 我可以在购买之前试用 Aspose.Tasks for .NET 吗？
是的，您可以通过访问 Aspose.Tasks for .NET 来探索 Aspose.Tasks for .NET 的功能[免费试用](https://releases.aspose.com/).
### 在哪里可以购买 Aspose.Tasks for .NET 的许可证？
您可以购买 Aspose.Tasks for .NET 的许可证[这里](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
