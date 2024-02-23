---
title: 使用 Aspose.Tasks 掌握 MS 项目费率
linktitle: Aspose.Tasks 中的费率收集
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 MS Project 文件中的费率。有效资源管理的分步教程。
type: docs
weight: 11
url: /zh/net/rate-recurring-tasks/rate-collection/
---
## 介绍
欢迎来到我们关于使用 Aspose.Tasks for .NET 在 MS Project 中管理费率的教程！在本指南中，我们将引导您完成使用 Aspose.Tasks 处理 MS Project 文件中的费率的过程。无论您是经验丰富的开发人员还是刚刚开始 .NET 开发，本教程都将为您提供有效处理项目中的速率的分步说明。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
### 1.安装Visual Studio
确保您的系统上安装了 Visual Studio。如果您还没有下载，可以从网站下载。
### 2..NET 的 Aspose.Tasks
从以下位置下载并安装 Aspose.Tasks for .NET 库[网站](https://releases.aspose.com/tasks/net/).
### 3. C#和.NET基础知识
熟悉 C# 编程语言和 .NET 框架基础知识，以便更好地理解本教程中提供的代码示例。
## 导入命名空间
在您的 C# 项目中，导入必要的命名空间以使用 Aspose.Tasks 功能：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
现在，让我们将每个示例分解为多个步骤：
## 第 1 步：加载 MS 项目文件
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
在这里，我们创建一个新的`Project`通过加载现有的 MS Project 文件来创建对象。
## 第 2 步：添加资源并设置工时和费率
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
我们向项目添加一个新资源，将其类型设置为工时、工时量和标准费率。
## 步骤 3：向资源添加费率
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
我们向资源添加费率，指定开始日期和结束日期、标准费率和费率格式。
## 第 4 步：打印费率信息
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
此步骤打印有关与资源关联的费率的信息。
## 第 5 步：更新费率
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
我们更新特定费率的结束日期。
## 第 6 步：删除费率
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
此步骤删除特定类型的所有费率。
## 第 7 步：迭代剩余利率
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
最后，我们迭代删除后的剩余速率。
## 结论
总之，本教程为您提供了使用 Aspose.Tasks for .NET 管理 MS Project 文件中的费率的综合指南。通过遵循本教程中概述的分步说明，您可以有效地处理项目中的费率，确保准确的资源管理。
## 常见问题解答
### 问：我可以将 Aspose.Tasks for .NET 与其他项目管理软件一起使用吗？
答：是的，Aspose.Tasks for .NET 支持与各种项目管理软件集成，包括 MS Project、Primavera 等。
### 问：Aspose.Tasks for .NET 是否与不同版本的 MS Project 文件兼容？
答：当然，Aspose.Tasks for .NET 支持处理不同版本的 MS Project 文件，确保灵活性和兼容性。
### 问：Aspose.Tasks for .NET 是否提供文档和支持？
答：是的，您可以在 Aspose.Tasks 上找到全面的文档并访问支持论坛[网站](https://reference.aspose.com/tasks/net/).
### 问：我可以在购买前试用 Aspose.Tasks for .NET 吗？
答：是的，您可以免费试用 Aspose.Tasks for .NET 来评估其功能以及与您的要求的兼容性。
### 问：如何购买 Aspose.Tasks for .NET 的许可证？
答：您可以从 Aspose.Tasks for .NET 购买许可证[网站](https://purchase.aspose.com/temporary-license/)，它提供了灵活的许可选项来满足您的需求。