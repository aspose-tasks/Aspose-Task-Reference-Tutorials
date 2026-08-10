---
date: 2026-04-06
description: 学习如何在 Aspose.Tasks for .NET 中删除所有基线并管理基线集合，配有逐步代码示例。
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: 使用 Aspose.Tasks 基线集合删除所有基线
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 基线集合删除所有基线
url: /zh/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 删除所有基线使用 Aspose.Tasks 基线集合

## 介绍

Aspose.Tasks for .NET 让您可以直接在 .NET 应用程序中操作 Microsoft Project 文件。最强大的功能之一是能够为资源 **删除所有基线**，这在需要重置项目跟踪数据或启动新的基线周期时至关重要。在本教程中，我们将逐步演示整个过程——从加载项目文件到移除特定资源的每一个基线——并提供清晰、易懂的说明以及可直接运行的 C# 代码。

## 快速答案
- **“删除所有基线”到底做了什么？** 它会移除所选资源的所有已存储基线记录，清除历史成本和工作数据。  
- **我为什么需要它？** 在项目发生重大变更或原有基线不再适用时，用于重置跟踪。  
- **哪个库提供此功能？** Aspose.Tasks for .NET。  
- **需要许可证吗？** 生产环境必须使用有效的 Aspose.Tasks 许可证；提供免费试用版。  
- **代码兼容 .NET 6+ 吗？** 是的，API 支持 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6。

## 什么是基线以及为什么要删除所有基线？

基线捕获了在特定时间点的成本、工作和进度的原始计划。项目生命周期中，您可能会创建多个基线（Baseline 1、Baseline 2 等），以便将实际进度与不同的计划快照进行比较。然而，在项目重新范围或全新开始等情形下，保留这些历史基线会导致混乱。删除所有基线可以让您拥有一个干净的起点，从而设置反映当前实际情况的新基线。

## 先决条件

1. **Visual Studio** – 任意近期版本（Community、Professional 或 Enterprise）。  
2. **Aspose.Tasks for .NET** – 从 [download link](https://releases.aspose.com/tasks/net/) 下载。  
3. **基本的 C# 知识** – 您应熟悉变量、循环和控制台输出。  
4. **Microsoft Project 文件** (`.mpp`) – 示例文件名为 *WorkWithBaselineCollection.mpp*，将在示例中使用。

## 导入命名空间

首先，将必要的命名空间引入作用域，以便编译器能够找到我们将使用的类。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 步骤 1：加载项目文件

我们从加载已有的 Project 文件开始。请将 `DataDir` 调整为指向包含 `.mpp` 文件的文件夹。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 步骤 2：获取目标资源

演示中我们获取 UID = 1 的资源。在实际场景中，您可能会通过名称或其他标识符定位资源。

```csharp
var resource = project.Resources.GetByUid(1);
```

## 步骤 3：显示现有基线信息

在删除任何内容之前，查看资源当前附带的基线信息是很有帮助的。这可以让您确认正在删除正确的数据。

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 步骤 4：遍历所有基线

这里我们遍历每个基线，打印关键指标，如成本、工作量和挣值（BCWP/BCWS）。此步骤可选，但对日志记录或审计很有用。

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 删除所有基线

现在执行核心操作：为选定资源 **删除所有基线**。我们首先将集合复制到列表，以避免在遍历时修改集合，然后逐一移除每个基线。

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

运行此代码块后，`resource.Baselines.Count` 将为 `0`，表明所有基线记录已被清除。

## 常见问题与技巧

- **NullReferenceException** – 确保项目文件确实包含您要定位的资源，否则 `GetByUid` 会返回 `null`。  
- **Licensing** – 没有有效的 Aspose.Tasks 许可证，输出中会出现水印并且功能受限。  
- **Performance** – 对于超大项目，可考虑使用 `Parallel.ForEach` 加速移除过程，但请记住底层集合并非线程安全。

## 常见问题

**Q: Aspose.Tasks 能处理大型项目文件吗？**  
A: 可以，Aspose.Tasks 已针对性能进行优化，能够高效处理多 GB 的 `.mpp` 文件。

**Q: 该库兼容所有 Microsoft Project 版本吗？**  
A: Aspose.Tasks 支持 Project 2000 到 Project 2024，涵盖旧的 `.mpp` 格式以及新版基于 XML 的文件。

**Q: 我可以在删除之前自定义基线吗？**  
A: 完全可以。在决定删除之前，您可以读取或修改任何基线属性（成本、工作、日期等）。

**Q: Aspose.Tasks 能在云平台上运行吗？**  
A: 能，API 可在任何兼容 .NET 的环境中运行，包括 Azure App Service、AWS Lambda（通过 .NET Core）以及 Docker 容器。

**Q: 我可以在哪里向社区求助？**  
A: 访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 与其他开发者和 Aspose 员工交流。

## 结论

本指南演示了如何使用 Aspose.Tasks for .NET 为资源 **删除所有基线**。通过遵循逐步代码，您可以重置基线数据，保持项目跟踪的整洁，并为新的计划周期做好准备。删除后，您也可以尝试创建新基线，观察库如何更新项目文件。

---

**最后更新:** 2026-04-06  
**测试环境:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}