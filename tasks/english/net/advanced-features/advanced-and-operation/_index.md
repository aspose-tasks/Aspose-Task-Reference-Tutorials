---
title: Advanced AND Operation in Aspose.Tasks
linktitle: Advanced AND Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to perform advanced AND operations in Aspose.Tasks for .NET to efficiently filter project tasks based on multiple criteria.
weight: 10
url: /net/advanced-features/advanced-and-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Advanced AND Operation in Aspose.Tasks

## Introduction

In this tutorial, we will delve into the advanced AND operation in Aspose.Tasks for .NET, a powerful tool for managing tasks and projects. We will explore how to filter project tasks based on multiple conditions using the `Util.And` class.

## Prerequisites

Before we begin, ensure you have the following:

1. Basic knowledge of C# programming language.
2. Installed Aspose.Tasks for .NET. If not, you can download it from [here](https://releases.aspose.com/tasks/net/).
3. Integrated development environment (IDE) such as Visual Studio.

## Import Namespaces

First, let's import the necessary namespaces to our C# project:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Step 1: Initialize Project and Collect Tasks

Begin by initializing a new Aspose.Tasks project and collecting all tasks within it:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Step 2: Define Filter Conditions

Next, define the filter conditions. For this example, we'll create two conditions: one to filter summary tasks and another to filter non-null tasks:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Step 3: Combine Conditions with AND Operation

Now, combine the conditions using the `Util.And` class to create a composite condition:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Step 4: Apply Condition and Filter Tasks

Apply the combined condition to the collected tasks and filter them accordingly:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Step 5: Output Filtered Tasks

Finally, output the filtered tasks:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Conclusion

In this tutorial, we learned how to perform advanced AND operations in Aspose.Tasks for .NET. By combining conditions using the `Util.And` class, we can filter tasks efficiently based on multiple criteria.

## FAQ's

### Q1: What is Aspose.Tasks for .NET?

A: Aspose.Tasks for .NET is a robust API that allows developers to manipulate Microsoft Project files programmatically in .NET applications.

### Q2: Can I apply more than two conditions using Util.And?

A: Yes, Util.And can be used to combine any number of conditions to create complex filtering criteria.

### Q3: Is there a free trial available for Aspose.Tasks for .NET?

A: Yes, you can download a free trial from [here](https://releases.aspose.com/).

### Q4: Where can I find documentation for Aspose.Tasks for .NET?

A: You can find the documentation [here](https://reference.aspose.com/tasks/net/).

### Q5: How can I get support for Aspose.Tasks for .NET?

A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
