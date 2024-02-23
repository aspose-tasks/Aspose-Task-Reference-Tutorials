---
title: 使用 Aspose.Tasks 管理 MS 项目组标准
linktitle: 在 Aspose.Tasks 中管理组标准集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 Group Criterion MS Project 集合。开发人员的分步指南。
type: docs
weight: 28
url: /zh/net/tasks-project-management/group-criterion-collection/
---
## 介绍
Aspose.Tasks for .NET 是一个功能强大的 API，允许开发人员以编程方式处理 Microsoft Project 文件。在本教程中，我们将探索如何使用 Aspose.Tasks 管理 MS Project 中的 Group Criterion 集合。

## 先决条件

在我们开始之前，请确保您具备以下条件：

1.  Aspose.Tasks for .NET：确保您的.NET项目中安装了Aspose.Tasks库。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).

2. Microsoft Project 文件：准备好可供使用的 Microsoft Project 文件 (MPP)。

## 导入命名空间

首先，您需要将必要的命名空间导入到 C# 代码中。此步骤对于访问 Aspose.Tasks 提供的功能至关重要。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## 第 1 步：加载项目文件

初始化一个`Project`通过加载 MPP 文件来获取对象。 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## 第 2 步：访问组标准

从项目中检索组并访问其标准。

```csharp
var group = project.TaskGroups.ToList()[0];
```

## 第 3 步：迭代组标准

循环遍历组中的每个条件并显示其属性。

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## 第 4 步：明确小组标准

如果现有组条件不是只读的，请清除它。

```csharp
group.GroupCriteria.Clear();
```

## 第 5 步：添加新标准

创建一个新的组标准并将其添加到组中。

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

## 第 6 步：将条件复制到另一个组

将条件从一组复制到另一组。

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### 结论

在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 管理 Group Criterion MS Project 集合。通过执行这些步骤，您可以以编程方式有效地操作 Microsoft Project 文件中的组条件。

## 常见问题解答

### Q1：Aspose.Tasks 是否与所有版本的 Microsoft Project 兼容？

答：是的，Aspose.Tasks支持各种版本的Microsoft Project文件，包括2003、2007、2010、2013和2016。

### Q2：我可以对一个组应用多个标准吗？

答：当然，您可以通过迭代每个条件并相应地添加它们来将多个条件添加到组中。

### Q3：Aspose.Tasks 有试用版吗？

答：是的，您可以从以下位置获取 Aspose.Tasks 的免费试用版：[这里](https://releases.aspose.com/).

### Q4：在哪里可以找到 Aspose.Tasks 的文档？

答：可以参考文档[这里](https://reference.aspose.com/tasks/net/).

### Q5：如果我遇到任何问题，如何获得支持？

答：如果您有任何疑问或遇到任何问题，您可以从 Aspose.Tasks 论坛寻求支持。[这里](https://forum.aspose.com/c/tasks/15).