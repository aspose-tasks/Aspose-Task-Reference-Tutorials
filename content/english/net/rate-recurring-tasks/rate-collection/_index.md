---
title: Master MS Project Rates with Aspose.Tasks
linktitle: Collection of Rates in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage rates in MS Project files using Aspose.Tasks for .NET. Step-by-step tutorial for effective resource management.
type: docs
weight: 11
url: /net/rate-recurring-tasks/rate-collection/
---
## Introduction
Welcome to our tutorial on managing rates in MS Project using Aspose.Tasks for .NET! In this guide, we'll walk you through the process of working with rates in your MS Project files using Aspose.Tasks. Whether you're a seasoned developer or just getting started with .NET development, this tutorial will provide you with step-by-step instructions to effectively handle rates within your projects.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites:
### 1. Visual Studio Installed
Ensure you have Visual Studio installed on your system. You can download it from the website if you haven't already.
### 2. Aspose.Tasks for .NET
Download and install the Aspose.Tasks for .NET library from the [website](https://releases.aspose.com/tasks/net/).
### 3. Basic Knowledge of C# and .NET
Familiarize yourself with C# programming language and the .NET framework basics to better understand the code examples provided in this tutorial.
## Import Namespaces
In your C# project, import the necessary namespaces to use Aspose.Tasks functionalities:
```csharp
using System;
using System.Collections.Generic;

```
Now, let's break down each example into multiple steps:
## Step 1: Load an MS Project File
```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
Here, we create a new `Project` object by loading an existing MS Project file.
## Step 2: Add a Resource and Set Work and Rates
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
We add a new resource to the project, set its type as work, work amount, and standard rate.
## Step 3: Add Rates to the Resource
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
We add rates to the resource specifying the start and end dates, standard rate, and rate format.
## Step 4: Print Rates Information
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
This step prints information about the rates associated with the resource.
## Step 5: Update a Rate
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
We update a specific rate's end date.
## Step 6: Remove Rates
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
This step removes all rates of a specific type.
## Step 7: Iterate Over Remaining Rates
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
Finally, we iterate over the remaining rates after removal.
## Conclusion
In conclusion, this tutorial provided you with a comprehensive guide on managing rates in MS Project files using Aspose.Tasks for .NET. By following the step-by-step instructions outlined in this tutorial, you can efficiently handle rates within your projects, ensuring accurate resource management.
## FAQ's
### Q: Can I use Aspose.Tasks for .NET with other project management software?
A: Yes, Aspose.Tasks for .NET supports integration with various project management software, including MS Project, Primavera, and more.
### Q: Is Aspose.Tasks for .NET compatible with different versions of MS Project files?
A: Absolutely, Aspose.Tasks for .NET supports working with MS Project files of different versions, ensuring flexibility and compatibility.
### Q: Does Aspose.Tasks for .NET offer documentation and support?
A: Yes, you can find comprehensive documentation and access to support forums on the Aspose.Tasks  [website](https://reference.aspose.com/tasks/net/).
### Q: Can I try Aspose.Tasks for .NET before purchasing?
A: Yes, you can avail of a free trial of Aspose.Tasks for .NET to evaluate its features and compatibility with your requirements.
### Q: How can I purchase a license for Aspose.Tasks for .NET?
A: You can purchase a license for Aspose.Tasks for .NET from the [website](https://purchase.aspose.com/temporary-license/), which provides flexible licensing options to suit your needs.
