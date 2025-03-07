---
title: Aspose.Tasks 中风险项的统计
linktitle: Aspose.Tasks 中风险项的统计
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 释放 MS Project 文件中风险分析的强大功能。轻松获得洞察、减少不确定性并推动项目成功。
weight: 21
url: /zh/net/resource-risk-analysis/risk-item-statistics/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中风险项的统计

## 介绍
您是否希望使用 Aspose.Tasks for .NET 来增强您的项目管理能力？通过我们有关获取 MS Project 文件中风险项目统计信息的分步教程，深入了解风险分析领域。通过利用 Aspose.Tasks 的强大功能，您可以获得对项目不确定性的宝贵见解，并做出明智的决策以有效降低风险。
## 先决条件
在我们开始这一旅程之前，请确保您具备以下先决条件：
1.  Aspose.Tasks for .NET Library：从以下位置下载并安装该库：[.NET 文档的 Aspose.Tasks](https://reference.aspose.com/tasks/net/)。该库为您提供了强大的工具，用于以编程方式操作 MS Project 文件。
2. .NET 开发环境：设置您的 .NET 开发环境，包括 Visual Studio 或您选择的任何其他 IDE，以促进 Aspose.Tasks 无缝集成到您的项目中。

## 导入命名空间
将必要的命名空间合并到您的项目中以利用 Aspose.Tasks 的功能：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## 第 1 步：定义数据目录
```csharp
String DataDir = "Your Document Directory";
```
确保更换`"Your Document Directory"`以及 MS Project 文件所在的文档目录的路径。
## 步骤 2：配置风险分析设置
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
调整`IterationsCount`根据您的项目需求参数来控制风险分析的精度。
## 第 3 步：加载 MS 项目文件
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
将所需的 MS Project 文件加载到`project`为进一步分析的对象。
## 第 4 步：定义任务并初始化风险模式
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
指定风险分析任务，并使用适当的参数（例如分布类型、乐观和悲观持续时间以及置信水平）配置风险模式。
## 第五步：分析项目风险
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
使用定义的设置和项目数据启动风险分析过程。
## 第 6 步：检索并显示统计数据
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
检索并显示与 MS Project 文件中的风险项目相关的各种统计指标，包括预期值、标准差、百分位数、最小值和最大值。

## 结论
总之，使用 Aspose.Tasks for .NET 掌握 MS Project 文件中的风险分析为项目经理和利益相关者开辟了新的可能性领域。通过遵循我们的综合教程，您可以自信地应对不确定性，确保项目取得成功。
## 常见问题解答
### 我可以将 Aspose.Tasks 与其他 .NET 库集成以实现扩展功能吗？
绝对地！ Aspose.Tasks 与各种 .NET 库无缝集成，允许您根据项目需求扩展其功能。
### Aspose.Tasks for .NET 是否有试用版？
是的，您可以通过访问来探索 Aspose.Tasks 的功能[免费试用](https://releases.aspose.com/)可在我们的网站上找到。
### Aspose.Tasks 的更新和增强功能多久发布一次？
我们努力通过定期发布更新和增强功能来不断改进 Aspose.Tasks，确保您始终能够访问最新的功能和优化。
### 我可以获得 Aspose.Tasks 的技术支持吗？
当然！我们的专业支持团队随时可以在[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)帮助您解决在实施过程中可能遇到的任何疑问或挑战。
### 你们为短期项目提供临时许可证吗？
是的，如果您需要 Aspose.Tasks 进行短期项目，您可以利用我们的便利[临时执照](https://purchase.aspose.com/temporary-license/)无需任何长期承诺即可满足您的许可需求的选项。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
