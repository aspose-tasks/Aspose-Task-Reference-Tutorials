---
title: 在 Aspose.Tasks 中掌握 MS 项目的扩展属性定义
linktitle: Aspose.Tasks 中扩展属性定义的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 中管理扩展属性定义。轻松定制和增强您的项目数据。
type: docs
weight: 14
url: /zh/net/tasks-project-management/extended-attribute-definition-collection/
---
## 介绍
在本教程中，我们将探索如何使用 Aspose.Tasks for .NET 在 Microsoft Project 中使用扩展属性定义。扩展属性提供了一种灵活的方式来自定义和增强项目数据，允许用户添加默认提供的标准字段之外的其他字段。借助 Aspose.Tasks，您可以轻松管理这些扩展属性，以满足您的项目管理需求。
## 先决条件
在继续之前，请确保您已安装以下先决条件：
- [.NET框架](https://dotnet.microsoft.com/download)
- .NET 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).

## 导入命名空间
首先，您需要导入必要的命名空间来访问 .NET 项目中的 Aspose.Tasks 类和方法。按着这些次序：
## 第 1 步：打开您的 .NET 项目
在您首选的 IDE（例如 Visual Studio）中打开 .NET 项目。
## 步骤2：添加Aspose.Tasks命名空间
在代码文件的开头添加以下行以导入 Aspose.Tasks 命名空间：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

现在，让我们将提供的代码示例分解为多个步骤，以便全面理解：
## 第 1 步：加载项目文件
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 步骤 2：清除现有的扩展属性定义（可选）
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## 步骤 3：为任务创建并添加扩展属性定义
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## 步骤 4：迭代任务扩展属性
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## 步骤 5：创建并添加资源的扩展属性定义
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## 步骤 6：插入资源扩展属性定义
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## 步骤 7：通过索引删除扩展属性
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## 结论
在本教程中，我们介绍了使用 Aspose.Tasks for .NET 在 Microsoft Project 中处理扩展属性定义的基础知识。通过执行这些步骤，您可以有效地管理和自定义扩展属性，以满足您的项目管理要求。
## 常见问题解答
### 问：我可以修改现有的扩展属性定义吗？
答：是的，您可以根据需要修改现有的扩展属性定义或创建新的扩展属性定义。
### 问：Microsoft Project 的所有版本都支持扩展属性吗？
答：是的，大多数版本的 Microsoft Project（包括最新版本）都支持扩展属性。
### 问：我可以使用扩展属性来计算自定义字段吗？
答：当然，扩展属性可用于根据您定义的特定条件计算自定义字段。
### 问：Aspose.Tasks 与其他 .NET 框架兼容吗？
答：Aspose.Tasks 与各种.NET 框架兼容，确保灵活性和易于集成。
### 问：在哪里可以找到有关 Aspose.Tasks 的更多资源和支持？
答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求支持并探索文档[这里](https://reference.aspose.com/tasks/net/).