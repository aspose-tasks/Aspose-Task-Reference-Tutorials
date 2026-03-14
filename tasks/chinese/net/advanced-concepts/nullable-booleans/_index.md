---
date: 2026-03-14
description: 了解如何在 Aspose.Tasks for .NET 中使用可空布尔值，包括转换可空布尔值和设置可空布尔属性。
linktitle: How to Use Nullable Booleans in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中使用可空布尔值
url: /zh/net/advanced-concepts/nullable-booleans/
weight: 21
---

 Aspose" => "**作者:** Aspose"

Then closing shortcodes.

Then backtop button shortcode.

Make sure to keep all shortcodes unchanged.

Now produce final content with translations.

Let's construct.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中使用可空布尔

在本教程中，我们将展示 **如何使用可空** 布尔值来操作 Aspose.Tasks .NET API。可空布尔提供了三种可能的状态——`true`、`false` 或 *未定义*——这在可能未显式指定的项目级设置中尤为方便。您将看到如何创建、转换以及 **设置可空布尔** 值，并了解正确处理可空布尔如何防止调度应用程序中出现意外行为。

## 快速答案
- **什么是可空布尔？** 一种可以保存 `true`、`false` 或未定义的类型。  
- **为什么在 Aspose.Tasks 中使用可空布尔？** 它们让您在不猜测默认值的情况下表示可选的项目属性。  
- **如何将可空布尔转换为普通 bool？** 使用隐式转换或先检查 `IsDefined`。  
- **主要类是什么？** `Aspose.Tasks` 命名空间中的 `NullableBool`。  
- **我需要许可证吗？** 是的，生产环境使用需有效的 Aspose.Tasks 许可证。

## 什么是可空布尔？

可空布尔 (`NullableBool`) 通过添加 *IsDefined* 标志扩展了常规的 `bool` 类型。当 `IsDefined` 为 `false` 时，该值被视为未定义，从而可以区分 “false” 与 “未设置”。

## 为什么在项目设置中处理可空布尔？

许多项目选项——如 **ActualsInSync** 或 **HonorConstraints**——都是可选的。使用普通 `bool` 会强制您选择 `true` 或 `false`，这可能无意中覆盖用户的意图。通过 **处理可空布尔**，您可以保留原始状态，避免意外的配置更改。

## 前置条件

在开始之前，请确保您拥有：

1. **Visual Studio**（或任何 .NET 兼容的 IDE）。  
2. **Aspose.Tasks for .NET** – 从 [here](https://releases.aspose.com/tasks/net/) 下载。

## 导入命名空间

首先，导入所需的命名空间：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
```

现在让我们一步步浏览每个示例。

## 使用 `NullableBool`

### 步骤 1：创建一个新的 `Project` 实例。

```csharp
var project = new Project();
```

### 步骤 2：实例化一个带有指定值的 `NullableBool` 对象。

```csharp
var actualsInSync = new NullableBool(false, false);
```

### 步骤 3：检查 `NullableBool` 对象的值和已定义状态。

```csharp
Console.WriteLine("'ActualsInSync' Value: " + actualsInSync.Value);
Console.WriteLine("'ActualsInSync' Is Defined: " + actualsInSync.IsDefined);
```

### 步骤 4：**在项目上设置可空布尔**。

```csharp
project.Set(Prj.ActualsInSync, actualsInSync);
```

### 步骤 5：使用单一值实例化另一个 `NullableBool` 对象。

```csharp
var honorConstraints = new NullableBool(true);
```

### 步骤 6：显示 `NullableBool` 对象的字符串表示。

```csharp
Console.WriteLine("'HonorConstraints' ToString: " + honorConstraints.ToString());
```

### 步骤 7：通过在项目中设置来使用 `NullableBool` 实例。

```csharp
project.Set(Prj.HonorConstraints, honorConstraints);
```

## 比较 `NullableBool` 实例

### 步骤 1：实例化两个 `NullableBool` 对象。

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### 步骤 2：检查每个 `NullableBool` 对象的字符串表示。

```csharp
Console.WriteLine("Nullable Bool 1: " + bool1.ToString());
Console.WriteLine("Nullable Bool 2: " + bool2.ToString());
```

### 步骤 3：隐式转换为 `bool` 并打印结果。

```csharp
if (bool1)
{
    Console.WriteLine("Nullable Bool 1 is True");
}
else
{
    Console.WriteLine("Nullable Bool 1 is False");
}
```

### 步骤 4：比较两个 `NullableBool` 对象的相等性。

```csharp
Console.WriteLine("Are bools equal: " + bool1.Equals(bool2));
```

## 获取 `NullableBool` 的哈希码

### 步骤 1：实例化两个 `NullableBool` 对象。

```csharp
var bool1 = new NullableBool(true);
var bool2 = new NullableBool(true, false);
```

### 步骤 2：打印每个 `NullableBool` 对象的哈希码。

```csharp
Console.WriteLine("Bool 1: {0} Hash Code 1: {1}", bool1.ToString(), bool1.GetHashCode());
Console.WriteLine("Bool 2: {0} Hash Code 1: {1}", bool2.ToString(), bool2.GetHashCode());
```

## 常见陷阱与技巧

- **永远不要假设可空布尔已定义。** 在使用 `Value` 之前始终检查 `IsDefined`。  
- **将可空布尔转换为普通 bool** 时如果不检查，值未定义会抛出异常。仅在确定已定义时才使用隐式转换。  
- **设置项目属性时**，使用带有 `NullableBool` 的 `Set` 方法，以在需要时保留未定义状态。

## 常见问题

**Q: 什么是可空布尔？**  
A: 可空布尔可以表示 `true`、`false` 或未定义状态，从而提供三种不同的结果。

**Q: 如何安全地将可空布尔转换为普通 bool？**  
A: 首先检查 `IsDefined`，然后使用 `Value` 属性或在确定已定义时使用隐式转换。

**Q: 为什么在 Aspose.Tasks 中使用可空布尔而不是普通 bool？**  
A: 它们让您保持可选项目设置不被更改，防止意外覆盖。

**Q: 我可以将可空布尔设置为未定义吗？**  
A: 可以——使用仅接受已定义标志的构造函数，例如 `new NullableBool(false, false)`。

**Q: 在哪里可以找到 Aspose.Tasks for .NET 的更多文档？**  
A: 您可以在 [here](https://reference.aspose.com/tasks/net/) 找到详细文档。

---

**最后更新:** 2026-03-14  
**测试环境:** Aspose.Tasks for .NET (latest release)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}