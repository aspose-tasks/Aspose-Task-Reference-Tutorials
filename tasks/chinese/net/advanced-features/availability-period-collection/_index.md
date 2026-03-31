---
date: 2026-03-21
description: 了解如何使用 Aspose.Tasks for .NET 管理资源的可用期间，并实现项目资源的有效可用性。本分步指南展示了如何添加、更新和删除可用期间。
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 项目资源可用性 – 在 Aspose.Tasks 中管理可用期间
url: /zh/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 项目资源可用性：Aspose.Tasks 中的可用期间集合

管理 **项目资源可用性** 是成功项目规划的核心部分。在本教程中，您将学习 **如何使用 Aspose.Tasks for .NET API 管理资源的可用期间**，一步步从加载项目到在资源之间复制期间。

## 快速答疑
- **可用期间的主类是什么？** `AvailabilityPeriod`，位于 `Aspose.Tasks` 命名空间。  
- **我可以清除已有的期间吗？** 可以，调用 `resource.AvailabilityPeriods.Clear()`。  
- **如何添加新期间？** 创建 `AvailabilityPeriod` 对象并使用 `Add` 或 `Insert`。  
- **可以将期间复制到其他资源吗？** 完全可以 – 使用 `CopyTo` 然后将每个项目添加到目标资源。  
- **生产环境需要许可证吗？** 需要，非试用部署必须使用商业版 Aspose.Tasks 许可证。

## 什么是项目资源可用性？
项目资源可用性定义了资源可以分配到任务的日期和单位（容量的百分比）。通过控制这些期间，您可以防止资源超分配并提升进度的准确性。

## 为什么使用 Aspose.Tasks 管理可用期间？
- **完整的 .NET 集成** – 无需 COM 互操作，纯托管代码。  
- **细粒度控制** – 可设置精确的开始/结束日期和分数单位。  
- **轻松复制** – 在资源之间移动可用性数据，无需手动解析。  
- **性能优化** – 能高效处理大型 MPP 文件。

## 前置条件
1. **Visual Studio** – 任意近期版本（2019、2022 或更高）。  
2. **Aspose.Tasks for .NET** – 从 [here](https://releases.aspose.com/tasks/net/) 下载。  
3. **基础 C# 知识** – 您应熟悉类、集合和 LINQ。

## 导入命名空间

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

我们导入核心的 Aspose.Tasks 命名空间以及后续需要的标准 .NET 集合。

## 步骤 1：初始化项目和资源

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

在这里我们加载已有的 MPP 文件并获取需要编辑可用性的资源（ID = 1）。

## 步骤 2：清除已有的可用期间

```csharp
resource.AvailabilityPeriods.Clear();
```

清除操作会移除之前定义的所有期间，为我们提供一个干净的起点。

## 步骤 3：添加可用期间

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

我们获取 `AvailabilityPeriod` 对象的集合（假设已在其他位置实现 `GetPeriods` 辅助方法），并在集合可写的情况下逐个添加。

## 步骤 4：插入新的可用期间

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

此代码为 2013 年创建一个自定义期间，并在位置 1（第二个槽位）插入，前提是该期间尚未存在。

## 步骤 5：显示可用期间

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

快速的控制台输出会显示总计数以及每个期间的详细信息——便于调试或验证。

## 步骤 6：将可用期间复制到另一个资源

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

我们将整个集合复制到数组，清除目标资源的期间，然后重新填充。这演示了如何在资源之间复制可用性数据。

## 步骤 7：更新并移除可用期间

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

这里我们调整倒数第二个期间的 `AvailableUnits`，随后移除之前添加的 2013 年期间。

## 常见问题及解决方案
- **只读集合错误** – 确保项目未以只读模式打开，或在添加新项之前已调用 `resource.AvailabilityPeriods.Clear()`。  
- **期间重叠** – Aspose.Tasks 不会自动合并重叠的期间；您可能需要编写自定义逻辑来检测并解决冲突。  
- **日期格式不正确** – 始终使用 `DateTime` 对象；字符串解析可能导致地区相关的错误。

## 常见问答

**问：我可以为可用期间添加自定义字段吗？**  
答：不可以，Aspose.Tasks for .NET 中的可用期间不支持自定义字段。

**问：可用期间是否与特定任务关联？**  
答：不关联，它们与资源关联，定义资源在一般情况下何时可用于任务。

**问：我可以从外部来源导入可用期间吗？**  
答：可以，您可以从 CSV、XML 或数据库读取数据，创建 `AvailabilityPeriod` 对象并添加到集合中。

**问：如何处理重叠的可用期间？**  
答：重叠不会自动解决；您需要实现自定义验证来合并或拒绝冲突的期间。

**问：资源的可用期间数量是否有限制？**  
答：没有硬性上限，但极大的集合可能影响性能；建议在可能的情况下合并期间。

## 结论

本指南涵盖了使用 Aspose.Tasks for .NET 管理 **项目资源可用性** 的全部关键步骤——从初始化项目、清除旧数据，到添加、插入、复制、更新和删除可用期间。掌握这些操作可帮助您保持资源日历的准确性，使项目进度更为真实可靠。

---

**最后更新：** 2026-03-21  
**测试环境：** Aspose.Tasks for .NET（最新发布）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}