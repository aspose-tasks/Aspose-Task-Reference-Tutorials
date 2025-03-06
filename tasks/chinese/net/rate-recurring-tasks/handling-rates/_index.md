---
title: 使用 Aspose.Tasks for .NET 处理 MS 项目费率
linktitle: 在 Aspose.Tasks 中处理费率
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 轻松掌握管理 MS 项目费率。高效地自动化任务，使项目工作流程更加顺畅。
type: docs
weight: 10
url: /zh/net/rate-recurring-tasks/handling-rates/
---
## 介绍
欢迎来到我们关于使用 Aspose.Tasks for .NET 处理 MS 项目费率的教程！在本指南中，我们将逐步引导您完成整个过程，确保您可以有效地管理 MS Project 文档中的费率。 Aspose.Tasks for .NET 提供了以编程方式操作 MS Project 文件的强大功能，使您可以轻松简化项目管理任务。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
1. 已安装 Visual Studio：确保您的系统上安装了 Visual Studio。
2.  Aspose.Tasks for .NET 库：下载并安装 Aspose.Tasks for .NET 库。你可以找到下载链接[这里](https://releases.aspose.com/tasks/net/).
3. C# 的基本了解：熟悉 C# 编程语言基础知识。
## 导入命名空间
首先，您需要将必要的命名空间导入到您的 C# 项目中。这些命名空间将提供对处理 MS 项目费率所需的类和方法的访问。
## 第1步：导入Aspose.Tasks命名空间
```csharp
using Aspose.Tasks;
using System;

```
现在，让我们将提供的示例分解为多个步骤并彻底理解每个步骤。
## 第 1 步：加载项目文件
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
在此步骤中，我们将使用以下命令加载名为“Project1.mpp”的现有 MS Project 文件`Project`由Aspose.Tasks提供的类。
## 第 2 步：添加资源并设置工作
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
在这里，我们向项目添加一个名为“Resource 1”的新资源，并将其类型设置为“Work”。我们还定义了该资源的工作持续时间。
## 第 3 步：设定标准费率
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
在此步骤中，我们将资源的标准费率设置为每小时 20 美元。
## 第 4 步：定义费率期间
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
在这里，我们定义资源的费率周期。费率1的设定时间为2019年1月1日至2019年11月11日，指定了标准费率和加班费率。
## 第 5 步：添加另一个费率期间
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
在最后一步中，我们添加了另一个费率期限，从 2019 年 11 月 12 日到 2019 年 12 月 31 日，并定义了不同的标准费率和每次使用成本。
恭喜！您已使用 Aspose.Tasks for .NET 成功处理了 MS Project Rates。
## 结论
以编程方式管理 MS 项目费率可以显着增强您的项目管理工作流程。借助 Aspose.Tasks for .NET，您可以高效地自动执行速率处理任务，从而节省时间和资源。
## 常见问题解答
### 问：Aspose.Tasks 可以处理复杂的项目结构吗？
答：是的，Aspose.Tasks 提供了强大的功能来轻松处理复杂的项目结构。
### 问：Aspose.Tasks 是否与所有版本的 MS Project 文件兼容？
答：Aspose.Tasks支持各种版本的MS Project文件，确保不同平台的兼容性。
### 问：我可以使用 Aspose.Tasks 修改 MS Project 文件中的现有费率吗？
答：当然！ Aspose.Tasks 允许您修改现有费率、添加新费率并动态管理它们。
### 问：Aspose.Tasks 是否支持自定义费率计算？
答：是的，您可以使用 Aspose.Tasks 实现自定义费率计算，以满足特定的项目要求。
### 问：Aspose.Tasks 用户是否有社区论坛或支持？
答： 是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求帮助并与其他用户互动。