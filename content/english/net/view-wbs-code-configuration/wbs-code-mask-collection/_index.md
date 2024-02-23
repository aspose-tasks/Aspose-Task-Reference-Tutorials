---
title: Mastering WBS Code Masks with Aspose.Tasks for .NET
linktitle: Collection of WBS Code Masks in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Enhance project management with Aspose.Tasks for .NET. Learn to create, manage, and transfer WBS Code Masks effortlessly in this comprehensive tutorial.
type: docs
weight: 15
url: /net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Introduction
In the dynamic world of project management, organizing tasks efficiently is crucial. Aspose.Tasks for .NET provides a powerful solution to manage project work breakdown structure (WBS) codes effortlessly. In this tutorial, we will delve into the Collection of WBS Code Masks, exploring how to implement and manipulate them using Aspose.Tasks for .NET.
## Prerequisites
Before we embark on this coding journey, ensure you have the following prerequisites in place:
- A working knowledge of C# programming language.
- Aspose.Tasks for .NET installed in your development environment. If not, download it [here](https://releases.aspose.com/tasks/net/).
- A code editor like Visual Studio for a seamless coding experience.
## Import Namespaces
To get started, let's import the necessary namespaces:
```csharp
    using System;
    using System.Collections.Generic;
    
```
## 1. Initialize Project and WBS Code Definition
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Define WBS Code Masks
Clear any existing code masks and add new ones:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Display Code Masks Information
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Add Tasks to the Project
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Retrieve Task Information
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipulate Code Masks
Remove a code mask and ensure it's removed:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Copy Code Masks to Another Project
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Display Code Masks in Another Project
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Add Tasks to the Other Project
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Display WBS Codes in the Other Project
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Conclusion
With Aspose.Tasks for .NET, managing WBS codes becomes an effortless task. This tutorial covered the creation, manipulation, and transfer of WBS Code Masks, providing you with a comprehensive guide to enhance your project management experience.
## FAQs
### Q: Can I use Aspose.Tasks for .NET with other programming languages?
A: Aspose.Tasks primarily supports .NET languages, but you can explore interoperability options with other languages.
### Q: Is there a trial version available for Aspose.Tasks for .NET?
A: Yes, you can download the trial version [here](https://releases.aspose.com/).
### Q: How do I seek help or report issues with Aspose.Tasks for .NET?
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for support and discussions.
### Q: What is the purpose of WBS codes in project management?
A: WBS codes help organize and structure project tasks hierarchically, providing a systematic approach to project planning.
### Q: Can I customize the format of WBS codes in Aspose.Tasks for .NET?
A: Absolutely, you have full control over the format and structure of WBS codes using Aspose.Tasks for .NET.
