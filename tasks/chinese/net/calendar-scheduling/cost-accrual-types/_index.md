---
date: 2026-07-05
description: 了解如何使用 Aspose.Tasks for .NET 跟踪项目预算并管理项目成本。定义成本累计类型以实现精确的成本跟踪。
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Aspose.Tasks 中的成本累计类型
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 中的成本累计类型跟踪项目预算
url: /zh/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 中的成本累计类型跟踪项目预算

## 介绍

准确地 **跟踪项目预算** 是成功交付项目的基石。当在恰当的时机捕获成本信息时，您可以预测超支、调整资源并让利益相关者保持知情。Aspose.Tasks for .NET 为开发者提供对成本累计的细粒度控制，让您决定 *何时* 记录成本——无论是在工作开始时、持续期间，还是仅在工作完成时。本教程将带您了解相关概念，展示如何设置累计类型，并演示可靠预算跟踪的最佳实践。

## 快速答疑
- **成本累计类型的主要目的是什么？** 它们决定在任务生命周期的哪个节点确认成本，从而实现精确的预算跟踪。  
- **哪个枚举值会将成本延迟到工作完成后？** `CostAccrualType.End`。  
- **运行代码是否需要许可证？** 是的，生产环境中必须使用有效的 Aspose.Tasks 许可证。  
- **我可以一次性更改多个资源的累计类型吗？** 可以——遍历 `Resources` 集合并分配所需的类型即可。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是成本累计类型？
**成本累计类型** 告诉 Aspose.Tasks 在何时将资源的成本计入项目预算。它由 `CostAccrualType` 枚举表示，可针对资源或任务单独设置。选择正确的类型可确保成本数据与组织的计费政策保持一致，无论是需要在工作开始时记录、按持续时间比例分摊，还是仅在完成后记录。

## 为什么使用成本累计类型来跟踪项目预算？
Aspose.Tasks 支持 **四种** 累计选项——`Start`、`Prorated`、`Duration` 和 `End`——覆盖了典型项目会计场景的全部范围。选择合适的选项可让您将成本确认与合同计费周期对齐，降低财务报告的差异，并生成可顺畅集成到 ERP 系统的成本报表，同时在大型项目中保持低内存占用。

## 前置条件

在开始之前，请确保具备以下前置条件：

### 1. 安装 Aspose.Tasks for .NET
要开始使用，您需要在开发环境中安装 Aspose.Tasks for .NET。可从[下载页面](https://releases.aspose.com/tasks/net/)获取库并按照提供的安装说明进行操作。

### 2. 熟悉 .NET 框架
需要具备 .NET 框架和 C# 编程语言的基础知识，以便跟随本教程中的示例。

## 如何为资源设置成本累计类型？

加载项目，定位目标资源，并分配所需的 `CostAccrualType`。下面的两行代码模式是标准做法：创建 `Project` 实例，按 ID 获取资源，然后设置 `CostAccrualType`。此简洁流程可确保在资源添加的瞬间就 **准确跟踪项目预算**。

### 步骤 1：导入命名空间
让我们先导入必要的命名空间，以在 .NET 项目中访问 Aspose.Tasks 功能：

```csharp

```

准备好命名空间后，我们即可继续加载项目文件。

### 步骤 2：加载项目文件
`Project` 类表示一个 Microsoft Project 文件，并提供对其任务、资源及其他数据的访问。

```csharp
var project = new Project("Project2.mpp");
```

首先，需要将项目文件加载到应用程序中。我们创建一个新的 `Project` 对象，并使用项目文件的路径进行初始化。

### 步骤 3：访问资源
`Resources` 集合包含项目中定义的所有资源。`GetById` 方法可通过唯一标识符检索资源。

```csharp
var resource = project.Resources.GetById(1);
```

接下来，访问我们希望应用成本累计类型的资源。使用 `Resources` 集合的 `GetById` 方法并传入资源 ID。这演示了 **按 ID 访问资源**，这是自动化成本更新时的常见需求。

### 步骤 4：设置成本累计类型
`Set` 方法用于为资源字段分配值。

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

在这里，我们为资源设置成本累计类型。本例中将其设为 `CostAccrualType.End`，这意味着只有在剩余工作为零时才会累计成本。选择 `End` 适用于希望在任务完全完成后才 **跟踪项目预算** 的场景。

### 步骤 5：继续处理项目
设置成本累计类型后，您可以根据需要继续处理项目，例如生成成本报告、更新分配或导出文件等。

## 常见陷阱与专业提示
- **专业提示：** 在修改累计类型后务必调用 `project.Save` 以持久化更改。  
- **陷阱：** 将 `CostAccrualType.Start` 设置在从未开始工作的资源上会导致预算报告膨胀——请先确认任务计划。  
- **专业提示：** 当需要批量更新大量资源时，使用 `project.Resources.ToList()`，可避免重复的集合查找并提升大型项目的性能。

## 常见问题

**问：我可以一次性更改多个资源的成本累计类型吗？**  
答：可以，遍历 `project.Resources` 并在 `foreach` 循环中为每个资源分配所需的 `CostAccrualType`。

**问：除了 `End` 之外，还有哪些可用的成本累计类型？**  
答：Aspose.Tasks 提供 `Start`、`Prorated` 和 `Duration`——每种都对应不同的计费策略。

**问：如何确定特定资源当前的成本累计类型？**  
答：通过 `resource.Get(TskResource.CostAccrualType)` 获取；它返回表示当前设置的枚举值。

**问：是否可以在同一项目的不同任务上应用不同的成本累计类型？**  
答：完全可以。任务和资源都公开 `CostAccrualType` 属性，允许对每个实体独立配置。

**问：Aspose.Tasks 是否支持自定义成本累计类型？**  
答：不支持，库目前仅提供这四种内置类型；如需自定义逻辑必须在外部实现。

---

**最后更新：** 2026-07-05  
**测试环境：** Aspose.Tasks 24.8 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [Aspose.Tasks 日历与调度](/tasks/net/calendar-scheduling/)
- [使用 Aspose.Tasks for .NET 处理 MS Project 费率](/tasks/net/rate-recurring-tasks/handling-rates/)
- [轻松管理 MS Project 资源](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}