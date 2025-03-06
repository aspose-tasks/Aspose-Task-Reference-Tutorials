---
title: Aspose.Tasks 中的持續時間處理
linktitle: Aspose.Tasks 中的持續時間處理
second_title: Aspose.Tasks .NET API
description: 透過逐步教學了解如何在 Aspose.Tasks for .NET 中有效處理持續時間。
weight: 30
url: /zh-hant/net/calendar-scheduling/duration-handling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的持續時間處理

## 介紹

有效處理工期對於專案管理應用程式至關重要。 Aspose.Tasks for .NET 提供了強大的功能來有效管理持續時間。在本教程中，我們將使用 Aspose.Tasks for .NET 來探索持續時間處理的各個方面。

## 先決條件

在我們深入學習本教程之前，請確保您具備以下先決條件：

1. C# 基礎知識：熟悉 C# 程式語言對於理解和實作範例至關重要。
2. Visual Studio：安裝 Visual Studio IDE 以建立和執行 .NET 應用程式。
3.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks for .NET 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).

## 導入命名空間

首先，讓我們匯入必要的命名空間以使用 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

讓我們以逐步指南的形式將每個範例分解為多個步驟：

## 更新任務的持續時間

### 第 1 步：載入專案文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：獲取任務和持續時間

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 第 3 步：更新持續時間

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 步驟 4：顯示更新持續時間

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## 減去任務的持續時間

### 第 1 步：載入專案文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：獲取任務和持續時間

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### 第 3 步：減去持續時間

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### 步驟 4：顯示更新持續時間

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## 將持續時間轉換為時間跨度

### 第 1 步：載入專案文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：獲取任務和持續時間

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 步驟 3：將持續時間轉換為時間跨度

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## 將持續時間轉換為字串

### 第 1 步：載入專案文件

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### 第 2 步：獲取任務和持續時間

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### 第 3 步：將持續時間轉換為字串

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## 結論

在本教程中，我們介紹了 Aspose.Tasks for .NET 中持續時間處理的各個方面。了解並有效管理工期對於成功的專案管理至關重要。 Aspose.Tasks 提供了全面的功能來簡化 .NET 應用程式中的持續時間管理任務。

## 常見問題解答

### Q1：什麼是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一個功能強大的函式庫，用於在 .NET 應用程式中處理 Microsoft Project 檔案。

### Q2：Aspose.Tasks 可以處理複雜的專案結構嗎？

A2：是的，Aspose.Tasks 可以輕鬆處理複雜的專案結構，提供廣泛的 API 進行操作。

### Q3：Aspose.Tasks for .NET 與 .NET Core 相容嗎？

A3：是的，Aspose.Tasks for .NET 與 .NET Core 相容，讓您在跨平台應用程式中使用它。

### Q4：Aspose.Tasks 支援讀寫 Microsoft Project 檔案嗎？

A4：是的，Aspose.Tasks 支援讀取和寫入各種格式的 Microsoft Project 文件，包括 MPP、XML 和 MPX。

### Q5：Aspose.Tasks for .NET 有試用版嗎？

A5：是的，您可以從以下位置獲得 Aspose.Tasks for .NET 的免費試用版：[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
