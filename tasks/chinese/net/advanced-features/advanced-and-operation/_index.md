---
title: Aspose.Tasks 中的高级 AND 运算
linktitle: Aspose.Tasks 中的高级 AND 运算
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中执行高级 AND 运算，以根据多个条件有效过滤项目任务。
weight: 10
url: /zh/net/advanced-features/advanced-and-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的高级 AND 运算

## 介绍

在本教程中，我们将深入研究 Aspose.Tasks for .NET 中的高级 AND 操作，这是一个用于管理任务和项目的强大工具。我们将探索如何使用以下方法根据多个条件过滤项目任务`Util.And`班级。

## 先决条件

在我们开始之前，请确保您具备以下条件：

1. C# 编程语言的基础知识。
2. 安装了 .NET 的 Aspose.Tasks。如果没有，您可以从以下位置下载[这里](https://releases.aspose.com/tasks/net/).
3. 集成开发环境 (IDE)，例如 Visual Studio。

## 导入命名空间

首先，让我们将必要的命名空间导入到我们的 C# 项目中：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## 第1步：初始化项目并收集任务

首先初始化一个新的 Aspose.Tasks 项目并收集其中的所有任务：

```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## 第2步：定义过滤条件

接下来，定义过滤条件。对于本示例，我们将创建两个条件：一个用于过滤摘要任务，另一个用于过滤非空任务：

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## 步骤 3：使用 AND 运算组合条件

现在，使用以下组合条件`Util.And`类来创建复合条件：

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 步骤 4：应用条件和过滤任务

将组合条件应用于收集的任务并相应地过滤它们：

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## 第5步：输出过滤后的任务

最后输出过滤后的任务：

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    //可以在这里进行额外的处理
}
```

## 结论

在本教程中，我们学习了如何在 Aspose.Tasks for .NET 中执行高级 AND 运算。通过组合条件使用`Util.And`类中，我们可以根据多个标准有效地过滤任务。

## 常见问题解答

### Q1：什么是 Aspose.Tasks for .NET？

答：Aspose.Tasks for .NET 是一个强大的 API，允许开发人员在 .NET 应用程序中以编程方式操作 Microsoft Project 文件。

### Q2：我可以使用 Util.And 应用两个以上的条件吗？

答：是的，Util.And 可用于组合任意数量的条件来创建复杂的过滤条件。

### 问题 3：Aspose.Tasks for .NET 是否有免费试用版？

答：是的，您可以从以下位置下载免费试用版：[这里](https://releases.aspose.com/).

### 问题 4：在哪里可以找到 Aspose.Tasks for .NET 的文档？

答：你可以找到文档[这里](https://reference.aspose.com/tasks/net/).

### Q5：如何获得 Aspose.Tasks for .NET 支持？

答：您可以从 Aspose.Tasks 社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
