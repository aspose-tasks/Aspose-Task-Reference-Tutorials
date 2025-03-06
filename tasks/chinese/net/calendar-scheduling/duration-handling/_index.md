---
title: Aspose.Tasks 中的持续时间处理
linktitle: Aspose.Tasks 中的持续时间处理
second_title: Aspose.Tasks .NET API
description: 通过分步教程了解如何在 Aspose.Tasks for .NET 中有效处理持续时间。
type: docs
weight: 30
url: /zh/net/calendar-scheduling/duration-handling/
---
## 介绍

有效处理工期对于项目管理应用程序至关重要。 Aspose.Tasks for .NET 提供了强大的功能来有效管理持续时间。在本教程中，我们将使用 Aspose.Tasks for .NET 探索持续时间处理的各个方面。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

1. C# 基础知识：熟悉 C# 编程语言对于理解和实现示例至关重要。
2. Visual Studio：安装 Visual Studio IDE 以创建和运行 .NET 应用程序。
3.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks for .NET 库。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).

## 导入命名空间

首先，让我们导入必要的命名空间以使用 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

让我们以分步指南的形式将每个示例分解为多个步骤：

## 更新任务的持续时间

### 第 1 步：加载项目文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：获取任务和持续时间

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 第 3 步：更新持续时间

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 步骤 4：显示更新持续时间

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## 减去任务的持续时间

### 第 1 步：加载项目文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：获取任务和持续时间

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 第 3 步：减去持续时间

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 步骤 4：显示更新持续时间

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## 将持续时间转换为时间跨度

### 第 1 步：加载项目文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：获取任务和持续时间

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 步骤 3：将持续时间转换为时间跨度

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## 将持续时间转换为字符串

### 第 1 步：加载项目文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：获取任务和持续时间

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 第 3 步：将持续时间转换为字符串

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## 结论

在本教程中，我们介绍了 Aspose.Tasks for .NET 中持续时间处理的各个方面。了解并有效管理工期对于成功的项目管理至关重要。 Aspose.Tasks 提供了全面的功能来简化 .NET 应用程序中的持续时间管理任务。

## 常见问题解答

### Q1：什么是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一个功能强大的库，用于在 .NET 应用程序中处理 Microsoft Project 文件。

### Q2：Aspose.Tasks 可以处理复杂的项目结构吗？

A2：是的，Aspose.Tasks 可以轻松处理复杂的项目结构，提供广泛的 API 进行操作。

### Q3：Aspose.Tasks for .NET 与 .NET Core 兼容吗？

A3：是的，Aspose.Tasks for .NET 与 .NET Core 兼容，允许您在跨平台应用程序中使用它。

### Q4：Aspose.Tasks 支持读写 Microsoft Project 文件吗？

A4：是的，Aspose.Tasks 支持读取和写入各种格式的 Microsoft Project 文件，包括 MPP、XML 和 MPX。

### Q5：Aspose.Tasks for .NET 有试用版吗？

A5：是的，您可以从以下位置获得 Aspose.Tasks for .NET 的免费试用版：[这里](https://releases.aspose.com/).