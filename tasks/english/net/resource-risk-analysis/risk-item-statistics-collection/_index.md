---
title: Collect MS Project Risk Item Statistics in Aspose.Tasks
linktitle: Collection of Risk Item Statistics in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to collect risk item statistics from MS Project files using Aspose.Tasks for .NET. Enhance your project management capabilities.
weight: 22
url: /net/resource-risk-analysis/risk-item-statistics-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Collect MS Project Risk Item Statistics in Aspose.Tasks

## Introduction
In this tutorial, we'll explore how to collect risk item statistics from MS Project files using Aspose.Tasks for .NET. This library provides powerful functionalities to analyze project data, including risk assessment and statistical analysis.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Aspose.Tasks for .NET: Download and install the Aspose.Tasks library. You can get it from the [download page](https://releases.aspose.com/tasks/net/).
2. Development Environment: Have a development environment set up for .NET programming.

## Import Namespaces
Before you start coding, make sure to import the necessary namespaces in your project:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Step 1: Load the Project File
First, you need to load the MS Project file into your application. Here's how you can achieve it:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Step 2: Define Risk Analysis Settings
Initialize the risk analysis settings, including the number of iterations, as shown below:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Step 3: Initialize a Risk Pattern
Set up a risk pattern for the analysis, specifying distribution type, optimistic and pessimistic percentages, and confidence level:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Step 4: Perform Risk Analysis
Instantiate the `RiskAnalyzer` class and analyze the project:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Step 5: Retrieve Statistics
Retrieve the risk item statistics, such as early finish, from the analysis result:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Step 6: Print Statistics
Iterate over the statistics and print the details:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    // Print other relevant statistics...
}
```

## Conclusion
In this tutorial, we've learned how to utilize Aspose.Tasks for .NET to collect risk item statistics from MS Project files. By following these steps, you can effectively analyze project data and assess potential risks, aiding in better decision-making and project management.

## FAQ's
### Q: Can Aspose.Tasks handle large MS Project files?
A: Yes, Aspose.Tasks is capable of handling large MS Project files efficiently, offering reliable performance and scalability.
### Q: Does Aspose.Tasks support other project file formats besides .mpp?
A: Yes, Aspose.Tasks supports various project file formats, including XML and MPT.
### Q: Is Aspose.Tasks suitable for enterprise-level project management applications?
A: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise-level project management applications, providing robust features and extensive documentation.
### Q: Can I customize risk analysis settings in Aspose.Tasks?
A: Yes, Aspose.Tasks offers flexibility in configuring risk analysis settings to suit your specific project requirements and scenarios.
### Q: Is technical support available for Aspose.Tasks users?
A: Yes, Aspose.Tasks users can access technical support through the Aspose [forums](https://forum.aspose.com/c/tasks/15), where they can ask questions, report issues, and interact with the community.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
