---
title: 在 Aspose.Tasks 中使用 NOT 操作
linktitle: 在 Aspose.Tasks 中使用 NOT 操作
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中使用 NOT 操作来有效地过滤任务。立即增强您的项目管理能力。
weight: 20
url: /zh/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中使用 NOT 操作

## 介绍

在本教程中，我们将探索如何在 Aspose.Tasks for .NET 中使用 NOT 操作。 NOT 操作允许我们反转过滤条件，使我们能够选择不满足指定条件的元素。

## 先决条件

在我们开始之前，请确保您具备以下条件：

1. Visual Studio：您需要安装有效的 Visual Studio 才能完成代码示例。
2.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET 库：[网站](https://releases.aspose.com/tasks/net/).
3. 对 C# 的基本了解：熟悉 C# 编程语言将有助于理解代码示例。

## 导入命名空间

首先，让我们为我们的代码导入必要的命名空间：

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 1 步：设置项目和任务

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

我们首先使用以下命令加载名为“Project2.mpp”的项目文件`Project`由Aspose.Tasks提供的类。确保指定目录中存在项目文件。

## 第2步：收集项目任务

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

在这里，我们创建一个`ChildTasksCollector`对象收集项目内的所有任务。然后我们使用`TaskUtils.Apply`方法遍历项目的任务层次结构并收集所有子任务。

## 步骤3：定义过滤条件

```csharp
var filter = new NullCondition();
```

我们使用名为的自定义类定义过滤条件`NullCondition`。此条件选择具有空值的任务。

## 步骤 4：应用 NOT 运算

```csharp
var condition = new Not<Task>(filter);
```

我们使用以下方法将 NOT 运算应用于过滤条件`Not<T>`由Aspose.Tasks提供的类。这将反转过滤条件，选择不具有空值的任务。

## 第 5 步：过滤任务

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

我们使用自定义过滤器根据应用条件过滤收集的任务`Filter`方法。该方法将任务的可枚举集合和过滤条件作为输入参数，并返回满足条件的任务列表。

## 第 6 步：处理过滤的任务

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    //与其他属性一起工作...
}
```

最后，我们迭代过滤后的任务并执行任何所需的操作。在此示例中，我们只是将任务名称打印到控制台。

## 结论

在本教程中，我们学习了如何在 Aspose.Tasks for .NET 中使用 NOT 操作。通过反转过滤条件，我们可以选择性地选择不符合指定条件的元素，从而增强项目内任务操作的灵活性。

## 常见问题解答

### Q1：我可以将 Aspose.Tasks 与其他 .NET 框架一起使用吗？

答：是的，Aspose.Tasks 支持各种 .NET 框架，包括 .NET Core、.NET Standard 和 .NET Framework。

### Q2：Aspose.Tasks 有免费试用版吗？

答：是的，您可以从以下网站下载免费试用版：[网站](https://releases.aspose.com/).

### Q3：如何获得 Aspose.Tasks 的支持？

答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)如有任何支持查询或技术援助。

### Q4：我可以购买 Aspose.Tasks 的临时许可证吗？

答：是的，您可以从以下机构购买临时许可证：[购买页面](https://purchase.aspose.com/temporary-license/).

### Q5：在哪里可以找到 Aspose.Tasks 的综合文档？

答：您可以访问以下网站上的完整文档[Aspose.Tasks 文档页面](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
