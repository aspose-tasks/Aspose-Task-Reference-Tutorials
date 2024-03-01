---
title: 在 Aspose.Tasks 中使用可用期
linktitle: 在 Aspose.Tasks 中使用可用期
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效率地管理資源可用期。本教程提供了有關在 .NET 專案中使用可用期的逐步指南。
type: docs
weight: 17
url: /zh-hant/net/advanced-features/working-with-availability-periods/
---
## 介紹

在本教程中，我們將探討如何在 Aspose.Tasks for .NET 中使用可用期。可用期間對於在專案管理場景中有效管理資源至關重要。我們將逐步指導您完成整個過程。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：

1. Visual Studio：安裝 Visual Studio 或任何其他用於 .NET 開發的首選 IDE。
2.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
3. 對 C# 程式設計的基本了解：熟悉 C# 程式語言基礎知識將會有所幫助。

## 導入命名空間

在深入程式碼之前，請確保導入必要的名稱空間：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

讓我們將範例程式碼分解為多個步驟：

## 第 1 步：建立一個新的專案實例

```csharp
var project = new Project();
```

此行初始化 Project 類別的新實例，它代表 Aspose.Tasks 中的一個項目。

## 第 2 步：新增資源

```csharp
var resource = project.Resources.Add("Work Resource");
```

在這裡，我們為專案新增一個名為「Work Resource」的新資源。

## 第 3 步：定義可用期限

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

我們稱之為`GetPeriods()`檢索可用時段集合的方法。

## 步驟 4：向資源新增可用期

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

我們迭代上一步中獲得的可用期集合並將它們添加到資源中。

## 第 5 步：顯示可用期詳細信息

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

最後，我們循環遍歷與資源關聯的可用期並列印其詳細信息，包括開始日期、結束日期和可用單位。

## 結論

在本教程中，我們學習如何在 Aspose.Tasks for .NET 中使用可用期。透過遵循逐步指南，您可以有效地管理專案管理應用程式中的資源可用性。

## 常見問題解答

### Q1：我可以在商業專案中使用 Aspose.Tasks for .NET 嗎？

 A1：是的，Aspose.Tasks for .NET可以用於商業專案。您可以購買許可證[這裡](https://purchase.aspose.com/buy).

### 問題 2：Aspose.Tasks for .NET 有沒有免費試用版？

A2：是的，您可以獲得 Aspose.Tasks for .NET 的免費試用版[這裡](https://releases.aspose.com/).

### Q3：在哪裡可以找到 Aspose.Tasks for .NET 的文件？

A3：你可以找到文檔[這裡](https://reference.aspose.com/tasks/net/).

### Q4：如何獲得 Aspose.Tasks for .NET 支援？

A4：您可以從社群論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).

### Q5：你們有提供 Aspose.Tasks for .NET 的臨時授權嗎？

 A5：是的，可以使用臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).