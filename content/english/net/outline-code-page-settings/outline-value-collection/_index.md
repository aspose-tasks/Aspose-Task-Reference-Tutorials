---
title: Manage MS Project Outline Values with Aspose.Tasks
linktitle: Collection of Outline Values in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage outline values in Microsoft Project files using Aspose.Tasks for .NET. Step-by-step tutorial with code examples.
type: docs
weight: 17
url: /net/outline-code-page-settings/outline-value-collection/
---
## Introduction
Aspose.Tasks for .NET provides a comprehensive set of features to interact with Microsoft Project files. One such feature is the ability to manage outline values within a project. In this tutorial, we will explore how to collect and manipulate outline values using Aspose.Tasks for .NET.
## Prerequisites
Before we begin, ensure you have the following:
1. Aspose.Tasks for .NET: You can download the library from [here](https://releases.aspose.com/tasks/net/).
2. Development Environment: Make sure you have a suitable IDE installed, such as Visual Studio.
3. Basic Knowledge of C#: Familiarity with C# programming language will be beneficial.
## Import Namespaces
In your C# code file, import the necessary namespaces to access Aspose.Tasks classes and methods:
```csharp
using System;

```
Let's break down the provided example into multiple steps:
## Step 1: Load a Project File
Firstly, initialize a `Project` object by loading an existing Microsoft Project file:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Step 2: Clear Existing Outline Values
Next, clear any existing outline values from the project:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Step 3: Define New Outline Code
Now, define a new outline code with a description and value:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Step 4: Update Outline Value
Update the value of the outline code:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Step 5: Iterate Over Outline Values
Iterate through the outline values and print their details:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Step 6: Manipulate Outline Values
Perform operations like removing, inserting, and copying outline values as needed:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Conclusion
In this tutorial, we learned how to work with outline values in Microsoft Project files using Aspose.Tasks for .NET. By following the provided steps, you can efficiently manage outline values within your projects, enabling greater control and flexibility.
## FAQ's
### Q: Can I manipulate multiple outline codes simultaneously?
A: Yes, you can define and manipulate multiple outline codes within a project using Aspose.Tasks.
### Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?
A: Yes, Aspose.Tasks supports various versions of Microsoft Project files, including MPP and XML formats.
### Q: How can I handle errors while working with outline values?
A: You can implement error handling mechanisms such as try-catch blocks to manage exceptions gracefully.
### Q: Can I customize the appearance of outline values in my project?
A: Yes, Aspose.Tasks provides extensive APIs to customize the appearance and behavior of outline values according to your requirements.
### Q: Where can I find additional resources and support for Aspose.Tasks?
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support and explore the [documentation](https://reference.aspose.com/tasks/net/) for detailed information on APIs and features.
