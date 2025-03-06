---
title: Types of Resources in Aspose.Tasks
linktitle: Types of Resources in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to work with different types of resources in Aspose.Tasks for .NET, including work, material, and cost resources, through a step-by-step tutorial.
weight: 14
url: /net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Types of Resources in Aspose.Tasks

## Introduction
Aspose.Tasks for .NET is a powerful library that allows developers to work with Microsoft Project files programmatically. Whether you're managing tasks, resources, or schedules, Aspose.Tasks simplifies the process by providing a comprehensive set of APIs. In this tutorial, we'll delve into the different types of resources that you can utilize within your projects using Aspose.Tasks for .NET.
## Prerequisites
Before we begin, ensure you have the following:
1. Visual Studio: Install Visual Studio, a powerful integrated development environment (IDE) for .NET development.
2. Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from [here](https://releases.aspose.com/tasks/net/).
3. Basic Knowledge of C#: Familiarize yourself with C#, the programming language used for .NET development.

## Import Namespaces
First, let's import the necessary namespaces to access the functionalities of Aspose.Tasks for .NET:
```csharp
    
```

## Step 1: Create a new Project instance
```csharp
var project = new Project();
```
This line initializes a new Project object, which serves as the container for all project-related data and operations.
## Step 2: Add a Work Resource
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Here, we create a new work resource named "Work resource" and specify its type as ResourceType.Work.
## Step 3: Add a Material Resource
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
This step adds a material resource named "Material resource" with its type set to ResourceType.Material. Additionally, we specify the material label as "kg" to indicate the unit of measurement.
## Step 4: Add a Cost Resource
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Finally, we add a cost resource named "Cost resource" and set its type as ResourceType.Cost. Additionally, we set the cost value to 59.99, representing the monetary value associated with this resource.

## Conclusion
In this tutorial, we've explored how to work with different types of resources in Aspose.Tasks for .NET, including work, material, and cost resources. By following the step-by-step guide, you can effectively manage resources within your projects programmatically.
## FAQ's
### Q: Can I use Aspose.Tasks for .NET with other project management software formats?
A: Yes, Aspose.Tasks supports various formats, including Microsoft Project (MPP), Primavera P6, and more.
### Q: Is there a free trial available for Aspose.Tasks for .NET?
A: Yes, you can access the free trial [here](https://releases.aspose.com/).
### Q: How can I get technical support for Aspose.Tasks for .NET?
A: You can visit the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15) for technical assistance.
### Q: Can I purchase a temporary license for Aspose.Tasks for .NET?
A: Yes, you can purchase a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Q: Does Aspose.Tasks for .NET provide documentation for reference?
A: Yes, you can find the documentation [here](https://reference.aspose.com/tasks/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
