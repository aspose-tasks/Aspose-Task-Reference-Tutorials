---
date: 2026-03-19
description: 学习如何使用 Aspose.Tasks for .NET 设置项目基准并高效管理任务基准，确保项目进度的准确跟踪。
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 设置项目基准 – 在 Aspose.Tasks 中管理分配基准
url: /zh/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 设置项目基准 – 在 Aspose.Tasks 中管理任务分配基准

## 介绍

在进行项目管理工作时，**设置项目基准**对于将实际进度与原始计划进行对比至关重要。Aspose.Tasks for .NET 不仅可以让你**设置项目基准**，还提供对任务分配基准的完整控制，从而实现精确的绩效跟踪。在本教程中，我们将完整演示整个过程——加载项目、设置基准、读取任务分配基准数据以及比较基准——帮助你自信地监控项目。

## 快速答案
- **“设置项目基准”是什么意思？** 它记录原始的进度和成本数据，以便后续与实际绩效进行比较。  
- **哪个 API 方法用于设置基准？** `Project.SetBaseline(BaselineType.Baseline)`。  
- **任务分配基准需要单独调用吗？** 不需要，设置项目基准时会自动保存分配基准。  
- **支持哪些格式？** MPP、XML、MPX 等，均由 Aspose.Tasks 提供。  
- **生产环境是否需要许可证？** 是的，非试用使用必须拥有商业许可证。

## 前置条件

在开始之前，请确保你具备以下条件：

- 基本的 C# 编程知识。  
- Visual Studio（任意近期版本）。  
- 已在项目中添加 Aspose.Tasks for .NET 库。可从 [here](https://releases.aspose.com/tasks/net/) 下载。  
- 拥有一个 MPP 格式的项目文件（例如 `AssignmentBaseline2007.mpp`）。

## 导入命名空间

在 C# 文件顶部添加所需的命名空间，以便编译器能够找到 Aspose.Tasks 类。

```csharp
using Aspose.Tasks;
using System;
```

## 步骤 1：加载项目并设置项目基准

首先，加载已有的 MPP 文件，然后调用 `SetBaseline` 为整个项目**设置项目基准**。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## 步骤 2：读取任务分配基准信息

基准设置完成后，每个资源分配都会拥有自己的基准记录。下面的循环提取并打印这些细节，包括开始/结束日期、成本、工作量以及任何时间相位数据。

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## 步骤 3：比较任务分配基准

你可以使用内置的相等和比较运算符比较不同任务分配的基准。这在需要检测任务进度偏移或成本超支时非常实用。

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## 常见问题及解决方案

| 问题 | 产生原因 | 解决办法 |
|------|----------|----------|
| **基准数据为空** | 项目文件以只读模式打开，或根本未设置基准。 | 在读取任务分配基准之前调用 `project.SetBaseline(BaselineType.Baseline)`。 |
| **`NullReferenceException` 出现在 `TimephasedData` 上** | 并非所有基准都包含时间相位条目。 | 始终检查 `baseline.TimephasedData != null`（如代码所示）。 |
| **获取 UID 不正确** | 不同文件版本的 UID 值不同。 | 使用 `ResourceAssignments.GetByUid` 并提供正确的 UID，或遍历查找所需的分配。 |

## 常见问答

**问：Aspose.Tasks 能否为单个任务分配处理多个基准？**  
答：可以，Aspose.Tasks 支持为每个任务分配维护多个基准，从而实现对项目进度的全面跟踪。

**问：Aspose.Tasks 是否兼容除 MPP 之外的其他项目文件格式？**  
答：是的，Aspose.Tasks 支持包括 XML、MPX、MPP 在内的多种项目文件格式，确保与各种项目管理工具的兼容性。

**问：我可以使用 Aspose.Tasks 以编程方式修改基准信息吗？**  
答：完全可以，Aspose.Tasks 提供丰富的 API，允许根据项目需求动态修改基准信息，提供灵活的项目管理控制。

**问：Aspose.Tasks 是否为开发者提供文档和支持资源？**  
答：是的，开发者可以在 Aspose.Tasks 官方网站上获取完整的文档、教程和论坛，帮助顺利集成并解决问题。

**问：是否有 Aspose.Tasks for .NET 的试用版可供下载？**  
答：有，开发者可以从 [here](https://releases.aspose.com/) 获取 Aspose.Tasks for .NET 的免费试用版，以评估其功能和性能后再决定购买。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-03-19  
**测试环境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

---