---
date: 2026-03-16
description: 了解如何在 Aspose.Tasks for .NET 中使用高级 AND 操作组合多个条件并筛选项目任务。
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中使用高级 AND 操作组合多个条件
url: /zh/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的高级 AND 操作

## 介绍

在本教程中，您将了解 **如何使用 Aspose.Tasks for .NET 的高级 AND 操作** 将多个条件组合在一起。阅读完本指南后，您将能够 **基于多个条件过滤项目任务**——这在需要一次性 **过滤任务**（例如汇总项、非空条目或自定义标记）时非常关键。

## 快速答案
- **高级 AND 操作的作用是什么？** 它将两个或多个过滤条件合并，只有同时满足 *所有* 条件的任务才会被返回。  
- **哪个类用于组合条件？** `Util.And<T>`（在 API 中显示为 `And<T>`）。  
- **需要特殊许可证吗？** 生产环境需要常规的 Aspose.Tasks 许可证；提供免费试用版。  
- **可以链式连接超过两个条件吗？** 可以——`And<T>` 接受任意数量的条件。  
- **支持哪些 .NET 版本？** .NET Framework 4.5 及以上、.NET Core 3.1 及以上、.NET 5/6 及以上。

## 在 Aspose.Tasks 中 “组合多个条件” 是什么？

组合多个条件指的是创建一个复合过滤器，同时对每个任务应用多条规则。这种方式比多次遍历任务列表更高效，因为库会在一次遍历中完成所有逻辑判断。

## 为什么使用高级 AND 操作？

- **性能：** 减少对任务集合的遍历次数。  
- **可读性：** 使过滤逻辑保持声明式，易于维护。  
- **灵活性：** 可以将内置条件（如 `SummaryCondition`）与自定义谓词混合使用。  

## 前置条件

在开始之前，请确保您已具备以下条件：

1. 基本的 C# 编程知识。  
2. 已安装 Aspose.Tasks for .NET。若尚未下载，可前往 **[此处](https://releases.aspose.com/tasks/net/)** 获取。  
3. 任意版本的 Visual Studio（或其他 IDE）均可。  

## 导入命名空间

首先，导入提供任务模型和实用类的命名空间：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## 步骤 1：初始化项目并收集任务

我们将创建一个 `Project` 实例，并使用 `ChildTasksCollector` 收集文件中的所有任务。这演示了 **如何使用收集器** 获取任务的平面列表。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## 步骤 2：定义过滤条件

在此我们定义要应用的各个单独条件。本例中我们 **过滤汇总任务**，并确保任务对象不为 null。

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## 步骤 3：使用 AND 操作组合条件

现在我们使用 `And<T>` 类 **组合多个条件**。这就是 **高级 AND 操作** 的核心。

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 步骤 4：应用条件并过滤任务

准备好复合条件后，调用 `Filter` 根据组合逻辑 **过滤项目任务**。

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## 步骤 5：输出过滤后的任务

最后，显示满足 **全部** 条件的任务。您可以将 `Console.WriteLine` 替换为任何自定义处理逻辑。

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## 常见问题及解决方案

| 问题 | 产生原因 | 快速解决方案 |
|------|----------|--------------|
| 未找到 `Filter` 方法 | 缺少 `using Aspose.Tasks.Util;` | 确认已导入 Util 命名空间（参见导入命名空间）。 |
| 未返回任务 | 条件过于严格（例如过滤了不存在的汇总任务） | 检查项目是否真的包含汇总任务，或放宽条件。 |
| NullReferenceException | `coll.Tasks` 中包含 null 条目 | `NotNullCondition` 已经对其进行保护，保持在 AND 链中即可。 |

## FAQ

### Q1: 什么是 Aspose.Tasks for .NET？

A: Aspose.Tasks for .NET 是一个强大的 API，允许开发者在 .NET 应用程序中以编程方式操作 Microsoft Project 文件。

### Q2: 可以使用 Util.And 合并超过两个条件吗？

A: 可以，Util.And 能够组合任意数量的条件，以创建复杂的过滤标准。

### Q3: 是否提供 Aspose.Tasks for .NET 的免费试用？

A: 是的，您可以从 **[此处](https://releases.aspose.com/)** 下载免费试用版。

### Q4: 哪里可以找到 Aspose.Tasks for .NET 的文档？

A: 文档位于 **[此处](https://reference.aspose.com/tasks/net/)**。

### Q5: 如何获取 Aspose.Tasks for .NET 的技术支持？

A: 您可以在 Aspose.Tasks 社区论坛 **[此处](https://forum.aspose.com/c/tasks/15)** 获得支持。

**其他问答**

**问：如何按自定义字段值过滤任务？**  
答：创建 `CustomFieldCondition`（或实现 `ICondition<Task>`），并将其加入 `And<T>` 链中。

**问：可以用相同方法过滤资源吗？**  
答：可以——将 `Task` 替换为 `Resource`，并使用相应的条件类。

## 结论

通过上述步骤，您现在已经掌握了在 Aspose.Tasks for .NET 中使用 **高级 AND 操作** **组合多个条件** 的方法。此技术能够高效地 **过滤项目任务**，无论是针对汇总项、非空条目，还是您自定义的任何筛选标准。

---

**最近更新：** 2026-03-16  
**测试环境：** Aspose.Tasks for .NET（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}