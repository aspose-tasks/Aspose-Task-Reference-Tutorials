---
title: Manage MS Project Group Criteria with Aspose.Tasks
linktitle: Managing Group Criterion Collection in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage Group Criterion MS Project collection using Aspose.Tasks for .NET. Step-by-step guide for developers.
type: docs
weight: 28
url: /net/tasks-project-management/group-criterion-collection/
---
## Introduction
Aspose.Tasks for .NET is a powerful API that allows developers to work with Microsoft Project files programmatically. In this tutorial, we'll explore how to manage the Group Criterion collection within MS Project using Aspose.Tasks.

## Prerequisites

Before we begin, ensure you have the following:

1. Aspose.Tasks for .NET: Make sure you have the Aspose.Tasks library installed in your .NET project. You can download it from [here](https://releases.aspose.com/tasks/net/).

2. Microsoft Project File: Have a Microsoft Project file (MPP) ready to work with.

## Import Namespaces

Firstly, you need to import the necessary namespaces to your C# code. This step is crucial for accessing the functionalities provided by Aspose.Tasks.

```csharp
using System;
using System.Collections.Generic;
using NUnit.Framework;

```

## Step 1: Load the Project File

Initialize a `Project` object by loading the MPP file. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Step 2: Access Group Criteria

Retrieve the group from the project and access its criteria.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Step 3: Iterate Over Group Criteria

Loop through each criterion in the group and display its properties.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Step 4: Clear Group Criteria

Clear existing group criteria if it's not read-only.

```csharp
group.GroupCriteria.Clear();
```

## Step 5: Add New Criterion

Create a new group criterion and add it to the group.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Step 6: Copy Criteria to Another Group

Copy the criteria from one group to another.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Conclusion

In this tutorial, we've learned how to manage the Group Criterion MS Project collection using Aspose.Tasks for .NET. By following these steps, you can effectively manipulate group criteria within your Microsoft Project files programmatically.

## FAQ's

### Q1: Is Aspose.Tasks compatible with all versions of Microsoft Project?

A: Yes, Aspose.Tasks supports Microsoft Project files of various versions, including 2003, 2007, 2010, 2013, and 2016.

### Q2: Can I apply multiple criteria to a single group?

A: Absolutely, you can add multiple criteria to a group by iterating through each and adding them accordingly.

### Q3: Is there a trial version available for Aspose.Tasks?

A: Yes, you can obtain a free trial of Aspose.Tasks from [here](https://releases.aspose.com/).

### Q4: Where can I find documentation for Aspose.Tasks?

A: You can refer to the documentation [here](https://reference.aspose.com/tasks/net/).

### Q5: How can I get support if I encounter any issues?

A: If you have any questions or face any issues, you can seek support from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
