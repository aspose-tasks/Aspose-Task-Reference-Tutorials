---
title: 在 Aspose.Tasks 中管理 MS 项目属性集合
linktitle: 管理 Aspose.Tasks 中的扩展属性集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效管理 MS Project 扩展属性。通过分步指导无缝操作任务属性。
type: docs
weight: 12
url: /zh/net/tasks-project-management/extended-attribute-collection/
---
## 介绍
您是否希望使用 Aspose.Tasks for .NET 高效管理 MS Project 扩展属性？在本教程中，我们将逐步指导您完成该过程。让我们深入了解吧！
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. Visual Studio：在您的系统上安装 Visual Studio。
2.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[这里](https://releases.aspose.com/tasks/net/).
3. C# 基础知识：熟悉 C# 编程语言基础知识。

## 导入命名空间
首先将必要的命名空间导入到您的项目中：
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 第 1 步：加载项目文件
首先，使用以下代码片段加载 MS Project 文件：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 第2步：访问任务和扩展属性
访问特定任务及其扩展属性：
```csharp
var task = project.RootTask.Children.GetById(1);
```
## 第三步：清除扩展属性
如果需要，清除现有的扩展属性：
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## 步骤 4：创建扩展属性定义
为新的扩展属性创建定义：
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## 第 5 步：迭代任务扩展属性
迭代任务扩展属性：
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## 第6步：添加扩展属性
向任务添加新的扩展属性：
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## 第 7 步：使用扩展属性
根据需要对扩展属性进行操作。
## 第8步：删除扩展属性
通过索引或有条件地删除扩展属性：
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## 第 9 步：将属性复制到另一个任务
将属性复制到同一或不同项目中的另一个任务：
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## 结论
使用 Aspose.Tasks for .NET 可以无缝管理 MS Project 扩展属性集合。通过遵循本教程中概述的步骤，您可以有效地处理扩展属性，从而增强您的项目管理能力。
## 常见问题解答
### 问：我可以跨多个项目操纵扩展属性吗？
答：是的，您可以使用 Aspose.Tasks for .NET 在不同项目的任务之间复制扩展属性。
### 问：每个任务的扩展属性数量有限制吗？
答：Aspose.Tasks for .NET 对每个任务的扩展属性数量没有固有的限制。
### 问：我可以创建自定义扩展属性字段吗？
答：当然！ Aspose.Tasks for .NET 允许您定义适合您的项目需求的自定义扩展属性字段。
### 问：Aspose.Tasks for .NET 支持读写各种版本的 MS Project 文件吗？
答：是的，Aspose.Tasks for .NET 支持跨不同版本的 MS Project 文件格式。
### 问：Aspose.Tasks for .NET 有试用版吗？
答：是的，您可以从以下位置下载免费试用版：[这里](https://releases.aspose.com/).