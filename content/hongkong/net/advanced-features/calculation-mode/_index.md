---
title: Aspose.Tasks 中的計算模式
linktitle: Aspose.Tasks 中的計算模式
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中有效管理運算模式，以簡化專案排程和任務依賴性。
type: docs
weight: 29
url: /zh-hant/net/advanced-features/calculation-mode/
---
## 介紹

Aspose.Tasks for .NET 是一個功能強大的 API，允許開發人員在其 .NET 應用程式中以程式設計方式使用 Microsoft Project 檔案。使用專案文件的一個重要方面是管理計算模式，這決定了任務和專案進度表的計算和更新方式。在本教程中，我們將深入研究 Aspose.Tasks for .NET 支援的各種計算模式，並示範如何有效地使用它們。

## 先決條件

在開始之前，請確保您具備以下條件：

1. Visual Studio：確保您的系統上安裝了 Visual Studio。
2.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
3. 對 C# 程式設計的基本了解：熟悉 C# 程式設計概念。

## 導入命名空間

在開始使用 Aspose.Tasks for .NET 之前，讓我們先匯入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;


```

## 應用自動計算模式

### 第 1 步：建立一個新的專案實例

初始化一個新的`Project`對象並設定其`CalculationMode`財產給`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### 第 2 步：設定專案開始日期並新增任務

定義專案的開始日期並新增任務。

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 第 3 步：連結任務

建立任務之間的依賴關係。

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### 第 4 步：驗證重新計算的日期

檢查日期是否已自動重新計算。

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
//根據需要添加更多驗證
```

## 應用手動計算模式

### 第 1 步：建立一個新的專案實例

初始化一個新的`Project`對象並設定其`CalculationMode`財產給`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### 第 2 步：設定專案開始日期並新增任務

定義專案的開始日期並新增任務。

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 步驟 3：驗證任務屬性

檢查手動模式下任務屬性設定是否正確。

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
//根據需要添加更多驗證
```

### 第 4 步：連結任務並驗證日期

將任務連結在一起並檢查它們的日期是否未重新計算。

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## 應用無計算模式

### 第 1 步：建立一個新的專案實例

初始化一個新的`Project`對象並設定其`CalculationMode`財產給`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### 第 2 步：新增任務

新增任務至項目。

```csharp
var task = project.RootTask.Children.Add("Task");
```

### 步驟 3：驗證任務屬性

檢查任務屬性是否未自動計算。

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
//根據需要添加更多驗證
```

## 結論

在本教程中，我們探索了 Aspose.Tasks for .NET 中可用的計算模式，並學習如何在實際場景中應用它們。無論您需要自動、手動或無運算模式，Aspose.Tasks 都能提供滿足您專案需求的靈活性。

## 常見問題解答

### Q1：我可以在運行時動態改變運算模式嗎？

A1：是的，您可以在運行時的任何時刻透過修改`CalculationMode`財產。

### Q2：Aspose.Tasks 是否支援 Microsoft Project 以外的其他專案管理文件格式？

A2：Aspose.Tasks 主要專注於 Microsoft Project 檔案格式，但它也支援其他格式，如 Primavera P6 XML、Primavera DB 和 Asta Powerproject XML。

### Q3：Aspose.Tasks 適合小型和企業級專案嗎？

A3：當然！ Aspose.Tasks 旨在以其全面的功能和強大的 API 來滿足小型和企業級專案的需求。

### Q4：我可以將 Aspose.Tasks 與其他 .NET 函式庫和框架整合嗎？

A4：是的，您可以將 Aspose.Tasks 與其他 .NET 程式庫和框架無縫集成，以增強應用程式的功能。

### Q5：Aspose.Tasks 使用者有可用的社群論壇或支援管道嗎？

 A5: 是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持和討論。